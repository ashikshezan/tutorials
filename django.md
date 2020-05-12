# Django Notes



### Admin site columns for a model

To display the desired fields in different columns in the admin panel for a model, you have to edit the `admin.py` file of the model in this way. 

```python
@admin.register(Tweet)
class TweetAdmin(admin.ModelAdmin):
    list_display = ['id', 'posted_date']
```



### Clean-up or Custom validation of Forms

Validation of `form.py` of a model

```py
from django import forms
from .models import Tweet

MAX_CHAR = 240
class TweetForm(forms.ModelForm):
    class Meta:
        model = Tweet
        fields = ['content'] # list of fields from the model

    def clean_content(self):
        content = self.cleaned_data.get('content')
        if len(content) > MAX_CHAR:
            raise forms.ValidationError('Too long')
        else:
            return content

```



### Some queryset methods

```py
# latest tweets first
tweets = Tweet.objects.all().order_by('-posted_date')
```
