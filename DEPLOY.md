# Protocolo de despliegue - somorrostrobeach.com

## Requisitos previos

- Hugo instalado (`brew install hugo`)
- lftp instalado (`brew install lftp`)
- Credenciales FTP del hosting

## Pasos para desplegar

### 1. Verificar cambios localmente

```bash
cd "/Users/pablo/Library/Mobile Documents/com~apple~CloudDocs/ICM/somorrostrobeach/site"
hugo server
```

Abre http://localhost:1313 y verifica que todo se ve bien.
Presiona `Ctrl+C` para detener el servidor.

### 2. Generar el sitio de producción

```bash
rm -rf public
hugo --minify
```

Esto genera la carpeta `public/` con las URLs correctas (usando `baseURL` de `hugo.yaml`).

### 3. Subir al hosting

#### Opción A: Con lftp (recomendado)

```bash
lftp -u USUARIO,PASSWORD ftp://SERVIDOR <<EOF
set ssl:verify-certificate no
mirror -R --verbose --delete public/ /public_html/
quit
EOF
```

Reemplaza:
- `USUARIO` - tu usuario FTP
- `PASSWORD` - tu contraseña FTP
- `SERVIDOR` - hostname FTP (ej: `ftp.somorrostrobeach.com` o IP del servidor)

#### Opción B: Con Cyberduck/FileZilla

1. Conecta al servidor FTP
2. Navega a `public_html/`
3. Sube todo el contenido de la carpeta `public/`

### 4. Verificar el despliegue

1. Abre https://www.somorrostrobeach.com
2. Limpia caché del navegador si es necesario (`Cmd+Shift+R`)
3. Verifica que los enlaces del menú funcionan

## Comando rápido (todo en uno)

```bash
cd "/Users/pablo/Library/Mobile Documents/com~apple~CloudDocs/ICM/somorrostrobeach/site" && \
rm -rf public && \
hugo --minify && \
lftp -u USUARIO,PASSWORD ftp://SERVIDOR -e "set ssl:verify-certificate no; mirror -R --verbose --delete public/ /public_html/; quit"
```

## Notas importantes

- **NO uses** la carpeta `public/` generada mientras `hugo server` está corriendo (usa `localhost:1313`)
- **Siempre** regenera con `hugo --minify` antes de subir
- El flag `--delete` en lftp elimina archivos remotos que ya no existen localmente

---

## Gestión de contenido dinámico

### Publicaciones

Las publicaciones se gestionan como archivos individuales en `content/publications/papers/`. El sistema las agrupa automáticamente por año y permite búsqueda.

#### Añadir una nueva publicación

Crear un archivo `.md` en `content/publications/papers/` con el siguiente formato:

```yaml
---
title: "Título del paper"
date: 2024-06-01          # Fecha de publicación (YYYY-MM-DD)
type: paper               # "paper" o "preprint"
authors:
  - "Apellido, N."
  - "Sánchez, P."         # Tu nombre se resalta automáticamente
  - "Otro, A."
journal: "Nombre de la Revista"
volume: "12(3)"           # Opcional
pages: "123-456"          # Opcional
doi: "10.1000/ejemplo"
link: "https://doi.org/10.1000/ejemplo"
---
```

**Convención de nombres:** `apellido-año-keyword.md` (ej: `sanchez-2024-metagenomes.md`)

#### Características automáticas

- Agrupación por año
- Buscador por título, autores y revista
- Tu nombre resaltado en negrita
- Pre-prints con estilo diferenciado (borde naranja)

### Proyectos

Los proyectos se leen automáticamente del directorio `content/projects/`.

#### Añadir un nuevo proyecto

1. Crear carpeta: `content/projects/nombre-proyecto/`
2. Crear archivo `index.md` dentro:

```yaml
---
title: "Nombre del Proyecto"
description: "Descripción breve que aparece en la tarjeta del índice."
weight: 4                 # Orden en el índice (1 = primero)
tags:
  - "Tag1"
  - "Tag2"
  - "Tag3"
cover:
    image: "/images/proyecto/imagen.jpg"
    alt: "Nombre del Proyecto"
---

## Contenido del proyecto aquí...
```

3. Añadir imagen en `static/images/proyecto/`

#### Estructura de archivos

```
content/
├── publications/
│   ├── _index.md              # Configuración de la sección
│   └── papers/                # Archivos individuales de papers
│       ├── sanchez-2024-metagenomes.md
│       ├── paoli-2022-biosynthetic.md
│       └── ...
└── projects/
    ├── _index.md              # Configuración (incluye sección GitHub)
    ├── polaromics/
    │   └── index.md
    ├── malaspina/
    │   └── index.md
    └── tara-oceans/
        └── index.md
```

### Layouts personalizados

Los layouts que generan las vistas dinámicas están en:

- `layouts/publications/list.html` - Lista de publicaciones con buscador
- `layouts/projects/list.html` - Grid de proyectos con tarjetas

Los estilos CSS están en `assets/css/extended/custom.css`.
