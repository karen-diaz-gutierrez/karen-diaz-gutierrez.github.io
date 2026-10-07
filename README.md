# Portafolio — Karen Paola Díaz Gutiérrez

Web de una sola página, estática, sin dependencias ni build. Se abre haciendo doble clic en
`index.html` y funciona igual publicada en cualquier hosting.

---

## 1. Estado actual

| Qué | Estado |
|---|---|
| **LinkedIn** | listo — `linkedin.com/in/karen-diaz-gutierrez`, en 3 sitios |
| **Correo** | `karendjaz5@gmail.com`, en 5 sitios. Para cambiarlo, buscarlo y reemplazarlo |
| **CV en PDF** | **no se publica** — ver abajo |
| **GitHub** | solo infraestructura — **no aparece como enlace** en la web |

### CV y GitHub: decisión tomada

La web **no enlaza ni ofrece el CV para descarga**, y **no muestra ningún enlace a GitHub**
(ni icono en la cabecera, ni fila en contacto, ni en el hero). GitHub se usa únicamente como
repositorio del código y destino de publicación.

Si algún día hay que revertirlo, es trabajo manual: los bloques se eliminaron del HTML, no quedaron
comentados. El CV tampoco debe guardarse en `assets/docs/`, porque todo lo que vive ahí queda
accesible por URL directa aunque no esté enlazado.

---

## 2. Publicar en GitHub Pages

Repositorio de destino (ya configurado como `origin`, **no crear otro**):

```
https://github.com/karen-diaz-gutierrez/portafolio.github.io
```

Rama principal: `main`.

Desde la terminal, en esta carpeta:

```
git push -u origin main
```

En el primer `push` se abre el navegador para iniciar sesión en GitHub una sola vez.

### Activar Pages (hay que hacerlo a mano)

El repositorio se llama `portafolio.github.io`, no `karen-diaz-gutierrez.github.io`, así que para
GitHub es un repositorio de proyecto normal: **Pages no se activa solo**.

1. En el repositorio: **Settings → Pages**
2. **Source**: *Deploy from a branch*
3. **Branch**: `main`, carpeta `/ (root)` → **Save**

La URL resultante es:

```
https://karen-diaz-gutierrez.github.io/portafolio.github.io/
```

> Para que la URL fuera la corta (`https://karen-diaz-gutierrez.github.io`) el repositorio tendría
> que llamarse exactamente `karen-diaz-gutierrez.github.io`. Se mantiene el nombre pedido,
> `portafolio.github.io`, asumiendo la URL larga.

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
│   └── docs/                   cartas de recomendación censuradas (el CV no va aquí)
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
- **CV y GitHub**: no se enlazan desde la web (ver punto 1).

---

## 5. Cambios habituales

**Editar un texto**: abrir `index.html` en el Bloc de notas o en VS Code y buscar la frase.

**Cambiar la foto principal**: sustituir `assets/img/hero-karen.jpg` y `.webp` manteniendo los
nombres. Si el encuadre queda mal, ajustar `object-position` en `.hero-figure img` dentro de
`style.css`.

**Colores**: están todos arriba del todo de `style.css`, en el bloque `:root`.

**Añadir un proyecto**: duplicar un bloque `<article class="project">` completo y cambiar el texto.

---

## 6. QR

Una vez publicada, con la URL definitiva se puede generar un QR que apunte a la web para imprimirlo
en el CV en papel. Eso no implica publicar el CV en la web.
