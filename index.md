---
title: Instrucciones del ejercicio
permalink: index.html
layout: home
---

# Ejercicios

En esta página se enumeran los ejercicios asociados con el curso de aptitudes de Microsoft **MS-4022: Ampliación de Microsoft 365 Copilot en Copilot Studio**.

Ruta de aprendizaje relacionada: [Ampliación de Microsoft 365 Copilot en Copilot Studio](https://learn.microsoft.com/training/paths/extend-microsoft-365-copilot-studio/).

**Nota**: para completar estos ejercicios, necesitarás:

- Una cuenta profesional o educativa con [acceso a Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/requirements-licensing-subscriptions). Si aún no tienes acceso a Copilot Studio, en función de la configuración de tu organización de Microsoft 365, puedes [crear una cuenta de prueba](https://learn.microsoft.com/microsoft-copilot-studio/sign-up-individual).
- Una licencia de Microsoft 365 Copilot
- Credenciales necesarias para conectarte a los orígenes de contenido deseados (conectores, API, etc.)

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %} {% assign labs = labs | sort: "lab.title" %} {% for activity in labs  %}
- [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) {% endfor %}

