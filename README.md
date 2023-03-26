# celery

Celery is a distributed task scheduling module which can be easily integrated with applications (in our case, python celery) and provide task scheduling options in a simple yet reliable manner.  Celery can be used to schedule consumer polls at regular intervals instead of running it forever, however things like graceful message consumption, offset management had to be tuned to make this work. 
