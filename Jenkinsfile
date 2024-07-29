Pipeline{
  agent any


  stages{
	Stage(CleanWorkspace){
		steps{
		 cleanWs()
		}
	}
        Stage(Build){
                steps{
                 sh "mvn clean package"
                }
        }

 }
}
