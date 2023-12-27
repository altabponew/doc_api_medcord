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

Nuestra API espera recibir en cada petición un token de autorización el cual será entregado por el área de soporte de Alta BPO.

La variable {base_url} deberá ser reemplazada con el dominio que use la instancia de Odoo a conectar.

`Authorization: xxxxxxxxx`

<aside class="notice">
Debe reemplazar <code>xxxxxxxxx</code> con su API key.
</aside>

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
        {
            "id": 1,
            "name": "Medcorp",
            "vat": false
        },
        {
            "id": 8,
            "name": "MedcorpX",
            "vat": false
        },
        {
            "id": 9,
            "name": "vendedor",
            "vat": false
        }
    ]
}
```

Este endpoint devuelve todos los contactos.


# Tarifas

## Obtener la lista de tarifas

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