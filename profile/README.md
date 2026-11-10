## GitOps Manager — build and deploy globally across clouds

Open-source GitHub Actions that take your applications from a commit to a healthy Kubernetes cluster. Docker Bake builds every image in a repo and pushes to Amazon ECR, Azure ACR or both. The rendered manifests are committed to your CD repo, and Argo CD syncs them and reports when they are healthy.

▶ **[See how it fits together — 14 slides](https://eksmanager.io/cicd.html)**

### The actions

| Action | What it does |
|---|---|
| [multicloud-build-action](https://github.com/gitopsmanager/multicloud-build-action) | Docker Bake build, pushed to ECR, ACR or both |
| [detect-cloud](https://github.com/gitopsmanager/detect-cloud) | Tells a job which cloud its runner is in |
| [k8s-load-env](https://github.com/gitopsmanager/k8s-load-env) | Picks the target cluster from your environment map |
| [k8s-deploy](https://github.com/gitopsmanager/k8s-deploy) | Renders Kustomize manifests into your CD repo and syncs Argo CD |
| [k8s-helm-deploy](https://github.com/gitopsmanager/k8s-helm-deploy) | The same, rendering Helm charts — nothing is helm-installed |
| [Auto-Commit-Squash-Merge](https://github.com/gitopsmanager/Auto-Commit-Squash-Merge) | Writes to a repo by pull request and squash merge |
| [ArgoCD-Manage-Applications](https://github.com/gitopsmanager/ArgoCD-Manage-Applications) | Creates, syncs and health-checks Argo CD applications |
| [k8s-restore-cluster](https://github.com/gitopsmanager/k8s-restore-cluster) | Rebuilds every application on a cluster from the CD repo |

Each does one job, so you can adopt one piece without taking the rest. A typical app repo needs two steps: the build, and one deploy workflow. All are MIT-licensed.

### The managed service

GitOps Manager runs the rest for you, inside your own cloud: self-hosted build runners with Docker Bake on BuildKit, lighter deploy runners, Argo CD, and the environment map of your clusters, DNS zones and registries.

- **AWS:** [EKS Manager](https://eksmanager.io) · [AWS Marketplace](https://aws.amazon.com/marketplace/pp/prodview-ne3pafhkcikaq)
- **Azure:** [AKS Manager](https://aksmanager.io)
- **About us:** [gitopsmanager.io](https://gitopsmanager.io) · [contact@gitopsmanager.io](mailto:contact@gitopsmanager.io)
