## Student ()

Essa classe é controlada pela [Account](/methods.md) para guardar os dados raspados.

## Atributos

```js
private name: string;
private registeredEmails: IRegisteredEmail[];
private partialGrades: IPartialGrade[];
private enrolledDisciplines: Discipline[] = [];
private schedules: ISchedule[];
private history: IHistoryEntry[];
```

## Métodos

### Público

- `public setProfile (profile: IProfile): void`
- `public getProfile (): IProfile`
- `public setAcademicCalendar (calendar: Calendar): void`
- `public getAcademicCalendar (): Calendar`
- `public setSchoolGrade (schoolGrade: SchoolGrade): void`
- `public getSchoolGrade (): SchoolGrade`
- `public setHistory (history: History): void`
- `public getHistory (): History`
- `public setSchedules (schedules: Schedule[]): void`
- `public getSchedules (): Schedule[]`
- `public getEnrolledDisciplineByCode (code: string): Discipline`
- `public setName (name: string): void`
- `public getName (): string`
- `public setRegisteredEmails (registeredEmails: IRegisteredEmail[]): void`
- `public getRegisteredEmails (): IRegisteredEmail[]`
- `public setPartialGrades (partialGrades: IPartialGrade[]): void`
- `public getPartialGrades (): IPartialGrade[]`
- `public setEnrolledDisciplines (disciplines: Discipline[]): void`
- `public getEnrolledDisciplines (): Discipline[]`
- `public setEnrolledDiscipline (discipline: Discipline): void`
- `public getEnrolledDisciplineIndexByCode (code: string): number`

### Privado

- `private updateDiscipline (discipline: Discipline)`
