# laboratorio-final
En el proyecto se verá:
1. Integración al pipelne de la herramienta SAST SonarQube cloud
2. Integración al pipeline la herramienta SCA dependency check
3. Creación de imagen Docker
4. Escaneo de vulnerabilidades sobre la imagen Docker generada usando Trivy
5. Despliegue de imagen Docker y escaneo DAST con OWASP ZAP


## Curl útiles de sonar:
```bash
curl -f -X POST -u "XXXXXXXXXXXXXXXXX:" "https://sonarcloud.io/api/measures/component" \
-d "component=<project_id>" \
-d "metricKeys=sqale_rating,security_rating,bugs,vulnerabilities,code_smells,coverage" 

curl -f -X POST -u "XXXXXXXXXXXXXXXXX:" "https://sonarcloud.io/api/issues/search" \
-d "componentKeys=<project_id>" \
-d "types=VULNERABILITY" \
-d "severities=MINOR"

curl -f -X POST -u "XXXXXXXXXXXXXXXXX:" "https://sonarcloud.io/api/issues/search" \
-d "componentKeys=<project_id>" \
-d "types=VULNERABILITY" \
-d "impactSeverities=BLOCKER,HIGH,MEDIUM"
```

