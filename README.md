# accounts-app
Djangoのログイン用アプリです

## USAGE

PROJECT_NAME/settings.py
```python3:settings.py
...
INSTALLED_APPS = [
...
  "accounts",
...
]
...

```

PROJECT_NAME/urls.py
```python3:urls.py
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
