# BoostÉtoiles — SaaS de gestion d'avis pour restaurants

> Plaques **NFC / QR** qui centralisent les avis Google d'un restaurant et
> collectent les retours clients, avec un tableau de bord de suivi en temps réel.
> **100 % conforme** aux règles de Google et au RGPD (pas de *review gating*).

🔗 **Site :** https://boostetoiles.fr
📊 **Dashboard (démo) :** https://dashboard.boostetoiles.fr

> ℹ️ Ce dépôt est une **vitrine** : il documente le projet et son architecture.
> Le code source du produit n'est pas public (projet commercial en exploitation).

---

## Le problème

Les restaurateurs peinent à collecter des avis Google, et se retrouvent souvent
avec des clients mécontents qui publient directement un avis négatif public,
sans que le gérant puisse réagir à temps.

## La solution

Une plaque **NFC + QR** posée sur la table. En la scannant, le client arrive sur
une page qui :
- met en avant l'avis Google (accès direct, sans filtrage) ;
- propose **en plus** un canal de retour privé vers le gérant ;
- fait remonter chaque interaction (scan, clic, ressenti) vers un tableau de bord.

Le gérant suit ses statistiques en temps réel : nombre de scans, taux de clic vers
Google, répartition des ressentis, retours privés à traiter.

## Fonctionnalités clés

- **Multi-établissements** : chaque commerce a son espace isolé.
- **Contrôle d'accès par rôles** : `ADMIN` (vue globale) et `MANAGER` (son seul
  établissement) — un gérant ne peut jamais voir les données d'un autre.
- **Ingestion d'événements** : scans NFC/QR, clics Google, ressentis, retours.
- **Tableau de bord analytique** : métriques et suivi d'évolution.
- **Conformité by design** : aucun *review gating*, gestion du consentement RGPD
  pour la collecte de contacts.

## Architecture technique

- **Base de données :** PostgreSQL (hébergée sur **Neon**), modèle relationnel
  conçu avec **Prisma** (commerces, utilisateurs, événements, retours clients).
- **Dashboard :** Next.js / TypeScript, authentification et rôles via NextAuth.
- **Vitrine :** page publique en PHP.
- **Hébergement :** domaine `boostetoiles.fr` + sous-domaine dédié au dashboard.

Flux : *plaque NFC/QR → page client → API d'ingestion → PostgreSQL → tableau de bord*

## Stack

`PostgreSQL` · `Prisma` · `Next.js` · `TypeScript` · `NextAuth` · `PHP` · `Neon` · `Git`

## Mon rôle

Projet **entrepreneurial** que j'ai conçu et piloté de bout en bout :
- Conception du **modèle de données** et administration de la base **PostgreSQL**.
- Mise en place de l'**authentification et du contrôle d'accès par rôles**
  (isolation des données entre établissements).
- Configuration de l'**hébergement** et **déploiement** (domaines, environnements).
- Réflexion **produit & conformité** (RGPD, règles Google).

## Captures d'écran

[Acceuil](assets/boostetoiles-index.png)
[Dashboard](assets/boostetoiles-dashboard.png)
[Plaques](assets/boostetoiles-plaques.png)
[Devis](assets/boostetoiles-devis.png)

## Statut

🟢 En ligne et en exploitation — évolutions en cours.

## Contact

**Müttaki SERTOGLU** — [LinkedIn](https://linkedin.com/in/müttaki-sertoglu-811706368) · [GitHub](https://github.com/muttakisertoglu69)
