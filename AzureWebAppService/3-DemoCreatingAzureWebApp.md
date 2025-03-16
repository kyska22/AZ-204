# **Esquema 1: Pasos para crear una Azure Web App**

1. **Iniciar la creación de un recurso**:
   - Ir a "Agregar un nuevo recurso" en Azure Portal.
   - Seleccionar "Web App" en la sección "Popular".

2. **Configurar detalles básicos**:
   - Elegir la **suscripción** y el **grupo de recursos**.
   - Asignar un **nombre único** para la Web App.

3. **Configurar la publicación**:
   - Dejar la opción "Publicar" como **Código** (Code).

4. **Seleccionar el entorno de ejecución**:
   - Elegir el **Runtime Stack** (pila de ejecución), por ejemplo, **ASP.NET V4.7**.

5. **Elegir la región**:
   - Seleccionar una región, por ejemplo, **Centro de EE. UU.** (Central US).

6. **Configurar el App Service Plan**:
   - Azure creará automáticamente un **App Service Plan** en la misma región.
   - Revisar el **SKU y tamaño** asignado (por ejemplo, **Standard S1**).
   - Cambiar el tamaño del plan si es necesario (por ejemplo, a un plan **Básico**).

7. **Revisar características del plan**:
   - Ver las **características incluidas** y el **hardware** del plan seleccionado.
   - Elegir un plan adecuado (por ejemplo, **Basic App Service Plan**).

8. **Configurar monitoreo**:
   - Decidir si habilitar **Application Insights** (en este caso, no se habilita).

9. **Agregar etiquetas (opcional)**:
   - Dejar las etiquetas sin cambios.

10. **Revisar y crear**:
    - Verificar la configuración y hacer clic en **Crear**.

11. **Esperar la creación**:
    - La creación de la Web App y el App Service Plan puede tomar de **2 a 4 minutos**.

12. **Verificar la Web App creada**:
    - Una vez creada, revisar los detalles en la sección **Descripción general**:
      - **URL** de la aplicación.
      - **Estado** de la Web App (en ejecución, detenida, etc.).
      - Opciones para **detener**, **reiniciar** o **eliminar** la Web App.

13. **Acceder a la aplicación**:
    - Abrir la **URL** en una nueva pestaña para ver la página de inicio de la aplicación de muestra.

---

# **Esquema 2: Recursos y aplicaciones utilizados (gráfico textual)**

```
Azure Portal
│
├── **Nuevo recurso**
│   └── **Web App** (Aplicación web)
│       ├── **Suscripción**: (Nombre de la suscripción)
│       ├── **Grupo de recursos**: (Nombre del grupo de recursos)
│       ├── **Nombre de la Web App**: (Nombre único)
│       ├── **Publicar**: Código (Code)
│       ├── **Runtime Stack**: ASP.NET V4.7
│       ├── **Región**: Centro de EE. UU. (Central US)
│       └── **App Service Plan**
│           ├── **SKU y tamaño**: Standard S1 (recomendado)
│           ├── **Opciones de plan**:
│           │   ├── Free (60 minutos/día)
│           │   ├── Shared (240 minutos/día)
│           │   └── Basic (sin límites de tiempo)
│           └── **Características incluidas**: (Dependen del plan)
│
├── **Monitoreo**
│   └── **Application Insights**: No habilitado
│
├── **Etiquetas**: Sin cambios
│
└── **Revisar y crear**
    └── **Recursos creados**:
        ├── **Azure Web App**
        └── **App Service Plan**
```

---

### **Explicación del gráfico textual**:

1. **Azure Portal**: Es la interfaz desde donde se gestionan todos los recursos de Azure.
2. **Web App**: El recurso principal que se está creando.
3. **App Service Plan**: El plan que define la capacidad y características de la Web App.
4. **Runtime Stack**: El entorno de ejecución seleccionado (en este caso, ASP.NET V4.7).
5. **SKU y tamaño**: Define el nivel de servicio y el costo asociado (por ejemplo, Standard S1).
6. **Application Insights**: Herramienta de monitoreo que no se habilita en este caso.
7. **Recursos creados**: Al finalizar, se crean dos recursos: la Web App y el App Service Plan.
