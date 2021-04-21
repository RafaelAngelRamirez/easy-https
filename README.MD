# easy-https

> Certificados para desarrollo en local.

Funcionan para crear un servidor de desarrollo en express, o angular. Esto no es mágico.

### Instalación

`npm i @codice-progressio/easy-https`

### Express

Agrega una excepción para cargar el certificado.

### Angular

Modifica el script de inicio para desarrollo señalando a `desarrollo.key` y `desarrollo.csr`

### Ajuste a tu navegador

Instala `ca.pem` en la pestaña de autoridades de certificadoras de confianza de tu navegador o sistema operativo para que los certificados sean validos.

### Configuraciones.

Actualmente el certificado trabaja con las siguientes ip:

- https://127.0.0.1
- https://192.168.1.149

# Disclaimer

Este certificado no se debe usar bajo ninguna circunstancia en modo producción. Las claves de cifrado estan expuestas en este repositorio, lo que lo vuelve completamente vulnerable.
