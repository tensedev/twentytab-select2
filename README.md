twentytab-select2
=================

A Django widget with [Select2](http://ivaynberg.github.com/select2/) integration. 

## Installation

Use the following command: <b><i>pip install twentytab-select2</i></b>

## Configuration

- Settings.py

Open settings.py and add select2 to your INSTALLED_APPS:

```py
INSTALLED_APPS = {
    ...,
    'select2',
    ...
}

```

twentytab-select2 will set his own jquery plugin. If you already use yours you have to define the following parameters in your settings:

```py

STATIC_URL = u'/static/'
JQUERY_LIB = 'path_to_jquery'
SELECT2_LIB = 'path_to_select2_js'
SELECT2_CSS_LIB = 'path_to_select2_css'

```
- Static files

Run collectstatic command or map static directory.

## Usage

- forms.py

```py

from testapp.models import ModelTest
from django import forms
from select2.widgets import SelectAutocomplete, SelectMultipleAutocomplete


class TestForm(forms.ModelForm):
    class Meta:
        model = ModelTest
        widgets = {
            'myfield': SelectAutocomplete(),
            'mymultiplefield': SelectMultipleAutocomplete(),
        }


```
Both widgets take a parameter called "plugin_options". It's a dictionary and it can take all select2 options.