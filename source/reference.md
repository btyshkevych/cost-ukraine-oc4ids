# Опис схеми

Схему стандарту можна завантажити у форматі [JSON Schema](https://json-schema.org/) за [посиланням](./schema/project-schema.json) або переглянути у форматі таблиць нижче. Непередбачені базовою версією стандарту атрибути мають позначку **розширення**.

## Project

`Project` — це об'єкт найвищого рівня, що включає дані на рівні проекту та об'єкти нижчого рівня. Для опису предмета проекту додане розширення items (відповідає об’єкту [Item](https://standard.open-contracting.org/latest/en/schema/reference/#item) в OCDS). Статус виконання графіка проекту зазначається в розширенні `scheduleStatus`, кошторисна вартість — `budget/estimatedAmount`.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :include:
    :collapse: items,period,sector,locations,budget/amount,budget/budgetBreakdown,documents,contractingProcesses,completion/finalValue,budget/estimatedAmount
```

## ContractingProcess

Один інфраструктурний проект може включати декілька закупівель. Об’єкт `ContractingProcess` включає 

1. перелік;
2. істотні подробиці закупівель;
3. історію змін до угод.


```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :include:
    :pointer: /definitions/ContractingProcess
    :collapse: summary,releases

```

## ContractingProcessSummary

Об’єкт `ContractingProcessSummary` містить подробиці здійснених закупівель та історію змін до угод.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :include:
    :pointer: /definitions/ContractingProcessSummary
    :collapse: items,documents,tender/costEstimate,tender/procuringEntity,tender/bids,suppliers,contractValue,contractPeriod,finalValue,modifications,warranties

```

## Структурні блоки

### Address

Запис адреси має містити щонайменше одне заповнене поле `streetAddress` або `postalCode`.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Address
    :include:
    :collapse:

```

### Bid

Один тендер може мати декілька цінових пропозицій. Кожна цінова пропозиція представлена об'єктом `Bid`.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Bid
    :include:
    :collapse: tenderers,value

```

### BudgetBreakdown

Структура фінансування описується масивом, що складається з об’єктів `BudgetBreakdown`. Властивості з базового OC4IDS: `uri`, `period`, `sourceParty`, не використовуються.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/BudgetBreakdown
    :include:
    :collapse: amount

```

### Classification

Для представлення всіх класифікацій використовується об’єкт `Classification`.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Classification
    :include:
    :collapse:

```

### ContactPoint

Контактні дані організацій подаються в об’єкті `ContactPoint`. У [Prozorro](http://api-docs.openprocurement.org/uk_UA/latest/standard/organization.html#contactpoint) обов'язковим є заповнення одного з полів або `email`, або `telephone`.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/ContactPoint
    :include:
    :collapse:

```

### Dates

Для зазначення дат використовується стандарт [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) включно з часовою зоною, наприклад:

> 2019-07-25T12:30:00+03:00


### Document

Для представлення метаданих документів використовується об’єкт `Document`. Базовий стандарт розширено властивістю `number`. Вона містить дані про номер документа, що присвоюється видавником.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Document
    :include:
    :collapse:

```

### Item

Об'єкт `Item` використовується як розширення для представлення предмета(-ів) угоди (об'єкт `ContractingProcessSummary`) або проекту в цілому (об'єкт `Project`). 

1. **Угоди.** Наразі portal.costukraine.org публікує лише інформацію про класифікацію предмета за CPV (атрибут `classification`). 
2. **Проекти.** Як основна класифікація використовується класифікація за об'єктом робіт (атрибут `classification`), а одиниця вимірювання — площа ремонту (атрибути `quantity` і `unit`).

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Item
    :include:
    :collapse: classification,additionalClassifications

```

### Location

Проект може мати одне або більше розташувань, які зазначаються в одному масиві. Об'єкт `Location` описує розташування у декілька способів:

- просторові дані в форматі JSON;
- [газетир](https://uk.wikipedia.org/wiki/%D0%93%D0%B0%D0%B7%D0%B5%D1%82%D0%B8%D1%80);
- адреса.

У якості газетира для автомобільних шляхів використовується Перелік автомобільних доріг загального користування затверджений [Постановою Кабінету Міністрів України від № 55 30.01.2019](https://zakon.rada.gov.ua/laws/show/55-2019-%D0%BF). В об'єкт `Location` додані розширення порталу: `pikets` (пікетна прив'язка), `length` (довжина відрізка шляху).


```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Location
    :include:
    :collapse: address

```

### Modification

`Modification` — об’єкт, що містить структурований опис змін умов угоди. Стандарт даних передбачає лише фіксацію змін вартості й строків виконання угоди. Властивості з базового OC4IDS: `description` і `rationale`, не використовуються.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Modification
    :include:
    :collapse: oldContractValue,newContractValue,oldContractPeriod,newContractPeriod

```

### Organization

`Organization` — об’єкт, що використовується для представлення даних про організації (у тому числі, юридичних осіб і фізичних осіб-підприємців). Стандарт даних portal.costukraine.org, як і [Prozorro](http://api-docs.openprocurement.org/uk_UA/latest/standard/organization.html), використовує модифікацію OCDS. Властивості `id`, `roles` та `additionalIdentifiers` не використовуються. Об’єкт `OrganizationReference` виключений з моделі даних.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Organization
    :collapse: address,contactPoint

```

### Period

`Period` — об’єкт, що використовується для позначення відрізків часу. Стандарт даних portal.costukraine.org не використовує властивість 'maxExtentDate' (як і [Prozorro](http://api-docs.openprocurement.org/uk_UA/latest/standard/util.html)). Властивість 'durationInDays' використовується для представлення гарантійних термінів, коли дати початку та кінця гарантії невказані. Всі дати подаються відповідно до стандарту ISO 8601.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Period
    :include:
    :collapse:

```

### LinkedRelease

Метадані OCDS релізів представлені об'єктом `LinkedRelease`. Властивість `tag` не використовується в стандарті, оскільки дані з системи Prozorro оприлюднюються одним релізом.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/LinkedRelease
    :include:
    :collapse:

```


### Value

Для зазначення всіх вартостей використовується об’єкт `Value`.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Value
    :include:
    :collapse:

```

### Warranty

Товари, роботи, їх окремі компоненти (властивості) можуть мати кілька гарантійних термінів. Кожна гарантія представляється об'єктом `Warranty`. Термін гарантії окреслюється датою початку та завершення. Якщо дати невідомі, то вказується загальна тривалість терміну у днях.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Warranty
    :include:
    :collapse:

```