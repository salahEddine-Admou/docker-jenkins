pipeline{
agent any
  parameters{
    choice(name:'VERSION',choices:['1.1.1','1.1.2'],description:'version of build')
    booleanParam(name:'execute',defaultValue:true,description:'check execution success')
  }
stages{
stage("build"){
steps{
  when{
    expression{
      params.execute == true
    }
  }
  steps{
    ech "hellooo ${params.VERSION}"
  }
}
}
stage("test"){
steps{
  echo "test the project"
}
}
stage("deploy"){
steps{
  echo "deploy the project"
}
}
}
}
