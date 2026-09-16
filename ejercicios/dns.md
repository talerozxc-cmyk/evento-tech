# E2 — DNS Archaeology

## Objetivo

Investigar cómo funciona DNS usando `nslookup` y consultar los registros de tres sitios web.

## 1. Bancolombia

Comando utilizado:

```text
nslookup -debug bancolombia.com
```

Resultados principales:

* Servidor DNS utilizado: `gpon.net`
* Dirección del servidor DNS: `fe80::1`
* IPv4:

  * `45.60.241.99` — TTL: `3360` segundos (56 minutos)
  * `45.60.251.99` — TTL: `3360` segundos (56 minutos)
* No se obtuvo registro IPv6 (AAAA).

## 2. Google

Comando utilizado:

```text
nslookup -debug google.com
```

Resultados principales:

* IPv4:

  * `74.125.141.101` — TTL: `258` segundos (4 minutos 18 segundos)
  * `74.125.141.139` — TTL: `258` segundos
  * `74.125.141.100` — TTL: `258` segundos
  * `74.125.141.113` — TTL: `258` segundos
  * `74.125.141.102` — TTL: `258` segundos
  * `74.125.141.138` — TTL: `258` segundos
* IPv6:

  * `2800:3f0:4005:418::200e` — TTL: `111` segundos (1 minuto 51 segundos)

## 3. Mi sitio de GitHub Pages

Dominio consultado:

```text
talerozxc-cmyk.github.io
```

Comando utilizado:

```text
nslookup -debug talerozxc-cmyk.github.io
```

Resultados principales:

* IPv4:

  * `185.199.111.153` — TTL: `3600` segundos (1 hora)
  * `185.199.108.153` — TTL: `3600` segundos
  * `185.199.110.153` — TTL: `3600` segundos
  * `185.199.109.153` — TTL: `3600` segundos
* IPv6:

  * `2606:50c0:8003::153` — TTL: `3600` segundos
  * `2606:50c0:8000::153` — TTL: `3600` segundos
  * `2606:50c0:8002::153` — TTL: `3600` segundos
  * `2606:50c0:8001::153` — TTL: `3600` segundos

## ¿Qué aprendí?

DNS permite traducir un nombre de dominio, como `google.com`, a una dirección IP que puede utilizarse para localizar el servicio en la red.

El **TTL (Time To Live)** indica durante cuánto tiempo una respuesta DNS puede mantenerse en caché antes de necesitar una nueva consulta.

También observé que un mismo dominio puede tener varias direcciones IP y puede contar tanto con registros IPv4 como IPv6.

## Conclusión

El ejercicio permitió comprobar directamente cómo DNS relaciona los nombres de dominio con direcciones IP y cómo los valores de TTL pueden variar entre diferentes dominios.
