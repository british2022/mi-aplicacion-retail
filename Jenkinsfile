pipeline {
    agent any

    tools {
        maven 'Maven 3.9.11'  // Asegúrate de que este nombre coincida con el configurado en Jenkins
        jdk 'Java 11'
    }

    stages {
        stage('Obtener codigo fuente de Git') {
            steps {
                echo 'Obteniendo el código fuente del repositorio Git...'
                git 'https://github.com/britanico2022/mi-aplicacion-retail.git'
            }
        }

        stage('Compilar y Ejecutar Pruebas') {
            steps {
                echo 'Compilando y ejecutando pruebas con Maven...'
                sh 'mvn clean install'
            }
        }

        stage('Empaquetar') {
            steps {
                echo 'Generando archivo .jar/.war'
                sh 'mvn package'
            }
        }

        stage('Despliegue') {
            steps {
                echo 'Desplegando la aplicación (placeholder)...'
                // Aquí puedes agregar comandos reales para el despliegue
            }
        }
    }

    post {
        success {
            echo 'Pipeline ejecutado con éxito.'
        }
        failure {
            echo 'Error en el pipeline. Revisar logs.'
        }
    }
}
