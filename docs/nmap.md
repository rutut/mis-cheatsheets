# 🔍 Nmap Cheat Sheet

Una guía de referencia rápida con los comandos y parámetros más utilizados en **Nmap** (Network Mapper) para el escaneo de redes, descubrimiento de hosts y auditorías de seguridad.

---

## 📌 Tabla de Contenidos
- [🚀 Escaneos Básicos y Descubrimiento](#-escaneos-básicos-y-descubrimiento)
- [🔌 Técnicas de Escaneo de Puertos](#-técnicas-de-escaneo-de-puertos)
- [🎯 Selección de Puertos](#-selección-de-puertos)
- [🏷️ Detección de Versiones y S.O.](#️-detección-de-versiones-y-so)
- [📜 Scripts de Nmap (NSE)](#-scripts-de-nmap-nse)
- [🥷 Evasión de Firewalls y IDS](#-evasión-de-firewalls-y-ids)
- [📄 Formatos de Salida](#-formatos-de-salida)

---

## 🚀 Escaneos Básicos y Descubrimiento

| Comando | Descripción |
| :--- | :--- |
| `nmap <target>` | Escaneo estándar de los 1000 puertos TCP más comunes. |
| `nmap <ip1> <ip2>` | Escanea múltiples IP especificadas individualmente. |
| `nmap 192.168.1.1-20` | Escanea un rango de direcciones IP. |
| `nmap 192.168.1.0/24` | Escanea una subred completa (CIDR). |
| `nmap -sn <target>` | **Ping Sweep**: Descubre hosts activos en la red sin escanear puertos. |
| `nmap -Pn <target>` | Desactiva el ping previo; asume que el host está activo (útil si bloquean ICMP). |

---

## 🔌 Técnicas de Escaneo de Puertos

| Comando | Descripción |
| :--- | :--- |
| `nmap -sS <target>` | **SYN Scan (Stealth)**: Rápido y sigiloso; no completa el handshake TCP (requiere `sudo`). |
| `nmap -sT <target>` | **Connect Scan**: Usa llamadas del sistema TCP; más lento pero no requiere privilegios `root`. |
| `nmap -sU <target>` | **UDP Scan**: Escanea puertos UDP (suele ser más lento que TCP). |
| `nmap -sA <target>` | **ACK Scan**: Mapea reglas de firewall para verificar si los puertos están filtrados. |
| `nmap -sN <target>` | **NULL Scan**: Envía paquetes sin ningún flag TCP activado. |
| `nmap -sF <target>` | **FIN Scan**: Envía paquetes con la bandera FIN activada. |
| `nmap -sX <target>` | **Xmas Scan**: Envía paquetes con banderas FIN, URG y PUSH activadas. |

---

## 🎯 Selección de Puertos

| Comando | Descripción |
| :--- | :--- |
| `nmap -p 80 <target>` | Escanea un puerto específico (ej. puerto 80). |
| `nmap -p 22,80,443 <target>` | Escanea una lista de puertos separados por coma. |
| `nmap -p 1-1024 <target>` | Escanea un rango continuo de puertos. |
| `nmap -p- <target>` | Escanea los **65,535 puertos** TCP disponibles. |
| `nmap -F <target>` | **Fast Scan**: Escanea los 100 puertos más comunes en lugar de los 1000. |
| `nmap -r <target>` | Escanea los puertos de forma secuencial en lugar de aleatoria. |

---

## 🏷️ Detección de Versiones y S.O.

| Comando | Descripción |
| :--- | :--- |
| `nmap -sV <target>` | Detecta la versión exacta del servicio que corre en cada puerto abierto. |
| `nmap -O <target>` | Intenta identificar el Sistema Operativo del objetivo. |
| `nmap -A <target>` | **Escaneo Agresivo**: Activa detección de S.O., versiones, scripts por defecto y traceroute. |
| `nmap --traceroute <target>` | Traza la ruta de red hasta el objetivo en el escaneo. |

---

## 📜 Scripts de Nmap (NSE)

| Comando | Descripción |
| :--- | :--- |
| `nmap -sC <target>` | Ejecuta la lista de scripts predeterminados por defecto (`--script=default`). |
| `nmap --script=vuln <target>` | Ejecuta scripts de detección de vulnerabilidades conocidas. |
| `nmap --script=http-title <target>` | Ejecuta un script específico (ej. obtiene el título de un sitio web). |
| `nmap --script="http-*" <target>` | Ejecuta todos los scripts de la categoría o comodín especificado. |

---

## 🥷 Evasión de Firewalls y IDS

| Comando | Descripción |
| :--- | :--- |
| `nmap -f <target>` | Fragmenta los paquetes para dificultar la inspección por firewalls. |
| `nmap -D RND:10 <target>` | Utiliza señuelos (*decoys*) con IPs aleatorias para enmascarar tu IP real. |
| `nmap -S <ip-falsa> <target>` | Falsifica la dirección IP de origen (*IP Spoofing*). |
| `nmap --source-port 53 <target>` | Modifica el puerto de origen enviando tráfico desde un puerto común (ej. DNS/53). |
| `nmap --mtu 24 <target>` | Especifica el tamaño personalizado de la MTU para los paquetes. |

---

## 📄 Formatos de Salida

| Comando | Descripción |
| :--- | :--- |
| `nmap -oN salida.txt <target>` | Guarda el resultado en formato de texto normal. |
| `nmap -oX salida.xml <target>` | Guarda el resultado en formato **XML** (ideal para importar en otras herramientas). |
| `nmap -oG salida.gnmap <target>` | Guarda en formato **Grepable** (fácil de procesar con `grep`, `awk`, etc.). |
| `nmap -oA resultado <target>` | Guarda el escaneo en los tres formatos principales al mismo tiempo (`.txt`, `.xml`, `.gnmap`). |

---
💡 *Cheat Sheet de Nmap creado para referencia rápida en auditorías de red y GitHub.*
