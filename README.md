links I found

using Environment variables.
  https://e.printstacktrace.blog/jenkins-pipeline-environment-variables-the-definitive-guide/

  https://www.eficode.com/blog/jenkins-groovy-tutorial

Escaping quotes.
  https://gerg.dev/2021/03/adventures-with-escaping-quotes-in-jenkins-pipelines/



Skipping the default checkout so we don't have the step 
  Declarative: Checkout SCM  listed.

options {
    skipDefaultCheckout( true ) 
    buildDiscarder( logRotator(daysToKeepStr: '7', numToKeepStr: '1') )
}

Then in the step of the stage do the checkout.
checkout scm