# Deploy HipsterShop on example-foundations

## Instructions

1. Set necessary variables as env vars or tfvars file. These will be outputs (TODO:example-foundation) after spinning up a project.
1. tf init, plan and apply
1. Run the command `gcloud compute ssh ... ` given by the output `bastion_ssh` in terminal window. This will open an ssh tunnel.
1. In a seperate terminal window run `gcloud container clusters ... ` given by the output `connect_svpc_cluster_internal`. This will generate the kubeconfig.
1. Run command `HTTPS_PROXY=localhost:8888 kubectl get pods --all-namespaces` given by the output `example_kubectl_command` to verify the setup. This should list all pods across all ns.
1. Run `./deploy.sh` to deploy HipsterShop.
1. Run `HTTPS_PROXY=localhost:8888 kubectl get svc frontend-external` and wait till an external ip address has been assigned.
