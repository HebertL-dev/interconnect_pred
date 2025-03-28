# 📊 Predicción de Tasa de Cancelación de Clientes - Interconnect

## 📌 Descripción del Proyecto

El operador de telecomunicaciones **Interconnect** busca predecir la **tasa de cancelación de clientes** con el objetivo de ofrecer códigos promocionales y planes especiales a quienes tienen mayor probabilidad de abandonar el servicio. Para ello, se analizarán datos recopilados por el equipo de marketing, que incluyen información personal, detalles de los planes y contratos.

## 🛠️ Servicios de Interconnect

Interconnect ofrece dos servicios principales:

1. **Teléfono Fijo:** Con opción de conexión a múltiples líneas simultáneamente.
2. **Internet:** A través de dos tecnologías:
   - **DSL** (*Línea de abonado digital*).
   - **Fibra óptica**.

### Otros servicios adicionales:

- **Seguridad en Internet:**
  - *ProtecciónDeDispositivo*: Software antivirus.
  - *SeguridadEnLínea*: Bloqueador de sitios web maliciosos.
- **Soporte Técnico**: Línea de asistencia para resolver problemas técnicos.
- **BackupOnline**: Almacenamiento en la nube y respaldo de datos.
- **Streaming**:
  - *StreamingTV*: Servicio de televisión.
  - *StreamingPelículas*: Acceso a un catálogo de películas.

Los clientes pueden elegir entre un **pago mensual** o **contratos de 1 o 2 años**, con múltiples opciones de pago y facturación electrónica.

## 📁 Descripción de los Datos

El análisis se basa en cuatro conjuntos de datos principales, identificados por el campo `customerID`, que es un identificador único para cada cliente.

1. **contract.csv**: Información relacionada con los contratos.
2. **personal.csv**: Datos personales de los clientes.
3. **internet.csv**: Información sobre los servicios de Internet.
4. **phone.csv**: Información sobre los servicios telefónicos.

> **Nota:** La información del contrato está actualizada a partir del **1 de febrero de 2020**.

## 📊 Objetivo del Proyecto

- Predecir qué clientes tienen mayor probabilidad de cancelar el servicio.
- Desarrollar un modelo de machine learning para identificar patrones de cancelación.
- Implementar estrategias de retención mediante promociones personalizadas.

## 📂 Acceso a los Datos

Puedes descargar el conjunto de datos en el siguiente enlace:

🔗 [final_provider.zip](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/94210e31-fd3d-451b-a350-4a8476756413/final_provider.zip)

Los datos también están disponibles en la carpeta: `/datasets/final_provider/`

## 🚀 Tecnologías Utilizadas

- Python (Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn)
- Jupyter Notebooks
- Machine Learning
- Análisis Exploratorio de Datos (EDA)

## 📜 Código de Ejemplo

```python
import pandas as pd

# Cargar los datos
contract = pd.read_csv('datasets/final_provider/contract.csv')
personal = pd.read_csv('datasets/final_provider/personal.csv')
internet = pd.read_csv('datasets/final_provider/internet.csv')
phone = pd.read_csv('datasets/final_provider/phone.csv')

# Unir los DataFrames
data = contract.merge(personal, on='customerID').merge(internet, on='customerID', how='left').merge(phone, on='customerID', how='left')

# Vista previa de los datos
print(data.head())
