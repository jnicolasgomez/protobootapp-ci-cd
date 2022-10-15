# URL Repositorio
https://github.com/jnicolasgomez/protobootapp-ci-cd
# Setup GitHub Actions
1. Se inicializa proyecto con lo siguientes archivos archivos: Check files -> github/workflows/maven.yml and pom.xml
3.  Configurado para ejecutar la accion y hacer el build de maven al hacer push a la rama main
## Results
Se ejecutó le build de forma correcta
![github_results](https://github.com/jnicolasgomez/protobootapp-ci-cd/tree/main/images/images/github_results.png)
# Setup Jenkins
1. Se descargó la version lts de Jenkins desde una imagen de Docker. y se ejecuta en el port 8080
2. Configuracion de Plugins adicionales
    1. JaCoCo Plugin
    2. Warnings Next Generation Plugin
3.  Se realizo la configuracion de pipeline de integración
    1. ***Source Code Management*** s utilizó el repositorio de github configurado en la rama  */main
    2. ***Build Steps*** se confugiró maven comando (compile test install package)
    3. **Post build actions ***
        1. Publlish JUint test result report
           ```target/surefire-reports/*.xml```
    4. ***Static analysis Tools***
        1. SpotBugs
        2. CheckStyle
        3. PMD
    5. ***Record JaCoCo coverage report***

## Results
1. La ejecucion resulta exitosa Mostrando en el dashboard los reultados de cada herramienta
   ![jenkins_results](https://github.com/jnicolasgomez/protobootapp-ci-cd/tree/main/images/jenkins_results_2.png)

2. Prueba con test fallidos y reduccion de coverage
   ![jenkins_results](https://github.com/jnicolasgomez/protobootapp-ci-cd/tree/main/images/jenkins_results_3.png)

![jenkins_results](https://github.com/jnicolasgomez/protobootapp-ci-cd/tree/main/images/jenkins_results_4.png)

![jenkins_results](https://github.com/jnicolasgomez/protobootapp-ci-cd/tree/main/images/jenkins_results_5.png)