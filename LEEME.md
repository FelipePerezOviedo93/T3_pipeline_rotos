# Tema 3 - Tres pipelines rotos

Cada carpeta (`caso1`, `caso2`, `caso3`) trae archivos que reemplazan a los del repositorio de la
API de tareas. Con esos archivos, el pipeline de CI falla. El trabajo es encontrar **por qué** a
partir de lo que muestra la ejecución, corregirlo y dejar el diagnóstico por escrito.

## Cómo reproducir cada caso

Para cada caso, en el repositorio propio:

```bash
git switch main
git pull
git switch -c diagnostico-caso1          # caso2, caso3 para los otros
cp -r <ruta>/caso1/. .                   # copia los archivos del caso encima del repositorio
git add -A
git commit -m "Caso 1 de diagnóstico"
git push -u origin diagnostico-caso1
```

Después se abre un pull request de esa rama hacia `main` y se mira la ejecución en la pestaña
**Actions** (o en la sección de checks del pull request).

## Qué registrar por caso

Se registra en la plantilla `diagnostico-ci.md` de este zip, que al final va al repositorio como
`docs/diagnostico-ci.md` (guía de laboratorio del Tema 3, Parte 3).

| Campo | Contenido |
|---|---|
| Síntoma | Qué paso del pipeline falló y qué mensaje mostró (copiado del log, como texto) |
| Causa | Qué está mal y en qué archivo |
| Corrección | Qué se cambió (enlace al commit que lo corrige) |
| Prevención | Qué práctica o control evitaría que vuelva a pasar |

Un caso puede mostrar más de un paso en rojo. Conviene identificar cuál falló **primero**: los
demás pueden ser consecuencia de ese.
