ignasi.md
Començo a una instal"lació d'Ubuntu un projecte de Django baixat des de Github.
És un blog d'un desenvolupador en Django.

# Començo des de Django Tailwind Blog
git clone https://github.com/ashish-makes/django-tailwind-blog.git
Escurço el nom
mv django-tailwind-blog/ django-blog

# Entorn virtual Python
python3 -m venv .venv
source .venv/bin/activate
 
# Instal·lació del projecte
pip install -r requirements.txt

Com que falta un paquet
sudo apt install libpq-dev 

# Tailwind
pip install django-tailwind

python manage.py tailwind init
python manage.py tailwind install

# Ups falta node!!!
# installs nvm (Node Version Manager)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

# download and install Node.js (you may need to restart the terminal)
nvm install 20

# verifies the right Node.js version is in the environment
node -v # should print `v20.15.0`

# verifies the right NPM version is in the environment
npm -v # should print `10.7.0`

# Falta el path a npm a settings.py?
which npm 
Ens diu:
/home/ignasi/.nvm/versions/node/v20.15.0/bin/npm

# Cal posar el path a settings.py
Troba NPM_BIN_PATH i escriu el path:
NPM_BIN_PATH = "/home/ignasi/.nvm/versions/node/v20.15.0/bin/npm"

# Actualitzat npm
npm install -g npm@10.8.1

python manage.py tailwind install

Un problemilla de seguretat
npm audit fix

# Finalment crea la base de dades (SQLite per defecte no l'he canviat)

python manage.py migrate
python manage.py runserver

# Crear usuari i contrassenya ( de fet son insegurs)
python manage.py createsuperuser
ignasi/ignasi

Per arribar al admin afegeix /admin a l'adreça de la web i entra la contrassenya
Pots editar els blocs etc

# Versió 4.1.4
Me n'adono que la versió és la Django 4.1.4 i ja van per la 5 la qual cosa pot ser un problema. 

# Canvio amb git a la branca develop
git checkout -b "develop"

# actualitza Python
python -m pip install -U Django
# Comprovo les princiapls funcionalitats.
python manage.py runserver

Si tot funciona bé .... 
Copio la configuració
pip freeze > requirements.txt

Recorda que som a la branca 'develop'

Puc fer un commit i una etiqueta
git add .
git commit -m 'Actualitzat a Django 5.0.6'
git tag 'Django_506'
git push --set-upstream origin develop
