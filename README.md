# 🐙 Git Cheat Sheet – Guía práctica

Guía de Git con los comandos más usados.

---

## 🔹 1. Inicialización y configuración

```bash
git init
```

Crea un repositorio Git nuevo en la carpeta actual.

**Ejemplo:**

```bash
mkdir mi-proyecto
cd mi-proyecto
git init
```

```bash
git clone <url>
```

Clona un repositorio remoto en tu máquina local.

**Ejemplo:**

```bash
git clone https://github.com/usuario/proyecto.git
```

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

Configura tu nombre y correo para los commits globalmente.

```
git config --global --list
```
Para ver la configuración global de Git.

---

## 🔹 2. Estado y cambios

```bash
git status
```

Muestra archivos modificados, listos para commit o sin seguimiento.

```bash
git diff
```

Muestra las diferencias entre los archivos modificados y la última versión guardada.

```bash
git log --oneline
```

Muestra el historial de commits de forma resumida.

```bash
git show <hash>
```

Muestra los detalles de un commit específico, incluyendo cambios.

---

## 🔹 3. Añadir y confirmar cambios

```bash
git add <archivo>
git add .
```

Prepara archivos para commit. `.` añade todos los cambios.

```bash
git commit -m "Mensaje descriptivo"
```

Guarda los cambios preparados con un mensaje.

```bash
git commit -am "Mensaje"
```

Atajo: añade y hace commit de archivos modificados (no nuevos).

---

## 🔹 4. Ramas (Branches)

```bash
git branch
```

Lista todas las ramas y muestra la actual.

```bash
git branch <nombre-rama>
```

Crea una nueva rama.

```bash
git checkout <nombre-rama>
```

Cambia a otra rama.

```bash
git checkout -b <nombre-rama>
```

Crea y cambia a una nueva rama en un solo paso.

```bash
git merge <rama>
```

Fusiona la rama indicada en la actual.

```bash
git branch -d <rama>
```

Borra una rama local que ya no se necesita.

---

## 🔹 5. Sincronización con remoto

```bash
git remote -v
```

Muestra los repositorios remotos configurados.

```bash
git pull origin <rama>
```

Trae cambios del remoto y los fusiona con tu rama local.

```bash
git fetch
```

Descarga cambios del remoto sin fusionarlos.

```bash
git push origin <rama>
```

Sube tus commits locales al remoto.

---

## 🔹 6. Arreglos y manejo de errores

```bash
git reset --hard HEAD~1
```

Deshace el último commit y borra los cambios.

```bash
git checkout -- <archivo>
```

Deshace cambios en un archivo específico.

```bash
git stash
```

Guarda temporalmente cambios sin hacer commit.

```bash
git stash pop
```

Recupera los cambios guardados con `stash`.

---

## 🔹 7. Etiquetas (Tags)

```bash
git tag <nombre-tag>
```

Marca un commit con una versión.

```bash
git tag
```

Lista todas las etiquetas.

```bash
git push origin <nombre-tag>
```

Sube la etiqueta al remoto.

---

## 🔹 8. Buenas prácticas en commits

* Mensajes claros y consistentes:

```text
feat: añadir nueva funcionalidad
fix: corregir bug
docs: actualizar documentación
```

---

| Comando           | Uso principal                     | Ejemplo                               |
| ----------------- | --------------------------------- | ------------------------------------- |
| git status        | Ver estado de archivos            | `git status`                          |
| git diff          | Ver cambios antes del commit      | `git diff archivo.txt`                |
| git add           | Preparar archivos para commit     | `git add index.html`                  |
| git commit        | Guardar cambios preparados        | `git commit -m "feat: nueva función"` |
| git commit -am    | Añadir y commitear modificaciones | `git commit -am "fix: bug login"`     |
| git log --oneline | Historial resumido                | `git log --oneline`                   |
| git branch        | Listar o crear ramas              | `git branch`                          |
| git checkout      | Cambiar de rama                   | `git checkout feature-login`          |
| git checkout -b   | Crear y cambiar a una rama        | `git checkout -b feature-UI`          |
| git merge         | Fusionar ramas                    | `git merge feature-login`             |
| git pull          | Traer y fusionar del remoto       | `git pull origin main`                |
| git fetch         | Traer cambios sin fusionar        | `git fetch origin`                    |
| git push          | Subir cambios al remoto           | `git push origin main`                |
| git stash         | Guardar cambios temporalmente     | `git stash`                           |
| git stash pop     | Recuperar cambios guardados       | `git stash pop`                       |
| git reset --hard  | Descartar cambios en archivos y commits | `git reset --hard HEAD` |

