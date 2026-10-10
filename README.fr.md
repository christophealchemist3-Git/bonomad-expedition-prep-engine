🇬🇧 [Read in English](README.md)

# BoNomad – Expedition Prep Engine

**Planification d'expéditions assistée par IA pour le voyage off-road et overland.**

BoNomad est un prototype fonctionnel conçu pour explorer comment l'IA peut simplifier la préparation d'expéditions off-road et de voyages overland, en combinant les contraintes du véhicule, la planification d'itinéraire et des recommandations contextuelles.

Le projet adopte une approche de l'IA orientée produit, en transformant des exigences de voyage complexes en une expérience de planification structurée et personnalisée.

Il associe un planificateur d'expédition structuré en 7 étapes, un pipeline d'IA hybride (cache exact → cluster de similarité → génération par Claude), des recommandations d'équipement basées sur des règles, et une transparence de l'IA conforme aux exigences européennes, le tout sur une stack moderne React 19 / Next.js 16.

## Le défi

Préparer une expédition off-road ne se résume pas à choisir une destination. Le voyageur doit tenir compte des capacités du véhicule, du terrain, de l'autonomie, des contraintes d'itinéraire, de la logistique et des exigences de préparation.

BoNomad réunit ces éléments dans une expérience plus cohérente et plus simple à utiliser : l'utilisateur décrit son voyage et son véhicule, et la plateforme génère un roadbook sur mesure.

## Fonctionnalités principales

- **Planificateur d'expédition en sept étapes** : saisie structurée de la destination, de la durée, du véhicule, de l'équipement, du style de voyage, du terrain, de l'autonomie (carburant/eau) et des préférences de risque/confort/isolement ; la progression du brouillon est conservée localement, ce qui permet de terminer le parcours en plusieurs sessions
- **Planification d'expédition personnalisée** qui transforme ces informations en un brief off-road / overland cohérent (et non un chat de voyage générique)
- **Génération d'itinéraire et roadbook interactif** pour le voyage off-road et overland : vue du voyage par onglets avec itinéraire jour par jour, tracé sur carte satellite avec waypoints, et checklist de préparation adaptée au véhicule ; les utilisateurs peuvent enregistrer leurs voyages dans un tableau de bord personnel et les rouvrir plus tard
- **Comptes et tableau de bord** : authentification Supabase, bibliothèque personnelle d'itinéraires, sauvegarde de la progression des checklists sur les voyages enregistrés, et export GPX depuis les roadbooks enregistrés ou fraîchement générés
- Recommandations contextuelles pour accompagner la préparation du voyage
- Préparation de l'expédition grâce à des checklists structurées
- **Transparence de l'IA (alignée sur l'AI Act européen)** : étiquettes détaillées sur le contenu généré (sections éditoriales, tracé de la carte, recommandations non issues de l'IA), pour que les utilisateurs sachent ce qui a été produit par le modèle et ce qui relève d'une logique déterministe
- Export GPX pour une utilisation sur appareils et applications de navigation
- **Suggestions d'équipement contextuelles** (basées sur des règles, sans LLM) : les déclencheurs d'affiliation sont dérivés des réponses du planificateur et du contexte de l'itinéraire, ce qui garantit des recommandations cohérentes et évite un coût en tokens IA à chaque consultation
- Système de crédits et liste d'attente

## Surfaces de la plateforme (prototype)

Au-delà de la génération, le prototype comprend des parcours complémentaires qui reflètent une vision produit complète :

- **Carte interactive** : exploration de données d'adresses de type POI sélectionnées, avec filtres (complément de la planification de voyage, et pas seulement une carte statique d'illustration)
- **Univers Off-Road** (`/guides`) : recueil d'intérêt pour des produits (ex. carte imprimée, carnet de bord) et inscription par e-mail pour valider la demande avant le lancement de fonctionnalités payantes
- **Crédits et liste d'attente** : solde de crédits, liste d'attente avant paiement pour de futurs packs, et génération réservée aux utilisateurs authentifiés disposant de crédits

## Démonstration du produit

**Plateforme en ligne :** [Ouvrir la démo](https://roadbook-five.vercel.app/)

La plateforme est un prototype. Les fonctionnalités et capacités doivent être comprises dans le contexte de son stade de développement actuel.

## Captures d'écran

<p align="center">
<img width="800" alt="BoNomad - Page d'accueil avec appel à l'action" src="https://github.com/user-attachments/assets/36f25d2f-1c7b-421c-8e97-25f325225883" />
</p>
<p align="center"><em>Page d'accueil avec appel à l'action</em></p>

<p align="center">
<img width="800" alt="BoNomad - Proposition de valeur" src="https://github.com/user-attachments/assets/706fa066-cc74-4e57-8d61-7e584698f109" />
</p>
<p align="center"><em>Page d'accueil : proposition de valeur pour la planification d'expéditions off-road</em></p>

<p align="center">
<img width="800" alt="BoNomad - Saisies structurées" src="https://github.com/user-attachments/assets/0657b63d-f943-46cf-9567-19b78b0f662b" />
</p>
<p align="center"><em>Planificateur multi-étapes : saisies structurées avant la génération par l'IA</em></p>

<p align="center">
<img width="800" alt="BoNomad - Roadbook généré avec itinéraire jour par jour, carte et checklist" src="https://github.com/user-attachments/assets/1dd3c111-0d2f-496a-a65e-97c070f950fd" />
</p>
<p align="center"><em>Résultat du voyage : onglets du roadbook (itinéraire, carte, préparation)</em></p>

<p align="center">
<img width="800" alt="BoNomad - Produits affiliés" src="https://github.com/user-attachments/assets/152f7aa8-a737-4b4d-8617-ba9f8d306158" />
</p>
<p align="center"><em>Produit recommandé pour l'itinéraire généré, selon le véhicule renseigné (ici, Maxtrax)</em></p>

<p align="center">
<img width="800" alt="BoNomad - Tableau de bord avec itinéraires enregistrés" src="https://github.com/user-attachments/assets/efda8c3f-67e2-4069-9fc1-23cb50e2a399" />
</p>
<p align="center"><em>Tableau de bord : expéditions enregistrées</em></p>

<p align="center">
<img width="800" alt="BoNomad - Carte interactive avec filtres de POI" src="https://github.com/user-attachments/assets/a387056a-94cb-4df5-aa7a-788ebfd334c5" />
</p>
<p align="center"><em>Carte : données de type POI sélectionnées et filtres</em></p>

<p align="center">
<img width="800" alt="BoNomad - Page d'intérêt produit Univers Off-Road" src="https://github.com/user-attachments/assets/1b3d2544-1308-4a26-8593-fd14902f6f3c" />
</p>
<p align="center"><em>Univers Off-Road : recueil d'intérêt produit</em></p>

<p align="center">
<img width="800" alt="BoNomad - Solde de crédits et liste d'attente de pré-lancement" src="https://github.com/user-attachments/assets/aae56160-6ae0-4ee0-9700-6acac2f69b6c" />
</p>
<p align="center"><em>Page d'acquisition de crédits (bientôt disponible)</em></p>

## Stack technique

| Couche | Technologies |
|---|---|
| **Frontend** | Next.js 16 (App Router), React 19, TypeScript 5 (strict), Tailwind CSS v4, Framer Motion |
| **Backend & données** | Supabase (PostgreSQL, Auth, Row Level Security), Server Actions & Route Handlers |
| **IA** | API Anthropic Claude (Messages) pour la génération d'itinéraires |
| **Cartographie** | Mapbox GL JS, react-map-gl, Leaflet |
| **UI** | Design system sur mesure, Tailwind CSS, react-hot-toast |
| **Qualité & outillage** | ESLint 9, Node.js 20+ |
| **Déploiement** | Vercel, GitHub |

La stack est volontairement de dernière génération : **React 19** et **Next.js 16 App Router** pour l'interface et les frontières serveur, **Tailwind CSS v4** avec des design tokens en CSS (`@theme`), **Supabase** avec Row Level Security pour l'authentification et les données, et des appels **exclusivement côté serveur** à **Anthropic Claude** pour que les clés d'API ne soient jamais exposées au navigateur. La cartographie combine **Mapbox GL** (vue satellite du voyage) et **Leaflet** là où une expérience cartographique plus légère convient.

## Approche produit et technologique

Le projet combine conception produit, exigences fonctionnelles, cas d'usage de l'IA et prototypage itératif. Les choix techniques visent à construire une expérience utilisable, évolutive et centrée sur l'utilisateur, tout en maîtrisant les coûts d'IA et les temps de réponse.

L'UX tenant compte de la réglementation (transparence de l'IA section par section) est traitée comme une exigence produit de premier plan, et non comme une couche ajoutée après le lancement.

## Défis et apprentissages

### Construire une plateforme complète de bout en bout en 3 mois

BoNomad a été conçu et réalisé de bout en bout en trois mois : définition du produit, UX, base de données et authentification, intégration de l'IA, cartographie, déploiement. Le principal défi était de prendre rapidement des décisions produit, design et techniques tout en gardant une architecture suffisamment propre pour évoluer.

### Un pipeline de génération IA économe

Appeler un LLM à chaque requête est lent et coûteux. Une part importante du travail a consisté à concevoir une logique de cache à plusieurs niveaux, afin que l'IA ne soit sollicitée que lorsque c'est vraiment nécessaire.

Chaque requête de génération suit cet ordre :

1. **Hachage des paramètres** : les paramètres du voyage (destination normalisée, durée, saison, véhicule, terrain, difficulté, objectif, et curseurs de risque / confort / isolement arrondis) sont réduits à un hash SHA-256 déterministe. Seuls les paramètres qui modifient réellement l'itinéraire sont pris en compte, et non chaque champ du formulaire.
2. **Cache exact** : si un voyage identique a déjà été généré, le roadbook stocké est renvoyé instantanément, sans appel à l'IA. Un compteur de hits suit la réutilisation.
3. **Correspondance par cluster** : en l'absence de correspondance exacte, le système recherche un voyage similaire (même destination, même type de véhicule et même difficulté) dans un cluster d'itinéraires déjà générés. Si le cluster est suffisamment fourni, son roadbook représentatif est réutilisé, là aussi sans appel à l'IA.
4. **Génération par l'IA** : uniquement lorsque les deux niveaux échouent, Claude génère un nouvel itinéraire. Le résultat est ensuite enregistré dans le cache et ajouté à son cluster, afin que les futures requêtes similaires en bénéficient.

Cette approche réduit les coûts d'API et la latence, et la plateforme gagne en efficacité à mesure que son usage augmente.

## Ma contribution

- Vision produit et définition des cas d'usage
- Conception fonctionnelle et définition du parcours utilisateur
- Identification des opportunités IA et approche d'intégration
- Développement full-stack, du schéma de base de données au pipeline IA
- Choix technologiques et développement du prototype
- Tests itératifs et amélioration continue

## Statut actuel

BoNomad est un prototype en cours de développement, utilisé pour explorer l'application concrète de l'IA à la planification d'expéditions. Les améliorations futures pourraient inclure une intelligence d'itinéraire renforcée, des données contextuelles plus riches et une personnalisation plus poussée.

À ce jour, la géométrie des routes suit les séquences de waypoints sur la carte (l'intégration d'un moteur de routage est à l'étude, mais ne fait pas partie de cette version du prototype).

## Contact

[Christophe Marechal](https://www.linkedin.com/in/christophe-marechal-5296615)

## Propriété intellectuelle

© 2026 BoNomad – Expedition Prep Engine. Tous droits réservés.

Ce dépôt est fourni à des fins de portfolio et de démonstration uniquement. Aucune licence n'est accordée pour utiliser, copier, modifier, distribuer ou exploiter commercialement son contenu original sans l'autorisation écrite préalable du titulaire des droits.
