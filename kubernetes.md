# Kubernetes

## Example Deployment Pipeline
1. Push branch
2. Run unit tests
3. Build docker container(s)
5. Publish containers to container registry
6. Deploy to Auto-test environment
7. Run integration tests
8. Deploy to ephemeral dev environment
9. Run post-deployment tests
10. Notify of successful build and deployment to dev
11. Manual trigger to deploy to ephemeral canary for T time
12. Run post-deployment tests
13. Notify when expiration of canary nears
14. Manual trigger to deploy to prod
15. Run post-deployment tests
