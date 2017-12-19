# Account (user: string, password: string)

> From v7.2 **.login()** is no longer mandatory to use the methods.

> For instance: you can call **account.getPartialGrades()** without calling **account.login()** first.

-----

{% method name="login" %}
### `public login(): Promise`

This will request SIGA for access and set the account as logged in.

{% endmethod %}



{% method name="getName" %}
### `public getName(): Promise<string>`

Will return the account's user name.

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const myAccount = new fatecApi.Account('LOGIN', 'PASSWORD')

myAccount.getName().then(name => {
  console.log(name)
  // <- 'YOUR FULL NAME WITH CAPSLOCK'
})
```
{% endmethod %}

{% method name="getProfile" %}
### `public getProfile (): Promise<any>`

Will return your profile data, available at home and at exchange programs page

{% sample lang="js" %}
```js
{
  "averageGrade": number,
  "birthday": Date,
  "code": string,
  "course": string,
  "cpf": string,
  "email": string,
  "name": string,
  "period": string,
  "progress": number,
  "unit": string
}
```

{% endmethod %}

{% method name="getRegisteredEmails" %}
### `public getRegisteredEmails(): Promise<IRegisteredEmail[]>`

Will return a list of registered emails and it's respective integrations:

{% sample lang="js" %}
```js
[{
  email: string,
  integrations: [ 'fatec', 'etec', 'preferential', 'websai']
}]
```
{% endmethod %}


{% method name="getPartialGrades" %}
### `public getPartialGrades (): Promise<object>`

Will return a list of partial grades


> `"discipline"` is a instance of [Discipline](/methods/discipline.md)

> `"evaluations"` is a list of instances of [Evaluation](/methods/evaluation.md)

{% sample lang="js" %}
```js
[{
  "approved": boolean,
  "discipline": Discipline {
    "name": string,
    "code": string,
    "classRoomId": number,
    "quitDate": date,
    "periodId": number,
    "courseId": number,
    "teacherId": number
  },
  "evaluations": [
    Evaluation {
      "applyDates": {
        "applied": date,
        "predicted": date,
        "published": date
      },
      "description": string,
      "grades": [
        {
          "date": date,
          "score": number
        }
      ],
      "code": date,
      "title": date,
      "weight": number
    }
  ],
  "finalScore": number,
  "frequency": number
}]
```

{% endmethod %}

{% method name="getEnrolledDisciplines" %}

### `public getEnrolledDisciplines (): Promise<object>`

Will return the enrolled disciplines with attendance, teacher data

{% sample lang="js" %}
```js
[
  Discipline {
    "absenses": number,
    "name": string,
    "code": string,
    "classRoomId": number,
    "classRoomCode": string,
    "quitDate": date,
    "periodId": number,
    "courseId": number,
    "presences": number,
    "teacherId": number,
    "teacherName": string
  }
]
```

{% endmethod %}

{% method name="getSchedules" %}

### `public getSchedules (): Promise<string> `

Will return the schedules with weekday and periods

{% sample lang="js" %}
```js
[
  {
    "weekday": number
    "periods": [
      {
        "classroomCode": string,
        "discipline": Discipline {
          "code": string,
        },
        "endAt": date,
        "startAt": date
      },
    ]
  }
]
```

{% endmethod %}




{% method name="getHistory" %}

### `public getHistory (): Promise<string>`

Will return the history with it's entries

{% sample lang="js" %}
```js
[
  {
    "absenses": number,
    "approved": boolean,
    "discipline": Discipline {
      "name": string,
      "code": string,
      "quitDate": date
    },
    "frequency": number,
    "grade": number,
    "observation": string,
    "period": string
  }
]
```

{% endmethod %}

  


{% method name="getSchoolGrade" %}

### `public getSchoolGrade (): Promise<object[]>`

Will return the school grade with the semesters disciplines:

{% sample lang="js" %}
```js
{
  "disciplines": [
    Discipline {
      "name": string,
      "code": string,
      "quitDate": date,
      "state": DisciplineState
    }
  ],
  "number": number
}
```

Where `DisciplineState`:

{% sample lang="js" %}
```js
enum DisciplineState {
  approved = "approved",
  notAttended = "not-attended",
  attending = "attending",
  dismissed = "dismissed",
  quited = "quited",
}
```

{% endmethod %}


{% method name="getAcademicCalendar" %}
### `public getAcademicCalendar (): Promise<any>`

Will return every month of the calendar with it's respective events (usually holidays):

{% sample lang="js" %}
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
    }
  ]
}
```

{% endmethod %}
