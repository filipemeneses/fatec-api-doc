# Network

Methods to connect and parse SIGA's pages

{% method name="scrap" %}
### `public static scrap ({ cookie, route, scrapper }: {cookie: string, route: string, scrapper: (object) => void}): any `

`cookie` can be retrieved at `Account.login`
`route` can be a full URL or subpath. Already defined 
URLs are available at `Network.ROUTES`.
`scrapper` is a function that will receive a Cheerio loaded instance (jQuery-like selector)

```js
Network.scrap({
  cookie: 'somecookie...',
  route: Network.ROUTES.HOME,
  scrapper: ($) => {
    return $('title').text()
  }
})
// <- Promise(cheerio.load(html))
```
{% endmethod %}

{% method name="post" %}
### `public static post ({ form, route }: { form: object, route: string}): Promise<any>`

`form` is a JSON with the data to send to specified route
`route` can be a full URL or subpath. Already defined 
URLs are available at `Network.ROUTES`.

```js
Network.post({
  route: Network.ROUTES.LOGIN,
  form: {somedata: '123'}
})
// <- Promise(html)
```
{% endmethod %}
{% method name="get" %}
### `public static get ({ cookie, route }: { cookie?: string, route: string}): Promise<any> `

`cookie` can be retrieved at `Account.login`
`route` can be a full URL or subpath. Already defined 
URLs are available at `Network.ROUTES`.


```js
Network.get({
route: Network.ROUTES.HOME,
form: {somedata: '123'}
})
// <- Promise(html)
```
{% endmethod %}



