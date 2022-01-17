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


Added a webhook using ngrok.

First I run socat to be able to forward to my local minikube cluster. 
My minikube cluster is running a nginx ingress controller which is why 
I am forwarding to port 80.

Add an entry to /etc/hosts for
MyInternal.name

SESSION 1. socat tcp-listen:30888,reuseaddr,fork tcp:MyInternal.name:80
SESSION 2. ngrok http 30888

In github add a webhook with the URL
https://ngrok-name.ngrok.io/github-webhook/

test2
