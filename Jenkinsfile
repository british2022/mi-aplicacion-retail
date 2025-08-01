pipeline {
    agent any
    environment {
        // Asegúrate que 'Maven 3.9.11' coincida con el nombre que le diste a tu instalación de Maven en Jenkins.
        M2_HOME = tool 'Maven 3.9.11'
        PATH = "${M2_HOME}/bin:${PATH}"
    }
    stages {
        stage('Obtener Código Fuente de Git') {
            steps {
                echo "Obteniendo el código fuente del repositorio Git..."
                // No necesitas un 'git checkout' explícito aquí si configuras el SCM en el job de Jenkins.
            }
        }
        stage('Realizar Análisis del Código (Compilación y Pruebas)') {
            steps {
                echo "Compilando y ejecutando pruebas con Maven..."
                // 'clean install' compila el código y ejecuta las pruebas unitarias
                sh 'mvn clean install'
            }
        }
        stage('Realizar Deployment (Simulado)') {
            steps {
                echo 'Simulando el despliegue de la aplicación a un entorno...'
                // Lista los archivos en la carpeta 'target' para ver el JAR generado
                sh 'ls -l target'
                echo 'Despliegue simulado completado.'
            }
        }
    }
    post {
        always {
            echo 'El Pipeline ha finalizado.'
        }
        success {
            echo 'El Pipeline se ejecutó exitosamente.'
        }
        failure {
            echo 'El Pipeline falló. Revisar la salida de consola para más detalles.'
        }
    }
}