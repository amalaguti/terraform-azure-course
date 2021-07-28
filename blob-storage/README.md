# Setup CosmosDB

# Sign in
```
az login
```

# Generate ssh key
```
ssh-keygen -t rsa -b 4096 -f mykey
```
# Run Terraform init
```
terraform init
```

# Run Terraform apply
```
terraform apply
```

# Ssh into virtual machine
The output of terraform shows the public ip

```
ssh demo@PUBLIC_IP_HERE-i mykey
```

# Get token and dowload content of blob file

```
curl 'http://169.254.169.254/metadata/identity/oauth2/token?api-version=2018-02-01&resource=https%3A%2F%2Fstorage.azure.com%2F' -H Metadata:true
```

```
curl https://<STORAGE ACCOUNT>.blob.core.windows.net/<CONTAINER NAME>/traningfile.txt -H "x-ms-version: 2017-11-09" -H "Authorization: Bearer <ACCESS TOKEN>"

curl https://trainingsanlmer.blob.core.windows.net/trainingconlmer/traningfile.txt -H "x-ms-version: 2017-11-09" -H "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6Im5PbzNaRHJPRFhFSzFqS1doWHNsSFJfS1hFZyIsImtpZCI6Im5PbzNaRHJPRFhFSzFqS1doWHNsSFJfS1hFZyJ9.eyJhdWQiOiJodHRwczovL3N0b3JhZ2UuYXp1cmUuY29tLyIsImlzcyI6Imh0dHBzOi8vc3RzLndpbmRvd3MubmV0L2ExNGYzYzEzLTJiZDUtNDljOS04YzJiLTljMzViMjEzOThjZS8iLCJpYXQiOjE2Mjc0ODYzNDIsIm5iZiI6MTYyNzQ4NjM0MiwiZXhwIjoxNjI3NTczMDQyLCJhaW8iOiJFMlpnWUNoWjgvUFJjL2VKNXNZZnVsZlZYV1VyQlFBPSIsImFwcGlkIjoiMjRkYTNkNDItYjI5MS00MzQ4LTk5MWItOGVjYjA2OWZlNTU0IiwiYXBwaWRhY3IiOiIyIiwiaWRwIjoiaHR0cHM6Ly9zdHMud2luZG93cy5uZXQvYTE0ZjNjMTMtMmJkNS00OWM5LThjMmItOWMzNWIyMTM5OGNlLyIsIm9pZCI6IjBhMzU0NzgwLTFhOGYtNDdjMy1hOTRhLTM3ZmQ4Yjg0MTdmYiIsInJoIjoiMC5BWGtBRXp4UG9kVXJ5VW1NSzV3MXNoT1l6a0k5MmlTUnNraERtUnVPeXdhZjVWUjVBQUEuIiwic3ViIjoiMGEzNTQ3ODAtMWE4Zi00N2MzLWE5NGEtMzdmZDhiODQxN2ZiIiwidGlkIjoiYTE0ZjNjMTMtMmJkNS00OWM5LThjMmItOWMzNWIyMTM5OGNlIiwidXRpIjoib1FjTkI0N00xMHFzT01MNm9mTUNBQSIsInZlciI6IjEuMCIsInhtc19taXJpZCI6Ii9zdWJzY3JpcHRpb25zL2JhMTFkZDQzLTVkZjAtNDY0ZC04NjhmLWZkM2E3NTAzZTY4MC9yZXNvdXJjZWdyb3Vwcy9kZW1vL3Byb3ZpZGVycy9NaWNyb3NvZnQuQ29tcHV0ZS92aXJ0dWFsTWFjaGluZXMvZGVtby12bSJ9.k4ui5QesDyKazK4wbV4QKo0zFyH1WpumkJuMJjq7EMuNaXkfbiWSXyWIwb3oVxNfMh4ra48UekAOvPPiL0tkYWynS7LJRx5f49FQXd5rdjrptztAST67TbX9Y3abR2RXfc7vzzzlDeAKhQBr3GLnACUSBqFSWRqAb53hTBlbqBnxgdr5HXmhRY7mseN3O5c39N3-0ShNUuVHque5_ZIcuI9_QZQoht84DBAxee3Tn0ohbdXquc3kbTlYbE74Q4TLTf69ozlpFcvMYvIfrb-JTbqzny66Q6BvzCqYssKae8UdAS7-tDcPgnO6h1O_6Y2xwAnK3yj4mLqzT0etHF8Y-Q"

```

# Cleanup Demo
```
terraform destroy
```
