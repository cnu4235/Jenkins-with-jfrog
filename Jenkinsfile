Pipeline{
  agent any


  stages{
	Stage(Clean Workspace){
		steps{
		 cleanws()
		}
	}
        Stage(Build){
                steps{
                 sh "mvn clean package"
                }
        }

 }
}
