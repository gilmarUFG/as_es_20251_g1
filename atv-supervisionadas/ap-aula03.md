# Requisitos Funcionais e Atributos de Qualidade

---

### **RF1**: O usuário deve poder escolher a aparência da interface, tendo as opções de selecionar entre modo claro, escuro e de alto contraste.  
**Atributos de Qualidade**:  
- **Usabilidade**: Disponibilizar diferentes contrastes e modos melhora a experiência do usuário e garante acessibilidade (ex.: adequação para pessoas com dificuldades visuais).  
- **Modificabilidade**: Flexibilidade para adicionar novos temas no futuro.  
- **Eficiência energética**: Modo escuro reduz consumo de energia em telas OLED.  

---

### **RF2**: O sistema deve enviar notificações automáticas para o cliente via SMS ou e-mail sempre que o status do pedido ou reserva for alterado.  
**Atributos de Qualidade**:  
- **Desempenho**: O envio não deve impactar o tempo de resposta do sistema.  
- **Integrabilidade**: Conexão com serviços externos de SMS/e-mail (ex.: Twilio, SendGrid).  
- **Segurança**: Garantir confidencialidade e integridade das mensagens (ex.: evitar vazamento de dados sensíveis).  

---

### **RF3**: O usuário deve buscar, através de um campo de busca, o nome do produto desejado.  
**Atributos de Qualidade**:  
- **Desempenho**:  
  - 95% das requisições devem retornar em ≤ 5 segundos sob 1.000 usuários simultâneos.  
- **Usabilidade**:  
  - Busca concluída em ≤ 3 cliques.  
- **Disponibilidade**:  
  - Uptime de 99,9% ao mês (≤ 43 minutos de indisponibilidade).  
  - Monitoramento com Prometheus.  

---

### **RF4**: O sistema deve permitir que o cliente adicione observações ou preferências aos itens do cardápio.  
**Atributos de Qualidade**:  
- **Disponibilidade**: Funcionamento contínuo durante pedidos.  
- **Modificabilidade**: Adaptação a mudanças no cardápio.  
- **Usabilidade**: Facilidade de uso e suporte ao usuário.  

---

### **RF5**: O sistema deve gerar uma comanda digital para cada mesa ou cliente.  
**Atributos de Qualidade**:  
- **Disponibilidade**:  
  - Operacional mesmo sob alto volume de pedidos ou falhas pontuais de rede.  
- **Desempenho**:  
  - CRUD de comandas em ≤ 2 segundos, independente do volume.  
- **Proteção**:  
  - Dados protegidos contra acessos não autorizados e ataques (ex.: criptografia, RBAC).  

---

**Legenda**:  
- **CRUD**: Create, Read, Update, Delete.  
- **RBAC**: Role-Based Access Control.  
- **SLA**: Service Level Agreement.  
