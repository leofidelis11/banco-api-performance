# Testes de Performance com k6

Repositório dedicado à execução de testes de performance utilizando a ferramenta [k6](https://k6.io/) em conjunto com scripts escritos em JavaScript. Os testes visam avaliar o desempenho da API do projeto [banco-api](https://github.com/juliodelimas/banco-api).

---

## 🔧 Tecnologias Utilizadas

- [k6](https://k6.io/) - Ferramenta para testes de performance
- JavaScript - Linguagem utilizada para os scripts de teste
- Variáveis de ambiente - Para configuração dinâmica dos testes

---

## 📁 Estrutura do Repositório

```bash
banco-api-performance/
├── config/
│   ├── config.local.json
├── fixtures/
│   ├── postLogin.json
├── helpers/
│   ├── autenticacao.js   
├── tests/
│   ├── login.test.js
│   ├── transferencias.test.js
├── utils/
│   └── variaveis.js
├── README.md
```

---

## 🎯 Objetivo de Cada Grupo de Arquivos

- **`config/`**: Arquivos de configuração de variáveis de ambiente.
- **`fixtures/`**: Dados de entrada para testes (ex: usuários, payloads).
- **`helpers/`**: Funções utilitárias reutilizáveis para interação com a API.
- **`tests/`**: Casos de teste organizados por módulo da API.
- **`utils/`**: Funções utilitárias reutilizáveis.
- **`README.md`**: Documentação do projeto.

---

## 🚀 Instalação

1. Certifique-se de ter o [k6 instalado](https://k6.io/docs/getting-started/installation/) na sua máquina.
2. Clone este repositório:
   ```bash
   git clone https://github.com/leofidelis11/banco-api-performance.git
   cd banco-api-performance
   ```

---

## ▶️ Execução dos Testes

Antes de executar os testes, defina a variável de ambiente `BASE_URL` com a URL da API que será testada no arquivo `config.local.json`:

```json
{
    "baseUrl": "http://localhost:3000"
}
```

### Executar um teste normalmente

```bash
k6 run tests/login.test.js
```

### Acompanhamento em tempo real com Dashboard Web

Você pode visualizar os resultados dos testes em tempo real utilizando o dashboard web do k6:

```bash
K6_WEB_DASHBOARD=true k6 run tests/login.test.js -e BASE_URL=http://localhost:3000 
```

### Exportar relatório HTML ao final do teste

Caso queira salvar o relatório gerado:

```bash
K6_WEB_DASHBOARD=true K6_WEB_DASHBOARD_EXPORT=relatorio.html k6 run scripts/stress.js -e BASE_URL=http://localhost:3000 
```

> 💡 O relatório será salvo como `html-report.html` no diretório raiz após a execução.
