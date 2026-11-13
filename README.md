# ENI Mail
Pre-requis : Python (PATH), Node.js LTS, PostgreSQL (service demarre).
1. setup.bat (une seule fois)
2. Creer l'admin (dans backend, venv active) :
   python manage.py createadmin admin onirak19@gmail.com admin123 "Administrateur"
3. start.bat -> http://localhost:5173
Annuaire : recherche par nom, nom d'utilisateur, e-mail exact ou adresse @enimail.com.
Chaque utilisateur a une adresse interne username@enimail.com (non routee sur Internet).
Reinitialiser toute la base : python reset_db.py (dans backend, venv active)
Config e-mail et base : backend/.env (ne jamais partager ce fichier).

## Si le code de verification n'arrive pas
Dans backend (venv active) : python test_email.py
- "BLOQUE" sur les ports 587 et 465 : votre reseau/antivirus/pare-feu bloque Gmail. Essayez un autre reseau (partage de connexion du telephone) ou desactivez la protection e-mail de l'antivirus.
- Seul 587 bloque : mettez EMAIL_PORT=465 dans backend/.env puis relancez le backend.
En attendant, avec EMAIL_FALLBACK=1 le code s'affiche dans la fenetre noire du backend.
