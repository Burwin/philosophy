# Kubernetes

## Example Deployment Pipeline

### DEV Iterations
1. Push to non-`master` branch
2. Run unit tests
3. Build docker container(s)
5. Publish containers to container registry
6. Deploy to Auto-test environment
7. Run integration tests
8. Deploy to ephemeral dev environment
9. Run post-deployment tests
10. Notify of successful build and deployment to dev

### Deployments to PROD
1. Merge dev-code into `master`
2. Run unit tests
3. Build docker container(s)
4. Publish containers to container registry
5. Deploy to ephemeral canary
6. Run post-deployment tests targeting canary
7. If problems, rollback (all the way to the commit to `master`)
8. If no problems and canary period expires, deploy to full prod
9. Run post-deployment tests

### Ephemeral DEV

DEV should have the ability to deploy any number of versions concurrently **_iff_** there are more than 1 dev teams. This enables sandboxed testing on semi-real systems.

These will be ephemeral in that they will automatically delete themselves at expiration (1 week?) unless extended by the devs. They can also be deleted early if necessary.

### Ephemeral Canary

Canary deployments should be good, but we can hold them here in a separate cluster for a period of time just to be sure. If we aren't alerted to any bugs by users or logs, then the canary period will expire and it will be automatically promoted to full prod (on the main cluster).
