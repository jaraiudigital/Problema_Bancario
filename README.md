# 🏦 Banco de Colombia - Simulación de Cajeros Bancarios



## 📋 Descripción del Proyecto

Este proyecto realiza una **simulación de eventos discretos** para analizar el desempeño de los cajeros del Banco de Colombia durante operaciones de **retiros** y **pagos/consignaciones**. El banco dispone de **3 cajeros** y debe decidir la mejor asignación entre retiros y pagos para minimizar los tiempos de espera y maximizar la atención al cliente.

### 🎯 Objetivos

- Evaluar dos configuraciones de asignación de cajeros:
  - **Configuración 1:** 1 caja para retiros + 2 cajas para pagos
  - **Configuración 2:** 2 cajas para retiros + 1 caja para pagos
- Calcular métricas de rendimiento (tiempos de espera, ocupación, usuarios atendidos)
- Determinar si se necesita un cuarto cajero
- Proporcionar una recomendación basada en datos

## 📊 Datos de Entrada

### Tabla 1: Tiempos de Servicio y Llegada (distribución exponencial)

| Acción | Tipo Usuario | Servicio (min) | Llegada (min) |
|--------|--------------|----------------|---------------|
| Retiro | Rápido | 1 | 1 |
| Retiro | Normal | 2 | 2 |
| Retiro | Lento | 3 | 3 |
| Retiro | Muy lento | 4 | 3 |
| Pago | Rápido | 3 | 1 |
| Pago | Normal | 3 | 2 |
| Pago | Lento | 5 | 3 |
| Pago | Muy lento | 7 | 4 |

### Tabla 2: Probabilidades por Tipo de Usuario

| Acción | Tipo Usuario | Probabilidad |
|--------|--------------|--------------|
| Retiro | Rápido | 0.23 |
| Retiro | Normal | 0.40 |
| Retiro | Lento | 0.17 |
| Retiro | Muy lento | 0.20 |
| Pago | Rápido | 0.10 |
| Pago | Normal | 0.20 |
| Pago | Lento | 0.30 |
| Pago | Muy lento | 0.40 |

**Distribución de acciones:**
- 70% de los usuarios → Retiros
- 30% de los usuarios → Pagos/Consignaciones

## 🚀 Características de la Simulación

- **Modelo de colas:** M/M/1 (cajeros independientes)
- **Horario de operación:** 8 horas/día (480 minutos)
- **Número de réplicas:** 10 días simulados
- **Métricas calculadas:**
  - Usuarios atendidos por día
  - Tiempo de espera promedio
  - Ocupación de cada cajero (%)
  - Distribución de usuarios por tipo
  - Tiempo de servicio por cajero
📈 Resultados Esperados
Métricas Comparativas
Métrica	Configuración 1 (1R,2P)	Configuración 2 (2R,1P)
Usuarios/día	~460	~420
Tiempo espera (min)	~2.5	~3.8
Ocupación (%)	~85%	~90%

Visualizaciones Generadas
Gráfico de Comparación de Métricas
Barras comparativas con barras de error
Comparación cajero por cajero

Evolución por Réplica

Líneas de tendencia para 10 réplicas

Visualización de estabilidad del modelo

Distribución de Usuarios

Boxplots por tipo de usuario

Comparación entre configuraciones

📊 Interpretación de Resultados
Configuración Recomendada: 1 caja para retiros + 2 cajas para pagos
Justificación:

✅ Menor tiempo de espera para el 70% de usuarios (retiros)

✅ Mayor número de usuarios atendidos por día

✅ Mejor balance de carga entre cajeros

✅ Los pagos (más lentos) tienen más capacidad

¿Se necesita un cuarto cajero?
Si la ocupación promedio supera el 80%, se recomienda agregar un cuarto cajero. En ambas configuraciones la ocupación supera este umbral, por lo que se sugiere:

Recomendación a largo plazo: Ampliar a 4 cajeros con asignación 2 retiros + 2 pagos

Licencia
Este proyecto está bajo la Licencia MIT - ver el archivo LICENSE para más detalles.

Autor: Jorge Jaramillo - Johan Orrego


