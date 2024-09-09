# Utiliser une image légère de Debian comme base
FROM debian:latest


# Mettre à jour les paquets et installer les dépendances nécessaires, incluant Nmap
RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y nmap git perl && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Installer Nikto manuellement depuis le dépôt GitHub
RUN git clone https://github.com/sullo/nikto.git /opt/nikto && \
    ln -s /opt/nikto/program/nikto.pl /usr/local/bin/nikto

# Créer un répertoire de travail (optionnel)
WORKDIR /app

# Définir le point d'entrée (optionnel, ici on ouvre un shell pour exécuter les commandes)
ENTRYPOINT ["/bin/bash"]
