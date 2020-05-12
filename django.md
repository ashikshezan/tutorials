# Django Notes



### Admin site columns for a model

To display the desired fields in different columns in the admin panel for a model, you have to edit the `admin.py` file of the model in this way. 

```python
@admin.register(Tweet)
class TweetAdmin(admin.ModelAdmin):
    list_display = ['id', 'posted_date']
```




