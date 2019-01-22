# Example of python application deployed to OpenShift.

_Source code is from:_
https://realpython.com/flask-connexion-rest-api/

#### Commands to run on OpenShift:
```
oc new-build --binary --name=py3project -l app=py3project
oc start-build py3project --from-dir=. --follow
oc new-app py3project -l app=py3project
oc expose svc/py3project
oc set probe dc/py3project --readiness --get-url=http://:5000/api/health
```

