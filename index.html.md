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
            "codigo": 11,
            "nombre": "ALTA BUSINESS PROCESS OUTSOURCING S.A.C._2",
            "examnes": [
                {
                    "codigo_examen": "897",
                    "nombre_examen": "Test de Epworth",
                    "precio_examen": 27.0
                },
                {
                    "codigo_examen": false,
                    "nombre_examen": "Agudeza visual de lejos y cerca - refracción",
                    "precio_examen": 22.5
                }
            ]
        },
        {
            "codigo": 10,
            "nombre": "ALTA BUSINESS PROCESS OUTSOURCING S.A.C._1",
            "examnes": [
                {
                    "codigo_examen": "0123",
                    "nombre_examen": "Evaluación psicológica básica",
                    "precio_examen": 25.0
                },
                {
                    "codigo_examen": false,
                    "nombre_examen": "Psicosensométrico",
                    "precio_examen": 15.0
                }
            ]
        },
        {
            "codigo": 9,
            "nombre": "ROSA EFE MODA S.A.C._3",
            "examnes": [
                {
                    "codigo_examen": "001",
                    "nombre_examen": "Examen 1",
                    "precio_examen": 17.82
                },
                {
                    "codigo_examen": "002",
                    "nombre_examen": "Examen 2",
                    "precio_examen": 12.15
                },
                {
                    "codigo_examen": "003",
                    "nombre_examen": "Examen 3",
                    "precio_examen": 22.95
                },
                {
                    "codigo_examen": "004",
                    "nombre_examen": "Examen 4",
                    "precio_examen": 36.0
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
            "codigo_perfil": 41,
            "codigo_cliente": 12,
            "nombre_perfil": "C1.V2_ADM_OPE#PERFIL ADMINSTRATIVO",
            "codigo_chequeo": false,
            "codigo_tarifario": 9,
            "examenes": [
                {
                    "codigo_examen": "001",
                    "nombre_examen": "Examen 1",
                    "precio_examen": 19.8
                },
                {
                    "codigo_examen": "004",
                    "nombre_examen": "Examen 4",
                    "precio_examen": 40.0
                }
            ]
        },
        {
            "codigo_perfil": 40,
            "codigo_cliente": 12,
            "nombre_perfil": "C1_ADM_OPE#PERFIL ADMINISTRATIVO",
            "codigo_chequeo": false,
            "codigo_tarifario": 9,
            "examenes": [
                {
                    "codigo_examen": "001",
                    "nombre_examen": "Examen 1",
                    "precio_examen": 19.8
                },
                {
                    "codigo_examen": "002",
                    "nombre_examen": "Examen 2",
                    "precio_examen": 13.5
                },
                {
                    "codigo_examen": "003",
                    "nombre_examen": "Examen 3",
                    "precio_examen": 25.5
                }
            ]
        },
        {
            "codigo_perfil": 43,
            "codigo_cliente": 7,
            "nombre_perfil": "Perfil Administrador 006",
            "codigo_chequeo": false,
            "codigo_tarifario": 10,
            "examenes": [
                {
                    "codigo_examen": "0123",
                    "nombre_examen": "Evaluación psicológica básica",
                    "precio_examen": 25.0
                },
                {
                    "codigo_examen": false,
                    "nombre_examen": "Psicosensométrico",
                    "precio_examen": 15.0
                }
            ]
        },
        {
            "codigo_perfil": 42,
            "codigo_cliente": 7,
            "nombre_perfil": "Perfil Operativo 007",
            "codigo_chequeo": false,
            "codigo_tarifario": 10,
            "examenes": [
                {
                    "codigo_examen": "0123",
                    "nombre_examen": "Evaluación psicológica básica",
                    "precio_examen": 25.0
                }
            ]
        }
    ]
}
```

Este endpoint devuelve todos los perfiles que tengan una pre-cotización asociada a una orden de venta confirmada.