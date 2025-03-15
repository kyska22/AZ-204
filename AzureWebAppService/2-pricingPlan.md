# Explicación de conceptos clave para el examen AZ-204:

1. **Planes de App Service**:
   - Los planes de App Service definen la capacidad de los recursos (CPU, memoria, almacenamiento) que se asignan a tus aplicaciones.
   - Cada plan tiene diferentes características y precios, y debes elegir el que mejor se adapte a tus necesidades.

2. **Tipos de planes de App Service**:
   - **Plan Gratuito (Free)**: Ideal para pruebas y desarrollo inicial. Tiene limitaciones como 60 minutos de CPU por día y 1 GB de espacio en disco. No incluye un SLA.
   - **Plan Compartido (Shared)**: Ofrece más recursos que el plan gratuito (240 minutos de CPU por día), pero sigue siendo limitado. Tampoco incluye un SLA.
   - **Plan Básico (Basic)**: Diseñado para entornos de desarrollo y pruebas más serios. Ofrece más recursos (10 GB de espacio en disco) y permite hasta 3 instancias (máquinas virtuales) para escalar.
   - **Plan Estándar (Standard)** y **Premium**: Ofrecen más capacidad, escalabilidad avanzada, soporte para staging slots, y otras características avanzadas. Estos planes incluyen un SLA.

3. **Limitaciones de los planes gratuitos y compartidos**:
   - **Minutos de CPU**: Los planes gratuitos y compartidos tienen un límite diario de minutos de CPU (60 y 240, respectivamente). Esto significa que tu aplicación dejará de ejecutarse una vez que se alcance este límite.
   - **Sin SLA**: No hay garantía de tiempo de actividad para estos planes, lo que los hace inadecuados para aplicaciones críticas.

4. **Escalabilidad**:
   - Los planes básicos, estándar y premium permiten escalar verticalmente (aumentar el tamaño de las instancias) y horizontalmente (agregar más instancias).
   - Esto es crucial para aplicaciones que necesitan manejar cargas de trabajo variables o crecientes.

5. **Espacio en disco**:
   - Cada plan ofrece una cantidad específica de espacio en disco. Por ejemplo, el plan gratuito ofrece 1 GB, mientras que el plan básico ofrece 10 GB.
   - Elige un plan que se ajuste a las necesidades de almacenamiento de tu aplicación.

6. **Acuerdo de Nivel de Servicio (SLA)**:
   - Los planes básicos, estándar y premium incluyen un SLA, que garantiza un cierto nivel de disponibilidad y rendimiento.
   - Los planes gratuitos y compartidos no tienen SLA, lo que significa que no hay garantías de tiempo de actividad.

---

### Resumen:
- **Planes gratuitos y compartidos**: Ideales para pruebas y desarrollo, pero con limitaciones significativas (minutos de CPU, sin SLA).
- **Planes básicos, estándar y premium**: Ofrecen más recursos, escalabilidad y características avanzadas, adecuados para aplicaciones en producción.
- **Escalabilidad**: Los planes superiores permiten escalar vertical y horizontalmente para manejar cargas de trabajo mayores.
- **SLA**: Solo disponible en planes de pago, lo que garantiza un nivel de servicio confiable.

---
## Tabla resumen con la información sobre los planes de Azure App Service, basada en el texto que proporcionaste:

| **Plan**         | **Uso recomendado**       | **Aplicaciones permitidas** | **Espacio en disco** | **Minutos de CPU/día** | **Instancias (VM)** | **SLA**       | **Escalabilidad**       | **Notas**                                                                 |
|-------------------|---------------------------|-----------------------------|----------------------|------------------------|---------------------|---------------|-------------------------|---------------------------------------------------------------------------|
| **Gratuito (Free)** | Pruebas y desarrollo inicial | Hasta 10 aplicaciones       | 1 GB                 | 60 minutos             | No aplica           | No            | No                      | Ideal para pruebas, sin garantía de tiempo de actividad.                  |
| **Compartido (Shared)** | Desarrollo y pruebas básicas | Hasta 10 aplicaciones       | 1 GB                 | 240 minutos            | No aplica           | No            | No                      | Más minutos de CPU que el plan gratuito, pero aún limitado.               |
| **Básico (Basic)** | Desarrollo y pruebas avanzadas | Aplicaciones ilimitadas     | 10 GB                | Ilimitado              | Hasta 3 instancias  | Sí            | Escalabilidad manual    | Entorno dedicado, ideal para pruebas más serias y pequeñas cargas de trabajo. |
| **Estándar (Standard)** | Producción pequeña a mediana | Aplicaciones ilimitadas     | 50 GB                | Ilimitado              | Hasta 10 instancias | Sí            | Escalabilidad automática | Soporta staging slots, despliegues Blue-Green, y mayor capacidad.         |
| **Premium (Premium)** | Producción crítica y de alto rendimiento | Aplicaciones ilimitadas     | Hasta 1 TB           | Ilimitado              | Hasta 20 instancias | Sí            | Escalabilidad avanzada  | Máxima capacidad, aislamiento de red, y soporte para cargas de trabajo intensivas. |

---

### Explicación de la tabla:

1. **Plan Gratuito (Free)**:
   - **Uso**: Ideal para pruebas iniciales y desarrollo.
   - **Limitaciones**: Solo 60 minutos de CPU al día y 1 GB de espacio en disco.
   - **Sin SLA**: No hay garantía de tiempo de actividad.

2. **Plan Compartido (Shared)**:
   - **Uso**: Desarrollo y pruebas básicas.
   - **Limitaciones**: 240 minutos de CPU al día y 1 GB de espacio en disco.
   - **Sin SLA**: No es adecuado para aplicaciones críticas.

3. **Plan Básico (Basic)**:
   - **Uso**: Desarrollo y pruebas avanzadas.
   - **Recursos**: 10 GB de espacio en disco y hasta 3 instancias.
   - **Con SLA**: Garantía de tiempo de actividad.
   - **Escalabilidad**: Manual, ideal para pequeñas cargas de trabajo.

4. **Plan Estándar (Standard)**:
   - **Uso**: Producción pequeña a mediana.
   - **Recursos**: 50 GB de espacio en disco y hasta 10 instancias.
   - **Con SLA**: Garantía de tiempo de actividad.
   - **Escalabilidad**: Automática, soporta staging slots y despliegues Blue-Green.

5. **Plan Premium (Premium)**:
   - **Uso**: Producción crítica y de alto rendimiento.
   - **Recursos**: Hasta 1 TB de espacio en disco y hasta 20 instancias.
   - **Con SLA**: Máxima garantía de tiempo de actividad.
   - **Escalabilidad**: Avanzada, con aislamiento de red y soporte para cargas de trabajo intensivas.
