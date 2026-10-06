# Portafolio — Karen Paola Díaz Gutiérrez

Web de una sola página, estática, sin dependencias ni build. Se abre haciendo doble clic en
`index.html` y funciona igual publicada en cualquier hosting.

---

## 1. Antes de publicar: 4 cosas por cambiar

Están marcadas para que sean fáciles de encontrar.

| Qué | Dónde | Cómo encontrarlo |
|---|---|---|
| **LinkedIn** | `index.html` — 3 sitios | buscar `CAMBIAR-USUARIO` |
| **GitHub** | `index.html` — 3 sitios | buscar `CAMBIAR-USUARIO` |
| **CV en PDF** | falta el archivo | guardarlo como `assets/docs/CV-Karen-Diaz-Gutierrez.pdf` |
| **Correo** | `index.html` — 5 sitios | buscar `karendjaz5@gmail.com` (cámbialo si prefieres otro) |

Para comprobar que no queda ninguno sin cambiar:

```
findstr /n "CAMBIAR-USUARIO" index.html
```

---

## 2. Publicar en GitHub Pages

### Opción A — repositorio personal (URL más corta y limpia)

La URL queda `https://TU-USUARIO.github.io`.

1. En GitHub: **New repository**, con el nombre exacto `TU-USUARIO.github.io` (tu usuario literal),
   público, sin README.
2. Sube **el contenido de esta carpeta** (no la carpeta en sí): `index.html` tiene que quedar en la
   raíz del repositorio. Se puede arrastrar todo a la página de subida de GitHub.
3. **Settings → Pages**: en *Source* elige `Deploy from a branch`, rama `main`, carpeta `/ (root)`.
4. En 1–2 minutos está en línea.

### Opción B — repositorio con nombre propio

La URL queda `https://TU-USUARIO.github.io/portafolio`.

Igual que la opción A, pero el repositorio puede llamarse como quieras (por ejemplo `portafolio`).

### Desde la terminal

```
cd "C:\Users\karen\Desktop\Pagina Web\sitio"
git init
git add .
git commit -m "Portafolio profesional"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/TU-REPO.git
git push -u origin main
```

Después, **Settings → Pages** como en el paso 3.

---

## 3. Qué hay dentro

```
sitio/
├── index.html                  todo el contenido de la página
├── .nojekyll                   evita que GitHub Pages procese los archivos
├── assets/
│   ├── css/style.css           estilos
│   ├── js/main.js              menú, navegación activa, aparición al hacer scroll
│   ├── favicon.svg             icono de la pestaña
│   ├── img/                    fotos optimizadas (.jpg + .webp, ~3,8 MB en total)
│   └── docs/                   cartas de recomendación (y aquí va el CV)
```

Cada foto está en dos formatos: `.webp` (la que cargan los navegadores modernos, pesa la mitad)
y `.jpg` como respaldo. Si cambias una, cambia las dos o quita la línea `<source>` correspondiente.

---

## 4. Decisiones de privacidad ya aplicadas

- **Cartas de recomendación**: los PDF publicados en `assets/docs/` son **copias censuradas**. Se
  taparon los correos y teléfonos de las tres personas que firman. Se conservan nombre, cargo y
  empresa. En las dos cartas de texto el dato se eliminó del archivo, no solo se tapó visualmente;
  la de Javier Roblero se rasterizó para que no quede capa recuperable. Los originales siguen
  intactos en `Cartas de recomendación/`.
- **Certificados**: solo aparecen como texto. No se publicó el PDF del TOEFL (contiene fecha de
  nacimiento, dirección y parte del número de pasaporte) ni el diploma de Ipartek (contiene número
  de documento).
- **Fotos de Aspen Technology**: no se usan capturas de herramientas ni información de proyectos de
  cliente. La sección se apoya en un diagrama propio.

---

## 5. Cambios habituales

**Editar un texto**: abrir `index.html` en el Bloc de notas o en VS Code y buscar la frase.

**Cambiar la foto principal**: sustituir `assets/img/hero-karen.jpg` y `.webp` manteniendo los
nombres. Si el encuadre queda mal, ajustar `object-position` en `.hero-figure img` dentro de
`style.css`.

**Colores**: están todos arriba del todo de `style.css`, en el bloque `:root`.

**Añadir un proyecto**: duplicar un bloque `<article class="project">` completo y cambiar el texto.

---

## 6. QR para el CV

Una vez publicada, con la URL definitiva se puede generar un QR que apunte a la web para
imprimirlo en el CV.
