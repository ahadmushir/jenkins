pipeline {
  agent any
  
  stages {
    stage("build") {
      steps{
        println("in build")
        test()
      }
    }
    
  }

}


void test() {
  String str1 = "v0.0.0"
  def (major, minor, patch) = str1.tokenize('.').collect { it.toInteger() }
  println(major)
  println(minor)
  println(patch)
}
