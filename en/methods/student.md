## Student ()

This class is controlled by [Account](/methods.md) to store the scrapped data. 

This class also provides the getters/setters from the following variables:

```js
private name: string;
private registeredEmails: IRegisteredEmail[];
private partialGrades: IPartialGrade[];
private enrolledDisciplines: Discipline[] = [];
private schedules: ISchedule[];
private history: IHistoryEntry[];
```

besides that, also provides:

{% method name="isEnrolledAtDiscipline" %}
### public isEnrolledAtDiscipline (discipline: Discipline): boolean
{% endmethod %}
