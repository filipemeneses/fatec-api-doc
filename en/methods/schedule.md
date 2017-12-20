## Schedule ({weekday, periods})

## Argument type

```js
{
  weekday: number,
  periods: IPeriod[]
}
```

and has the following interface:

```js

interface IPeriod {
  startAt: Date;
  endAt: Date;
  discipline: Discipline;
}
```

## Attributes

```js
private weekday: number;
private periods: IPeriod[];
```

## Methods

### Public

- `public setWeekday (weekday: number): void`
- `public getWeekday (): number`
