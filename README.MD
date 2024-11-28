
 # Server REST - Testes Automatizados com Postman e Newman

Este repositório contém um projeto de testes automatizados para um servidor REST, desenvolvido utilizando o [Postman](https://www.postman.com/) e o [Newman](https://github.com/postmanlabs/newman).

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
   newman run SERVER_REST_CASOS_DE_TESTES.postman_collection.json \
     -e SERVER_REST_ENV.postman_environment.json \
     -r cli,html --reporter-html-export results/report.html