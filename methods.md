# Account (user: string, password: string)

{% method name="login" %}
### `public login(): Promise`

This will request SIGA for access and set the account as logged in.
{% endmethod %}

{% method name="getName" %}
### `public getName(): Promise<string>`

Will return the account's user name
{% endmethod %}

{% method name="getRegisteredEmails" %}
### `public getRegisteredEmails(): Promise<IRegisteredEmail[]>`

Will return a list of registered emails and it's respective integrations:

```js
[{
  email: string,
  integrations: [ 'fatec', 'etec', 'preferential', 'websai']
}]
```
{% endmethod %}
