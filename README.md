# WAX n8n Workflows

Repositorio de workflows n8n para WAX Studio orientado a dos flujos principales:

- chat de consultoría para construir prompts de moda 3D
- generación de modelos 3D con Meshy AI desde texto o desde imagen

## Archivo principal

El archivo recomendado para importar manualmente en n8n es `WAX Studio - Fashion 3D Generator.json`.

Ese workflow incluye:

- `meshy-chat`: webhook del asistente conversacional
- `meshy-generate`: generación text-to-3d
- `meshy-status`: consulta de estado para tareas de texto
- `meshy-generate-image`: generación image-to-3d
- `meshy-status-image`: consulta de estado para tareas de imagen

## Soporte de imagen

La integración image-to-3d usa el endpoint `POST /openapi/v1/image-to-3d` de Meshy.

Puntos importantes:

- Meshy no recibe la imagen como `multipart/form-data` en este endpoint.
- El workflow espera `imageDataUrl` en el body del webhook y lo reenvía a Meshy como `image_url` en JSON.
- El valor de `image_url` debe ser un Data URI válido o una URL pública accesible.

## Estructura

- `WAX Studio - Fashion 3D Generator.json`: workflow oficial, único archivo a importar en n8n.

## Stack

- n8n como orquestador
- OpenAI GPT-4o-mini para la parte conversacional
- Meshy AI para text-to-3d e image-to-3d

## Flujo de trabajo

1. El usuario conversa con el asistente para refinar una idea de accesorio.
2. Puede generar un modelo 3D por texto.
3. También puede generar un modelo 3D a partir de una imagen de referencia.
4. El frontend consulta los endpoints de estado hasta obtener el modelo final.

## Ramas

- `main`: producción
- `develop`: integración
- `feature/*`: trabajo de funcionalidades
- `hotfix/*`: correcciones urgentes

## Notas

- Este repositorio contiene workflows n8n. Los cambios del frontend viven fuera de este repo.
- Si se actualiza la lógica del frontend para image-to-3d, el contrato esperado por `meshy-generate-image` debe mantenerse alineado con `imageDataUrl`.

## Licencia

MIT
