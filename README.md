# Horizon — Prévision de trésorerie

Application web monofichier (HTML + CSS + JS, sans dépendance) de prévision de trésorerie.

## Fonctionnalités

- Projection quotidienne du solde sur un graphique canvas (zoom molette, déplacement par glisser-déposer)
- Cartes de synthèse (solde, revenus, dépenses, solde minimum)
- Opérations ponctuelles, tous les N jours ou mensuelles, avec date de fin optionnelle
- Recherche et filtres, thème clair/sombre
- Export / import JSON
- Données stockées dans le `localStorage` (clé `horizon-cashflow-v1`, thème : `horizon-theme`)

## Configuration par défaut

Au démarrage, si le `localStorage` ne contient aucune opération, l'application charge
`./horizon-sauvegarde-2026-10-20.json` (chemin relatif, compatible GitHub Pages), le valide
et l'enregistre. Si le chargement échoue, l'application démarre vide. Les données existantes
de l'utilisateur ne sont jamais écrasées.

## Déploiement GitHub Pages

Le workflow `.github/workflows/deploy-pages.yml` active GitHub Pages si nécessaire, puis déploie
`index.html` et le fichier JSON à chaque push sur `main` (ou manuellement via `workflow_dispatch`).

Pour tester en local : `python3 -m http.server` puis ouvrir `http://localhost:8000`.
