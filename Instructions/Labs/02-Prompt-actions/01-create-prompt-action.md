---
lab:
  title: '2.1: Crear una acción de solicitud'
---

# Creación de una acción de solicitud

En este ejercicio crearás una acción de solicitud, probarás la indicación en Copilot Studio y también en el agente de Copilot. Crearás una acción de solicitud que ayude a los usuarios a convertir sus nuevas ideas en presentaciones de marketing organizadas que siguen un formato y directrices específicos.

Este ejercicio debería tardar aproximadamente **15** minutos en completarse.

## Creación de un mensaje personalizado en Copilot Studio

1. Abre Copilot Studio en el explorador web; para ello, ve a [Copilot Studio](https://copilotstudio.microsoft.com) en `https://copilotstudio.microsoft.com`.
1. Seleccione **Herramientas** en el panel de navegación de la izquierda.
1. Seleccione **Crear nuevo** y, después, **Mensaje**. Se le ha llevado a la interfaz de usuario del generador de mensajes.
1. En el cuadro de texto **Instrucciones**, escribe `Create a marketing pitch for a product based on a `.
1. Coloca el cursor al final de la frase que escribiste y selecciona **Agregar contenido**
1. Selecciona **Texto**.
1. En el campo **Nombre**, escriba `draft`.
1.  En el campo **Datos de ejemplo**, escribe `The Mighty Mechanical Pencil is new, exciting, and useful. It's not only the first of its kind pencil, but it's fun to use.` y selecciona **Cerrar**.

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

## Configuración y publicación del mensaje

Después de guardar el mensaje, aparece la ventana **Configurar para su uso en Agente**.

1. En el campo **Nombre**, escriba `Create a Contoso Marketing Pitch`.
1. En el campo **Descripción del agente para saber cuándo usar esta herramienta**, escriba `Create a marketing pitch that follows Contoso guidelines` y, después, seleccione **Siguiente**. Se te dirigirá a la página **Crear indicación**.
1. Seleccione **Agregar**.

## (Opcional) Agregar una acción de solicitud a un agente

Si has completado el laboratorio anterior y has creado un agente declarativo, puedes agregar esta acción al agente y actualizar sus instrucciones para hacer referencia a la acción.

### Adición de la herramienta de mensaje

1. En la barra lateral de Copilot Studio, seleccione **Agentes**.
1. Seleccione **Microsoft 365 Copilot**.
1. En **Agentes**, seleccione el agente **Soporte técnico del producto** al que quiere agregar la acción.
1. En la sección **Herramientas** de la página, seleccione **Agregar herramienta**.
1. Seleccione el filtro **Mensaje**.
1. Seleccione el mensaje **Crear una acción de marketing de Contoso**.
1. Seleccione **Agregar al agente**. La herramienta aparece ahora en **Herramientas** del agente de Soporte técnico del producto.

### Configuración de la herramienta de mensaje

1. En la sección **Herramientas** de la página de información general del agente, seleccione la herramienta `Contoso Marketing Pitch`. Se le dirigirá a una página para configurar las propiedades y los valores de la herramienta.
1. Seleccione **Entradas** en el panel de navegación superior dentro de la herramienta de mensaje.
1. En **Entradas adicionales**, selecciona **Agregar**.
1. Selecciona la variable **Draft**. Aparece un formulario.
1. Asegúrate de que el campo **Cómo rellenará el agente esta entrada** está establecido en **Rellenar dinámicamente con la mejor opción (predeterminado)**.
1. En el campo **Nombre para mostrar**, escriba `Initial draft`.
1. Asegúrate de que el campo **Identificar como** está establecido en **La respuesta completa del usuario**
1. Selecciona **Guardar** en la parte superior de la ventana.

### Actualización de las instrucciones del agente

Actualice las instrucciones del agente a fin de proporcionar instrucciones para usar el mensaje.

1. En el cuadro de texto **Instrucciones**, agrega lo siguiente al texto de las instrucciones existentes: `Use the Contoso Marketing Pitch action to help marketing stakeholders craft pitches for products based on their draft ideas.`

## (Opcional) Prueba de una herramienta de mensaje en Copilot Studio

A continuación, probará el agente con la herramienta de mensaje en Copilot Studio.

1. En el panel **Probar el agente** en la página de información general del agente en Copilot Studio, selecciona el botón **Actualizar** para actualizar el panel de pruebas y cargar los cambios más recientes del agente.
1. En el cuadro de texto de la conversación de prueba, escribe `Create a Contoso marketing pitch based on the following draft: "Bouncy ball is the hottest product on the market for both youth and adults. It's durable and the largest of its kind."` y envía el mensaje.
1. Revise la respuesta y observe que el agente sigue las instrucciones que le ha proporcionado en las instrucciones del mensaje personalizado.

Ha completado el ejercicio y ha validado la funcionalidad de la herramienta de mensaje.
