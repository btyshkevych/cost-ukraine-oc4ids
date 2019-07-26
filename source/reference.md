# Опис схеми

Схему стандарту можна завантажити у форматі [JSON Schema](https://json-schema.org/) за [посиланням](./schema/project-schema.json) або переглянути у форматі таблиць нижче. Непередбачені базовою версією стандарту атрибути мають позначку **розширення**.

## Project

`Project` — це об'єкт найвищого рівня, що включає дані на рівні поректу та об'єкти нижчого рівня.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :include:
    :collapse: items,period,sector,locations,budget/amount,budget/budgetBreakdown,documents,contractingProcesses,completion/finalValue,budget/estimatedAmount
```

## ContractingProcess

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :include:
    :pointer: /definitions/ContractingProcess
    :collapse: summary

```

## ContractingProcessSummary

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :include:
    :pointer: /definitions/ContractingProcessSummary
    :collapse: documents,tender/costEstimate,tender/procuringEntity,suppliers,contractValue,contractPeriod,finalValue,modifications

```

## Структурні блоки

### Dates

Для зазначення дат використовується стандарт ISO 8601 включно з часовою зоною, наприклад:

> 2019-07-25T12:30:00+03:00


### Address

Запис адреси має містити щонаймеше заповнене поле `streetAddress` або `postalCode`.

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Address
    :include:
    :collapse:

```

### BudgetBreakdown

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/BudgetBreakdown
    :include:
    :collapse:

```

### Classification

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Classification
    :include:
    :collapse:

```

### ContactPoint

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/ContactPoint
    :include:
    :collapse:

```

### Document

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Document
    :include:
    :collapse:

```


### Location 

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Location
    :include:
    :collapse: address

```

### Modification

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Modification
    :include:
    :collapse: oldContractValue,newContractValue,oldContractPeriod,newContractPeriod

```

### Organization

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Organization
    :collapse: identifier,address,contactPoint

```

### Period

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Period
    :include:
    :collapse:

```

### Value

```eval_rst

.. jsonschema:: ../schema/project-schema.json
    :pointer: /definitions/Value
    :include:
    :collapse:

```