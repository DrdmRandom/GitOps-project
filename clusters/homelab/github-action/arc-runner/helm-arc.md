# ADD Arc to help repo
helm repo add actions-runner-controller https://actions-runner-controller.github.io/actions-runner-controller

# Update Repo
helm repo update

# installing arc using helm
helm install actions-runner-controller \
    actions-runner-controller/actions-runner-controller \
    --create-namespace \
    --namespace arc-systems \
    --set githubWebhookServer.enabled=false \
    --set syncSecret.enabled=false

#Verify it run
kubectl get pods -n arc-systems
