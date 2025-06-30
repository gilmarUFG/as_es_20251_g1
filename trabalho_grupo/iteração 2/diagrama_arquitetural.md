@startuml
skinparam monochrome true
skinparam defaultFontName Courier
skinparam roundCorner 20

rectangle "Frontend (Unity + OpenXR)" as frontend {
  component "Aplicação RA\n(3D/Teleconsulta)" as ra
  component "Interface Web/Mobile" as ui
}

rectangle "API Gateway" as gateway {
  component "Auth Gateway" as auth_gateway
  component "Rate Limiting" as rate_limit
}

rectangle "Microsserviços" as backend {
  rectangle "Serviço de Autenticação" as auth {
    component "JWT/OAuth2" as jwt
    database "Banco de Usuários\n(PostgreSQL)" as user_db
  }

  rectangle "Autenticador de Documentos" as doc_auth {
    component "LibreSign\n(ICP-Brasil)" as libresign
    database "Certificados Digitais" as cert_db
  }

  rectangle "Repositório de Documentos" as storage {
    component "Criptografia AES-256" as aes
    database "S3 Buckets" as s3
  }

  rectangle "Serviço de Consultas" as consultas {
    component "Gravação de Vídeos" as video
    database "Banco de Consultas e avaliações\n(PostgreSQL)" as consultas_db
    database "Auditoria Gravações\n(MongoDB)" as mongo_audit
  }


}

frontend --> gateway : HTTPS (REST/gRPC/WebSocket)
gateway --> backend : Request/Response

auth_gateway --> auth : Validação JWT
auth --> user_db : CRUD

doc_auth --> libresign : Assinatura Digital
libresign --> cert_db : Valida Certificado
doc_auth --> storage : Armazena docs

storage --> aes : Cripto/Decripto
aes --> s3 : Dados sensíveis

consultas --> video : Grava teleconsultas
video --> mongo_audit : Metadados gravações
consultas --> consultas_db : Dados consultas e avaliações

all --> auditoria : Logs de Acesso
auditoria --> audit_db : Armazena trilhas
@enduml