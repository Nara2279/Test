# Test
from django.contrib import admin

from resume_cv.models import ResumeCv, ResumeCvCategory, ResumeCvTemplate

admin.site.register(ResumeCv)
admin.site.register(ResumeCvCategory)
admin.site.register(ResumeCvTemplate)

from django.apps import AppConfig


class ResumeCvConfig(AppConfig):
    default_auto_field = 'django.db.models.BigAutoField'
    name = 'resume_cv'

    from django import forms

from resume_cv.models import ResumeCv

class ResumeCvForm(forms.ModelForm):
    class Meta:
        model = ResumeCv
        exclude = ("user", "view_count", "is_published")

        
