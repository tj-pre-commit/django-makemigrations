# django-makemigrations
Run Django's [makemigrations](https://docs.djangoproject.com/en/3.1/ref/django-admin/#django-admin-makemigrations) as a pre-commit hook.


# graphene-django-precommit-hook
[pre-commit](https://pre-commit.com) hook to generate [django migrations](https://docs.djangoproject.com/en/3.1/ref/django-admin/#django-admin-makemigrations)


See [pre-commit](https://github.com/pre-commit/pre-commit) for installation instructions


Sample basic `.pre-commit-config.yaml`

```yaml
-   repo: https://github.com/tj-pre-commit/django-makemigrations
    rev: v1.0.0
    hooks:
      - id: django-makemigrations
        stages: [commit]
```


Sample complex `.pre-commit-config.yaml`

```yaml
-   repo: https://github.com/tj-pre-commit/django-makemigrations
    rev: v1.0.0
    hooks:
      - id: django-makemigrations
        stages: [commit]
        args: [
          '--settings',
          'project.settings',  # Defaults to: DJANGO_SETTINGS_MODULE
          '--merge',  # Enables fixing of migration conflicts.
          '--empty',  # Creates an empty migration.
          '--no-input',  # Do not prompt for user input.
          '--verbosity', # OR '-v'
          '2', # Set the verbosity level {0,1,2,3}
          #  See https://docs.djangoproject.com/en/3.1/ref/django-admin/#makemigrations for more information
        ]
```
