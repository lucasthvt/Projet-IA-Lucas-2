# Projet IA à domicile — BTS SIO 2 SLAM

**Les consignes complètes** (sujets, exigences, déroulé du lundi et du mardi, barème) :
<https://ggaillard.github.io/portail-bts/distance/projet-ia.html>

Séances : 5, 6 et 8 octobre 2026 (le premier projet) ; **12 octobre, séance 24** : un second projet, sur un **autre sujet**, dans un nouveau dépôt `projet-ia-<prenom>-2`, prototypé avec une IA en ligne gratuite et sans carte bancaire, comparée au modèle local. Questions et rendu : par e-mail, à l'adresse Gmail habituelle de l'enseignant, objet `[BTS2 Projet IA] NOM Prénom — …`.

## Démarrer en trois gestes

1. En haut de cette page : **Use this template → Create a new repository**, à votre nom, nommé `projet-ia-<prenom>`.
2. Clonez **votre** dépôt, puis `cp .env.example .env` (Windows : `copy .env.example .env`) et remplissez `.env` (au moins `CODE_ACCES`). Ce fichier ne se commite jamais. Sans Docker : `uvicorn main:app --reload --env-file .env`.
3. Remplissez `README.md` au fil des séances : c'est votre dossier.

### Un dépôt créé avant le 12 octobre ? Y ajouter les fichiers de la séance 24

Pour la séance 24, créez plutôt un **nouveau** dépôt depuis ce modèle : il contient tout. Pour faire évoluer votre premier projet plus tard, téléchargez les deux fichiers, puis reprenez `main.py` et le `Dockerfile` de ce modèle :

```bash
curl -O https://raw.githubusercontent.com/ggaillard/BTS2-Projet-IA/main/fournisseurs.py
curl -O https://raw.githubusercontent.com/ggaillard/BTS2-Projet-IA/main/essai_fournisseur.py
```

| Fichier | Rôle |
|---|---|
| `main.py` | l'application FastAPI : page, `/api/demander`, `/sante`, `/a-propos`, code d'accès, limite de requêtes |
| `fournisseurs.py` | qui sert le modèle : Ollama sur votre PC, ou un fournisseur en ligne (OVHcloud, GitHub Models, Groq, Mistral, Google) — et où partent les données |
| `essai_fournisseur.py` | essayer un fournisseur sans lancer l'application |
| `prompt.txt` | la consigne donnée au modèle — à écrire pour votre sujet |
| `static/index.html` | la page — à adapter |
| `Dockerfile`, `compose.yaml` | la mise en production : l'application et le tunnel vers l'URL publique |
| `.env.example` | les réglages, à copier en `.env` |
| `evaluer.py`, `cas.json` | la mesure : rejouer vos cas et compter |
| `README.md` | votre dossier |
| `sujets/` | les six sujets détaillés, avec leurs données d'exemple — [commencez ici](sujets/) |

*Organisations et données des projets : fictives uniquement.*
