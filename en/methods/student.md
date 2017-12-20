## Student ()

This class is controlled by [Account](/methods.md) to store the scrapped data.

## Attributes

```js
private name: string;
private registeredEmails: IRegisteredEmail[];
private partialGrades: IPartialGrade[];
private enrolledDisciplines: Discipline[] = [];
private schedules: ISchedule[];
private history: IHistoryEntry[];
```

## Methods

### Public

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

### Private

- `private updateDiscipline (discipline: Discipline)`
