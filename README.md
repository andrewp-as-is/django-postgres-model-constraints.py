<!--
https://readme42.com
-->


[![](https://img.shields.io/pypi/v/django-postgres-model-constraints.svg?maxAge=3600)](https://pypi.org/project/django-postgres-model-constraints/)
[![](https://img.shields.io/badge/License-Unlicense-blue.svg?longCache=True)](https://unlicense.org/)
[![](https://github.com/andrewp-as-is/django-postgres-model-constraints.py/workflows/tests42/badge.svg)](https://github.com/andrewp-as-is/django-postgres-model-constraints.py/actions)

### Installation
```bash
$ [sudo] pip install django-postgres-model-constraints
```

#### Pros
designed for Django projects with a large number of models:

+   no need `makemigrations` and `migrate`
+   no migration conflicts
+   integrity checks - drop and create constraints again
+   define tables with raw SQL (optional)

#### Examples
```python
from django.apps import apps
from django_postgres_model_constraints.utils import get_add_foreign_key_constraint_statements, get_add_unique_constraint_statements


for model in apps.get_models():
    statements = get_add_unique_constraint_statements(
        model) + get_add_foreign_key_constraint_statements(model)
```

```python
from django.apps import apps
from django_postgres_model_constraints.utils import get_drop_foreign_key_constraint_statements, get_drop_unique_constraint_statements


for model in apps.get_models():
    statements = get_drop_foreign_key_constraint_statements(
        model) + get_drop_unique_constraint_statements(model)
```

<p align="center">
    <a href="https://readme42.com/">readme42.com</a>
</p>
