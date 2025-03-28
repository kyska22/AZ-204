### Gestión y acceso a contenedores en Azure Container Instances (ACI)  

"Perfecto, nuestro contenedor ya está listo. He limpiado la pantalla para mostrarles cómo **listar y gestionar contenedores** desde cero.  

#### **1. Listar contenedores con Azure CLI**  
- **Comando básico**:  
  ```bash
  az container list
  ```  
  Muestra **todos los contenedores** en la suscripción.  

- **Filtrar por grupo de recursos**:  
  ```bash
  az container show --resource-group "NombreDelGrupo"
  ```  
  Ejemplo (usando el grupo de recursos del laboratorio):  
  ```bash
  az container show --resource-group "WizLabs-RG-6613"
  ```  

- **Filtrar por nombre de contenedor**:  
  ```bash
  az container show --resource-group "WizLabs-RG-6613" --name "web-app-container-345"
  ```  

- **Cambiar formato de salida**:  
  Para ver los resultados en **tabla** (más legible):  
  ```bash
  az container list --output table
  ```  

---

#### **2. Acceder al contenedor desplegado**  
Nuestro contenedor está:  
- **Expuesto en el puerto 80**.  
- **Asignado a una IP pública**.  

**Pasos para probarlo**:  
1. Copiar la **IP pública** o **URL del DNS** (mostrada en la salida del comando `az container show`).  
2. Pegarla en un navegador web.  
   - Ejemplo de URL generada:  
     ```
     http://web-app-container-345.eastus.azurecontainer.io
     ```  
3. Verificar que la aplicación (en este caso, `aci-helloworld`) se muestre correctamente.  

**Nota**:  
- El **nombre DNS** se definió durante la creación con `--dns-name-label`.  
- Si tienes un dominio propio, puedes configurar un **registro CNAME** en tu DNS para apuntar a esta URL.  

---

#### **3. Origen de las imágenes de contenedor**  
En este ejemplo usamos una imagen pública de Microsoft:  
```bash
mcr.microsoft.com/azuredocs/aci-helloworld
```  
Pero puedes usar imágenes de:  
- **Docker Hub** (ej: `docker.io/nginx`).  
- **Azure Container Registry (ACR)**.  
- Otros repositorios privados.  

---

### **Explicación para el examen AZ-204**  
- **Dominio clave**: **Compute Solutions (20-25%)**.  
  - **Azure Container Instances (ACI)**:  
    - **Ventaja principal**: Despliegue rápido sin gestión de infraestructura.  
    - **Caso de uso típico**: Pruebas, aplicaciones efímeras o microservicios ligeros.  

- **Pregunta frecuente**:  
  *"¿Qué comando de Azure CLI usarías para ver los detalles de un contenedor específico en un grupo de recursos?"*  
  **Respuesta**:  
  ```bash
  az container show --resource-group MyRG --name MyContainer
  ```  

- **Diferencias clave**:  
  | **Concepto**               | **Descripción**                                                                 |  
  |----------------------------|-------------------------------------------------------------------------------|  
  | `az container list`        | Lista todos los contenedores en la suscripción.                               |  
  | `--dns-name-label`         | Asigna un nombre DNS público al contenedor (ej: `mi-contenedor.region.azurecontainer.io`). |  
  | **Puertos**                | ACI expone automáticamente los puertos definidos (ej: 80 para HTTP).          |  

---

### **Esquema textual del proceso**  
```
Gestión de contenedores en ACI  
│  
├── **1. Comandos Azure CLI**:  
│   ├── Listar: `az container list`  
│   ├── Filtrar: `az container show --resource-group X --name Y`  
│   └── Formato: `--output table`  
│  
├── **2. Acceso al contenedor**:  
│   ├── IP pública o URL DNS  
│   └── Configuración opcional de DNS personalizado  
│  
└── **3. Para el AZ-204**:  
    ├── Enfoque en ACI como solución serverless  
    └── Sintaxis CLI y casos de uso prácticos  
```  

**Conclusión**: Con ACI, puedes desplegar y gestionar contenedores en minutos, integrando IPs públicas y DNS sin configuración compleja. ¡Esencial para el AZ-204! 😊  
