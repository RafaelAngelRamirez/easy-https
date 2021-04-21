# easy-https

> Certificados para desarrollo en local.

Funcionan para crear un servidor de desarrollo en express, o angular. Esto no es mágico.

### Instalación

`npm i @codice-progressio/easy-https --save-dev`

### Express

Agrega una excepción para cargar el certificado.

``` typescript 
if (process.env.NODE_ENV === "production") {
    app.listen(process.env.PORT, ...)
  } else {
    // Https en local  
    https
      .createServer(
        {
          key: fs.readFileSync(
            "./node_modules/@codice-progressio/easy-https/cert/desarrollo.key"
          ),
          cert: fs.readFileSync(
            "./node_modules/@codice-progressio/easy-https/cert/desarrollo.crt"
          ),
        },
        app
      )
      .listen(process.env.PORT, ...)
  }

```

### Angular

Modifica el script de inicio para desarrollo señalando a `desarrollo.key` y `desarrollo.csr`

`package.json` para windows

``` json
"scripts": {
    "start-local": "ng serve -o
        --ssl true
        --ssl-key .\\node_modules\\@codice-progressio\\easy-https\\cert\\desarrollo.key
        --ssl-cert .\\node_modules\\@codice-progressio\\easy-https\\cert\\desarrollo.crt",
}
```

### Ajuste a tu navegador

Instala `ca.pem` en la pestaña de autoridades de certificadoras de confianza de tu navegador o sistema operativo para que los certificados sean validos.

### Configuraciones.

Actualmente el certificado trabaja con las siguientes ip:

- https://127.0.0.1
- https://192.168.1.170
- https://192.168.1.52

# Disclaimer

Este certificado no se debe usar bajo ninguna circunstancia en modo producción. Las claves de cifrado estan expuestas en este repositorio, lo que lo vuelve completamente vulnerable.
