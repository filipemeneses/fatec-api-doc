# Evaluation ({ applyDates, code, description, grades, title, weight })

## Argument types

```js
{
  applyDates: IApplyDate,
  code: string,
  description: string,
  grades: IGrade[],
  title: string,
  weight: number,
}
```

## Attributes

```js
private weight: number;
private code: string;
private title: string;
private description: string;
private grades: IGrade[];
private applyDates: IApplyDate;
```

and has the following interfaces:

```js
interface IGrade {
  releaseDate: Date;
  grade: number;
}

interface IApplyDate {
  predicted: Date;
  applied: Date;
  published: Date;
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
