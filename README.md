
````markdown


## 🔹 1. Inicialización y configuración
```bash
git init
````

* Crea un repositorio Git nuevo en la carpeta actual.
* **Ejemplo:**

```bash
mkdir mi-proyecto
cd mi-proyecto
git init
```

```bash
git clone <url>
```

* Copia un repositorio remoto a tu máquina local.
* **Ejemplo:**

```bash
git clone https://github.com/usuario/proyecto.git
```

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

* Configura tu nombre y correo para los commits.

---

## 🔹 2. Estado y cambios

```bash
git status
```

* Muestra archivos modificados, listos para commit o sin seguimiento.
* **Ejemplo:** `git status` → te dice qué archivos cambiaste o añadiste.

```bash
git diff
```

* Muestra las diferencias entre los archivos modificados y la última versión guardada.
* **Ejemplo:** `git diff archivo.txt` → ves qué líneas cambiaste.

```bash
git log --oneline
```

* Muestra el historial de commits de forma resumida.
* **Ejemplo:** `git log --oneline` →

```
a1b2c3d Fix bug in login
4f5g6h7 Add README
```

```bash
git show <hash>
```

* Muestra los detalles de un commit específico, incluyendo cambios.
* **Ejemplo:** `git show a1b2c3d`

---

## 🔹 3. Añadir y confirmar cambios

```bash
git add <archivo>
git add .
```

* Prepara archivos para commit (`.` añade todos los cambios del proyecto).
* **Ejemplo:** `git add index.html`

```bash
git commit -m "Mensaje descriptivo"
```

* Guarda los cambios preparados con un mensaje.
* **Ejemplo:** `git commit -m "feat: añadir página de contacto"`

```bash
git commit -am "Mensaje"`
```

* Atajo: añade y hace commit de archivos modificados (no nuevos).
* **Ejemplo:** `git commit -am "fix: corregido bug en login"`

---

## 🔹 4. Ramas (Branches)

```bash
git branch
```

* Lista todas las ramas y muestra en cuál estás.
* **Ejemplo:** `git branch` →

```
* main
  feature-login
```

```bash
git branch <nombre-rama>
```

* Crea una nueva rama.
* **Ejemplo:** `git branch feature-login`

```bash
git checkout <nombre-rama>
```

* Cambia a otra rama.
* **Ejemplo:** `git checkout feature-login`

```bash
git checkout -b <nombre-rama>
```

* Crea y cambia a una nueva rama en un solo paso.
* **Ejemplo:** `git checkout -b feature-UI`

```bash
git merge <rama>
```

* Fusiona la rama indicada en la actual.
* **Ejemplo:** `git merge feature-login` → fusiona los cambios en main.

```bash
git branch -d <rama>`
```

* Borra una rama local que ya no se necesita.
* **Ejemplo:** `git branch -d feature-login`

---

## 🔹 5. Sincronización con remoto

```bash
git remote -v
```

* Muestra los repositorios remotos configurados.
* **Ejemplo:** `git remote -v` → origin [https://github.com/usuario/proyecto.git](https://github.com/usuario/proyecto.git)

```bash
git pull origin <rama>
```

* Trae cambios del remoto y los fusiona con tu rama local.
* **Ejemplo:** `git pull origin main`

```bash
git fetch
```

* Descarga cambios del remoto sin fusionarlos.
* **Ejemplo:** `git fetch origin`

```bash
git push origin <rama>
```

* Sube tus commits locales al remoto.
* **Ejemplo:** `git push origin main`

---

## 🔹 6. Arreglos y manejo de errores

```bash
git reset --hard HEAD~1
```

* Deshace el último commit y borra los cambios.
* ⚠️ Peligroso, elimina trabajo no guardado.

```bash
git checkout -- <archivo>
```

* Deshace cambios en un archivo específico.
* **Ejemplo:** `git checkout -- index.html`

```bash
git stash
```

* Guarda temporalmente cambios sin hacer commit.
* **Ejemplo:** `git stash`

```bash
git stash pop
```

* Recupera los cambios guardados con `stash`.
* **Ejemplo:** `git stash pop`

---

## 🔹 7. Etiquetas (Tags)

```bash
git tag <nombre-tag>
```

* Marca un commit con una versión.
* **Ejemplo:** `git tag v1.0`

```bash
git tag
```

* Lista todas las etiquetas.

```bash
git push origin <nombre-tag>
```

* Sube la etiqueta al remoto.
* **Ejemplo:** `git push origin v1.0`

---

## 🔹 8. Buenas prácticas en commits

* Mensajes claros y consistentes:

```text
feat: añadir nueva funcionalidad
fix: corregir bug
docs: actualizar documentación
```

* Facilita el seguimiento de cambios y la colaboración.

---

## 🔹 9. Resumen rápido de comandos esenciales

| Comando                  | Uso principal                     | Ejemplo                               |
| ------------------------ | --------------------------------- | ------------------------------------- |
| git status               | Ver estado de archivos            | `git status`                          |
| git diff                 | Ver cambios antes del commit      | `git diff archivo.txt`                |
| git add                  | Preparar archivos para commit     | `git add index.html`                  |
| git commit               | Guardar cambios preparados        | `git commit -m "feat: nueva función"` |
| git commit -am           | Añadir y commitear modificaciones | `git commit -am "fix: bug login"`     |
| git log --oneline        | Historial resumido                | `git log --oneline`                   |
| git branch               | Listar o crear ramas              | `git branch`                          |
| git checkout             | Cambiar de rama                   | `git checkout feature-login`          |
| git checkout -b          | Crear y cambiar a una rama        | `git checkout -b feature-UI`          |
| git merge                | Fusionar ramas                    | `git merge feature-login`             |
| git pull                 | Traer y fusionar del remoto       | `git pull origin main`                |
| git fetch                | Traer cambios sin fusionar        | `git fetch origin`                    |
| git push                 | Subir cambios al remoto           | `git push origin main`                |
| git stash                | Guardar cambios temporalmente     | `git stash`                           |
| git stash pop            | Recuperar cambios guardados       | `git stash pop`                       |
| git reset --hard HEAD\~1 | Deshacer último commit            | `git reset --hard HEAD~1`             |

---


¿Quieres que haga esa versión visual?
```
