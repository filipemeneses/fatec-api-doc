## Calendar (months: IMonth[])

This method is used to store the academic calendar.

Where `IMonth`:

```js
interface IMonth {
  events: IEvent
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
