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
  def num_str = str1.tokenize('v')
  println(num_str)
  
  def (major, minor, patch) = num_str.tokenize('.').collect { it.toInteger() }
  println(major)
  println(minor)
  println(patch)
}
