# Urban-Scooter-Final-project

## Resumen Ejecutivo
Se realizó una evaluación integral del sistema Urban Scooter, incluyendo aplicación web y móvil, utilizando diversas técnicas de testing para garantizar la calidad del software. El proyecto abarcó pruebas exhaustivas y documentación detallada de errores.

<a href="https://docs.google.com/spreadsheets/d/1ti2nSX1ytBepAQoZU5lgWsU-mRykalO4/edit?usp=sharing&ouid=103258639782325772763&rtpof=true&sd=true" target="_blank">
 📊​ Archivo original 
</a>

## Técnicas y Herramientas Utilizadas
1. Mapa mental
2. Listas de comprobación
3. Partición de clases de equivalencia
4. Informes de errores en Jira
5. Pruebas multinavegador
6. Pruebas multiplataforma
7. Diseño de casos de prueba
8. Pruebas de funcionalidad
9. Pruebas de interfaz
10. Pruebas de API
11. SQL y PostgreSQL
12. Línea de comandos
13. Protocolo SSH

## Mapa mental

<a href="https://github.com/LeyvaPilar/Urban-Scooter-final-project/blob/main/Pilar-Leyva-Proyecto%20Final.png?raw=true" target="_blank">
  <img src="https://github.com/LeyvaPilar/Urban-Scooter-final-project/blob/main/Pilar-Leyva-Proyecto%20Final.png?raw=true" alt="Mapa mental">
</a>


## Pruebas multinavegador

<a href="https://github.com/LeyvaPilar/Urban-Scooter-final-project/blob/main/Android_emulator.png" target="_blank">
  <img src="https://github.com/LeyvaPilar/Urban-Scooter-final-project/blob/main/Android_emulator.png?raw=true" alt="Pruebas multinavegador">
</a>

## Alcance de Pruebas Realizadas

### Entornos Evaluados
- **Web**: Opera 71+, Chrome 85+ (1920x1080, 1280x720)
- **Móvil**: Android 9.0 (Emulador Android Studio)
- **API**: Pruebas vía Postman

### Funcionalidades Evaluadas
- Sistema de pedidos y seguimiento
- Gestión de usuarios y repartidores
- Sistema de notificaciones push
- Funcionalidad offline
- Validación de datos
- Integración con base de datos

## Hallazgos Principales

### Problemas Críticos
1. **Sistema de Notificaciones**
   - Fallos en la entrega de notificaciones push
   - Problemas de temporización

2. **Validación de Datos**
   - Inconsistencias en campos especiales
   - Errores en límites de caracteres

3. **Compatibilidad**
   - Problemas en resoluciones específicas
   - Inconsistencias entre navegadores

4. **Gestión de Pedidos**
   - Errores en cancelación
   - Problemas con estados de entrega

### Aspectos Positivos
- Funcionalidad offline robusta
- API bien estructurada
- Sistema de seguimiento efectivo
- Interfaz intuitiva

## Documentación de Errores
- 60 tickets creados en Jira
- Clasificación por severidad
- Evidencias y pasos de reproducción
- Seguimiento de resolución




# Lista de Comprobación de Estado del Pedido

| Descripción | Estado Opera 71+ | Estado Chrome 85+ | 
|-------------|------------------|-------------------|
| Estado del pedido visible | Aprobado | Aprobado |
| Número de pedido correcto | Aprobado | Aprobado |
| Ajuste de texto multilínea | Aprobado | Aprobado |
| Cadena de estado del pedido | Aprobado | Aprobado |
| Mensaje de error - pedido no existe | Aprobado | Aprobado |
| Estados de pantalla activos | Aprobado | Aprobado |
| El scooter en almacén | Aprobado | Aprobado |
| Repartidor en camino | Aprobado | Aprobado |
| El servicio de entrega llegó | No aprobado | No aprobado |
| Navegadores soportados | No aprobado | Bloqueado |
| Pedido cancelado se elimina | No aprobado | No aprobado |
| Hora de entrega fija | No aprobado | No reportado |

**Interpretación**
- La mayoría de las funcionalidades básicas están aprobadas en ambos navegadores
- Se identifican problemas críticos en:
  1. Servicio de entrega
  2. Compatibilidad de navegadores
  3. Gestión de pedidos cancelados
  4. Programación de entregas

# Validación de Datos

| Campo | Validación | Estado Opera | Estado Chrome |
|-------|------------|--------------|---------------|
| Nombre | 2-15 caracteres | Aprobado | Aprobado |
| Apellido | 2-15 caracteres | Aprobado | Aprobado |
| Dirección | 5-50 caracteres | No aprobado | No aprobado |
| Teléfono | 10-12 dígitos | Aprobado | Aprobado |
| Estación Metro | Seleccionable | Bloqueado | No aprobado |
| Color Scooter | Obligatorio | Bloqueado | No aprobado |
| Comentario | Máx 24 caracteres | Bloqueado | No aprobado |

**Interpretación**
- Validación robusta en campos básicos (nombre, apellido, teléfono)
- Problemas significativos en:
  1. Validación de direcciones
  2. Selección de estaciones
  3. Selección de color
  4. Gestión de comentarios

# Casos de Prueba

| ID | Caso de Prueba | Resultado | Estado |
|----|----------------|-----------|---------|
| 1-10 | Notificaciones Push | No Aprobado | Crítico |
| 11-12 | Contenido Notificaciones | No Aprobado | Crítico |
| 13-19 | Funcionalidad Offline | Aprobado | Estable |
| 20-30 | Gestión de Pedidos | Mixto | En Revisión |
| 31-39 | Estados de Pedido | No Aprobado | Crítico |

**Interpretación**
- Problemas significativos en el sistema de notificaciones
- Buen manejo de funcionamiento offline
- Gestión de pedidos requiere mejoras
- Sistema de estados necesita revisión completa

# Pruebas de API

| Endpoint | Método | Resultado Esperado | Estado |
|----------|---------|-------------------|---------|
| /api/v1/courier | POST | 201 Created | Mixto |
| /api/v1/orders/track | GET | 200 OK | Aprobado |
| /api/v1/courier/:id | DELETE | 200 OK | Aprobado |
| /api/v1/stations/search | GET | 200 OK | Aprobado |

**Interpretación**
- La API muestra consistencia en operaciones básicas
- Problemas identificados en:
  1. Validación de entrada en creación de courier
  2. Manejo de caracteres especiales
  3. Validación de contraseñas
  4. Respuestas de error no estandarizadas

## Recomendaciones Generales:

1. **Prioridad Alta:**
   - Corregir sistema de notificaciones push
   - Estandarizar validación de datos
   - Resolver problemas de compatibilidad de navegadores

2. **Prioridad Media:**
   - Mejorar gestión de estados de pedido
   - Implementar validación más robusta en API
   - Optimizar manejo de errores

3. **Prioridad Baja:**
   - Refinar interfaz de usuario
   - Mejorar sistema de comentarios
   - Ampliar compatibilidad de navegadores
  

## Conclusión
La evaluación reveló una estructura básica sólida con áreas específicas de mejora. La implementación de las recomendaciones permitirá alcanzar un nivel óptimo de calidad en el sistema.


