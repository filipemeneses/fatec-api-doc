# Discipline ({absenses, name, code, classroomCode, classroomId, classHours, frequency, grade, quitDate, period, periodId, presences, courseId, state, teacherName, teacherId})

## Argument types

```js
{
  absenses?: number,
  name?: string,
  code: string,
  classroomCode?: string,
  classroomId?: number,
  classHours?: number,
  frequency?: number,
  grade?: number,
  quitDate?: Date,
  period?: string,
  periodId?: number,
  presences?: number,
  courseId?: number,
  state?: DisciplineState,
  teacherName?: string,
  teacherId?: number,
}
```

## Attributes

```js
private name: string;
private code: string;
private period: string;
private classroomCode: string;
private classroomId: number;
private quitDate: Date;
private periodId: number;
private courseId: number;
private grade: number;
private teacherName: string;
private teacherId: number;
private absenses: number;
private frequency: number;
private presences: number;
private classHours: number;
private state: DisciplineState;
```

## Methods

### Public

- `public isApproved (): boolean `
- `public isNotAttended (): boolean `
- `public isAttending (): boolean `
- `public isDismissed (): boolean `
- `public isQuited (): boolean `

- `public setFrequency (frequency: number): void `
- `public getFrequency (): number `
- `public setGrade (grade: number): void `
- `public getGrade (): number `
- `public setState (state: DisciplineState): void `
- `public getState (state): DisciplineState `
- `public setClassroomCode (classroomCode: string): void `
- `public getClassroomCode (): string `
- `public setTeacherName (teacherName: string): void `
- `public getTeacherName (): string `
- `public setAbsenses (absenses: number): void `
- `public getAbsenses (): number `
- `public setPresences (presences: number): void `
- `public getPresences (): number `
- `public setName (name: string): void `
- `public getName (): string `
- `public setCode (code: string): void `
- `public getCode (): string `
- `public setPeriod (period: string): void `
- `public getPeriod (): string `
- `public setclassroomId (classroomId: number): void `
- `public getClassroomId (): number  `
- `public setQuitDate (quitDate: Date): void `
- `public getQuitDate (): Date  `
- `public setPeriodId (periodId: number): void `
- `public getPeriodId (): number  `
- `public setCourseId (courseId: number): void `
- `public getCourseId (): number  `
- `public setTeacherId (teacherId: number): void `
- `public getTeacherId (): number  `
