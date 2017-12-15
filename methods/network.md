# Network

Methods to connect and parse SIGA's pages

{% method name="scrap" %}
#### `public static scrap ({ cookie, route, scrapper }: {cookie: string, route: string, scrapper: (object) => void}): any `

`Cookie` can be retreived at `Account.login`
`route` can be a full URL or subpath. Already defined 
URLs are available at `Network.ROUTES`.
`scrapper` is a function that will receive a Cheerio loaded instance (jQuery-like selector)

```js
Network.scrap({
      cookie: this.cookie,
      route: Network.ROUTES.HOME,
      scrapper: ($$) => {

```

{% endmethod %}

{% method name="getName" %}
#### `.getName(): Promise<string>`

Will return the account's user name
{% endmethod %}

{% method name="getRegisteredEmails" %}
#### `.getRegisteredEmails(): Promise<IRegisteredEmail[]>`

Will return a list of registered emails and it's respective integrations:

```js
[{
  email: string,
  integrations: [ 'fatec', 'etec', 'preferential', 'websai']
}]
```
{% endmethod %}
