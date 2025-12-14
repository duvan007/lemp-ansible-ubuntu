Saludos. 
# Servidor LEMP Automatizado con Ansible (Ubuntu 24.04)

[![Ansible](https://img.shields.io/badge/Ansible-2.14+-ee0000?logo=ansible)](https://www.ansible.com)
[![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04_LTS-E95420?logo=ubuntu)](https://ubuntu.com)
[![Nginx](https://img.shields.io/badge/Nginx-1.24-009639?logo=nginx)](https://nginx.org)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

Proyecto de automatización que instala y configura una pila **LEMP** (Linux, Nginx, MariaDB, PHP 8.3) en Ubuntu 24.04 mediante Ansible. Incluye página de prueba PHP y opción para certificado SSL gratuito con Let’s Encrypt.

Ideal como proyecto de portafolio para posiciones de **DevOps Junior**, **SysAdmin** o **Administrador de Sistemas Linux**.

## Diagrama de Arquitectura

```mermaid
graph TD
    A[Ansible Control Node] --> |Ejecuta playbook| B[Servidor Ubuntu 24.04]
    B --> C[Nginx Web Server]
    B --> D[MariaDB Database]
    B --> E[PHP 8.3 + FPM]
    B --> G["Página info.php de prueba"]



Características
instalación completa con un solo comando Ansible
Actualización segura del sistema
Configuración básica de Nginx y PHP-FPM
Página de prueba info.php para verificar funcionamiento

Requisitos

Máquina control (donde ejecutas Ansible): Ubuntu 22.04+ con Ansible instalado
Servidor objetivo: Ubuntu 24.04 LTS (puede ser localhost, VM o VPS)
Acceso root/sudo en el servidor objetivo

Instalación Rápida

1. Clona el repositorio
git clone https://github.com/TU_USUARIO/lemp-ansible-ubuntu.git
cd lemp-ansible-ubuntu

2. (Opcional) Edita variables en roles/lemp/vars/main.yml:
domain: tu-dominio.com
email: tu@email.com

3. Ejecuta el playbook:
ansible-playbook playbook.yml

Verificación

Accede vía navegador: http://IP_DEL_SERVIDOR/info.php
Si configuraste SSL: https://tu-dominio.com/info.php

Estructura del Proyecto

.
├── ansible.cfg              ← Configuración local de Ansible
├── inventory.ini            ← Inventario (localhost por defecto)
├── playbook.yml             ← Playbook principal
├── roles/
│   └── lemp/
│       ├── tasks/main.yml   ← Tareas principales
│       ├── handlers/main.yml← Handlers (reinicios)
│       └── vars/main.yml    ← Variables configurables
├── docs/                    ← Documentación adicional (opcional)
└── README.md

Mejoras Futuras (Ideas)

Integración con UFW/Firewall
Configuración de sitio virtual Nginx personalizado
Instalación de WordPress automatizada
Hardening de seguridad (CIS benchmarks)

Autor: Jorge Duvan Velasquez Ramirez
GitHub: @duvan007
Última actualización: Diciembre 2025

Deberías ver la página de información de PHP funcionando.
