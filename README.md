# UPIITA utilidades de LaTeX

## Portadas/templates

- [Portada simple](portada-simple): Portada para trabajos comúnes, del día a día. No tiene mucho formato, pero se ve elegante.

...más cosas por agregar después...

Todo el source code está bajo la licencia GPLv3, entonces eres libre de modificar lo que sea siempre y cuando lo que hagas lo liberes con la misma licencia.

## Comandos de utilidad

### Conversiones a PDF

- Convertir todas las imágenes a PDF

```
convert *.jpg tarea_Velasco_Guzman.pdf
```

- Convertir todas las imágenes a PDF y agregar portada al inicio

```
convert *.jpg tarea.tmp.pdf && pdfunite portada.pdf tarea.tmp.pdf tarea_Velasco_Guzman.pdf && rm tarea.tmp.pdf
```

### Compresiones del PDF

```
gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/prepress -dNOPAUSE -dQUIET -dBATCH -sOutputFile=compressed.pdf input.pdf
```

Opciones de `-dPDFSETTINGS`

- `dPDFSETTINGS=/screen` lower quality, smaller size. (**72 dpi**)

- `dPDFSETTINGS=/ebook` for better quality, but slightly larger pdfs. (**150 dpi**)

- `dPDFSETTINGS=/prepress` output similar to Acrobat Distiller "Prepress Optimized" setting (**300 dpi**)

- `dPDFSETTINGS=/printer` selects output similar to the Acrobat Distiller "Print Optimized" setting (**300 dpi**)

- `dPDFSETTINGS=/default` selects output intended to be useful across a wide variety of uses, possibly at the expense of a larger output file


Ver [pregunta](https://askubuntu.com/questions/113544/how-can-i-reduce-the-file-size-of-a-scanned-pdf-file) de AskUbuntu.


### Dependencias requeridas y explicaciones

- [`convert`](https://imagemagick.org/script/convert.php) es una utilidad de ImageMagick para convertir entre formatos. Para instalar: `dnf install ImageMagick`

- [`pdfunite`](https://fedoramagazine.org/pdf-modification-tools-fedora/) es una utilidad de Poppler utils para unir PDFs. Para instalar: `dnf install poppler-utils`

- [`ghostscript`](https://www.ghostscript.com/) es una utilidad para  trabajar con archivos PDF. **Pro Tip**: Ve los videos de *Computerphile* respecto a los PDF's para entender cómo almacenan y representan información.

Aguas con comandos como el siguiente

```
convert *.jpg tarea.pdf
```

Pues el glob pattern puede ser tratado de diferente forma si tienes una shell extraña.