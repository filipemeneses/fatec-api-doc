## Schedule ({weekday, periods})

## Tipo do argumento

```js
{
  weekday: number,
  periods: IPeriod[]
}
```

e tem as seguintes interfaces:

```js

interface IPeriod {
  startAt: Date;
  endAt: Date;
  discipline: Discipline;
}
```

## Atributos

```js
private weekday: number;
private periods: IPeriod[];
```

## Métodos

### Público

- `public setWeekday (weekday: number): void`
- `public getWeekday (): number`
