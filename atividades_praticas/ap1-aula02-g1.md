# Atividade Prática 1 - Aula 2 - 17/03/2025

# Arquitetura de Software

Problema: Problemas de gerenciamento de pedidos e reservas em um restaurante


## Requisitos Funcionais:

- RF1: O usuário deve poder escolher a aparência da interface, tendo as opções de selecionar entre modo claro, escuro e de alto contraste.

- RF2: O sistema deve enviar notificações automáticas para o cliente via SMS ou e-mail sempre que o status do pedido ou reserva for alterado (ex: "Pedido em "Preparação", "Pedido Enviado", "Reserva Confirmada").

- RF3: O usuário deve buscar, através de um campo de busca, o nome do produto desejado.

- RF4: O sistema deve permitir que o cliente adicione observações ou preferências (por exemplo, "sem cebola", "pedido sem sal") aos itens do cardápio ao realizar o pedido.

- RF5: O sistema deve gerar uma comanda digital para cada mesa ou cliente, associando os itens pedidos a essa comanda.



## Requisitos de Qualidade:

- RQ1: O tempo de resposta para a busca de produtos não deve ultrapassar 1 segundo, garantindo uma experiência ágil e eficiente para o usuário.

- RQ2:  O sistema deve garantir a entrega de 99% das notificações em até 5 segundos após a mudança de status do pedido.

- RQ3:  A interface do software deve ser acessível a pessoas de baixa visão.

- RQ4: O sistema deve ser projetado para ser intuitivo, com uma interface de usuário amigável e fácil de navegar, visando uma experiência sem fricções para o usuário.

- RQ5: O sistema deve garantir que as comandas digitais sejam armazenadas de forma segura e resiliente, garantindo que nenhum pedido seja perdido em caso de falha no sistema ou queda de conexão.

## Requisitos funcionais x Requisitos Não Funcionais

|Requisito Funcional|Requisito Não Funcional|
|---|---|
|RF1|RQ3|
|RF2|RQ2|
|RF3|RQ1|
|RF5|RQ5|
|RF4|RQ4|
