<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
</head>
<body>
  <h1>Teste de Fluxo de Cadastro e Onboarding de Usuário</h1>

  <p>Este é um teste automatizado desenvolvido com Cypress para verificar o fluxo de cadastro, login e onboarding de um usuário na aplicação web. O teste simula a interação do usuário com a interface, incluindo o registro de novos usuários, login, e preenchimento de informações bancárias.</p>

  <h2>Descrição</h2>
  <p>Este conjunto de testes realiza as seguintes ações na aplicação:</p>
  <ul>
    <li><strong>Cadastro de um novo usuário</strong>:
      <ul>
        <li>O usuário preenche os campos de nome, sobrenome, nome de usuário, senha e confirmação de senha.</li>
        <li>O formulário é enviado e o usuário é criado.</li>
      </ul>
    </li>
    <li><strong>Login</strong>:
      <ul>
        <li>O usuário realiza o login com as credenciais recém-criadas.</li>
      </ul>
    </li>
    <li><strong>Onboarding do usuário</strong>:
      <ul>
        <li>Após o login, o usuário passa pelo processo de onboarding.</li>
        <li>O usuário fornece informações bancárias, como nome do banco e número da conta bancária.</li>
      </ul>
    </li>
    <li><strong>Navegação pelo aplicativo</strong>:
      <ul>
        <li>O teste verifica a navegação para diferentes seções do app, como "Contatos", "Pessoal", e "Público".</li>
      </ul>
    </li>
  </ul>

  <h2>Pré-requisitos</h2>
  <p>Antes de rodar o teste, você precisa ter os seguintes itens configurados:</p>
  <ul>
    <li><strong>Node.js</strong>: A versão recomendada é a 14.x ou superior.</li>
    <li><strong>Cypress</strong>: Para rodar os testes automatizados.</li>
  </ul>

  <h3>Instalação</h3>
  <ol>
    <li>Clone este repositório para sua máquina local:</li>
    <pre><code>git clone &lt;URL-DO-REPOSITORIO&gt;
cd &lt;DIRETORIO-DO-REPOSITORIO&gt;</code></pre>
    <li>Instale as dependências do projeto:</li>
    <pre><code>npm install</code></pre>
    <li>Instale o Cypress:</li>
    <pre><code>npx cypress install</code></pre>
  </ol>

  <h3>Rodando os Testes</h3>
  <p>Após a instalação, você pode rodar os testes utilizando o seguinte comando:</p>
  <pre><code>npx cypress open</code></pre>
  <p>Isso abrirá a interface gráfica do Cypress onde você poderá escolher o teste para executar.</p>

  <h3>Estrutura do Teste</h3>
  <p>O código do teste está estruturado da seguinte forma:</p>
  <pre><code>
describe('template spec', () => {
  it('passes', () => {
    cy.visit('localhost:3000') // Visita a página inicial
    cy.get('[data-test="signup"]').click() // Clica no botão de cadastro
    cy.get('#firstName').type('Igor') // Preenche o nome
    cy.get('#lastName').type('Souza') // Preenche o sobrenome
    cy.get('#username').type('igorsouza') // Preenche o nome de usuário
    cy.get('#password').type('123456') // Preenche a senha
    cy.get('#confirmPassword').type('123456') // Confirma a senha
    cy.get('[data-test="signup-submit"]').click() // Envia o formulário de cadastro
    cy.get('#username').type('igorsouza') // Preenche novamente o nome de usuário no login
    cy.get('#password').type('123456') // Preenche a senha
    cy.get('[data-test="signin-submit"]').click() // Envia o formulário de login
    cy.get('[data-test="user-onboarding-dialog-title"]') // Verifica o título do onboarding
    cy.get('[data-test="user-onboarding-next"]').click() // Avança para a próxima etapa
    cy.get('#bankaccount-bankName-input').type('Banco Teste') // Preenche o nome do banco
    cy.get('#bankaccount-routingNumber-input').type('123456789') // Preenche o número da rota bancária
    cy.get('#bankaccount-accountNumber-input').type('123456789') // Preenche o número da conta bancária
    cy.get('[data-test="bankaccount-submit"]').click() // Envia o formulário bancário
    cy.get('[data-test="user-onboarding-dialog-title"]') // Verifica novamente o título do onboarding
    cy.get('[data-test="user-onboarding-next"]').click() // Avança para a próxima etapa do onboarding
    cy.get('[data-test="nav-public-tab"]') // Navega para a aba pública
    cy.get('[data-test="nav-contacts-tab"]') // Navega para a aba de contatos
    cy.get('[data-test="nav-personal-tab"]') // Navega para a aba pessoal
  })
})
  </code></pre>

  <h2>Observações</h2>
  <ul>
    <li>O teste foi desenvolvido para rodar localmente na URL <code>localhost:3000</code>. Caso sua aplicação utilize um endereço diferente, altere a URL no código.</li>
    <li>Certifique-se de que o servidor da aplicação esteja rodando antes de executar os testes.</li>
    <li>O teste simula uma interação de ponta a ponta, incluindo a navegação entre as páginas, preenchimento de formulários e verificação da interface.</li>
  </ul>


</body>
</html>
