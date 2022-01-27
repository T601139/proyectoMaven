// Sintaxis declarativa: MAS SENCILLA y LA MAS USADA. Menos potente que la de scripting... 
//          pero mucho MAS que los proyectos de estilo libre
// Sintaxis de scripting: MAS COMPLEJA Y MAS POTENTE: Puedo hacer lo que quiera con Jenkins

pipeline {
    
    agent any // Para definir DONDE QUIERO QUE SE EJECUTE ESTA TAREA
    
    stages {
       stage("Etapa 1") {
           steps { // Hacemos las llamadas a los plugins
               sh "echo Soy la etapa 1" // Llamada al plugin que ejecuta una shell
               sh "echo Sigo" // Llamada al plugin que ejecuta una shell
               sh "echo Sigo" // Llamada al plugin que ejecuta una shell
               sh "echo Sigo" // Llamada al plugin que ejecuta una shell
               sh "echo Salgo de la etapa 1" // Llamada al plugin que ejecuta una shell
           }
           post {
               always { // Post tareas que siempre deben de ejecutarse
                  sh "echo Acabó la etapa 1"
               }
               success { // Postareas que SOLO se ejecutan si los pasos (STEPS) han ido bien
                  sh "echo Y acabó bien"
               }
               failure { // Postareas que SOLO se ejecutan si los pasos (STEPS) han dado error
                  sh "echo Pero acabó mal"
               }
           }
       }
       stage("Etapa 2") {
           
           stages {
               stage("Etapa 2.1") {
                   steps {
                       sh "sleep 10"
                       sh "echo Soy la etapa 2.1"
                   }
                   post {
                       success { // Post tareas que siempre deben de ejecutarse
                          sh "echo Acabó la etapa 2.1 bien!"
                       }
                   }
               }
               stage("Etapa 2.2") {
                   steps {
                       sh "sleep 10"
                       sh "echo Soy la etapa 2.2"
                   }
                   post {
                       failure { // Post tareas que siempre deben de ejecutarse
                          sh "echo Acabó la etapa 2.2 con error"
                       }
                   }
               }
           }
           
           post {
               always { // Post tareas que siempre deben de ejecutarse
                  sh "echo Acabó la etapa 2"
               }
               success { // Postareas que SOLO se ejecutan si los pasos (STEPS) han ido bien
                  sh "echo Y acabó bien"
               }
               failure { // Postareas que SOLO se ejecutan si los pasos (STEPS) han dado error
                  sh "echo Pero acabó mal"
               }
           }
       }
    }

    post {
       always { // Post tareas que siempre deben de ejecutarse
          sh "echo Acabó la etapa 2"
       }
       success { // Postareas que SOLO se ejecutan si los pasos (STEPS) han ido bien
          sh "echo Y acabó bien"
       }
       failure { // Postareas que SOLO se ejecutan si los pasos (STEPS) han dado error
          sh "echo Pero acabó mal"
       }
    }
}