# SQL Injection Vulnerable Lab
### ISW-1013 Calidad del Software — Universidad Técnica Nacional

---

> ⚠️ **ADVERTENCIA**: Esta aplicación contiene vulnerabilidades **intencionales**.
> Úsela exclusivamente en entorno local controlado.
> **No exponga este proyecto a Internet.**

---

## Inicio rápido

```bash
# 1. Clonar el repositorio
git clone <URL_DEL_REPOSITORIO>
cd sqli_lab_vulnerable_app

# 2. Crear su rama de trabajo
git checkout -b nombre1_nombre2_nombre3

# 3. Levantar la aplicación
docker compose up --build

# 4. Abrir en el navegador
# http://localhost:5000
```

## Credenciales de prueba

| Usuario  | Contraseña  | Rol   |
|----------|-------------|-------|
| admin    | Admin123    | admin |
| analyst  | Analyst123  | user  |
| student  | Student123  | user  |

## Vulnerabilidades presentes

El archivo `app.py` contiene **8 vulnerabilidades intencionales** documentadas con comentarios. Su tarea es encontrarlas, entender por qué son peligrosas y corregirlas.

| ID   | Tipo                          | Ubicación         |
|------|-------------------------------|-------------------|
| V-01 | SQL Injection – Login         | `app.py` ruta `/login`  |
| V-02 | SQL Injection – Búsqueda      | `app.py` ruta `/search` |
| V-03 | Contraseñas en texto plano    | `app.py` / `init_db()`  |
| V-04 | SECRET_KEY hardcodeada        | `app.py` línea config   |
| V-05 | debug=True activo             | `app.py` al final       |
| V-06 | Exposición de query SQL       | `templates/search.html` |
| V-07 | Menú admin visible a todos    | `templates/layout.html` |
| V-08 | Sin protección CSRF           | Formularios             |

## Estructura del proyecto

```
sqli_lab_vulnerable_app/
├── app.py                  ← Lógica principal (aquí están las vulnerabilidades)
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
├── db/                     ← Base de datos SQLite (se crea automáticamente)
├── templates/
│   ├── layout.html
│   ├── login.html
│   ├── dashboard.html
│   ├── search.html
│   └── admin.html
└── static/
    └── style.css
```

## Detener la aplicación

```bash
docker compose down
```

## Entregar la solución

```bash
git add .
git commit -m "Corrección de vulnerabilidades SQLi"
git push origin nombre1_nombre2_nombre3
```
