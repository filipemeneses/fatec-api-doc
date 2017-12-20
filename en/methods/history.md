## History (entries)

## Argument type

```js
entries: IEntry[]
```

## Attributes

```js
private entries: IEntry[];
```

and has the following interface:

```js
interface IEntry {
  observation: number;
  discipline: Discipline;
}
```

## Methods

### Public

- `public setWeight (weight: number): void `
- `public getWeight (): number `
- `public setCode (code: string): void `
- `public getCode (): string `
- `public setTitle (title: string): void `
- `public getTitle (): string `
- `public setDescription (description: string): void `
- `public getDescription (): string `
- `public setGrades (grades: IGrade[]): void `
- `public getGrades (): IGrade[] `
- `public setApplyDates (applydates: IApplyDate): void `
- `public getApplyDates (): IApplyDate `
