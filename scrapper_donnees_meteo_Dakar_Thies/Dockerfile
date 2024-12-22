
# Utilise l'image de Python comme base
FROM python:3.10

# Copie de requirements.txt
COPY ./requirements.txt /app/requirements.txt

# Répertoire de travail
WORKDIR /app

# Vérifier si l'environnement est Linux 
RUN if [ "$(uname)" = "Linux" ]; then \
    # Installation des dépendances listées sans installer les dependances supplementaires
    pip install -r requirements.txt --no-deps; \
    else \
    # Installation des dépendances
    pip install -r requirements.txt; \
    fi


# Copie les fichiers de l'application vers le dossier de travail
COPY . /app

EXPOSE 5000

# Commande à exécuter au démarrage du conteneur
CMD ["python", "/app/main.py"]  