# WAX n8n Workflows

Este repositorio contiene los flujos de trabajo (workflows) de n8n para el proyecto WAX Studio, enfocado en la generación de prompts y modelos 3D de moda utilizando inteligencia artificial.

## Estructura

- `wax-studio-workflow.json`: Workflow principal para chat, generación y consulta de modelos 3D.
- `n8n-workflows-base/`: Otros flujos auxiliares o históricos.

## Inspiración

Este workflow se inspira en la necesidad de automatizar la creación de modelos 3D personalizados para moda, combinando:
- Consultoría conversacional con IA (OpenAI GPT-4o-mini)
- Generación de modelos 3D con Meshy AI
- Orquestación y automatización flexible con n8n

El diseño busca facilitar la interacción natural con usuarios no técnicos, permitiendo tanto la generación por texto como, próximamente, por imagen de referencia.

## Flujo de ramas

- `main`: Código listo para producción.
- `develop`: Integración y pruebas.
- `feature/*`: Nuevas funcionalidades.
- `hotfix/*`: Correcciones urgentes.

## Contribución

1. Crea una rama desde `develop` (`feature/tu-feature`).
2. Realiza tus cambios y haz commits descriptivos.
3. Abre un Pull Request a `develop` para revisión.
4. Una vez aprobado, se fusiona a `main` tras pruebas.

## Licencia

MIT
