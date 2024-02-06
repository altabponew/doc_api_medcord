# Introducción

Bienvenido a la API de Alta BPO.

# Autenticación

```python
from requests import request

headers = {
    'Authorization': 'xxxxxxxxx'
}

data = request('{base_url}/url/path', headers=headers)
```

```shell
# With shell, you can just pass the correct header with each request
curl "{base_url}/url/path" \
  -H "Authorization: xxxxxxxxx"
```

```javascript
promise = fetch('{base_url}/url/path', {
    headers: {
        'Authorization': 'xxxxxxxxx'
    }
})
```

> Asegurate de reemplazar `xxxxxxxxx` con su API key.

Nuestra API espera recibir en cada petición un token de autorización el cual será entregado por el área de soporte de
Alta BPO.

La variable {base_url} deberá ser reemplazada con el dominio que use la instancia de Odoo a conectar.

`Authorization: xxxxxxxxx`

<aside class="notice">
Debe reemplazar <code>xxxxxxxxx</code> con su API key.
</aside>

# Tarifas

## Obtener Lista de Tarifas

```python
from requests import request

data = request("{base_url}/web/api/pricelists", headers=headers)
```

```shell
curl "{base_url}/web/api/pricelists" \
  -H "Authorization: xxxxxxxxx"
```

```javascript
promise = fetch('{base_url}/web/api/pricelists', {
    headers: {
        'Authorization': 'xxxxxxxxx'
    }
})
```

> La solicitud devuelve una estructura JSON tal que:

```json
{
  "jsonrpc": "2.0",
  "id": null,
  "result": [
    {
      "code": false,
      "id": 1,
      "item_ids": [],
      "name": "Tarifa pública"
    },
    {
      "code": false,
      "id": 2,
      "item_ids": [
        1
      ],
      "name": "Tarifa Alta BPO"
    }
  ]
}
```

Este endpoint devuelve todas las tarifas.

## Obtener Tarifa

```python
from requests import request

data = request("{base_url}/web/api/pricelists/ID_TARIFA", headers=headers)
```

```shell
curl "{base_url}/web/api/pricelists/1" \
  -H "Authorization: xxxxxxxxx"
```

```javascript
promise = fetch('{base_url}/web/api/pricelists/1', {
    headers: {
        'Authorization': 'xxxxxxxxx'
    }
})
```

> La solicitud devuelve una estructura JSON tal que:

```json
{
  "jsonrpc": "2.0",
  "id": null,
  "result": {
    "code": false,
    "id": 1,
    "item_ids": [
      8
    ],
    "name": "Tarifa pública"
  }
}
```

Este endpoint devuelve la tarifa correspondiente al ID_TARIFA indicado para el ejemplo 1 = Tarifa pública

## Actualizar Tarifa

```python
from requests import request

data = requests.put("{base_url}/web/api/pricelist/ID_LINEA_TARIFA", data={
    "data": {
        "code": "TP",
        "name": "Tarifa pública TEST"
    }
})
```

```shell
curl -H 'Content-Type: application/json' -H "Authorization: xxxxxxxxx" -X PUT -d '{ "data": {
        "code": "TP",
        "name": "Tarifa pública TEST"
    }}' {base_url}/web/api/pricelist/1"`

```

```javascript

const example_put = {
    method: 'PUT',
    headers: {
        'Content-type': 'application/json; charset=UTF-8' // Indicates the content 
    },
    body: JSON.stringify({
        "data": {
            "code": "TP",
            "name": "Tarifa pública TEST"
        }
    })
}

// make the HTTP put request using fetch api
fetch('{base_url}/web/api/pricelist/1', example_put)
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(err => console.log(err))

```

> La solicitud devuelve una estructura JSON tal que:

```json
{
  "jsonrpc": "2.0",
  "id": null,
  "result": {
    "code": "TP",
    "id": 1,
    "item_ids": [
      8
    ],
    "name": "Tarifa pública TEST"
  }
}
```

Este endpoint devuelve la tarifa correspondiente al ID_TARIFA y su estructura actualizada solo es necesario
enviar los parámetros que se necesiten actualizar.

# Líneas de Tarifa

## Obtener Líneas de Tarifas

```python
from requests import request

data = request("{base_url}/web/api/pricelist_items", headers=headers)
```

```shell
curl "{base_url}/web/api/pricelist_items" \
  -H "Authorization: xxxxxxxxx"
```

```javascript
promise = fetch('{base_url}/web/api/pricelist_items', {
    headers: {
        'Authorization': 'xxxxxxxxx'
    }
})
```

> La solicitud devuelve una estructura JSON tal que:

```json
{
  "jsonrpc": "2.0",
  "id": null,
  "result": [
    {
      "fixed_price": 25.5,
      "id": 14,
      "min_quantity": 0.0,
      "pricelist_id": 6,
      "product_tmpl_id": 36
    },
    {
      "fixed_price": 15.0,
      "id": 8,
      "min_quantity": 0.0,
      "pricelist_id": 1,
      "product_tmpl_id": 34
    },
    ...
  ]
}
```

Este endpoint devuelve todas las lineas de tarifas.

## Obtener Línea de Tarifa

```python
from requests import request

data = request("{base_url}/web/api/pricelist_items/ID_LINEA_TARIFA", headers=headers)
```

```shell
curl "{base_url}/web/api/pricelist_items/8" \
  -H "Authorization: xxxxxxxxx"
```

```javascript
promise = fetch('{base_url}/web/api/pricelist_items/8', {
    headers: {
        'Authorization': 'xxxxxxxxx'
    }
})
```

> La solicitud devuelve una estructura JSON tal que:

```json
{
  "jsonrpc": "2.0",
  "id": null,
  "result": {
    "fixed_price": 15.0,
    "id": 8,
    "min_quantity": 0.0,
    "pricelist_id": 1,
    "product_tmpl_id": 34
  }
}
```

Este endpoint devuelve la línea tarifa correspondiente al ID_LINEA_TARIFA indicado para el ejemplo 8.

## Actualizar Línea de Tarifa

```python
from requests import request

data = requests.put("{base_url}/web/api/pricelist_items/ID_LINEA_TARIFA", data={
    "data": {
        "fixed_price": 20.0,
        "min_quantity": 0.0,
        "pricelist_id": 1,
        "product_tmpl_id": 34
    }
})
```

```shell
curl -H 'Content-Type: application/json' -H "Authorization: xxxxxxxxx" -X PUT -d '{ "data": {
        "fixed_price": 20.0,
        "min_quantity": 0.0,
        "pricelist_id": 1,
        "product_tmpl_id": 34
    }}' {base_url}/web/api/pricelist_items/8"`

```

```javascript

const example_put = {
    method: 'PUT',
    headers: {
        'Content-type': 'application/json; charset=UTF-8' // Indicates the content 
    },
    body: JSON.stringify({
        "data": {
            "fixed_price": 20.0,
            "min_quantity": 0.0,
            "pricelist_id": 1,
            "product_tmpl_id": 34
        }
    })
}

// make the HTTP put request using fetch api
fetch('{base_url}/web/api/pricelist_items/8', example_put)
    .then(response => response.json())
    .then(data => console.log(data)) // Manipulate the data retrieved back, if we want to do something with it
    .catch(err => console.log(err)) // Do something with the error

```

> La solicitud devuelve una estructura JSON tal que:

```json
{
  "jsonrpc": "2.0",
  "id": null,
  "result": {
    "fixed_price": 20.0,
    "id": 8,
    "min_quantity": 0.0,
    "pricelist_id": 1,
    "product_tmpl_id": 34
  }
}
```

Este endpoint devuelve la línea tarifa correspondiente al ID_LINEA_TARIFA y su estructura actualizada solo es necesario
enviar los parámetros que se necesiten actualizar.

# Contactos

## Obtener la lista de contactos

```python
from requests import request

data = request("{base_url}/web/api/contacts", headers=headers)
```

```shell
curl "{base_url}/web/api/contacts" \
  -H "Authorization: xxxxxxxxx"
```

```javascript
promise = fetch('{base_url}/web/api/contacts', {
    headers: {
        'Authorization': 'xxxxxxxxx'
    }
})
```

> La solicitud devuelve una estructura JSON tal que:

```json
{
  "jsonrpc": "2.0",
  "id": null,
  "result": [
    {
      "id": 7,
      "name": "ALTA BPO SAC",
      "vat": "20601681839"
    },
    {
      "id": 3,
      "name": "Administrator",
      "vat": false
    },
    ...
  ]
}
```

Este endpoint devuelve todos los contactos.

# Productos

## Obtener la lista de productos

```python
from requests import request

data = request("{base_url}/web/api/products", headers=headers)
```

```shell
curl "{base_url}/web/api/products" \
  -H "Authorization: xxxxxxxxx"
```

```javascript
promise = fetch('{base_url}/web/api/products', {
    headers: {
        'Authorization': 'xxxxxxxxx'
    }
})
```

> La solicitud devuelve una estructura JSON tal que:

```json
{
  "jsonrpc": "2.0",
  "id": null,
  "result": [
    {
      "default_code": false,
      "id": 15,
      "list_price": 25.0,
      "name": "Agudeza visual de lejos y cerca - refracción",
      "standard_price": 0.0
    },
    {
      "default_code": false,
      "id": 3,
      "list_price": 1.0,
      "name": "Ambulancias: Emergencias y eventos",
      "standard_price": 0.0
    },
    ...
  ]
}
```

Este endpoint devuelve todos los productos.

## Obtener Producto

```python
from requests import request

data = request("{base_url}/web/api/products/ID_PRODUCTO", headers=headers)
```

```shell
curl "{base_url}/web/api/products/15" \
  -H "Authorization: xxxxxxxxx"
```

```javascript
promise = fetch('{base_url}/web/api/products/15', {
    headers: {
        'Authorization': 'xxxxxxxxx'
    }
})
```

> La solicitud devuelve una estructura JSON tal que:

```json
{
  "jsonrpc": "2.0",
  "id": null,
  "result": {
    "default_code": false,
    "id": 15,
    "list_price": 25.0,
    "name": "Agudeza visual de lejos y cerca - refracción",
    "standard_price": 0.0
  }
}
```

Este endpoint devuelve el producto correspondiente al ID_PRODUCTO indicado para el ejemplo 15.