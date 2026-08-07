# 🐙 Git Cheat Sheet

Una guía de referencia rápida con los comandos más utilizados en **Git**, la herramienta estándar para el control de versiones. Ideal para guardar en tus proyectos de GitHub.

---

## 📌 Tabla de Contenidos
- [🚀 Configuración Inicial](#-configuración-inicial)
- [📁 Crear e Inicializar](#-crear-e-inicializar)
- [🔄 Flujo de Trabajo Local](#-flujo-de-trabajo-local)
- [🌿 Rama y Fusion (Branches & Merge)](#-ramas-y-fusión-branches--merge)
- [🌐 Remoto y Colaboración](#-remoto-y-colaboración)
- [⏪ Deshacer Cambios y Historial](#-deshacer-cambios-y-historial)
- [📦 Guardado Temporal (Stash)](#-guardado-temporal-stash)

---

## 🚀 Configuración Inicial

| Comando | Descripción |
| :--- | :--- |
| `git config --global user.name "Tu Nombre"` | Configura tu nombre de usuario global. |
| `git config --global user.email "tu@email.com"` | Configura tu correo electrónico global. |
| `git config --global init.defaultBranch main` | Establece `main` como la rama por defecto. |
| `git config --list` | Muestra la configuración actual de Git. |

---

## 📁 Crear e Inicializar

| Comando | Descripción |
| :--- | :--- |
| `git init` | Inicializa un nuevo repositorio de Git en la carpeta actual. |
| `git clone <url>` | Descarga un repositorio remoto completo a tu equipo. |

---

## 🔄 Flujo de Trabajo Local

| Comando | Descripción |
| :--- | :--- |
| `git status` | Muestra el estado del directorio de trabajo y del área de preparación (staging). |
| `git add <archivo>` | Agrega un archivo específico al área de preparación. |
| `git add .` | Agrega **todos** los cambios modificados y nuevos al área de preparación. |
| `git commit -m "Mensaje explicativo"` | Guarda los cambios preparados en el historial local. |
| `git commit -am "Mensaje"` | Agrega y commitea en un solo paso (solo archivos rastreados). |
| `git diff` | Muestra las diferencias no preparadas entre tu código y el último commit. |

---

## 🌿 Ramas y Fusión (Branches & Merge)

| Comando | Descripción |
| :--- | :--- |
| `git branch` | Lista todas las ramas locales (la actual con un `*`). |
| `git branch <nombre-rama>` | Crea una nueva rama. |
| `git switch <nombre-rama>` | Cambia a la rama especificada. |
| `git checkout -b <nombre-rama>` | Crea y cambia a la nueva rama en un solo comando. |
| `git merge <nombre-rama>` | Fusiona la rama indicada dentro de la rama actual. |
| `git branch -d <nombre-rama>` | Elimina una rama local. |

---

## 🌐 Remoto y Colaboración

| Comando | Descripción |
| :--- | :--- |
| `git remote add origin <url>` | Conecta tu repositorio local con uno remoto (como GitHub). |
| `git remote -v` | Lista las conexiones remotas configuradas. |
| `git fetch` | Descarga el historial remoto sin aplicar cambios a tu código. |
| `git pull` | Descarga e integra los cambios del remoto a tu rama actual (`fetch` + `merge`). |
| `git push origin <rama>` | Sube commits locales a la rama del repositorio remoto. |
| `git push -u origin main` | Sube la rama local y la establece como seguimiento por defecto. |

---

## ⏪ Deshacer Cambios y Historial

| Comando | Descripción |
| :--- | :--- |
| `git log` | Muestra el historial completo de commits. |
| `git log --oneline --graph` | Muestra el historial de forma compacta y visual. |
| `git restore <archivo>` | Descarta los cambios no commiteados de un archivo. |
| `git restore --staged <archivo>` | Saca un archivo del área de preparación manteniendo los cambios. |
| `git reset --soft HEAD~1` | Deshace el último commit manteniendo los cambios en staging. |
| `git reset --hard HEAD~1` | ⚠️ Deshace el último commit y elimina todos los cambios no guardados. |
| `git revert <hash-commit>` | Crea un nuevo commit que deshace un commit previo sin alterar el historial. |

---

## 📦 Guardado Temporal (Stash)

| Comando | Descripción |
| :--- | :--- |
| `git stash` | Guarda temporalmente los cambios no commiteados para limpiar el área de trabajo. |
| `git stash pop` | Aplica el último stash guardado y lo elimina de la lista. |
| `git stash list` | Muestra la lista de stashes guardados. |

---
💡 *Cheat Sheet de Git creado para referencia rápida en GitHub.*
