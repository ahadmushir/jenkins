pipeline {
  agent any
  stages {
    stage("build") {
      steps{
        println("in build")
        test()
      }
    }
    stage("docker-check") {
      steps{
        sh "jq -c '.versioning = "minor"' conf.json > tmp.$$.json && mv tmp.$$.json conf.json" 
      }
    }
    stage("shell") {
      steps{
        shh() 
      }
    }
  }

}


void test() {
  String str1 = "v0.0.0"
  def num_str = str1.tokenize('v')
  println(num_str)
  
  def (major, minor, patch) = num_str[0].tokenize('.').collect { it.toInteger() }
  println(major)
  println(minor + 1)
  println(patch + 4)
}

void shh() {
  String relname = sh(returnStdout: true, script: "jq -c '.versioning = "minor"' conf.json > tmp.$$.json && mv tmp.$$.json conf.json").trim()
  println(relname)
}
