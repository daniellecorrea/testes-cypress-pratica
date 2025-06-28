# Portfólio de Testes Automatizados com Cypress + BDD

Este repositório faz parte do meu portfólio como Analista de Qualidade, e contém **exercícios práticos de testes automatizados** utilizando o framework [Cypress](https://www.cypress.io/) com abordagem BDD (Behavior Driven Development) via Gherkin.

---

## 👩🏻‍💻 Sobre mim

Sou **Danielle Corrêa**, profissional apaixonada por qualidade de software, com experiência em testes manuais e em constante aprendizados para aprimorar meus conhecimentos em automação de testes. Este repositório documenta minha prática contínua e evolução técnica em automação de testes.

🔗 [LinkedIn](https://www.linkedin.com/in/daniellecorrea)  
💻 [GitHub](https://github.com/daniellecorrea)

---

## Tecnologias Utilizadas

- Cypress 14.x
- Cypress-Cucumber-Preprocessor
- Cypress-XPath
- JavaScript
- Gherkin
- VS Code

---

## Estrutura do Projeto

```
testes-cypress-pratica/
├── cypress/
│   ├── e2e/
│   │   └── tests/
│   │       ├── autenticar-usuario.feature
│   │       └── autenticar-usuario.cy.js
├── package.json
└── README.md
```

---

## Cenário Atual Testado

### Feature: `autenticar-usuario.feature`

```gherkin
Feature: Autenticar usuário
  Como um usuário que possui conta no sistema
  Eu quero realizar autenticação
  Para que eu possa acessar minha conta

  Scenario: Login de usuário com sucesso
    Given Eu acesso a página de login
    When Eu preencho os dados e solicito acesso
    Then Sistema faz a autenticação com sucesso
```

### Step Definitions: `autenticar-usuario.cy.js`

```javascript
import { Given, When, Then } from 'cypress-cucumber-preprocessor/steps';
import 'cypress-xpath';

Given("Eu acesso a página de login", () => {
    cy.visit('https://the-internet.herokuapp.com/login');
});

When("Eu preencho os dados e solicito acesso", () => {
    cy.xpath('//*[@id="username"]').type('tomsmith');
    cy.xpath('//*[@id="password"]').type('SuperSecretPassword!');
    cy.xpath('//*[@id="login"]/button').click();
});

Then("Sistema faz a autenticação com sucesso", () => {
    cy.url().should('include', '/secure');
    cy.screenshot({ overwrite: true });
});
```

---

## Como Executar os Testes

```bash
git clone git@github.com:daniellecorrea/testes-cypress-pratica.git
cd testes-cypress-pratica
npm install
npx cypress open
```

---

## Meus Aprendizados

- Estrutura de testes BDD com Gherkin
- Separação de lógica e comportamento
- Validação com Cypress XPath
- Utilização de assertions de URL e screenshots
- Organização de testes automatizados para portfólio

---

## Próximos Passos

- [ ] Criar cenários com dados inválidos
- [ ] Usar Page Objects
- [ ] Testes em múltiplos navegadores
- [ ] Integração com GitHub Actions (CI)

---

✨ *"Testes bem escritos são como documentação viva — falam o que o sistema deve fazer e garantem que ele continue fazendo."*

