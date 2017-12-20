<div style="width: 400px; margin-left: -34px;">
  <h1>
    <img src="/assets/logo.png" alt="Fatec API"/>
  </h1>
</div>

**fatec-api** é uma API para o SIGA do Centro Paula Souza feito para os alunos criar coisas baseadas em seus perfis. Criado com Typescript e disponível como um pacote javascript em [**npm**](https://www.npmjs.com/package/fatec-api). O código fonte está disponível em [Github](https://github.com/filipemeneses/fatec-api). Para sugestões/ajuda use o [Github Issues](https://github.com/filipemeneses/fatec-api/issues) ou entre no nosso [canal do Discord](https://discord.gg/RUv5Kxw).


---
{% method name="install" %}

## Instalando

Se você estiver em um projeto NPM, use:

{% sample lang="js" %}
```bash
npm install --save fatec-api
```

{% endmethod %}

{% method name="getting-started" %}

## Começando

Um exemplo rápido vai facilitar demonstrar como usar: raspando o nome do usuário.

> Usando [Node.js](https://nodejs.org/en/) com sintaxe ES6.


{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const minhaConta = new fatecApi.Account('LOGIN', 'PASSWORD')

minhaConta.getName().then(nome => {
  console.log(nome)
  // <- 'SEU NOME COM CAPSLOCK'
})
```

The scrapped data is available at `Account.student`, **continuing the example**:

{% sample lang="js" %}
```js
myAccount.student.getName()
// <- 'YOUR FULL NAME WITH CAPSLOCK'
```
{% endmethod %}

## How it works `account.getName()`

This library scrap data using HTTP requests with `request` and parses the HTML with `cheerio` library.

The [Account](/methods.md) class does the heavy lifting. Here's the flow of Account.getName():


![](/assets/requests.svg)

The scrapped data is later available at [Account.student](/methods/student.md) on an account instance.


{% method name="api" %}



{% endmethod %}
