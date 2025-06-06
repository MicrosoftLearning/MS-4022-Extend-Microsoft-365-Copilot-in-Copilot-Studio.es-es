---
lab:
  title: '2.1: Crear una acción de solicitud'
---

# Creación de una acción de solicitud

En este ejercicio crearás una acción de solicitud, probarás la indicación en Copilot Studio y también en el agente de Copilot. Crearás una acción de solicitud que ayude a los usuarios a convertir sus nuevas ideas en presentaciones de marketing organizadas que siguen un formato y directrices específicos.

Este ejercicio debería tardar aproximadamente **15** minutos en completarse.

## Crear una acción de solicitud en Copilot Studio

1. Abre Copilot Studio en el explorador web; para ello, ve a [Copilot Studio](https://copilotstudio.microsoft.com) en `https://copilotstudio.microsoft.com`.
1. Selecciona **Biblioteca** en el panel de navegación izquierdo.
1. Selecciona **Agregar nuevo** y, después, **Indicación**. Se abre el asistente para **agregar una acción de solicitud**.
1. En el campo **Nombre de acción**, escribe `Create a Contoso Marketing Pitch`.
1. En el campo **Descripción**, escribe `Create a marketing pitch that follows Contoso guidelines` y selecciona **Siguiente**. Se te dirigirá a la página **Crear indicación**.
1. En el cuadro de texto **Instrucciones**, escribe `Create a marketing pitch for a product based on a `.
1. Coloca el cursor al final de la frase que escribiste y selecciona **Agregar contenido**
1. Selecciona **Texto**.
1. En el campo **Nombre**, escriba `draft`.
1. En el campo **Datos de ejemplo**, escribe `The Mighty Mechanical Pencil is new, exciting, and useful. It's not only the first of its kind pencil, but it's fun to use.` y selecciona **Cerrar**.

    ![Captura de pantalla de la interfaz de usuario del generador de indicaciones en Copilot Studio en la que se muestra una variable de entrada configurada con el nombre "draft".](../Media/prompt-action-input.png)

## Probar y mejorar la indicación

1. Selecciona **Probar** encima del cuadro de instrucciones para probar la indicación con los datos de ejemplo que proporcionaste.
1. Ver la salida de la serie de pruebas

Vamos a mejorar la indicación para crear una salida más estructurada y coherente.

1. En el cuadro de texto **Instrucciones**, agrega lo siguiente a las instrucciones existentes para modificar la indicación:

    ```The pitch should follow the following Contoso guidelines:
       - Start with a brief hook
       - Describe unique value proposition
       - End with a call-to-action
       - Use an exciting and influential tone
    ```

1. Vuelve a seleccionar **Probar** para volver a probar la indicación.
1. Observa cómo difiere la respuesta.
1. Seleccione **Guardar**.

## Configurar y publicar la acción

1. En la página **Seleccionar parámetros de acción**, proporciona la siguiente **descripción** para la variable de entrada `draft`: `initial draft of the marketing pitch`.
1. Proporciona la siguiente **descripción** de la variable de salida `text`: `Final marketing pitch that adheres to Contoso guidelines`.
1. Seleccione **Siguiente**.
1. Asegúrate de que has escrito los detalles correctamente y selecciona **Publicar**.
1. Espera unos instantes mientras se guarda y publica la acción.
1. La acción ya está disponible en la biblioteca. Seleccione **Guardar y cerrar**.

   > **Nota**: la nueva acción de solicitud puede tardar varios minutos o más en aparecer en las secciones **Destacados** o **Biblioteca** de la página **Agregar acción** de un agente.

## (Opcional) Agregar una acción de solicitud a un agente

Si has completado el laboratorio anterior y has creado un agente declarativo, puedes agregar esta acción al agente y actualizar sus instrucciones para hacer referencia a la acción.

### Agregar la acción

1. En la **Biblioteca**, selecciona el agente declarativo al que deseas agregar la acción.
1. En la sección **Detalles**, selecciona **Editar**.
1. En el cuadro de texto **Instrucciones**, agrega lo siguiente al texto de las instrucciones existentes: `Use the Contoso Marketing Pitch action to help marketing stakeholders craft pitches for products based on their draft ideas.`
1. En la página de detalles del agente, en **Acciones**, selecciona **Agregar acción**.
1. En las secciones **Destacados** o **Biblioteca** de la ventana modal **Agregar acción**, selecciona **Contoso Marketing Pitch**.
1. En la página de acción, asegúrate de que el **nombre** es `Create a Contoso Marketing Pitch`
1. Asegúrate de que la **descripción** es `Create a marketing pitch that follows the Contoso guidelines`.
1. Seleccione **Agregar acción**. Esta operación puede tardar unos minutos. La acción se agrega a la lista de acciones disponibles para el agente en **Acciones**.

### Configuración de la acción

1. Selecciona la acción `Contoso Marketing Pitch` entre las acciones disponibles para el agente. Se te dirigirá a una página para configurar las propiedades y los valores de la acción.
1. Confirma que el **nombre de acción** está establecido en `Create a new Contoso marketing pitch`.
1. Selecciona **Entradas** en el panel de navegación superior dentro de la acción.
1. En **Entradas adicionales**, selecciona **Agregar**.
1. Selecciona la variable **Draft**. Aparece un formulario.
1. Asegúrate de que el campo **Cómo rellenará el agente esta entrada** está establecido en **Rellenar dinámicamente con la mejor opción (predeterminado)**.
1. En el campo **Nombre para mostrar**, escriba `Initial draft`.
1. Asegúrate de que el campo **Identificar como** está establecido en **La respuesta completa del usuario**
1. Selecciona **Guardar** en la parte superior de la ventana.

## (Opcional) Probar una acción de solicitud en Copilot Studio

A continuación, prueba el agente con la acción en Copilot Studio.

1. En el panel **Probar el agente** en la página de información general del agente en Copilot Studio, selecciona el botón **Actualizar** para actualizar el panel de pruebas y cargar los cambios más recientes del agente.
1. En el cuadro de texto de la conversación de prueba, escribe `Create a Contoso marketing pitch based on the following draft: "Bouncy ball is the hottest product on the market for both youth and adults. It's durable and the largest of its kind."` y envía el mensaje.
1. Revisa la respuesta y observa que el agente sigue las instrucciones que proporcionaste en las instrucciones de la acción de indicación personalizada.

Has completado el ejercicio y has validado la funcionalidad de la acción de solicitud.
