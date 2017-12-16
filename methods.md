# Account (user: string, password: string)

-----

{% method name="login" %}
### `public login(): Promise`

This will request SIGA for access and set the account as logged in.
{% endmethod %}

{% method name="getName" %}
### `public getName(): Promise<string>`

Will return the account's user name
{% endmethod %}

{% method name="getRegisteredEmails" %}
### `public getRegisteredEmails(): Promise<IRegisteredEmail[]>`

Will return a list of registered emails and it's respective integrations:

```js
[{
  email: string,
  integrations: [ 'fatec', 'etec', 'preferential', 'websai']
}]
```
{% endmethod %}


{% method name="getPartialGrades" %}
### `public getPartialGrades (): Promise<object>`

Will return a list of partial grades:

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


> `"discipline"` is a instance of [Discipline](/methods/discipline.md)

> `"evaluations"` is a list of instances of [Evaluation](/methods/evaluation.md)

{% endmethod %}

{% method name="getEnrolledDisciplines" %}

### `public getEnrolledDisciplines (): Promise<object>`

Will return the enrolled disciplines with attendance, teacher data

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







