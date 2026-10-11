# tablero-seguros
> Deploy app Miriam Itzel

---

## Descripción

Aplicación interactiva desarrollada con Python y Streamlit para explorar una cartera de seguros de autos y consultar indicadores técnicos. Incluye filtros para analizar distintos segmentos de la cartera y un cotizador que compara estimaciones de prima pura mediante métodos actuariales y modelos estadísticos.

## Funcionalidades

- **Filtros de cartera:** permiten seleccionar características de las pólizas para analizar diferentes segmentos.
- **Indicadores técnicos:** exposición, número de siniestros, frecuencia, severidad y prima pura.
- **Visualizaciones:** gráficas para explorar el comportamiento de la cartera.
- **Cotizador:** compara la prima pura empírica, la prima estimada mediante modelos GLM y Tweedie, y la tarifa calculada a partir de los gastos y el margen configurados.
- **Registro de cotizaciones:** integración opcional con Google Sheets para guardar y consultar cotizaciones, siempre que las credenciales y la configuración estén disponibles.

## Tecnologías utilizadas

- Python
- Streamlit
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- PyArrow
- gspread y Google Sheets para el registro de cotizaciones

## Estructura del proyecto

```text
tablero-seguros/
├── app_streamlit.py
├── datos/
│   └── datos.parquet
├── requirements.txt
├── .gitignore
└── README.md
```

La base de datos SQLite puede generarse a partir del archivo Parquet cuando se inicia la aplicación, según la lógica implementada en el código.

## Ejecutar el proyecto localmente

1. Clonar el repositorio:

   ```bash
   git clone https://github.com/MiriamItzel/tablero-seguros.git
   ```

2. Entrar a la carpeta del proyecto:

   ```bash
   cd tablero-seguros
   ```

3. Instalar las dependencias:

   ```bash
   python -m pip install -r requirements.txt
   ```

4. Ejecutar la aplicación:

   ```bash
   python -m streamlit run app_streamlit.py
   ```
5. Abrir la dirección local que indique Streamlit:

    ```bash
    http://localhost:8502
    ```

### Acceso mediante el puerto de VS Code

También se puede acceder a la aplicación mediante el enlace del puerto de VS Code, siempre que el entorno donde se ejecuta Streamlit permanezca activo:

**Liga de acceso:** [https://qpj870zc-8502.usw3.devtunnels.ms/]

Si deseas generarlo, puedes activar el túnel de VS Code siguiendo estos pasos:

1. Ejecuta el tablero en tu terminal (quedará corriendo por defecto en el puerto `8502`):

   ```bash
   streamlit run app_streamlit.py
   ```

2. En VS Code, abre el panel **PORTS** (ubicado junto a la pestaña de la TERMINAL, o a través del menú *View ➔ Open View... ➔ Ports*).

3. Haz clic en el botón **"Forward a Port"** e introduce el número `8502`.

4. Si el editor te lo solicita, inicia sesión con tu cuenta de GitHub.

5. Verás una dirección en la columna *Forwarded Address* configurada inicialmente como *Private*. Haz clic derecho sobre el puerto ➔ selecciona **Port Visibility** ➔ cámbialo a **Public**.

6. Copia esa dirección pública generada y ábrela en cualquier navegador.

*Nota: Recuerda que este puente es temporal y dejará de responder de forma automática en cuanto cierres VS Code o apagues tu computadora.*

## Aplicación publicada en Streamlit

**Tablero de Streamlit:**  
[https://tablero-seguros-avaafdaftqtyb76sc95cxm.streamlit.app/]

**Repositorio de GitHub:**  
[https://github.com/MiriamItzel/tablero-seguros.git]

## Configuración de Google Sheets

La integración con Google Sheets requiere configurar las credenciales de una cuenta de servicio y la URL de la hoja mediante *secrets* de Streamlit. No se deben publicar archivos de credenciales ni claves privadas en el repositorio.

Si la integración no está configurada, la aplicación puede mostrar un mensaje de error al intentar guardar una cotización.

## Consideraciones

Los resultados dependen de los datos disponibles, de la segmentación de la cartera y de los modelos implementados. Las primas estimadas son resultados del ejercicio académico y no constituyen por sí mismas una tarifa comercial autorizada.
