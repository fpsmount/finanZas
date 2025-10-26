# 🌟 FinanZas: Gerenciador Financeiro Pessoal

Este repositório centraliza o desenvolvimento do projeto **FinanZas**, uma solução completa para gestão de finanças pessoais, composta por um frontend web moderno, um backend robusto em Java e um bot de WhatsApp para registro rápido de transações.

## 🔗 Estrutura do Projeto

O projeto é dividido em três módulos principais, cada um em seu próprio repositório, mantendo a modularidade e a organização. Para detalhes de instalação e desenvolvimento de cada módulo, consulte seus respectivos `README.md`.

| Módulo | Repositório | Descrição |
| :--- | :--- | :--- |
| **Frontend** | [finanZas-frontend](https://github.com/fpsmount/finanZas-frontend) | Interface web do usuário (Single Page Application). |
| **Backend (API)** | [finanZas-backend](https://github.com/fpsmount/finanZas-backend) | API RESTful para persistência e lógica de negócios. |
| **WhatsApp Bot** | [finanZas-bot-whatsapp](https://github.com/fpsmount/finanZas-bot-whatsapp) | Interface de chat para registro rápido de transações. |

## ✨ Recursos Principais da Plataforma

O FinanZas oferece uma experiência completa para o controle financeiro pessoal:

* **Dashboard Intuitivo:** Visão geral do saldo, entradas, saídas e gráficos de pizza para análise rápida.
* **Gerenciamento de Transações:** Adição, edição e remoção detalhada de **Entradas** (receitas) e **Saídas** (despesas), com categorização de despesas (fixa/variável) e receitas (salário/outros).
* **Metas Financeiras:** Seção dedicada para criar, acompanhar e gerenciar metas de economia com data limite e categoria, como "Viagem" ou "Reserva de Emergência".
* **Relatórios Detalhados:** Análise gráfica de entradas vs. saídas e distribuição de despesas (fixas vs. variáveis).
* **Autenticação Segura:** Login via e-mail/senha e Google, utilizando Firebase Auth.
* **Integração com WhatsApp:** Permite registrar transações e consultar o resumo financeiro diretamente pelo chat.

## 💻 Detalhes dos Componentes

### 1. FinanZas Frontend

O frontend é a interface de usuário construída como uma SPA (Single Page Application).
* **Tecnologias:** React, Chakra UI, React Router Dom, Recharts e JavaScript (ES6+).
* **Acesso:** Disponível em `http://localhost:3000` durante o desenvolvimento local.
* **Roteamento:** Utiliza `react-router-dom` com rotas protegidas (`ProtectedRoutes`) para garantir que apenas usuários autenticados acessem as funcionalidades principais.

### 2. FinanZas Backend (API)

O backend é responsável pela lógica de negócios e persistência de dados.
* **Tecnologias:** Java 17, Spring Boot 3.5.5, Spring Data JPA.
* **Banco de Dados:** Configurado para utilizar **PostgreSQL**.
* **Endpoints Principais:**
    * `/api/entradas`: CRUD e cálculo do total.
    * `/api/saidas`: CRUD e cálculo do total.
    * `/api/metas`: CRUD para Metas Financeiras.
* **Porta:** `8080` (padrão).

### 3. FinanZas WhatsApp Bot

O bot permite interagir com a API de forma simplificada via WhatsApp.
* **Tecnologias:** Node.js, `whatsapp-web.js`, e `axios` para se comunicar com o Backend.
* **Comandos de Transação:** O bot analisa a descrição para definir propriedades, como `salario` (`true` se contiver "salário" ou "fixo" para entradas) e `tipo` (fixa ou variável para saídas).
* **Comando de Conexão:** O usuário precisa enviar o UID (ID de Usuário) obtido nas Configurações do Frontend usando o comando `CONECTAR SEU_ID_AQUI` para autenticar o número do WhatsApp com a conta FinanZas.
