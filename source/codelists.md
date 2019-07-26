# Довідники

Цей розділ містить інформацію про довідники (codelists), які використані в стандарті даних. Непередбачені базовою версією стандарту довідники мають позначку **розширення**.


```eval_rst
.. admonition:: Дізнатися більше
    :class: Tip

    .. markdown::

      Більше інформації про довідники в Open Contracting for Infrastructure Data Standards можна отримати за [посиланням](http://standard.open-contracting.org/infrastructure/latest/en/reference/codelists/).

```

## ProjectSector

Сектор інфрфструктури, якому реалізується проект.

```eval_rst

   .. csv-table::
      :header-rows: 1
      :class: codelist-table
      :file: ../schema/codelists/projectSector.csv

```

## ProjectStatus

Статус реалізації проекту.

```eval_rst

   .. csv-table::
      :header-rows: 1
      :class: codelist-table
      :file: ../schema/codelists/projectStatus.csv

```

## ScheduleStatus [розширення]

Статус виконання графіка проекта.

```eval_rst

   .. csv-table::
      :header-rows: 1
      :class: codelist-table
      :file: ../schema/codelists/scheduleStatus.csv

```

## ProjectType

Тип проекту за переважаючими видами робіт.

```eval_rst

   .. csv-table::
      :header-rows: 1
      :class: codelist-table
      :file: ../schema/codelists/projectType.csv

```

## ContractNature

Природа угоди за переважаючими видами робіт.

```eval_rst

   .. csv-table::
      :header-rows: 1
      :class: codelist-table
      :file: ../schema/codelists/contractNature.csv

```

## ContractNatureType [розширення]

Тип угоди за її предметом.

```eval_rst

   .. csv-table::
      :header-rows: 1
      :class: codelist-table
      :file: ../schema/codelists/contractNatureType.csv

```

## Method

Метод торгів, що використовується під час закупівлі.

```eval_rst

   .. csv-table::
      :header-rows: 1
      :class: codelist-table
      :file: ../schema/codelists/method.csv

```

## MethodDetails [розширення]

Вид закупівлі з Єдиної системи електронних закупівель (prozorro.gov.ua). Довідник Prozorro у форматі JSON можна завантажити за [посиланням](https://prozorroukr.github.io/standards/codelists/tender_procurement_method_type.json).

```eval_rst

   .. csv-table::
      :header-rows: 1
      :class: codelist-table
      :file: ../schema/codelists/methodDetails.csv

```

## ContractingProcessStatus

Статус укладення й реалізації угоди.

```eval_rst

   .. csv-table::
      :header-rows: 1
      :class: codelist-table
      :file: ../schema/codelists/contractingProcessStatus.csv

```

## ModificationType

Тип змін до угод.

```eval_rst

   .. csv-table::
      :header-rows: 1
      :class: codelist-table
      :file: ../schema/codelists/modificationType.csv

```

## GeometryType

Тип геометрії в GeoJSON.

```eval_rst

   .. csv-table::
      :header-rows: 1
      :class: codelist-table
      :file: ../schema/codelists/geometryType.csv

```

## DocumentType

Типи документів.

```eval_rst

   .. csv-table::
      :header-rows: 1
      :class: codelist-table
      :file: ../schema/codelists/documentType.csv

```

## Інші довідники

### Currency

Коди валют відповідно до ISO 4217:2010 у форматі [CSV](../../build/current_lang/codelists/currency.csv) (Джерело: Open Contracting for Infrastructure Data Standards), у форматі [JSON](https://data.gov.ua/dataset/5a2ba455-ea8c-4431-b58e-1201fb15d61d/resource/5814e041-2cf3-42b7-b576-ad0f74d6c275/download/skv.json) (Джерело: Державна служба статистики України).

### UnitCodes

Одиниці виміру UN/CEFACT, що є рекомендованими й використовуються в Prozorro у форматі [JSON](https://prozorroukr.github.io/standards/unit_codes/recommended.json)
(Джерело: Довідники системи Prozorro).

### OrganizationIdentifierScheme

Схеми ідентифікації організацій відповідно до [org-id.guide](http://org-id.guide/) у форматі [CSV](http://org-id.guide/download.csv), [JSON](http://org-id.guide/download.json) (Джерело: org-id.guide), у форматі [JSON](https://prozorroukr.github.io/standards/codelists/organization_identifier_scheme.json) (Джерело: Довідники системи Prozorro).

