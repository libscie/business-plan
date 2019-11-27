# Hypergraph registry design

- Main SQL database with API endpoint
  - GET always allowed
  - POST only allowed with a specific token/private key that we’ll feed in to Stripe and use webhooks to add Dat keys
- Maybe we reverse proxy this so we can scale the SQL database with Kubernetes?
- Docker image that automatically reseeds from the main SQL database
- Kubernetes to scale
- Need to test the AWS/GCP pipeline for this.

## Resources

- https://blog.datproject.org/2019/04/14/getting-dat-to-work-in-new-environments/
- https://www.npmjs.com/package/dat-librarian
