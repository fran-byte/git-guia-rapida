# Guía Rápida de Git

## 01 Configuración de Git

| Comando | Descripción |
|---------|-------------|
| `git config --global user.name "Tu Nombre"` | Establece el nombre que se adjuntará a tus commits y etiquetas |
| `git config --global user.email "tu@email.com"` | Establece la dirección de correo que se adjuntará a tus commits y etiquetas |
| `git config --global color.ui auto` | Habilita colores en la salida de Git |

## 02 Iniciar un Proyecto

| Comando | Descripción |
|---------|-------------|
| `git init [nombre_proyecto]` | Crea un nuevo repositorio local en el directorio actual. Si se proporciona `[nombre_proyecto]`, Git creará un nuevo directorio con ese nombre e inicializará un repositorio dentro de él |
| `git clone [url]` | Descarga un proyecto con todo su historial desde el repositorio remoto |

## 03 Trabajo Diario

| Comando | Descripción |
|---------|-------------|
| `git status` | Muestra el estado de tu directorio de trabajo. Incluye archivos nuevos, preparados y modificados |
| `git add [archivo]` | Añade un archivo al área de preparación. Usa `.` para añadir todos los archivos cambiados |
| `git diff [archivo]` | Muestra cambios entre el directorio de trabajo y el área de preparación |
| `git diff --staged [archivo]` | Muestra cambios entre el área de preparación y el repositorio |
| `git checkout -- [archivo]` | Descarta cambios en el directorio de trabajo. Esta operación no se puede deshacer |
| `git reset [ruta...]` | Revierte rutas en el índice a su estado en HEAD |
| `git commit` | Crea un nuevo commit desde los cambios añadidos al área de preparación |
| `git rm [archivo]` | Elimina archivo del directorio de trabajo y del área de preparación |

## 04 Almacenamiento Temporal

| Comando | Descripción |
|---------|-------------|
| `git stash` | Guarda cambios actuales en el directorio de trabajo para uso posterior |
| `git stash pop` | Aplica el contenido almacenado en stash al directorio de trabajo y limpia el stash |
| `git stash drop` | Elimina un stash específico de todos tus stashes anteriores |

## 05 Modelo de Ramas

| Comando | Descripción |
|---------|-------------|
| `git branch [-a]` | Lista todas las ramas locales. Con `-a` muestra todas las ramas (incluyendo remotas) |
| `git branch [nombre_rama]` | Crea nueva rama, referenciando el HEAD actual |
| `git rebase [nombre_rama]` | Aplica commits de la rama actual al HEAD de `[rama]` para hacer el historial más lineal |
| `git checkout [-b] [nombre_rama]` | Cambia el directorio de trabajo a la rama especificada. Con `-b` crea la rama si no existe |
| `git merge [nombre_rama]` | Fusiona la rama especificada con tu rama actual |
| `git branch -d [nombre_rama]` | Elimina la rama seleccionada, si ya está fusionada en otra. `-D` fuerza la eliminación |

### Conceptos Clave

| Término | Descripción |
|---------|-------------|
| **Commit** | Un estado de la base de código |
| **Rama** | Una referencia a un commit; puede tener un upstream rastreado |
| **Etiqueta** | Una referencia (estándar) o un objeto (anotado) |
| **HEAD** | La posición actual de tu directorio de trabajo |

## 06 Inspeccionar Historial

| Comando | Descripción |
|---------|-------------|
| `git log [~n count]` | Lista el historial de commits de la rama actual. `~n count` limita la lista a los últimos n commits |
| `git log --oneline --graph --decorate` | Vista general con etiquetas de referencia y gráfico de historial. Un commit por línea |
| `git log ref...` | Lista commits presentes en la rama actual y no fusionados en ref |
| `git log ...ref` | Lista commits presentes en ref y no fusionados en la rama actual |
| `git reflog` | Lista operaciones (ej. checkouts o commits) realizadas en el repositorio local |

## 07 Etiquetado de Commits

| Comando | Descripción |
|---------|-------------|
| `git tag` | Lista todas las etiquetas |
| `git tag [nombre] [commit sha]` | Crea una referencia de etiqueta llamada `nombre` para el commit actual. Añade `commit sha` para etiquetar un commit específico |
| `git tag -a [nombre] [commit sha]` | Crea un objeto de etiqueta llamado `nombre` para el commit actual |
| `git tag -d [nombre]` | Elimina una etiqueta del repositorio local |

## 08 Revertir Cambios

| Comando | Descripción |
|---------|-------------|
| `git reset [~hard] [referencia_objetivo]` | Cambia la rama actual a la `referencia_objetivo`, dejando la diferencia como cambio no confirmado. Con `~hard` se descartan todos los cambios |

## 09 Sincronizar Repositorios

| Comando | Descripción |
|---------|-------------|
| `git fetch [remoto]` | Obtiene cambios del `remoto`, pero no actualiza las ramas de seguimiento |
| `git fetch --prune [remoto]` | Elimina referencias remotas que fueron eliminadas del repositorio `remoto` |
| `git pull [remoto]` | Obtiene cambios del `remoto` y fusiona la rama actual con su upstream |
| `git push [--tags] [remoto]` | Envía cambios locales al `remoto`. Usa `--tags` para enviar etiquetas |
| `git push -u [remoto] [rama]` | Envía rama local al repositorio `remoto`. Establece su copia como upstream |

## 10 Archivo .gitignore

Para ignorar archivos, crea un archivo `.gitignore` en tu repositorio con una línea para cada patrón.

Ejemplo:
```
logs/*
!logs/.gitkeep
tmp/
*.svp
```

En este ejemplo, se ignoran todos los archivos en el directorio logs (excepto el archivo `.gitkeep`), el directorio tmp y todos los archivos `.svp`.
