# Server REST - Testes Automatizados com Postman e Newman

Este repositório contém um projeto de testes automatizados para um servidor REST, desenvolvido utilizando o [Postman](https://www.postman.com/) e o [Newman](https://www.npmjs.com/package/newman).

## Objetivo do Projeto

Este projeto foi desenvolvido com o objetivo de realizar testes automatizados para uma API REST que simula um **e-commerce**, garantindo que ela funcione corretamente em diversos cenários. O foco é validar os endpoints, verificar a integridade dos dados e garantir o comportamento esperado. Os principais objetivos incluem:

- **Validar Endpoints da API:** Garantir que todos os endpoints da API estejam funcionando conforme o esperado, sem erros de integração.
- **Simular Diferentes Cenários de Teste:** Utilizar variáveis de ambiente para testar diferentes condições e configurações de ambiente, garantindo que a API seja robusta e flexível.
- **Gerar Relatórios Detalhados:** O Newman gera relatórios HTML para análise aprofundada dos resultados, permitindo uma verificação rápida e precisa dos testes realizados.

## Estrutura do Projeto

- **Casos de Teste:** Arquivo contendo a coleção de casos de teste do Postman.
  - `SERVER_REST_CASOS_DE_TESTES.postman_collection.json`

- **Ambiente:** Configurações de ambiente para execução dos testes no Postman.
  - `SERVER_REST_ENV.postman_environment.json`

- **Resultados:** Pasta com relatórios gerados pelo Newman, incluindo relatórios HTML para análise detalhada dos testes executados.
  - `results/`

## Como Executar os Testes

1. **Pré-requisitos:**
   - [Node.js](https://nodejs.org/) instalado no sistema.
   - Instale o Newman globalmente:
     ```bash
     npm install -g newman
     ```

2. **Executar os Testes:**
   Utilize o Newman para executar a coleção de testes:
   ```bash
   newman run SERVER_REST_CASOS_DE_TESTES.postman_collection.json -e SERVER_REST_ENV.postman_environment.json -r cli,html --reporter-html-export results/report.html
   ```
## Collections

### USUÁRIO
- CT 1 - SUCESSO - CRUD (ADMIN TRUE)
- CT 2 - SUCESSO - CRUD (ADMIN FALSE)
- CT 3 - FALHA - CRIAR USUARIO - USUARIOS IGUAIS
- CT 4 - FALHA - CRIAR USUARIO - JSON INCOMPLETO
- CT 5 - FALHA - ATUALIZAR USUARIO - EMAIL JA USADO

### LOGIN
- CT 1 - SUCESSO - REALIZAR LOGIN - ADMIN TRUE
- CT 2 - SUCESSO - REALIZAR LOGIN - ADMIN FALSE
- CT 3 - FALHA - REALIZAR LOGIN  - CREDENCIAIS INVALIDAS
- CT 4 - FALHA - REALIZAR LOGIN  - JSON INCOMPLETO

### PRODUTO
- CT 1 - SUCESSO - CRIA PRODUTO
- CT 2 - FALHA - CRIAR PRODUTO - PRODUTO REPETIDO
- CT 3 - FALHA - CRIAR PRODUTO - JSON INCOMPLETO
- CT 4 - FALHA - ATUALIZAR PRODUTO - NOME REPETIDO
- CT 5 - FALHA - CRIAR/ATUALIZAR PRODUTO - ADMIN FALSE
- CT 6 - FALHA - CRIAR/ATUALIZAR PRODUTO - SEM TOKEN

### CARRINHO
- CT 1 - SUCESSO - CONCLUIR COMPRA
- CT 2 - SUCESS0 - CANCELAR COMPRA
- CT 3 - FALHA - CONCLUIR COMPRA - USUARIO SEM CARRINHO
- CT 4 - FALHA - CANCELAR COMPRA - USUARIO SEM CARRINHO
- CT 5 - FALHA - AUSENCIA DE TOKEN
- CT 6 - FALHA - DELETAR USUÁRIO/PRODUTO EM CARRINHO
