def gv 
pipeline{
agent any
  parameters{
    choice(name:'VERSION',choices:['1.1.1','1.1.2'],description:'version of build')
    booleanParam(name:'execute',defaultValue:true,description:'check execution success')
  }
stages{
stage("build"){
  when{
    expression{
      params.execute == true
    }
  }
  steps{
    echo "hellooo ${params.VERSION}"
  }

}
stage("test"){
steps{
  input{
    message "select the env"
    ok "done"
    parameters{
      choice(name:'ENV',choices:['dev','prod'],description:'env of deployment')
    }
  }
  script{
    gv = load "script.groovy"
    gv.hello()
  }
}
}
stage("deploy"){
steps{
  script{
    gv.hello()
    echo "deploying to ${ENV}"
  }
}
}
}
}
