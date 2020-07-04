# Assignment1
Django application : college
[views.py]
from django.shortcuts import render
from django.http import HttpResponse

def cse(request):
    return HttpResponse("Welcome to CSE page") 
def etc(request):
    return HttpResponse("Welcome to ETC page")
def mech(request):
    return HttpResponse("Welcome to Mech page")
def civil(request):
    return HttpResponse("Welcome to Civil page")            

[urls.py/college]
from django.contrib import admin
from django.urls import path,include
from . import views
urlpatterns = [
    
    path('cse', views.cse,name="cse"),
    path('etc', views.etc,name="etc"),
    path('mech', views.mech,name="mech"),
    path('civil', views.civil,name="civil")
]

[urls.py/Assignment1]
from django.contrib import admin
from django.urls import path,include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('college/', include("college.urls")),
]
