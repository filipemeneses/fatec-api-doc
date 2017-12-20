# Calendar (months)

Essa classe é usada para guardar o calendário acadêmico.

## Tipo do argumento

```js
months: IMonth[];
```

## Atributos

```js
private months: IMonth[];
```

Onde `IMonth`:

```js
interface IMonth {
  events: IEvent[];
}
```

Onde `IEvent`:

```js
interface IEvent {
  date: Date;
  name: string;
  reason: string;
}
```

## Métodos

### Público

- `public setMonths (months: IMonth[])`
- `public getMonths (): IMonth[]`
