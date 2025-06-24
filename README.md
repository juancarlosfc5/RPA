# 📘 Proyecto RPA Pix Studio + FormularioUploader

## 📄 Descripción del Proyecto

Este proyecto implementa un flujo completo de automatización RPA que involucra:

1. Obtención de productos mediante una petición HTTP GET a una API.
2. Almacenamiento de los productos localmente y en Google Drive (como evidencia mediante archivo Log).
3. Registro de los productos en una base de datos PostgreSQL utilizando un archivo DDL que incluye validación para evitar duplicados.
4. Generación de un reporte en Excel y su cargue a Google Drive.
5. Envió automático de dicho reporte mediante un formulario JotForm utilizando un script en C# con Selenium WebDriver.

Este proyecto integra el uso de Pix Studio como motor principal de automatización para los pasos 1 a 3, mientras que el paso 4 se realiza mediante código en C# como se documenta en el proyecto "FormularioUploader".

---

## 🧭 Pasos para la Ejecución

1. Abrir el proyecto **RPA** en Pix Studio.
2. Dentro del proyecto, abrir el archivo **`Project`** ubicado en la carpeta `Framework`.
3. Pix Studio ejecutará las siguientes actividades:

   * Petición GET para obtener los productos.
   * Almacenamiento del log en Google Drive y local.
   * Registro de productos en base de datos usando un archivo DDL.
   * Verificación para evitar duplicados.
   * Generación de archivo Excel con los productos.
   * Subida del Excel a Google Drive.
4. Finalmente, el paso 4 se ejecuta desde el script en C# ubicado en la carpeta **`FormularioUploader`**, el cual:

   * Toma el archivo Excel generado.
   * Llena el formulario en [JotForm](https://form.jotform.com/251733906511050) de forma automática.
   * Captura una imagen como evidencia y la almacena en la carpeta `Evidencias`.

---

## ⚙️ Requisitos y Dependencias

* ✅ Pix Studio instalado y configurado correctamente.
* ✅ [.NET SDK 9.0.3](https://dotnet.microsoft.com/en-us/download/dotnet/9.0)
* ✅ [Google Chrome](https://www.google.com/chrome/) instalado.
* ✅ ChromeDriver compatible, ya incluido en: `WebDriver\bin`
* ✅ Paquetes NuGet necesarios para C#:

  ```bash
  dotnet add package Selenium.WebDriver
  dotnet add package Selenium.WebDriver.ChromeDriver
  ```
* ✅ Archivo `pix-robotics-2025-81245fbb790f` (enviado por correo) que **no debe ser publicado en GitHub** por motivos de seguridad. Debe colocarse manualmente en la carpeta:

  ```
  data/
  ```

> 📌 **Nota importante:** Si el proyecto no se ejecuta correctamente, es probable que debas reemplazar todas las rutas que comienzan con:
>
> `C:\Users\Reyes\Downloads\`
>
> Por la ruta de tu entorno local correspondiente.

---

## 🔗 Enlace del Formulario Usado

[https://form.jotform.com/251733906511050](https://form.jotform.com/251733906511050)

---

> 🧠 Este proyecto automatiza el ciclo completo de obtención, validación, almacenamiento y reporte de productos usando herramientas modernas de RPA + C#. El paso final de enviar el reporte es realizado por un script documentado en el `README.md` del subproyecto **FormularioUploader**.
