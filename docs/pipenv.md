# 🐍 Pipenv Cheat Sheet

Un resumen rápido y práctico de los comandos más utilizados en **Pipenv**, la herramienta oficial de gestión de dependencias y entornos virtuales en Python. Ideal como referencia para tus proyectos.

---

## 📌 Tabla de Contenidos
- [🚀 Inicio y Entorno](#-inicio-y-entorno)
- [📦 Instalación y Dependencias](#-instalación-y-dependencias)
- [🗑️ Desinstalación y Limpieza](#️-desinstalación-y-limpieza)
- [🛠️ Ejecución e Información](#️-ejecución-e-información)
- [🔍 Árbol de Dependencias y Seguridad](#-árbol-de-dependencias-y-seguridad)
- [📄 Estructura de Archivos](#-estructura-de-archivos)

---

## 🚀 Inicio y Entorno

| Comando | Descripción |
| :--- | :--- |
| `pipenv shell` | Activa el entorno virtual. Si no existe, lo crea automáticamente. |
| `pipenv --python 3.11` | Crea el entorno virtual especificando una versión concreta de Python. |
| `exit` | Sale del entorno virtual activo. |
| `pipenv --rm` | Elimina por completo el entorno virtual asociado al proyecto. |

---

## 📦 Instalación y Dependencias

| Comando | Descripción |
| :--- | :--- |
| `pipenv install <paquete>` | Instala un paquete y lo registra en el `Pipfile`. |
| `pipenv install <paquete>==1.2.3` | Instala una versión específica de un paquete. |
| `pipenv install <paquete> --dev` | Instala un paquete únicamente como dependencia de desarrollo. |
| `pipenv install` | Instala todas las dependencias listadas en el `Pipfile`. |
| `pipenv install --dev` | Instala dependencias de producción y de desarrollo. |
| `pipenv install --deploy` | Instala las versiones exactas según el `Pipfile.lock` (modo producción/CI). |

---

## 🗑️ Desinstalación y Limpieza

| Comando | Descripción |
| :--- | :--- |
| `pipenv uninstall <paquete>` | Desinstala un paquete y lo remueve del `Pipfile`. |
| `pipenv uninstall --all` | Desinstala todos los paquetes del entorno virtual. |
| `pipenv uninstall --all-dev` | Desinstala únicamente las dependencias de desarrollo. |

---

## 🛠️ Ejecución e Información

| Comando | Descripción |
| :--- | :--- |
| `pipenv run python script.py` | Ejecuta un script dentro del entorno sin necesidad de hacer `pipenv shell`. |
| `pipenv --venv` | Muestra la ruta en disco donde está almacenado el entorno virtual. |
| `pipenv --py` | Muestra la ubicación exacta del ejecutable de Python usado. |
| `pipenv --where` | Muestra la ruta del directorio raíz del proyecto actual. |

---

## 🔍 Árbol de Dependencias y Seguridad

| Comando | Descripción |
| :--- | :--- |
| `pipenv graph` | Muestra en formato de árbol todas las dependencias y sus subdependencias. |
| `pipenv check` | Escanea el proyecto en busca de vulnerabilidades de seguridad conocidas (PEP 508). |
| `pipenv lock` | Actualiza y regenera el archivo `Pipfile.lock`. |

---

## 📄 Estructura de Archivos

Cuando trabajás con Pipenv, se generan dos archivos clave:

* `Pipfile`: Reemplaza al tradicional `requirements.txt`. Define las dependencias directas y sus versiones generales.
* `Pipfile.lock`: Mantiene el registro exacto con hashes de seguridad y versiones secundarias para garantizar compilaciones reproducibles.

---
💡 *Cheat Sheet creado para referencia rápida en GitHub.*
