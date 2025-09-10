# veterinariaproject
proyecto de titulo
Veterinaria (Django)

Gestión básica para clínica veterinaria: Clientes, Mascotas, Veterinarios, Agenda (Citas) y Fichas clínicas.
Incluye landing pública simple y estructura para crecer.

🧱 Tecnologías

Python 3.11+

Django 5.x

(Opcional) Django REST Framework en el futuro

Git/GitHub

✅ Requisitos previos

Python y pip instalados

Git instalado

Acceso al repositorio en GitHub (haber aceptado la invitación)

SETUP PRIMERA VEZ
# 1) Clonar repo
git clone https://github.com/TU-USUARIO/TU-REPO.git
cd TU-REPO

# 2) Crear entorno virtual
python -m venv .venv

# 3) Activar venv
# Windows:
.\.venv\Scripts\activate
# macOS/Linux:
# source .venv/bin/activate

# 4) Instalar dependencias
pip install -r requirements.txt

# 5) Variables de entorno
# Windows:
copy .env.example .env
# macOS/Linux:
# cp .env.example .env
# 👉 Edita .env y completa SECRET_KEY (y otros si corresponde)

# 6) Migrar base de datos
python manage.py migrate

# 7) (Opcional) Crear superusuario
python manage.py createsuperuser

# 8) Correr servidor
python manage.py runserver

Flujo de trabajo para el equipo
1) Traer lo último
git checkout main
git pull origin main

2) Crear rama por tarea
git checkout -b feature/nombre-de-la-tarea

3) Trabajar y commitear
git add .
git commit -m "feat: descripción corta del cambio"
git push -u origin feature/nombre-de-la-tarea

4) Abrir Pull Request

Desde GitHub: Compare & pull request → destino main.

Otro compañero revisa y aprueba → Merge.

(Opcional) Reglas de protección: Settings → Branches → proteger main y requerir 1 aprobación.

🔄 Actualizar dependencias

Si instalas un paquete nuevo:

pip install <paquete>
pip freeze > requirements.txt
git add requirements.txt
git commit -m "chore: actualizar requirements"
git push


Tus compañeros después harán:

git pull
pip install -r requirements.txt

🔧 Comandos útiles
# Activar entorno
.\.venv\Scripts\activate            # Windows
# source .venv/bin/activate         # macOS/Linux

# Migraciones
python manage.py makemigrations
python manage.py migrate

# Crear superusuario
python manage.py createsuperuser

# Correr servidor
python manage.py runserver

🆘 Troubleshooting

ModuleNotFoundError: No module named 'app.urls'
Asegúrate de que la app tenga urls.py y que config/urls.py la incluya correctamente.

Error por vista inexistente
Si en app/urls.py apuntas a views.inicio, crea la función inicio en app/views.py (o cambia el nombre).

git push rechazado (divergent histories)
El repo remoto tenía un commit inicial (README). Solución:

git pull --rebase origin main --allow-unrelated-histories
git push


No se ven los cambios
git pull origin main, reinstala dependencias si cambió requirements.txt, y corre python manage.py migrate.
