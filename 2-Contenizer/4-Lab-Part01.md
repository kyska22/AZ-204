### Laboratorios prácticos con contenedores en Azure :

Muy bien, ahora hablemos sobre los laboratorios de contenedores. Para acceder a estos laboratorios, estoy utilizando **Wiz Labs** como entorno de pruebas para experimentar y demostrar las capacidades de los contenedores en Microsoft Azure.  

Con el **entorno Sandbox** proporcionado por Wiz Labs, podemos trabajar con:  
- **Azure Container Instances (ACI)** (nuestro foco principal)  
- **Kubernetes (AKS)**  
- **Registros de contenedores**  
- **Configuración de redes**  

Al desplazarnos hacia abajo, veremos una variedad de servicios disponibles para practicar.  

---

### **Paso 1: Configuración del entorno Sandbox**  
1. **Iniciar el Sandbox**:  
   - Ejecuto el Sandbox por **1 hora** y hago clic en *"Create Sandbox Environment"*.  
   - Acepto los términos y hago clic en *"Start Sandbox"*.  
   - La carga tarda unos minutos (pauso el video mientras se prepara).  

2. **Acceder al Sandbox**:  
   - Una vez listo, tengo **55 minutos** para explorar.  
   - Hago clic en *"Open Console"*, que me redirige a **portal.azure.com**.  
   - Si no estás autenticado, el sistema solicitará credenciales (usuario y contraseña proporcionados por Wiz Labs).  

---

### **Paso 2: Creación de un contenedor**  
#### **Método 1: Interfaz gráfica (Azure Portal)**  
- Navegar a **Container Instances** > *"Create"* y seguir el asistente.  

#### **Método 2: Azure CLI (recomendado para producción)**  
1. **Abrir Cloud Shell**:  
   - Seleccionar **Bash** (no usar valores predeterminados en Wiz Labs).  
   - Configurar **Advanced Settings**:  
     - Usar un **grupo de recursos existente** (ej: `...6613`).  
     - Crear una **cuenta de almacenamiento nueva** (nombre único, ej: `WizLabsACCNA`).  
     - Habilitar **File Share**.  

2. **Comandos clave en Azure CLI**:  
   - Listar grupos de recursos:  
     ```bash
     az group list --output table
     ```  
   - Crear un contenedor:  
     ```bash
     az container create \
       --resource-group "NombreDelGrupoDeRecursos" \
       --name "web-app-container-345" \
       --image "mcr.microsoft.com/azuredocs/aci-helloworld" \
       --ports 80 443 \
       --dns-name-label "web-app-container-345" \
       --location "eastus"
     ```  
   - **Explicación de parámetros**:  
     - `--image`: Imagen pública de Microsoft (contiene una app web de ejemplo).  
     - `--dns-name-label`: Asigna un nombre DNS público al contenedor.  
     - `--location`: Región de Azure donde se despliega.  

3. **Errores comunes**:  
   - Sintaxis incorrecta (ej: `--dns-name-label` vs `--dns-hyen-label`).  
   - Grupos de recursos mal escritos (usar `az group list` para verificarlos).  

---

### **Explicación para el examen AZ-204**  
- **Dominio clave**: **Compute Solutions (20-25%)**  
  - **Azure Container Instances (ACI)**:  
    - Servicio **serverless** para ejecutar contenedores sin gestionar infraestructura.  
    - Ideal para **tareas efímeras** o **pruebas rápidas**.  
  - **Diferencia con AKS**:  
    - **ACI**: Sin orquestación.  
    - **AKS**: Para clústeres Kubernetes complejos.  

- **Pregunta típica**:  
  *"¿Qué comando de Azure CLI usarías para crear un contenedor con una imagen pública en el puerto 80?"*  
  **Respuesta**:  
  ```bash
  az container create --resource-group myRG --name myContainer --image mcr.microsoft.com/azuredocs/aci-helloworld --ports 80
  ```  

---

### **Esquema textual del proceso**  
```
Laboratorio con Wiz Labs  
│  
├── **1. Configuración inicial**:  
│   ├── Sandbox de 1 hora  
│   └── Acceso a Azure Portal  
│  
├── **2. Creación de contenedores**:  
│   ├── Método GUI (Azure Portal)  
│   └── Método CLI (comandos `az container`)  
│  
├── **3. Comandos clave**:  
│   ├── `az group list`  
│   ├── `az container create`  
│   └── Parámetros: --image, --ports, --dns-name-label  
│  
└── **4. Para el AZ-204**:  
    ├── Enfoque en ACI vs AKS  
    └── Sintaxis correcta de Azure CLI  
```  

**Conclusión**: Este laboratorio te prepara para trabajar con contenedores en Azure, un tema esencial para el AZ-204. ¡Practica estos comandos y conceptos para dominarlos! 😊  
