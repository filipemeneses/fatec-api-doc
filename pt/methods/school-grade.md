## SchoolGrade (semesters)

## Tipo do argumento

```js
semesters: ISemester[]
```

## Atributos

```js
private semesters: ISemester[];
```

e tem as seguintes interfaces:

```js
interface ISemester {
  number: number;
  disciplines: Discipline[];
}
```

## Métodos

### Público

- `public setSemesters (semesters: ISemester[]): void`
- `public getSemesters (): ISemester[]`
