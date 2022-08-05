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
11. Manual trigger to merge, build, and deploy to ephemeral staging
12. Run post-deployment tests
13. Notify of successful deployment to staging
14. Manual trigger to deploy to ephemeral canary for T time
15. Run post-deployment tests
16. Notify of successful deployment to canary
17. Notify when expiration of canary nears
18. Manual trigger to deploy to prod
19. Run post-deployment tests
20. Notify of successful deployment to prod

### 11 - Merge, Build, and Deploy to Ephemeral Staging

When building containers for release to STAGE, the code should first be merged into `master`. This will be the "final build", passing this image along to canary and prod deployments.

... no, this is crazy. It needs significantly simplified.
