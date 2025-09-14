# Guía Rápida de Git


⚠️ **ADVERTENCIA**: comandos pueden causar pérdida de trabajo no commitado o alterar permanentemente el historial

| Comando | Riesgo |
|---------|--------|
| `git checkout -- [archivo]` | Descarta cambios locales permanentemente |
| `git reset --hard [commit]` | Elimina commits y cambios no commitados |
| `git clean -fd` | Elimina archivos no rastreados permanentemente |
| `git push --force` | Sobrescribe historial remoto (puede afectar a otros colaboradores) |
| `git stash drop` | Elimina cambios almacenados en stash |
| `git stash clear` | Elimina todos los stashes |
| `git branch -D [rama]` | Fuerza eliminación de rama (incluso sin merge) |
| `git rebase --interactive` | Puede reescribir historial de commits |

## 01 Configuración de Git

| Comando | Descripción |
|---------|-------------|
| `git config --global user.name "Tu Nombre"` | Establece el nombre que se adjuntará a tus commits y etiquetas |
| `git config --global user.email "tu@email.com"` | Establece la dirección de correo que se adjuntará a tus commits y etiquetas |
| `git config --global color.ui auto` | Habilita colores en la salida de Git |

## 02 Iniciar un Proyecto

| Comando | Descripción |
|---------|-------------|
| `git init [nombre_proyecto]` | Crea un nuevo repositorio local en el directorio actual |
| `git clone [url]` | Descarga un proyecto con todo su historial desde el repositorio remoto |

## 03 Trabajo Diario

| Comando | Descripción |
|---------|-------------|
| `git status` | Muestra el estado de tu directorio de trabajo |
| `git add [archivo]` | Añade un archivo al área de preparación |
| `git diff [archivo]` | Muestra cambios entre directorio de trabajo y área de preparación |
| `git diff --staged [archivo]` | Muestra cambios entre área de preparación y repositorio |
| ⚠️ `git checkout -- [archivo]` | Descarta cambios en el directorio de trabajo (irreversible) |
| `git reset [ruta...]` | Revierte rutas en el índice a su estado en HEAD |
| `git commit` | Crea un nuevo commit desde los cambios preparados |
| `git rm [archivo]` | Elimina archivo del directorio de trabajo y área de preparación |

## 04 Almacenamiento Temporal

| Comando | Descripción |
|---------|-------------|
| `git stash` | Guarda cambios actuales para uso posterior |
| `git stash pop` | Aplica el contenido almacenado y limpia el stash |
| ⚠️ `git stash drop` | Elimina un stash específico (irreversible) |
| ⚠️ `git stash clear` | Elimina todos los stashes (irreversible) |

## 05 Modelo de Ramas

| Comando | Descripción |
|---------|-------------|
| `git branch [-a]` | Lista todas las ramas locales (con `-a` incluye remotas) |
| `git branch [nombre_rama]` | Crea nueva rama referenciando el HEAD actual |
| `git rebase [nombre_rama]` | Aplica commits de la rama actual al HEAD de otra rama |
| `git checkout [-b] [nombre_rama]` | Cambia a la rama especificada (con `-b` la crea si no existe) |
| `git merge [nombre_rama]` | Fusiona la rama especificada con tu rama actual |
| ⚠️ `git branch -D [nombre_rama]` | Fuerza eliminación de rama (incluso sin merge) |

### Conceptos Clave

| Término | Descripción |
|---------|-------------|
| **Commit** | Un estado de la base de código |
| **Rama** | Una referencia a un commit |
| **Etiqueta** | Una referencia (estándar) o un objeto (anotado) |
| **HEAD** | La posición actual de tu directorio de trabajo |

## 06 Inspeccionar Historial

| Comando | Descripción |
|---------|-------------|
| `git log [~n count]` | Lista historial de commits de la rama actual |
| `git log --oneline --graph --decorate` | Vista general con etiquetas y gráfico de historial |
| `git log ref...` | Commits presentes en rama actual no fusionados en ref |
| `git log ...ref` | Commits presentes en ref no fusionados en rama actual |
| `git reflog` | Lista operaciones realizadas en el repositorio local |

## 07 Etiquetado de Commits

| Comando | Descripción |
|---------|-------------|
| `git tag` | Lista todas las etiquetas |
| `git tag [nombre] [commit sha]` | Crea referencia de etiqueta para commit actual/específico |
| `git tag -a [nombre] [commit sha]` | Crea objeto de etiqueta para commit actual/específico |
| `git tag -d [nombre]` | Elimina una etiqueta del repositorio local |

## 08 Revertir Cambios

| Comando | Descripción |
|---------|-------------|
| ⚠️ `git reset --hard [referencia]` | Descarta todos los cambios y commits posteriores (extremadamente peligroso) |
| `git reset --soft [referencia]` | Mantiene cambios en área de staging |
| `git reset --mixed [referencia]` | Mantiene cambios en directorio de trabajo (default) |

## 09 Sincronizar Repositorios

| Comando | Descripción |
|---------|-------------|
| `git fetch [remoto]` | Obtiene cambios del remoto sin actualizar ramas de seguimiento |
| `git fetch --prune [remoto]` | Elimina referencias remotas eliminadas del repositorio remoto |
| `git pull [remoto]` | Obtiene cambios del remoto y fusiona rama actual con upstream |
| `git push [--tags] [remoto]` | Envía cambios locales al remoto (con `--tags` envía etiquetas) |
| `git push -u [remoto] [rama]` | Envía rama local al repositorio remoto y establece upstream |
| ⚠️ `git push --force [remoto] [rama]` | Fuerza push sobrescribiendo historial remoto (muy peligroso) |

## 10 Limpieza

| Comando | Descripción |
|---------|-------------|
| ⚠️ `git clean -n` | Muestra qué archivos no rastreados serían eliminados (dry run) |
| ⚠️ `git clean -f` | Elimina archivos no rastreados (irreversible) |
| ⚠️ `git clean -fd` | Elimina archivos y directorios no rastreados (irreversible) |

## 11 Archivo .gitignore

Para ignorar archivos, crea un archivo `.gitignore` con patrones:

```
logs/*
!logs/.gitkeep
tmp/
*.svp
```

Se ignoran todos los archivos en directorio logs (excepto `.gitkeep`), directorio tmp y archivos `.svp`.

---

## Comandos Potencialmente Peligrosos/Irreversibles

⚠️ **ADVERTENCIA**: Los siguientes comandos pueden causar pérdida de trabajo no commitado o alterar permanentemente el historial:

| Comando | Riesgo |
|---------|--------|
| `git checkout -- [archivo]` | Descarta cambios locales permanentemente |
| `git reset --hard [commit]` | Elimina commits y cambios no commitados |
| `git clean -fd` | Elimina archivos no rastreados permanentemente |
| `git push --force` | Sobrescribe historial remoto (puede afectar a otros colaboradores) |
| `git stash drop` | Elimina cambios almacenados en stash |
| `git stash clear` | Elimina todos los stashes |
| `git branch -D [rama]` | Fuerza eliminación de rama (incluso sin merge) |
| `git rebase --interactive` | Puede reescribir historial de commits |

