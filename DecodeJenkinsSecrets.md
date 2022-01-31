If we pull up a secret from the Credentials page and select update anwe can then inspect the page where we can find the encrypted secret

eg {AQAAABAAAAAQlI/0ApLu3oAoflKtLirppOQRhqr1lAZ8+stbbgrcoYY=}

Then from the jenkins console  http://jenkinsurl/script 

println hudson.util.Secret.decrypt("{AQAAABAAAAAQlI/0ApLu3oAoflKtLirppOQRhqr1lAZ8+stbbgrcoYY=}")


