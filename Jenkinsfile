pipeline {
  agent any
  
  stages {
    stage("build") {
      steps{
        println("in build")
        String str1 = "v0.0.0"
        test()
      }
    }
    
  }

}


void test() {
  def (major, minor, patch) = relname.tokenize('.').collect { it.toInteger() }
  println(major)
  println(minor)
  println(patch)
}
