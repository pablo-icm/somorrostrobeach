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
