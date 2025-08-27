
# Banco API Teste de Performance 

Repositorio com testes de performance automatizados desenvolvidos com a ferramenta[Grafana K6] (https://k6.io/) e escritos em JavaScript, voltados para API do sistema bancario.

📌 Repositório: [Banco API Performance](https://github.com/Doug1Gogax/banco-api-performance)  

---

## 🚀 Introdução  

Este projeto tem como objetivo simular diferentes cargas e cenarios de uso para a API do banco, avaliando seu desempenho e identificando possivéis gargalos. 
Os testes são escritos em modularidade, organização por contexto e reutilização de modelos de dados 

---

## 🛠 Tecnologias utilizadas  

- [Node.js](https://nodejs.org/) (ambiente de execução JavaScript)  
- [k6](https://k6.io/) (ferramenta para testes de performance)  
- [npm](https://www.npmjs.com/) (gerenciador de pacotes)
- Variavei de ambiente para configuração dinamica (ex:'BASE_URL')
- JavaScript (ES6)
- [GJSON] (http://github.com/tidawll/gjosn) - Para extração de dados em respostas JSON

---

## 📂 Estrutura do repositório  

A estrutura básica do repositório é a seguinte:  

```
banco-api-performance/
│── config/        # Arquivo de Configuração locais do projeto
│── fixtures/      # Dados de entrada para os testes (ex:usuarios, payloads)
│── tests/         # Scripts de teste do k6
│── utils/         # Funções utilitárias reutilizáveis
│── package.json   # Dependências do projeto
│── README.md      # Documentação do repositório
│── helpers/       # Funções utilitárias reutilizaveis para interação com a API

---

## 🎯 Objetivo de cada grupo de arquivos  

- **config/** → Arquivo de Configuração locais do projeto  
- **fixtures/** → Dados de entrada para os testes (ex:usuarios, payloads).  
- **tests/** → Scripts de teste do k6.  
- **utils/** → Funções auxiliares para reaproveitamento de lógica nos testes.  
- **helpers/** → Funções utilitárias reutilizaveis para interação com a API
---

## ⚙️ Modo de instalação  

1. Clone este repositório:  
   ```bash
   git clone https://github.com/Doug1Gogax/banco-api-performance.git
   cd banco-api-performance
   ```

2. Instale as dependências:  
   ```bash
   npm install
   ```

3. Verifique se o **k6** está instalado:  
   ```bash
   k6 version
   ```
   Caso não tenha, siga a [documentação oficial](https://k6.io/docs/get-started/installation/) para instalar.  

---

## ▶️ Modo de execução  

Antes de rodar os testes, é necessário definir a variável de ambiente **BASE_K6**, que representa a URL base da API que será testada.  

### Execução simples  
```bash
 k6 run tests/login.test.js
```
    Certifique-se de passar a variavel de ambiente 'BASE_URL', caso não esteja usando um 'config.local.json' 
    ou uma abordagem de carregamento automarico:

### Execução com acompanhamento em tempo real (dashboard web)  
```bash
k6 run tests/transferencias.test.js -e BASE_URL=http://localhost:3000
```

### Execução com exportação do relatório em HTML  
```bash
 K6_WEB_DASHBOARD=true K6_WEB_DASHBOARD_EXPORT=html-report.html k6 run tests/login.test.js -e BASE_URL=http://localhost:3000
```

Após a execução, o relatório será salvo no arquivo **html-report.html**, podendo ser aberto no navegador.  
