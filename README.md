## django-plugins

[![Build Status](https://travis-ci.org/krischer/django-plugins.svg?branch=master)](https://travis-ci.org/krischer/django-plugins) ||  Latest stable version: **0.2.5**

`django-plugins` provides functionality for Django apps to make them more
reusable.

**Home page:** http://pypi.python.org/pypi/django-plugins

**Documentation:** http://packages.python.org/django-plugins/

**Source code:** https://github.com/krischer/django-plugins

### Installation

`django-plugins` is currently tested with Python **2.7**, **3.2**, **3.3**, and
**3.4** along with Django versions **1.7** and **1.8**. It might well work
with other versions. See the [Travis build 
matrix](https://travis-ci.org/krischer/django-plugins) for detailed information
regarding the latest master.


Installation works via `pip`:

```bash
$ pip install django-plugins
```


### Signals

There are two registered signals with Django that you might use for hooking event handlers in case a django plugin gets disabled or enabled at a certain point.

Example

```python
from django.dispatch.dispatcher import receiver
from djangoplugins.signals import django_plugin_disabled, django_plugin_enabled

@receiver(django_plugin_enabled)
def _django_plugin_enabled(sender, plugin, **kwargs):
    enable_plugin(plugin)
    
@receiver(django_plugin_disabled)
def _django_plugin_disabled(sender, plugin, **kwargs):
    disable_plugin(plugin)

```
