# Grade Submission Portal (Kubernetes Deployment on Docker Desktop)

This project demonstrates deploying a **full-stack Grade Submission application** on a local **Kubernetes cluster (Docker Desktop)**.  
It uses **sidecar containers for health checking**, resource limits for stability, and port-forwarding for local access.

---

##  Features
- Backend API (`grade-submission-api`) with a sidecar health-checker.  
- Frontend Portal (`grade-submission-portal`) with a sidecar health-checker.  
- Kubernetes resource **requests and limits** for CPU/Memory.  
- Localhost **port-forwarding** to access services without cloud deployment.  
- **Log streaming** to verify pod health and application status.  

---

##  Deploying Pods
- kubectl apply -f backend-pod.yaml
- kubectl apply -f frontend-pod.yaml

##  Port Forwarding
- kubectl port-forward grade-submission-api 3000:3000 (Backend API)
- kubectl port-forward grade-submission-portal 9090:3000 (Frontend Portal)

## Log Streaming
# Backend containers
- kubectl logs -f grade-submission-api -c grade-submission-api
- kubectl logs -f grade-submission-api -c grade-submission-api-health-checker

# Frontend containers
- kubectl logs -f grade-submission-portal -c grade-submission-portal
- kubectl logs -f grade-submission-portal -c grade-submission-portal-health-checker


## Next tasks
- Adding Kubernetes Services for stable networking
- Deploying using Deployments(for autoscaling and autohealing purposes)

