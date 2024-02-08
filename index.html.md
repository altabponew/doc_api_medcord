# INTRODUCCIÓN

Bienvenido a la API de Alta BPO.

# AUTORIZACIÓN

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

# CLIENTES

## Lista de clientes

```python
from requests import request

data = request("{base_url}/web/api/contacts", headers=headers)
```

```shell
curl "{base_url}/web/api/clientes" \
  -H "Authorization: xxxxxxxxx"
```

```javascript
promise = fetch('{base_url}/web/api/clientes', {
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
      "commercial_name": false,
      "id": 7,
      "name": "ALTA BUSINESS PROCESS OUTSOURCING S.A.C.",
      "type_customer": "2",
      "ubigeo_departament": "15",
      "ubigeo_district": "15",
      "ubigeo_province": "0",
      "vat": "20601681839"
    },
    {
      "commercial_name": "ROSA FRANCIA",
      "id": 12,
      "name": "ROSA EFE MODA S.A.C.",
      "type_customer": "occupational_health",
      "ubigeo_departament": "15",
      "ubigeo_district": "22",
      "ubigeo_province": "0",
      "vat": "20510089368"
    }
  ]
}
```

Este endpoint devuelve todos los clientes que tengan una pre-cotización asociada a una orden de venta confirmada.

# TARIFARIOS

## Lista de tarifarios

```python
from requests import request

data = request("{base_url}/web/api/contacts", headers=headers)
```

```shell
curl "{base_url}/web/api/tarifarios" \
  -H "Authorization: xxxxxxxxx"
```

```javascript
promise = fetch('{base_url}/web/api/tarifarios', {
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
      "id": 10,
      "name": "ALTA BUSINESS PROCESS OUTSOURCING S.A.C._1",
      "lines": [
        {
          "id": 28,
          "code": "0123",
          "name": "Evaluación psicológica básica",
          "price": 25.0
        },
        {
          "id": 27,
          "code": false,
          "name": "Psicosensométrico",
          "price": 15.0
        }
      ]
    },
    {
      "id": 9,
      "name": "ROSA EFE MODA S.A.C._3",
      "lines": [
        {
          "id": 26,
          "code": "001",
          "name": "Examen 1",
          "price": 17.82
        },
        {
          "id": 25,
          "code": "002",
          "name": "Examen 2",
          "price": 12.15
        },
        {
          "id": 24,
          "code": "003",
          "name": "Examen 3",
          "price": 22.95
        },
        {
          "id": 23,
          "code": false,
          "name": "Perfil de Conducta",
          "price": 36.0
        }
      ]
    }
  ]
}
```

Este endpoint devuelve todos los tarifarios que tengan una pre-cotización asociada a una orden de venta confirmada.

# PERFILES

## Lista de perfiles

```python
from requests import request

data = request("{base_url}/web/api/perfiles", headers=headers)
```

```shell
curl "{base_url}/web/api/perfiles" \
  -H "Authorization: xxxxxxxxx"
```

```javascript
promise = fetch('{base_url}/web/api/perfiles', {
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
      "code": 11,
      "name": "ALTA BUSINESS PROCESS OUTSOURCING S.A.C._2",
      "lines": [
        {
          "exam_code": false,
          "exam_name": "Test de Epworth",
          "exam_price": 27.0
        },
        {
          "exam_code": false,
          "exam_name": "Agudeza visual de lejos y cerca - refracción",
          "exam_price": 22.5
        }
      ]
    },
    {
      "code": 10,
      "name": "ALTA BUSINESS PROCESS OUTSOURCING S.A.C._1",
      "lines": [
        {
          "exam_code": "0123",
          "exam_name": "Evaluación psicológica básica",
          "exam_price": 25.0
        },
        {
          "exam_code": false,
          "exam_name": "Psicosensométrico",
          "exam_price": 15.0
        }
      ]
    },
    {
      "code": 9,
      "name": "ROSA EFE MODA S.A.C._3",
      "lines": [
        {
          "exam_code": "001",
          "exam_name": "Examen 1",
          "exam_price": 17.82
        },
        {
          "exam_code": "002",
          "exam_name": "Examen 2",
          "exam_price": 12.15
        },
        {
          "exam_code": "003",
          "exam_name": "Examen 3",
          "exam_price": 22.95
        },
        {
          "exam_code": "004",
          "exam_name": "Examen 4",
          "exam_price": 36.0
        }
      ]
    }
  ]
}
```

Este endpoint devuelve todos los perfiles que tengan una pre-cotización asociada a una orden de venta confirmada.