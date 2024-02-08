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
      "codigo": 7,
      "tipo_cliente": 2,
      "nro_ruc": "20601681839",
      "razon_social": "ALTA BUSINESS PROCESS OUTSOURCING S.A.C.",
      "nombre_comercial": false,
      "ubigeo_departamento": "15",
      "ubigeo_provincia": "0",
      "ubigeo_distrito": "15"
    },
    {
      "codigo": 12,
      "tipo_cliente": 1,
      "nro_ruc": "20510089368",
      "razon_social": "ROSA EFE MODA S.A.C.",
      "nombre_comercial": "ROSA FRANCIA",
      "ubigeo_departamento": "15",
      "ubigeo_provincia": "0",
      "ubigeo_distrito": "22"
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
      "code": 41,
      "customer_code": 12,
      "name": "C1.V2_ADM_OPE#PERFIL ADMINSTRATIVO",
      "type_check_code": false,
      "rate_code": 9,
      "detail_exams": [
        {
          "code_exam": 82,
          "name_exam": "Examen 1",
          "price_exam": 19.8
        },
        {
          "code_exam": 83,
          "name_exam": "Examen 4",
          "price_exam": 40.0
        }
      ]
    },
    {
      "code": 40,
      "customer_code": 12,
      "name": "C1_ADM_OPE#PERFIL ADMINISTRATIVO",
      "type_check_code": false,
      "rate_code": 9,
      "detail_exams": [
        {
          "code_exam": 79,
          "name_exam": "Examen 1",
          "price_exam": 19.8
        },
        {
          "code_exam": 80,
          "name_exam": "Examen 2",
          "price_exam": 13.5
        },
        {
          "code_exam": 81,
          "name_exam": "Examen 3",
          "price_exam": 25.5
        }
      ]
    },
    {
      "code": 43,
      "customer_code": 7,
      "name": "Perfil Administrador 006",
      "type_check_code": false,
      "rate_code": 10,
      "detail_exams": [
        {
          "code_exam": 85,
          "name_exam": "Evaluación psicológica básica",
          "price_exam": 25.0
        },
        {
          "code_exam": 86,
          "name_exam": "Psicosensométrico",
          "price_exam": 15.0
        }
      ]
    },
    {
      "code": 42,
      "customer_code": 7,
      "name": "Perfil Operativo 007",
      "type_check_code": false,
      "rate_code": 10,
      "detail_exams": [
        {
          "code_exam": 84,
          "name_exam": "Evaluación psicológica básica",
          "price_exam": 25.0
        }
      ]
    }
  ]
}
```

Este endpoint devuelve todos los perfiles que tengan una pre-cotización asociada a una orden de venta confirmada.