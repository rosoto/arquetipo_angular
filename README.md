# Arqutipo_Angular

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 14.2.12.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
##

# Image Compression in Angular using Compressorjs Nov_2023

Este componente demuestra cómo implementar la compresión de imágenes en una aplicación Angular utilizando la librería `compressorjs`.

## ImageCompressorComponent

El `ImageCompressorComponent` es un servicio inyectable que proporciona funcionalidad para comprimir imágenes.

### Funcionalidad

- Compresión de imágenes utilizando `compressorjs`.
- Configuración de calidad, ancho máximo, alto máximo y tamaño de conversión.
- Devuelve un `Blob` de la imagen comprimida.

### Uso

Para utilizar este componente, inyecte `ImageCompressorComponent` en su componente y llame al método `compressImage(file: File)`.

## UploadImageComponent

El `UploadImageComponent` permite a los usuarios cargar y comprimir imágenes, y luego descargar la versión comprimida.

### Proceso

1. El usuario selecciona un archivo de imagen usando el input de tipo archivo.
2. `onFileChange` se activa al cambiar el archivo, llamando a `compressImage` del servicio `ImageCompressorComponent`.
3. El blob de imagen comprimido se almacena y está listo para descargarse.

### Descarga de Imágenes Comprimidas

- Al hacer clic en el botón "Descargar Comprimido", se activa `downloadCompressedImage`.
- Este método crea un enlace para descargar el blob de imagen comprimido.

## Código de Ejemplo

A continuación se muestra un ejemplo básico de cómo se utiliza `ImageCompressorComponent` en `UploadImageComponent`:

```typescript
// Ejemplo del método onFileChange en UploadImageComponent
onFileChange(event: any): void {
  const file = event.target.files[0];
  if (!file) {
    return;
  }
  this.imageCompressor.compressImage(file).then(compressedBlob => {
    this.compressedBlob = compressedBlob;
  }).catch(err => {
    console.error('Compression error: ', err.message);
  });
}
```

## Instalación compressorjs

```code 

npm install compressorjs


