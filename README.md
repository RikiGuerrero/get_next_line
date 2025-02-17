# get_next_line

![C Language](https://img.shields.io/badge/C-Programming-blue.svg) ![Makefile](https://img.shields.io/badge/Makefile-Build-orange.svg) ![Git](https://img.shields.io/badge/Git-Version%20Control-red.svg) ![Norminette](https://img.shields.io/badge/Norminette-Code%20Style-brightgreen.svg)

## 📌 Descripción

El proyecto **get_next_line** tiene como objetivo implementar una función en C capaz de leer una línea completa desde un descriptor de archivo, manejando múltiples descriptores simultáneamente y gestionando eficientemente la memoria dinámica.

A través de este proyecto, se profundiza en conceptos clave como el uso de variables estáticas, la manipulación de archivos en C y la optimización de la asignación de memoria. Es una excelente oportunidad para mejorar la comprensión sobre buffers, control de flujo de lectura y el funcionamiento de `read()`.

## 🛠 Lenguajes y Tecnologías

- **C**
- **GIT**
- **Makefile**
- **Norminette**
- **File descriptors**
- **Funciones variádicas**

## 💡 Conceptos de Programación Aplicados

- Manipulación de Memoria
- Manejo de Archivos
- Variables Estáticas

## 📂 Estructura del Proyecto

```
get_next_line
├── README.md
├── includes
│   ├── get_next_line.h
│   └── get_next_line_bonus.h
└── src
    ├── bonus
    │   ├── get_next_line_bonus.c
    │   └── get_next_line_utils_bonus.c
    ├── get_next_line.c
    └── get_next_line_utils.c
```

## 🚀 Instalación y Uso

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/RikiGuerrero/get_next_line.git
   cd get_next_line
2. Para usar **get_next_line** en tu proyecto, inclúye el archivo de cabecera:
   ```c
   #include "get_next_line.h"
   ```
   Ejemplo de uso:
   ```c
   #include <fcntl.h>
   #include <stdio.h>
   #include "get_next_line.h"

   int main(void)
   {
     int fd = open("archivo.txt", O_RDONLY);
     if (fd == -1)
       return (1);
     char *line;
     while ((line = get_next_line(fd)))
     {
       printf("%s", line);
       free(line);
     }
     close(fd);
     return (0);
   }
   ```
3. Compilamos el código:
   ```bash
   gcc -Werror -Wextra -Wall main.c src/*.c -Iincludes
   ```
4. Ejecutamos el programa con un **archivo.txt** del que queramos leer su contenido como parametro:
   ```bash
   ./a.out archivo.txt
   ```

## ✅ Normas y Estilo de Código

El código sigue las reglas de la **Norminette**, la herramienta de estilo de 42. Para verificar:
```bash
norminette
```

## 📜 Licencia

Este proyecto es parte del currículo de 42 y sigue las reglas de la escuela.
