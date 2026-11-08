---
title: "Lección 10 - Recapitulación y siguientes pasos"
description: "Repasa el flujo de trabajo de Copilot CLI, las dos solicitudes de incorporación de cambios, las personalizaciones reutilizables y otros recursos."
authors:
  - geektrainer
lastUpdated: 2026-09-29
---

Has usado GitHub Copilot CLI en un flujo de trabajo continuo con Tailspin Toys. En este recorrido:

- preparaste un Codespace, instalaste Copilot CLI, exploraste el proyecto y encontraste la incidencia de filtrado ya creada.
- añadiste valoraciones con estrellas, revisaste el resultado en un navegador con el puerto reenviado y fusionaste manualmente tu primera solicitud de incorporación de cambios (PR).
- partiste de la incidencia de filtrado, definiste el enfoque en modo Plan, lo implementaste en modo Autopilot y lo revisaste en modo Interactive.
- orientaste al agente con instrucciones personalizadas, personalizaste la skill existente `quality-checks` y la usaste para ejecutar pruebas unitarias, lint y comprobaciones de tipos.
- añadiste el servidor Playwright Model Context Protocol (MCP) y lo usaste para explorar el filtrado en un navegador real.
- creaste y seleccionaste un agente personalizado de control de calidad (QA) para evaluar los requisitos, la cobertura, los resultados de la skill y las pruebas del navegador.
- revisaste todos los cambios de filtrado y autorizaste Agent Merge para fusionar la PR correspondiente.
- exploraste comandos de barra para gestionar el contexto y los modelos, compartir sesiones y delegar tareas opcionalmente al agente en la nube.

## Lo que has entregado

El taller incluye dos hitos de PR, cada uno en su propia rama creada desde `main` actualizado:

1. **Valoraciones con estrellas:** muestra en las tarjetas de juegos el valor existente de `starRating` y un estado explícito para los juegos sin valorar.
2. **Filtrado y flujo de trabajo de calidad:** implementa el filtrado, actualiza las instrucciones y aplícalas a la funcionalidad, personaliza el informe de `quality-checks`, crea un perfil de QA e incluye las pruebas correspondientes.

Desde la planificación del filtrado hasta la creación de su PR, usaste la misma conversación y rama. Combinamos ese trabajo en una sola PR para simplificar el taller.

## Distintas formas de verificar

Comprobaste el código de varias maneras: con pruebas automatizadas, inspeccionándolo en el navegador y usando MCP para que Copilot explorase el navegador. La skill `quality-checks` ejecutó las pruebas unitarias, lint y comprobaciones de tipos, y presentó los resultados con el nuevo formato. Antes de la PR, QA reunió esos resultados con una revisión de los requisitos y la cobertura de pruebas.

Las pruebas nuevas deben cubrir carencias reales; una ejecución de QA que no necesite pruebas nuevas también puede ser correcta. Revisa el código y las pruebas antes de autorizar la fusión, y actualiza las pruebas afectadas después de hacer cambios.

## Buenas prácticas

El contexto y las herramientas que proporcionas a Copilot influyen en su trabajo. En este taller actualizaste instrucciones, personalizaste una skill, creaste un perfil de QA y configuraste un servidor MCP. Reutiliza estas personalizaciones entre conversaciones y ajústalas a las necesidades del equipo. Las instrucciones establecen normas, las skills describen tareas repetibles, los agentes personalizados definen funciones especializadas y los servidores MCP conectan herramientas externas. Revisa los cambios y los resultados de las herramientas, no solo el resumen del agente.

Adapta el **modo y el modelo** a la tarea. Usa **Plan** para pensar el enfoque antes de construir, **Interactive** para seguir de cerca cambios concretos y **Autopilot** para tareas bien delimitadas. Elige un modelo más rápido para ediciones rutinarias y uno más capaz para tareas complejas.

El contexto sigue siendo tan importante como la infraestructura. Explicar con claridad *qué* quieres crear, *por qué* y *cómo* influye de forma significativa en el resultado.

## Más información

Ya has recorrido el flujo de trabajo principal. Estas son algunas funciones más de Copilot CLI que puedes probar:

- `/review` para pedir al agente de revisión de código que analice los cambios.
- `/rubber-duck` para hablar de un problema y obtener otra perspectiva.
- `/fleet` para coordinar subtareas independientes en paralelo.
- `/worktree` para aislar una tarea.
- `/delegate` para enviar una tarea al agente en la nube de Copilot.

## Siguientes pasos

La mejor forma de mejorar con cualquier herramienta es seguir usándola. Úsala con código de producción, en proyectos personales o para crear esa pequeña aplicación que llevas años imaginando. Comparte lo que aprendas con el equipo y aprende de sus experiencias. Y, como siempre, explora la documentación.

Si quieres ampliar Tailspin Toys desde el terminal, continúa con la serie opcional [Foundry Backer Concierge][foundry]. Para comparar otros entornos, explora el [taller de VS Code][vscode], el [taller de la aplicación GitHub Copilot][app] o el [taller del agente en la nube de Copilot][cloud].

## Recursos

- [Acerca de GitHub Copilot CLI][about-cli]
- [Referencia de comandos de Copilot CLI][cli-reference]
- [Personalizar Copilot CLI][customize-cli]
- [Gestionar solicitudes de incorporación de cambios con Copilot CLI][manage-prs]

[previous-lesson]: ../9-cli-power-tools/
[foundry]: ../8-foundry-agent/
[vscode]: ../../vscode/
[app]: ../../app/
[cloud]: ../../cloud/
[about-cli]: https://docs.github.com/copilot/concepts/agents/about-copilot-cli
[cli-reference]: https://docs.github.com/copilot/reference/copilot-cli-reference/cli-command-reference
[customize-cli]: https://docs.github.com/copilot/how-tos/copilot-cli/customize-copilot
[manage-prs]: https://docs.github.com/copilot/how-tos/copilot-cli/use-copilot-cli/manage-pull-requests
