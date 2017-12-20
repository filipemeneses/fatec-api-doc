## SchoolGrade (semesters)

## Argument type

```js
semesters: ISemester[]
```

## Attributes

```js
private semesters: ISemester[];
```

and has the following interface:

```js
interface ISemester {
  number: number;
  disciplines: Discipline[];
}
```

## Methods

### Public

- `public setSemesters (semesters: ISemester[]): void`
- `public getSemesters (): ISemester[]`
