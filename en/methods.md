# Account (user, password)

## Argument types

```js
user: string,
password: string
```

## Attributes

```js
private static readonly STATES = {
  DENIED: 1,
  IDLE: 0,
  LOGGED: 2,
};

public username: string;
public password: string;
public cookie: string = "";
public state: number = Account.STATES.IDLE;
public student: Student = new Student();
```

## Methods

### Public

#### State

- `public isLogged (): boolean`
- `public isDenied (): boolean`
- `public isIdle (): boolean`


#### Authentication

{% method name="login" %}
### `public login(): Promise`

This method will request SIGA for access and try to log in. **This is no longer required, but is useful to catch if credentials are incorrect (or any other error in SIGA)**

{% endmethod %}


#### Scrapper

{% method name="getName" %}
### `public getName(): Promise<string>`

Will return the account's user name.

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const myAccount = new fatecApi.Account('LOGIN', 'PASSWORD')

myAccount.getName().then(name => {})
```

Exemple of `name` value:

```js
'FILIPE COSTA MENESES'
```
{% endmethod %}

{% method name="getProfile" %}
### `public getProfile (): Promise<any>`

Will return your profile data, available at home and at exchange programs page

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const myAccount = new fatecApi.Account('LOGIN', 'PASSWORD')

myAccount.getProfile().then(profile => {})
```

Exemple of `profile` value:

```js
profile = {
  "averageGrade": 8.82,
  "birthday": "1970-01-01T03:00:00.000Z",
  "code": "0000000000000",
  "course": "Tecnologia em Análise e Desenvolvimento de Sistemas",
  "cpf": "00000000000",
  "email": "flcmeneses@gmail.com",
  "name": "FILIPE COSTA MENESES",
  "period": "Manhã",
  "progress": 42.85,
  "unit": "Faculdade de Tecnologia de São José dos Campos - \"Professor Jessen Vidal\""
}
```

{% endmethod %}

{% method name="getRegisteredEmails" %}
### `public getRegisteredEmails(): Promise<IRegisteredEmail[]>`

Will return a list of registered emails and it's respective integrations:

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const myAccount = new fatecApi.Account('LOGIN', 'PASSWORD')

myAccount.getRegisteredEmails().then(emails => {})
```

Exemple of `emails` value:

```js
emails = [
  {
    "email": "filipe.meneses@fatec.sp.gov.br",
    "integrations": [
      "fatec"
    ]
  },
  ...
]
```
{% endmethod %}


{% method name="getPartialGrades" %}
### `public getPartialGrades (): Promise<object>`

Will return a list of partial grades


> `"discipline"` is a instance of [Discipline](/methods/discipline.md)

> `"evaluations"` is a list of instances of [Evaluation](/methods/evaluation.md)

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const myAccount = new fatecApi.Account('LOGIN', 'PASSWORD')

myAccount.getPartialGrades().then(partialGrades => {})
```

Exemple of `partialGrades` value:

```js
partialGrades = [
  {
    "discipline": Discipline {
      "name": "Interação Humano Computador",
      "code": "IHC001",
      "classroomId": 1,
      "frequency": 85,
      "grade": 10,
      "quitDate": "1970-01-01T00:00:00.000Z",
      "periodId": 1,
      "courseId": 24,
      "state": "approved",
      "teacherId": 171
    },
    "evaluations": [
      Evaluation {
        "applyDates": {
          "applied": "1970-01-01T00:00:00.000Z",
          "predicted": "1970-01-01T00:00:00.000Z",
          "published": "1970-01-01T00:00:00.000Z"
        },
        "description": "Projeto contendo o desenvolvimento de interfaces com HTML5",
        "grades": [
          {
            "date": "2017-12-04T00:00:00.000Z",
            "score": 10
          }
        ],
        "code": "P1",
        "title": "Projeto parte 1",
        "weight": 1
      },
      Evaluation {
        "applyDates": {
          "applied": "1970-01-01T00:00:00.000Z",
          "predicted": "1970-01-01T00:00:00.000Z",
          "published": "1970-01-01T00:00:00.000Z"
        },
        "description": "Projeto parte 2",
        "grades": [
          {
            "date": "2017-12-04T00:00:00.000Z",
            "score": 10
          }
        ],
        "code": "P2",
        "title": "Projeto parte 2",
        "weight": 1
      }
    ]
  }
]
```

{% endmethod %}

{% method name="getEnrolledDisciplines" %}

### `public getEnrolledDisciplines (): Promise<Discipline[]>`

Will return the enrolled disciplines

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const myAccount = new fatecApi.Account('LOGIN', 'PASSWORD')

myAccount.getEnrolledDisciplines().then(disciplines => {})
```

Exemple of `disciplines` value:

```js
disciplines = [
  Discipline {
    "absenses": 10,
    "name": "Programação Orientada a Objetos",
    "code": "ILP007",
    "classroomCode": "A",
    "classroomId": 1,
    "periodId": 1,
    "presences": 66,
    "courseId": 24,
    "teacherName": "GERSON DA PENHA NETO",
    "teacherId": 3131
  },
  ...
]
```

{% endmethod %}

{% method name="getSchedules" %}

### `public getSchedules (): Promise<Schedule[]> `

Will return the schedules with weekday and periods

> The day, month and year are relative to the current date. However, the hours and minutes remain the same.

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const myAccount = new fatecApi.Account('LOGIN', 'PASSWORD')

myAccount.getSchedules().then((schedules) => {})
```

Exemple of `schedules` value:

```js
schedules = [
  Schedule {
    "weekday": 3,
    "periods": [
      {
        "discipline": Discipline {
          "code": "ILP007",
          "period": "A"
        },
        "endAt": Date "2017-12-20T10:50:00.000Z",
        "startAt": Date "2017-12-20T10:00:00.000Z"
      },
      {
        "discipline": Discipline {
          "code": "ILP007",
          "period": "A"
        },
        "endAt": Date "2017-12-20T10:00:00.000Z",
        "startAt": Date "2017-12-20T09:10:00.000Z"
      }
    ]
  }
]
```
{% endmethod %}




{% method name="getHistory" %}

### `public getHistory (): Promise<History>`

Will return a instance of `History`

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const myAccount = new fatecApi.Account('LOGIN', 'PASSWORD')

myAccount.getHistory().then(history => {})
```

Exemple of `history` value:

```js
history = History {
  entries: [
    {
      "discipline": {
        "absenses": 11,
        "name": "Administração Geral",
        "code": "AAG001",
        "frequency": 86,
        "grade": 9.5,
        "period": "20162",
        "state": "approved"
      },
      "observation": "Aprovado por Nota e Frequência"
    },
    ...
  ]
}
```

{% endmethod %}




{% method name="getSchoolGrade" %}

### `public getSchoolGrade (): Promise<SchoolGrade>`

Will return a instance of `SchoolGrade`

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const myAccount = new fatecApi.Account('LOGIN', 'PASSWORD')

myAccount.getSchoolGrade().then(schoolGrade => {})
```

Exemple of `schoolGrade` value:

```js
schoolGrade = SchoolGrade {
  "semesters": [
    {
      "number": 1,
      "disciplines": [
        Discipline {
          "name": "Administração Geral",
          "code": "AAG001",
          "grade": 9.5,
          "quitDate": "1970-01-01T00:00:00.000Z",
          "state": "approved"
        },
      ]
    },
    ...
  ]
}
```

{% endmethod %}


{% method name="getAcademicCalendar" %}
### `public getAcademicCalendar (): Promise<Calendar>`

Will return a instance of `Calendar`

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const myAccount = new fatecApi.Account('LOGIN', 'PASSWORD')

myAccount.getAcademicCalendar().then(academicCalendar => {})
```

Exemple of `academicCalendar` value:

```js
Calendar {
  "months": [
    {
      "events": [
        {
          "date": "2017-01-01T02:00:00.000Z",
          "name": "Feriado Nacional",
          "reason": "CONFRATERNIZAÇÃO UNIVERSAL"
        }
      ]
    },
    ...
  ]
}
```

{% endmethod %}
