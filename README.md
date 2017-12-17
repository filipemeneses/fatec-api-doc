<div style="width: 400px">
  <h1>
    <img src="/assets/logo.png" alt="Fatec API"/>
  </h1>
</div>

**fatec-api** is an API for Centro Paula Souza's SIGA made for students to create things based in their profile data. 🙂

Created with Typescript and available as a javascript package at [**npm**](https://www.npmjs.com/package/fatec-api).

The source code is available at [Github](https://github.com/filipemeneses/fatec-api).

For suggestions/help use [Github Issues](https://github.com/filipemeneses/fatec-api/issues) or join our [Discord channel](https://discord.gg/RUv5Kxw).

---

## Getting Started

A quick example will show how to use it, scrapping the user name. And will cover the usage with [Node.js](https://nodejs.org/en/) using ES6 syntax.

```js
const fatecApi = require('fatec-api')
const myAccount = new fatecApi.Account('LOGIN', 'PASSWORD')

myAccount.login().then(() => {
  return myAccount.getName().then(name => {
    console.log(name)
    // <- 'YOUR FULL NAME WITH CAPSLOCK'
  })
})
```

The scrapped data is available at `Account.student`, **continuing the example**: 

```js
myAccount.student.getName()
// <- 'YOUR FULL NAME WITH CAPSLOCK'
```

## How it works (Account.getName)

This library scrap data using HTTP requests with `request` and parses the HTML with `cheerio` library.

The [Account](/methods.md) class does the heavy lifting. Here's the flow of Account.getName():


![](/assets/requests.svg)

The scrapped data is later available at [Account.student](/methods/student.md) on an account instance.


### Modules

* [Network](/methods/network.md)
* [Account](/methods.md)
  * [**Student**](/methods/student.md)
  * [Discipline](/methods/discipline.md)
  * [Evaluation](/methods/evaluation.md)
  



