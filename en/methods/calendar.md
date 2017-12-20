# Calendar (months)

This method is used to store the academic calendar.

## Argument type

```js
months: IMonth[];
```

## Attributes

```js
private months: IMonth[];
```

Where `IMonth`:

```js
interface IMonth {
  events: IEvent[];
}
```

Where `IEvent`:

```js
interface IEvent {
  date: Date;
  name: string;
  reason: string;
}
```

## Methods

### Public

- `public setMonths (months: IMonth[])`
- `public getMonths (): IMonth[]`
