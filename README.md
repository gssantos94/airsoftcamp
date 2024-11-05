# Sistema de Gestão para Campo de Airsoft

Este projeto é um sistema web de gestão para um campo de airsoft, desenvolvido com Django e React. Ele é focado no controle de agendamentos, vendas e estoque, permitindo que usuários reservem jogos, informem dados pessoais para rastreamento de consumo e realizem pagamentos parciais online. O sistema oferece funcionalidades específicas para donos e vendedores, incluindo gestão de estoque com alerta de reposição, histórico detalhado de movimentação vinculado ao CPF dos clientes, notificações automáticas e manuais, relatórios detalhados e integração com GitHub Actions para testes automatizados, garantindo a qualidade no ciclo de desenvolvimento.

## Objetivos

- Automatizar a gestão do campo de airsoft
- Permitir agendamentos online
- Gerenciar estoque com controle automático
- Fornecer extratos e relatórios detalhados
- Garantir segurança e controle de acesso
- Oferecer uma experiência responsiva e acessível

## Especificações

### 1. Módulo de Autenticação e Autorização
Sistema de autenticação com JWT para segurança, permitindo login e controle de permissões.

**Funcionalidades:**
- Login com e-mail e senha.
- Diferenciação de permissões para desenvolvedor, dono, vendedor e usuários.
- Acesso limitado para visitantes, permitindo visualizar eventos e agenda.

**Especificações Técnicas:**
- Autenticação JWT
- Controle de permissões por nível de usuário
- Validação e feedback de erro em login

### 2. Módulo de Controle de Estoque
Gestão de estoque para itens de loja e aluguel, com histórico detalhado e alertas automáticos.

**Funcionalidades:**
- Cadastro de produtos com nome, quantidade inicial e mínima.
- Registro de movimentação de entrada e saída, vinculando ao CPF para saídas.
- Alerta automático ao dono e vendedor para estoque baixo.

**Especificações Técnicas:**
- Campos: Nome, descrição, quantidade inicial e mínima
- Histórico de movimentação com data, quantidade, tipo e CPF
- Notificações automáticas de estoque baixo

### 3. Módulo de Agendamento de Jogos
Sistema de agendamento de partidas, com coleta de informações dos participantes e pagamento parcial.

**Funcionalidades:**
- Agendamento com seleção de horário, número de participantes e dados (CPF ou RG).
- Indicação de uso próprio ou aluguel de equipamentos.
- Pagamento de 25% do valor via sistema.

**Especificações Técnicas:**
- API REST para criação, modificação e consulta de agendamentos
- Integração com Mercado Pago, PicPay ou PagSeguro
- Notificações automáticas e manuais para lembretes e cancelamentos

### 4. Módulo de Gestão de Vendas e Extrato
Centralização das vendas e consumos dos usuários, com extrato final ao término do agendamento.

**Funcionalidades:**
- Registro de vendas, aluguel e consumação de itens.
- Consolidação de consumos e valores ao CPF do usuário.
- Geração de extrato final com opção de exportação para PDF.

**Especificações Técnicas:**
- Campos no extrato: valor do jogo, aluguéis, consumos
- Exportação para PDF
- Integração com o módulo de pagamentos para saldo pendente

### 5. Módulo de Relatórios
Relatórios detalhados para donos e vendedores, com opções de filtro e exportação.

**Funcionalidades:**
- Relatórios de estoque, agendamentos e vendas por período.
- Exportação dos relatórios para PDF ou Excel.

**Especificações Técnicas:**
- Relatórios de estoque por item, vendas por CPF e agendamentos com filtros.

### 6. Integração de Pagamento
Processamento de pagamento parcial para confirmar agendamentos.

**Funcionalidades:**
- Pagamento de 25% do agendamento via sistema.
- Registro do status de pagamento no sistema.

**Especificações Técnicas:**
- Integração com Mercado Pago, PicPay ou PagSeguro
- Callback para atualização do status do agendamento

### 7. GitHub Actions e Testes Automatizados
Integração contínua com GitHub Actions, automatizando testes em cada etapa do desenvolvimento.

**Funcionalidades:**
- Testes obrigatórios para branches de release e produção.
- Testes opcionais para branches de desenvolvimento e feature.
- Relatórios de cobertura de código.

**Especificações Técnicas:**
- Configuração de workflows para testes de backend (Django TestCase) e frontend (Jest).

## Marcos do Projeto

### Milestone 1: Configuração do Ambiente e Estrutura Inicial
- Configuração do ambiente com Django e PostgreSQL.
- Setup inicial do React e API.
- Configuração do GitHub Actions para CI/CD.

### Milestone 2: Autenticação e Controle de Acesso
- Implementação de autenticação JWT e permissões.
- Interface de login no React.
- Testes de autenticação e permissões.

### Milestone 3: Módulo de Controle de Estoque
- Cadastro e edição de produtos com quantidade inicial e mínima.
- Registro de movimentação com notificações de estoque baixo.

### Milestone 4: Módulo de Agendamento de Jogos
- Agendamento com pagamento parcial e notificações.
- Tela de agendamento no React.

### Milestone 5: Gestão de Vendas e Geração de Extrato
- Registro de vendas e geração de extrato final.
- Exportação para PDF.

### Milestone 6: Relatórios e Extração de Dados
- Relatórios detalhados com filtros e exportação para PDF/Excel.

### Milestone 7: Integração Completa de Pagamentos e Finalização para Produção
- Integração com provedores de pagamento.
- Revisão completa do sistema e preparação para monitoramento pós-lançamento.

## Tecnologias Utilizadas
- **Backend**: Django, Django REST Framework, PostgreSQL
- **Frontend**: React
- **CI/CD**: GitHub Actions
- **Pagamento**: Mercado Pago, PicPay, PagSeguro (a definir)

## Licença
Este projeto está licenciado sob a Licença MIT. Consulte o arquivo `LICENSE` para obter mais detalhes.