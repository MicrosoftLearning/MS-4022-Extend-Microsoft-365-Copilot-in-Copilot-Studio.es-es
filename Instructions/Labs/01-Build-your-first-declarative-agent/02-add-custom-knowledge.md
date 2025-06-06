---
lab:
  title: '1.2: Agregar conocimientos personalizados'
---

# Agregar conocimientos personalizados

En este ejercicio, actualizarás el agente declarativo que creaste en el ejercicio anterior con las instrucciones personalizadas y datos de fundamentación. En este ejercicio se supone que tienes un sitio de SharePoint con una biblioteca de documentos denominada "Products" que contiene archivos de producto de ejemplo.

Este ejercicio debería tardar aproximadamente **20** minutos en completarse.

## Antes de comenzar

Para poder comenzar este ejercicio, deberás cargar los documentos relacionados con el producto en Microsoft 365 que el agente declarativo usará como datos de fundamento. Completa los pasos siguientes para prepararte para el ejercicio.

> [!NOTE]
> Al cargar documentos en un nuevo sitio de SharePoint Online, hay un retraso antes de que los documentos se indexen y estén disponibles para que Copilot los use. Si deseas probar el agente inmediatamente, carga los documentos en un sitio **existente**. Los documentos se indexarán y estarán disponibles para su uso por parte del agente sin demora. Si decides usar un nuevo sitio de SharePoint Online, los documentos pueden tardar más tiempo en indizarse y estar disponibles para su uso por Copilot.
>
> **Las instrucciones siguientes te guían a través de la carga de los documentos en un nuevo sitio**. Si quieres usar un sitio existente, comienza con la sección etiquetada **Cargar datos de ejemplo** y usa la biblioteca existente en lugar de la biblioteca **Products**.

### Descargue los datos de ejemplo

1. En un explorador web, ve al [repositorio de GitHub](https://github.com/MicrosoftLearning/MS-4022-Extend-Microsoft-365-Copilot-in-Copilot-Studio/blob/master/Allfiles/Products.zip) del curso.
1. Selecciona el botón **Descargar archivo sin formato** para descargar **Products.zip**.

    :::image type="content" source="../media/download-github.png" alt-text="Captura de pantalla de Microsoft Edge en la que se resalta el botón Descargar archivo sin formato en GitHub.":::

1. **Abre** la carpeta descargada y **extrae todo** el contenido en una carpeta nueva en el equipo denominado `Products` al que podrás acceder más adelante.

### Crear un sitio de SharePoint

1. En un explorador web, ve a [https://www.microsoft365.com](https://www.microsoft365.com) e **inicia sesión** con la cuenta de Microsoft 365 que usas para este laboratorio.
1. En el menú de la izquierda, selecciona **Aplicaciones** (icono de cuadrícula) y, después, selecciona **SharePoint** en el catálogo de aplicaciones.
1. En el menú de la izquierda, selecciona **Crear** (icono más) y, después, selecciona **Sitio**.
1. Selecciona **Sitio de grupo** como el tipo de sitio.
1. En la página **Seleccionar una plantilla**, selecciona **Equipo estándar**.
1. En la página **Versión preliminar**, selecciona **Usar plantilla**.
1. En la página **Asignar un nombre al sitio**, escribe `Product support` y selecciona **Siguiente**.
1. En la página de configuración siguiente, cambia la **Configuración de privacidad** a **Público**.
1. Seleccione **Crear sitio**. La creación del sitio puede tardar unos minutos antes de activar el botón **Finalizar**.
1. Seleccione **Finalizar**.

### Crear una biblioteca de documentos

1. En el sitio de SharePoint **Product support**, selecciona el botón **Nuevo** en la parte superior de la página y, después, selecciona **Biblioteca de documentos**.
1. En la página **Crear una nueva biblioteca de documentos**, selecciona **Biblioteca en blanco**.
1. En el campo **Nombre**, introduce `Products` y selecciona **Crear**.

### Cargar datos de ejemplo

1. En la biblioteca **Products**, selecciona el botón **Cargar** y, después, selecciona **Archivos**.
1. Ve a la carpeta del equipo donde guardaste los archivos de ejemplo en un paso anterior.
1. Selecciona el campo **Seleccionar todo** para seleccionar todos los archivos de la carpeta Products local y, después, selecciona **Abrir** para cargarlos en SharePoint.
1. Espera a que se complete la carga. Los archivos aparecerán ahora en la biblioteca **Products** de SharePoint.

### Copiar la dirección URL de SharePoint

A continuación, copia la dirección URL directa en el sitio para usarla al configurar los conocimientos del agente.

1. En la página biblioteca **Products** de SharePoint, selecciona el icono **Configuración** de la parte superior derecha y elige **Configuración de biblioteca** y, después, **Más configuraciones de biblioteca**.

    :::image type="content" source="../media/sharepoint-library-settings.png" alt-text="Captura de pantalla de Microsoft Edge que muestra la opción de configuración de biblioteca en el menú de configuración.":::

1. Busca la propiedad **Web address**. La **dirección URL del sitio de SharePoint** es la parte de la dirección web que tiene el formato `https://DOMAIN.sharepoint.com/sites/SITE_NAME/LIBRARY_NAME`. La dirección URL debe ser `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products`.
1. **Copia** la dirección URL del sitio de SharePoint y guárdala para usarla en los próximos pasos del laboratorio.

## Configurar el agente con conocimientos personalizados

Agrega la dirección URL de SharePoint al agente como origen de conocimientos de fundamentación.

### Agregar dirección URL de SharePoint

1. En la página de información general del agente de soporte técnico del producto de Copilot Studio, selecciona **Agregar conocimientos** en la sección **Conocimientos**.

    ![Captura de pantalla de Copilot Studio en Microsoft Edge en la que se resalta el botón Agregar conocimientos para el agente de soporte técnico del producto.](../Media/product-support-add-knowledge.png)

2. En la página **Agregar conocimientos** del asistente que se abre, selecciona **SharePoint**.
3. En el cuadro de texto, pega la dirección URL de la biblioteca **Products** de SharePoint y selecciona **Agregar**. Debe tener el formato: `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products`

4. Selecciona **Agregar** en la ventana **Agregar SharePoint** y espera a que el origen de conocimientos se agregue al agente. Esto puede tardar un par de minutos.
5. Observa que la biblioteca **Products** aparece en la sección **Conocimientos** de la información general del agente.

> **Nota**: los agentes de Copilot Studio acceden a documentos en nombre del usuario. El agente solo podrá obtener respuestas y contenido de los documentos a los que tienen acceso los usuarios finales.

### Actualizar las instrucciones personalizadas

A continuación, actualiza las instrucciones del agente para describir cómo debe usar el origen de conocimientos.

1. En la página de información general del agente en Copilot Studio, selecciona **Editar** en la sección **Detalles**.
1. Actualiza el contenido del cuadro de texto **Instrucciones** a lo siguiente: `You are an agent tasked with answering questions about Contoso Electronics products. Start every response by enthusiastically thanking the user for their question or comment, then respond to their question or comment. You will use documents from the Products folder in SharePoint as your source of information. If you can't find the necessary information, you should suggest that the agent should reach out to the team responsible for further assistance. Your responses should be concise and always include a cited source.`
1. Selecciona **Guardar** en la sección **Detalles**.

## Probar el agente en Copilot Studio

Por último, prueba la capacidad del agente para usar el origen de conocimientos personalizados.

1. En el panel **Probar el agente** en la página de información general del agente en Copilot Studio, selecciona el botón **Actualizar** para actualizar el panel de pruebas y cargar los cambios más recientes del agente.
1. En el cuadro de texto de la conversación de prueba, escribe `Tell me about Eagle Air` y envía el mensaje.
1. Espera la respuesta. Observa que la respuesta contiene información sobre el dron Eagle Air. La respuesta contiene citas y referencias del documento de Eagle Air almacenado en el sitio de SharePoint.

Probemos algunas indicaciones más:

1. En el cuadro de mensaje, escribe `Recommend a product suitable for a farmer` y envía el mensaje.
1. Espera la respuesta. Observa que la respuesta contiene información sobre Eagle Air y algún contexto adicional sobre los motivos por los que se recomienda Eagle Air. La respuesta contiene citas y referencias del documento de Eagle Air almacenado en OneDrive.
1. En el cuadro de mensaje, escribe `Explain why the Eagle Air is more suitable than Contoso Quad` y envía el mensaje.
1. Espera la respuesta. Ten en cuenta que la respuesta explica con más detalle por qué es más adecuado que los agricultores usen el Eagle Air y no Contoso Quad 

Por último, vamos a probar la respuesta de reserva haciendo una pregunta que el agente no puede responder:

1. En el cuadro de mensaje, escribe `When was Mark8 released?` y envía el mensaje.
1. Espera la respuesta. Observa que la respuesta sugiere que el agente debe ponerse en contacto con el equipo responsable de obtener más ayuda, según lo definido en las instrucciones.
