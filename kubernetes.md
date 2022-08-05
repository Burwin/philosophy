# Kubernetes

## Example Deployment Pipeline
1. Push branch
2. Run unit tests
3. Build docker container(s)
5. Publish containers to container registry
6. Deploy to Auto-test environment
7. Run integration tests
8. Deploy to ephemeral dev environment
9. Notify of successful build and deployment to dev
10. Manual trigger to deploy to ephemeral canary for T time
11. Notify when expiration of canary nears
12. Manual trigger to deploy to prod
