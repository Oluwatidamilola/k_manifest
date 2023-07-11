# 🚀 Setup pipeline using CircleCI, update GitHub Kubernetes manifest repo and push image on Docker

✨This repository containe the code of the kubernetes manifest files.

## 🏠 Architecture
![Architecture of the application](architecture.gif)

## 🔶 Story
- When CircleCI notices any changes in the application code, it starts executing the jobs that we have set up. There are a total of four jobs:

### 🧪 Test: 
- This job tests the code. After the test job is completed, CircleCI proceeds to the next job. 
- Note: I didn't add this job to save time. 😎

### 🏗️ Build: 
- In the build job, CircleCI pulls the base Docker images and packages our application code inside the image.

### 🪠 Push: 
- The push job pushes the newly generated images to Docker Hub with a new tag.

### 🆕 Update Manifest: 
- After the successful completion of the push job, the last job is executed, which updates the Kubernetes manifest repository with the new tag. This enables ArgoCD to detect the change and apply it to the cluster.

By following this pipeline, we ensure that our application code is thoroughly tested, built into Docker images, and deployed with the updated manifest using the GitOps approach.
