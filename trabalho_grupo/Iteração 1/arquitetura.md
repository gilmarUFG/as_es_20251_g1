# Visão geral da arquitetura do sistema

**Sistema de Consultas Médicas com Realidade Virtual Aumentada**

## Estilo arquitetural adotado:

O estilo arquitetural adotado para o back-end será **Microsserviços**, abordagem que permite a entrega rápida e aplicativos grandes e complexos, uma vez que divide o sistema em vários serviços, os quais podem ser implementados de forma independente e que secomunicam por meio de APIs.

Justificativas técnicas para a utilização de Microsserviços:
- **Escalabilidade independente:** diferentes funcionalidades do sistema terão cargas variáveis. Por exemplo, o serviço de consultas em tempo real, usado pela RA, demanda alta performance gráfica e baixa latência, enquanto o serviço de agendamento de consultas e exames tem picos em horários específicos. Nesse sentido, cada microsserviço pode ser escalado de acordo com sua demanda específica e pode-se evitar desperdício de recursos computacionais;
- **Disponibilidade e Tolerância a falhas:** como os serviços são independentes, caso ocorra a falha em um serviço, os outros não serão afetados. Essa característica é fundamental para a disponibilidade do sistema, uma vez que, caso haja uma falha, não ocorrerá de o sistema inteiro ser derrubado; 
- **Flexibilidade tecnológica:** como utilizaremos RA na aplicação, porém necessitamos de um back-end eficiente e confiável, a utilização de microsserviços nos permite adaptar a stack conforme nossas necessidades, já que cada serviço pode ser desenvolvido na linguagem ou tecnologia mais adequada;
- **Performance otimizada para RA:** a Realidade Aumentada exige baixa latência e sincronização precisa entre múltiplos usuários. Microsserviços são naturalmente distribuídos e suportam comunicação síncrona e assíncrona. Assim, podemos garantir performance e escalabilidade para o sistema;
- **Manutenção e evolução contínuas:** Serviços podem ser desenvolvidos e testados de maneira independente, o que reduz o risco de alterações em um módulo afetarem todo o sistema. Dessa forma, a correção ou introdução de funcionalidades torna-se mais eficiente;
- **Segurança granular:** como o sistema trabalha com dados sensíveis, é necessário auditoria granular (por exemplo, caso um usuário acesse um prontuário), e criptografia em trânsito e em repouso. A arquitetura escolhida permite controles de seguranças específicos por serviço, o que é importante para a LGPD e para regulamentações de saúde. 

Quanto ao front-end com RA, as tecnologias escolhidas foram Unity com OpenXR, considerando questões como curva de aprendizado, custo e robustez da aplicação. O Unity é plataforma líder em desenvolvimento 3D e RA, e com suporte a múltiplos dispositivos e alta performance gráfica, enquanto OpenXR é um padrão aberto e livre de royalties desenvolvido pela Khronos que visa simplificar o desenvolvimento de RA/RV.

Justificativas técnicas para a utilização de Unity + OpenXR:
- Alta performance gráfica, essencial para modelos anatômicos, exames 3D, ou simulações médicas.
- Suporte a múltiplas plataformas.
- Permite interfaces naturais: interação via gestos, voz, dispositivos de controle ou touch 3D.
- Compatível com dispositivos como webcams, câmeras 3D ou sensores específicos.
- Integração Fácil com Backend via REST, WebSocket e gRPC conexão com microsserviços.

## Resumo da stack tecnológica:

- Unity 3D (C#):	Motor gráfico para interface 3D/RA desktop com alta performance.
- OpenXR:	Padrão aberto para integração de dispositivos RA/XR.
- WebSocket / REST / gRPC:	Comunicação com o backend em tempo real ou via APIs.
- Microsserviços:	Java (Spring Boot).
- Banco de dados relacional: PostgreSQL.
