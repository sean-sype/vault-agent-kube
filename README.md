# vault-agent-kube

Mini kube and vault agent demo

# Powershell commands
write a policy with GC: `gc ..\vault_configs\myapp-kv-ro.hcl | vault policy write myapp-kv-ro -`

Convert base64 decryption: 
First set your var: `$env:SA_JWT_TOKEN=$(kubectl get secret $env:VAULT_SA_NAME --output 'go-template={{ .data.token }}')` 
then set a 2nd var: `$env:SA_JWT_TOKEN_DECODED = [Convert]::ToBase64String([Text.Encoding]::Unicode.GetBytes($env:SA_JWT_TOKEN))`