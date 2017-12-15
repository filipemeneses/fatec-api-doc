## Evaluation ({ applyDates, code, description, grades, title, weight })

Discipline class contains the following attributes (and it's respective getters and setters):

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