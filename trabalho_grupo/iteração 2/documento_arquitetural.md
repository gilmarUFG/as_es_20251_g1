# Visão de Segurança - Ayu
### Segurança na Arquitetura de Microsserviços (Backend)

- Serviço de Autenticação:
Verificação JWT/OAuth2 em todas as requisições com Auth Gateway e uso de Rate Limiting para prevenir contra invasões de autenticação DDoS/brute force. Dessa maneira,garantimos que somente o médico acessa a sua conta no sistema e seu autenticador de documentos.

- Autenticador de documentos médicos:
Para garantir a segurança e anti-fraude de documentos médicoso sistema vai usar a  Assinatura Digital com Certificado ICP-Brasil, por meio da biblioteca LibreSign que é compatível com o ICP.

Esse tipo de assinatura tem validade jurídica na Lei 14.063/2020 para prescrições digitais,sendo muito seguro para este domínio da saúde.

Limitar permissões por tipo de usuário (médico/paciente).

- Repositório de documentos:
Seguir o princípio da LGPD Compliance e Armazenar documentos médicos e dados sensíveis, como exames e laudos, usando a criptografia em repouso com AES-256 dos buckets S3 da AWS. 

- Serviço de Consultas
Gravar vídeos de teleconsultas protegidos mesmo em cloud e construir banco dedicado de avaliações de pacientes para evitar vazamento cruzado.

