# **Proyecto de Despliegue con Helm, Terraform y CI/CD**

Este proyecto está diseñado para automatizar el despliegue de una aplicación en un clúster de Kubernetes (AKS) utilizando Helm, Terraform y un pipeline de CI/CD con GitHub Actions. A continuación, se explica el funcionamiento del proyecto.

---

## **Estructura del Proyecto**

my-helm-project/
├── .github/
│   └── workflows/
│       └── cicd-pipeline.yml
├── helmfile.yaml
├── environments/
│   ├── dev.yaml
│   └── stage.yaml
├── charts/
│   └── my-app/
│       ├── Chart.yaml
│       ├── values.yaml
│       ├── templates/
│       │   ├── deployment.yaml
│       │   └── service.yaml
│       └── secrets.yaml
└── terraform/
└── main.tf


---

## **Funcionamiento del Proyecto**

1. **Terraform**:
   - Define la infraestructura en Azure, incluyendo el clúster de AKS y el grupo de recursos.

2. **Helmfile**:
   - Gestiona los despliegues de Helm en diferentes entornos (dev y stage).
   - Utiliza los archivos de configuración en `environments/` para personalizar los valores por entorno.

3. **Helm**:
   - Define el chart de la aplicación (`charts/my-app/`) con plantillas para Deployment, Service y Secrets.

4. **GitHub Actions**:
   - Automatiza el proceso de CI/CD, ejecutando pruebas y despliegues cada vez que se realiza un cambio en el repositorio.

---

## **Requisitos Previos**

1. **Herramientas Necesarias**:
   - [Terraform](https://www.terraform.io/downloads.html)
   - [Helm](https://helm.sh/docs/intro/install/)
   - [Helmfile](https://github.com/roboll/helmfile)
   - [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)
   - [kubectl](https://kubernetes.io/docs/tasks/tools/)

2. **Cuenta de Azure**:
   - Acceso a una suscripción de Azure para crear recursos.

3. **Repositorio en GitHub**:
   - Un repositorio para almacenar el proyecto y ejecutar el pipeline de CI/CD.

---

