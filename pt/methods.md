# Account (user, password)

## Tipos do argumento

```js
user: string,
password: string
```

## Atributos

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

## Métodos

### Público

#### State

- `public isLogged (): boolean`
- `public isDenied (): boolean`
- `public isIdle (): boolean`


#### Authentication

{% method name="login" %}
### `public login(): Promise`

Esse método irá requisitar o SIGA para acessar e tentar logar. **Esse método não é obrigatório mais, mas é útil para tratar erros quando as credenciais estão incorretas (ou caso outro qualquer erro no SIGA)**

{% endmethod %}


#### Scrapper

{% method name="getName" %}
### `public getName(): Promise<string>`

Irá retornar o nome do usuário da conta.

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const minhaConta = new fatecApi.Account('LOGIN', 'PASSWORD')

minhaConta.getName().then(name => {})
```

Exemplo do valor de `name`:

```js
'FILIPE COSTA MENESES'
```
{% endmethod %}

{% method name="getProfile" %}
### `public getProfile (): Promise<any>`

Irá retornar os dados do seu perfil, disponíveis na tela inicial e na de intercâmbios

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const minhaConta = new fatecApi.Account('LOGIN', 'PASSWORD')

minhaConta.getProfile().then(perfil => {})
```

Exemplo do valor de `perfil`:

```js
perfil = {
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


Irá retornar uma lista de e-mails registrados e suas respectivas integrações:

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const minhaConta = new fatecApi.Account('LOGIN', 'PASSWORD')

minhaConta.getRegisteredEmails().then(emails => {})
```

Exemplo do valor de `emails`:

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

Irá retornar uma lista de notas parciais

> `"discipline"` é uma instância de [Discipline](/methods/discipline.md)
> `"evaluations"` é uma lista de instâncias de [Evaluation](/methods/evaluation.md)

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const minhaConta = new fatecApi.Account('LOGIN', 'PASSWORD')

minhaConta.getPartialGrades().then(notasParciais => {})
```

Exemplo do valor de `notasParciais`:

```js
notasParciais = [
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

Irá retornar as disciplinas matriculadas

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const minhaConta = new fatecApi.Account('LOGIN', 'PASSWORD')

minhaConta.getEnrolledDisciplines().then(disciplinas => {})
```

Exemplo do valor de `disciplinas`:

```js
disciplinas = [
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

Irá retornar os horários com o dia da semana e períodos.

> O dia, mês e ano são relativos a data atual. Contudo, as horas e minutos permanecem os mesmos.

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const minhaConta = new fatecApi.Account('LOGIN', 'PASSWORD')

minhaConta.getSchedules().then((horarios) => {})
```

Exemplo do valor de `horarios`:

```js
horarios = [
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

Irá retornar uma instância de `History`

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const minhaConta = new fatecApi.Account('LOGIN', 'PASSWORD')

minhaConta.getHistory().then(historico => {})
```

Exemplo do valor de `historico`:

```js
historico = History {
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

Irá retornar uma instância de `SchoolGrade`

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const minhaConta = new fatecApi.Account('LOGIN', 'PASSWORD')

minhaConta.getSchoolGrade().then(gradeEscolar => {})
```

Exemplo do valor de `gradeEscolar`:

```js
gradeEscolar = SchoolGrade {
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

Irá retornar uma instância de `Calendar`

{% sample lang="js" %}
```js
const fatecApi = require('fatec-api')
const minhaConta = new fatecApi.Account('LOGIN', 'PASSWORD')

minhaConta.getAcademicCalendar().then(calendarioAcademico => {})
```

Exemplo do valor de `calendarioAcademico`:

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
