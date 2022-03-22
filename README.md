# accounts-app
Djangoのログイン用アプリです

## USAGE

```shell
git submodule add git@github.com:zoonaka/accounts-app.git accounts
```


```python3
# PROJECT_NAME/settings.py

...
INSTALLED_APPS = [
...
  "accounts",
...
]
...

```


```python3
# PROJECT_NAME/urls.py

...
urlpatterns = [
    ...
    path('accounts/', include('django.contrib.auth.urls')),
    ...
]
...
```

例としてテンプレートには下記のように書きます
```htmldjango
{% if not user.is_authenticated %}
  <a href="{% url 'login' %}?next={{ request.path }}">Login</a>
{% endif %}
{% if user.is_authenticated %}
  <a href="{% url 'logout' %}?next={{ request.path }}">Logout</a>
{% endif %}
```
