## 3. Diagrama de Casos de Uso

O diagrama de casos de uso abaixo foi elaborado com PlantUML, com base nos requisitos RF01–RF05.  
Você pode editar este bloco diretamente ou abrir o arquivo externo `casos-de-uso.puml` (via VSCode ou visualizador online).

```plantuml
@startuml UseCaseDiagram
title Casos de Uso – Sistema Telemedicina VR
left to right direction

actor Paciente
actor Médico

rectangle "Sistema Telemedicina VR" {
  (RF01: Cadastro de usuários)                as UC1
  (RF02: Agendar consulta VR)                 as UC2
  (RF02b: Participar de consulta VR)          as UC2b
  (RF03: Envio de exames e documentos médicos) as UC3
  (RF04: Interação em ambiente virtual 3D)    as UC4
  (RF05: Chat e anotações médicas)             as UC5
}

Paciente --> UC1
Médico   --> UC1

Paciente --> UC2
UC2b --> UC2 : <<include>>
Paciente --> UC2b
Médico   --> UC2b

Paciente --> UC3

UC4 -down-> UC2b : <<extend>>
UC5 -down-> UC2b : <<extend>>

Paciente --> UC4
Médico   --> UC4

Paciente --> UC5
Médico   --> UC5
@enduml
