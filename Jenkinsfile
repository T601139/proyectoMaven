// Declarativo       *** Más sencilla y menos potente que la de scripting... pero mucho más que los proyectos de estilo libre. 
// Scripted          *** Menos sencilla (más compleja) y mucho más potente (puedo hacer lo que quiera con Jenkins)

pipeline {
    
    agent any //Para definir DONDE QUIERO QUE SE EJECUTE ESTA TAREA
    
    stages {
        
        stage("Etapa 1") {
            
            steps { //Hacemos las llamadas a los plugins
                
                sh "echo Soy la etapa 1"    //Llamada al plugin que ejecuta una shell
            }
            
        }
        
        stage("Etapa 2") {
            
            steps {
                
                sh """
                    echo Soy la etapa 2
                    echo Acabó la etapa 2
                    """
            }
            
        }

    }
}