# 9.5 Lab

### 1. NOTE For this lab, you can use any OS you prefer (try it on multiple ones if you would like), and make sure you are using PowerShell 7.1 or higher.

Now it’s your turn. We’re assuming that you’re working in a virtual machine or other machine that is okay to mess up a little in the name of learning. Please don’t do this in a production environment on a mission-critical computer!

This exercise will be about secrets management. DevOps engineers should be very familiar with this concept. The idea is simple: We have a bunch of sensitive information (passwords, connection strings, etc.) that we need to use in our commands, but we need to keep those secrets in a secure location. We also may want to share those secrets with other members on our team—and an email is not secure enough, folks!

The PowerShell team has recently been working on a module called Secrets Management to do just this. It’s a generic module for interacting with any secret store that supports it. Some will be local secret stores like the macOS Keychain, and others will be cloud services like Azure Key Vault and HashiCorp Vault. Your goal is to grab this module, store a secret in your secret store of choice, and then retrieve it. If you use a cloud-based secret store, try to retrieve the secret from a different machine as the ultimate test.

###
