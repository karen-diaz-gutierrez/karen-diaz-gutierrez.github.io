# Portafolio — Karen Paola Díaz Gutiérrez

Web de una sola página, estática, sin dependencias ni build. Se abre haciendo doble clic en
`index.html` y funciona igual publicada en cualquier hosting.

---

## 1. Estado actual

| Qué | Estado |
|---|---|
| **LinkedIn** | listo — `linkedin.com/in/karen-diaz-gutierrez`, en 3 sitios |
| **GitHub** | listo — `github.com/karen-diaz-gutierrez`, en 3 sitios |
| **Correo** | `karendjaz5@gmail.com`, en 5 sitios. Para cambiarlo, buscarlo y reemplazarlo |
| **CV en PDF** | **pendiente** — los botones están ocultos, ver abajo |

### Reactivar el CV

Los tres botones de "Descargar CV" están comentados porque el QR de esta web vive *dentro* del CV,
así que de momento no aporta. Para volver a activarlos:

1. Guardar el PDF como `assets/docs/CV-Karen-Diaz-Gutierrez.pdf`
2. En `index.html`, buscar `CV-PENDIENTE` y quitar las marcas de comentario `<!--` y `-->`
   que rodean el bloque
3. El botón del hero se cambió por uno de "Contactar"; si quieres el de CV ahí también,
   hay que volver a añadirlo

---

## 2. Publicar en GitHub Pages

El repositorio tiene que llamarse exactamente `karen-diaz-gutierrez.github.io` dentro de la cuenta
`karen-diaz-gutierrez`. Ese nombre exacto es lo que hace que la URL sea
`https://karen-diaz-gutierrez.github.io` y no una ruta larga.

1. En GitHub (con la cuenta `karen-diaz-gutierrez`): **New repository**
2. **Repository name**: `karen-diaz-gutierrez.github.io`
3. **Public**, sin README ni .gitignore — tiene que quedar vacío
4. **Create repository**

Y desde la terminal, en esta carpeta:

```
git push -u origin main
```

El remote ya está configurado. En el primer `push` se abre el navegador para iniciar sesión
en GitHub una sola vez.

En repositorios con ese nombre, Pages se activa solo: en 1–2 minutos la web está en línea.

### Actualizar la web más adelante

Después de cambiar cualquier archivo:

```
cd "C:\Users\karen\Desktop\Pagina Web\sitio"
git add .
git commit -m "describe el cambio"
git push
```

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
