---
lab:
  title: '3.1: Crear una acción del conector'
---

# Crear una acción del conector

En este ejercicio configurarás una acción del conector para un agente declarativo en Copilot Studio. Usarás el conector "SharePoint - List folder" para recuperar una lista de archivos de la carpeta Products que contiene archivos de soporte técnico del producto.

Este ejercicio debería tardar aproximadamente **15** minutos en completarse.

## Antes de comenzar

Este ejercicio se centra en agregar acciones del conector a un agente existente. En este ejercicio se da por supuesto lo siguiente:

1. Ya has creado un agente declarativo de **soporte técnico del producto** en Copilot Studio. Si necesita instrucciones para crear un agente declarativo, consulta: [Creación de un agente declarativo](../01-Build-your-first-declarative-agent/01-create-declarative-agent.md).
1. Tiene un sitio de SharePoint titulado **Product Support** que contiene una biblioteca de documentos denominada **Products** que contiene archivos con datos relacionados con el producto de ejemplo. Para obtener instrucciones, consulta la sección titulada **Antes de comenzar** en el ejercicio: [Agregar conocimientos personalizados](../01-Build-your-first-declarative-agent/02-add-custom-knowledge.md).

## Crear una acción del conector de SharePoint

1. En el explorador web, ve a [Copilot Studio](https://www.copilotstudio.microsoft.com) en `https://www.copilotstudio.microsoft.com`.
1. En la **biblioteca**, selecciona el agente de **soporte técnico del producto**.
1. En **Acciones**, selecciona **Agregar acción**.
1. En la ventana **Agregar acción**, escribe `SharePoint` en la barra **Buscar**. Espera a que se muestren las acciones pertinentes en la ventana.
1. Busca y selecciona la acción del conector **List Folder SharePoint**.
1. La ventana modal muestra una conexión para el conector de SharePoint. Se mostrará una marca de verificación verde junto al conector cuando la conexión esté activa. Puedes seleccionar **...** para ver los detalles de la conexión.
    ![Captura de pantalla que muestra el estado de las conexiones de SharePoint](../Media/SharePoint-connection.png)
1. Selecciona **Siguiente** cuando la conexión esté activa. Se te dirige a la página **Carpeta de lista** para configurar las propiedades de la acción.
1. En el cuadro de texto **Nombre**, escribe `List product support files`.
1. En el cuadro de texto **Descripción**, escribe `List product support files available in the Products folder`.
1. Asegúrate de que la **autenticación de usuario final** esté establecida en **Autenticación de usuario**.
1. Expande la sección **entradas y salidas**.
1. Selecciona la entrada **Dirección del sitio**.
1. En el cuadro de texto **Valor**, escribe la dirección URL del sitio de SharePoint de **soporte técnico del producto** en el formato `https://DOMAIN.sharepoint.com/sites/ProductSupport` y, después, selecciona **Listo**.
1. Selecciona la entrada **identificador de archivo**.
1. Establece **¿Cómo rellenará el agente esta entrada?** en **Establecer como un valor** en la lista desplegable y, después, selecciona **Confirmar**.
1. En el cuadro de texto **Valor**, escribe `Products` y selecciona **Listo**.
1. Selecciona el botón **Agregar acción** y espera a que se agregue la acción de SharePoint al agente. La acción debe aparecer ahora en la sección **Acciones** de la página de detalles del agente.

## Configuración de la acción

1. En la sección **Acciones**, selecciona la acción **Enumerar archivos de soporte técnico del producto** para abrir su página de detalles.
1. Ve a la pestaña **Salidas**.
1. Con fines de prueba, en **Elegir cómo se mostrará el resultado de esta acción**, activa la casilla **Enviar un mensaje inmediatamente después de ejecutar la acción**. Se mostrará una opción de configuración adicional.
1. Selecciona el elemento desplegable en **¿Cómo deseas mostrar la información al usuario?** y selecciona **Crear un mensaje**. Se mostrará un cuadro de texto.
1. En el cuadro de texto **Mensaje para mostrar**, escribe `You used the SharePoint connector` y selecciona **Guardar** en la parte superior de la página.

## Modificar las instrucciones del agente

También vamos a actualizar las instrucciones del agente que proporcionan instrucciones para usar la acción del conector.

1. En la sección **Detalles** del agente de **soporte técnico del producto**, selecciona **Editar**.
1. En el cuadro de texto **Instrucciones**, agrega lo siguiente al texto de las instrucciones existentes: `When asked about available support resources, use the SharePoint connector to list the files in the Products folder.`
1. Seleccione **Guardar**.

## Probar el agente con la acción

1. Expanda el panel **Probar el agente** en el lado derecho de la página de detalles del agente.
1. Selecciona el botón **Actualizar** del panel de prueba para cargar los cambios más recientes del agente.
1. En el cuadro de mensaje, escribe `What product support files are available?` y envía el mensaje.
1. Observa que el agente responde con el mensaje "Has usado el conector de SharePoint" y, después, enumera los archivos disponibles en la carpeta Products.

Has validado que la acción del conector funciona según lo previsto en el agente.
