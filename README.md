# AgentSecure — Sécurisez vos agents IA

Business web d'un expert indépendant français en **cybersécurité × agents IA**, destiné aux PME qui déploient des agents IA (CRM, email, facturation, support) sans garde-fous.

**Positionnement 2026 :** les agents voyous font la une, la chute des coûts (Gemini −50 %, Palmyra −52 %) a explosé l'adoption PME, et le marché est passé de « pourquoi adopter » à « comment contenir ». La sécurité des agents est le nouveau champ de bataille — AgentSecure apporte la méthode des SOC aux PME.

## Livrables

| Fichier | Rôle |
|---|---|
| `index.html` | Landing page — design « cyber terminal » (fond noir #050a08, vert phosphore #39ff88, JetBrains Mono, grille fine, animations de scan). Hero « Vos agents travaillent. Qui les surveille ? », contexte 2026, 3 menaces réelles, 4 piliers, 3 offres, formulaire EmailJS. |
| `audit.html` | **Outil réel** — questionnaire 15 questions pondérées (total 100 pts) → score /100, 4 niveaux (Critique <40, Élevé 40-59, Modéré 60-79, Sain 80+), répartition par 8 catégories, 5 recommandations personnalisées, export imprimer/PDF, sauvegarde de session. |
| `checklist-protection-40-points.md` | 40 points d'action concrets en 8 catégories (accès, données, permissions, validation, monitoring, tests, incident, gouvernance) — livrable du Pack Protection. |
| `README.md` | Ce fichier. |

## Offres

| Offre | Prix | Contenu |
|---|---|---|
| **Audit gratuit** | 0 € | 15 questions (5 min) → score de risque /100 + 5 recommandations immédiates, export PDF |
| **Pack Protection** | 49 € | Checklist 40 points (8 catégories) + 4 procédures prêtes à l'emploi (moindre privilège, validation humaine, monitoring, journaux) + modèle de politique + plan de revue trimestriel |
| **Pack Entreprise** | 149 € | Audit complet des agents (accès, données, permissions, flux) + plan de correction priorisé + lettre de conformité + session de restitution 1 h + suivi 30 jours |

Paiement par virement ou message direct — facture fournie. (Stripe en attente.)

## Formulaire EmailJS

Réel et opérationnel sur `index.html` :

- **Service ID** : `service_cy1ytdb`
- **Template ID** : `template_xpo58cv`
- **Clé publique** : `8Pui4ZEqxW2jRVF7h`
- **Payload** : `{ site: "AgentSecure", name, email, question }`

Points de vigilance déjà traités :
- Le CDN `@emailjs/browser@4` est chargé **avant** l'appel `emailjs.init({ publicKey })` (formulaire mort sinon).
- Validation client (champs requis, format email) + états de statut (`[OK]` / `[ERR]`) avec repli sur l'adresse directe `contact@agentsecure.fr`.

## Architecture du score d'audit

- **15 questions** pondérées : 5 questions à 8 pts + 10 questions à 6 pts = **100 pts max**.
- **8 catégories** scorées indépendamment : accès, données, permissions, validation humaine, monitoring, tests, incident, gouvernance.
- **4 niveaux** : Critique <40 · Élevé 40-59 · Modéré 60-79 · Sain 80+.
- **Recommandations** : calculées sur les ratios par catégorie (faible <50 %, modéré <80 %), avec filet de recommandations génériques si moins de 5 catégories sont faibles.
- Persistance des réponses en `sessionStorage` (rechargement accidentel sans perte), champ entreprise optionnel injecté dans le rapport PDF.

## Design — « Cyber terminal / SOC »

Volontairement distinct des autres business de l'utilisateur (sombre cyan/violet 3D, fintech émeraude, éditorial ambre, institutionnel bleu clair, corail/tangerine, bleu roi/or ivoire) :

- Fond noir profond `#050a08`, accents **vert phosphore** `#39ff88` et blanc cassé `#e9f4ee`.
- Typographie **JetBrains Mono** pour les accents (prompts `$`, tags, titres, code) + Inter pour le corps.
- Grille fine façon terminal en arrière-plan, voile de scan animé, fenêtres terminal décoratives avec ligne de balayage.
- Cadres lumineux (`box-shadow` vert), curseur clignotant, ambiance froide et experte — un SOC, pas un site de startup.

## Déploiement

Site 100 % statique, aucun build requis. Hébergement recommandé : GitHub Pages ou tout hébergeur statique.

```bash
cd ~/Documents/livrables/agent-secure
# ouvrir en local :
open index.html
# ou servir via un serveur statique :
python3 -m http.server 8000
# puis http://localhost:8000
```

## Méthode

1. Le prospect lance l'**audit gratuit** (`audit.html`) → score /100 + 5 recommandations.
2. Le score est l'argument de vente : faible → besoin immédiat du **Pack Protection (49 €)** (checklist + procédures) ; structure ou conformité exigée → **Pack Entreprise (149 €)** (audit complet + plan de correction + lettre de conformité).
3. Chaque pack est livré sous 48 h ouvrées, accompagnement par email inclus.

---

*© 2026 AgentSecure — Sécurisez vos agents IA · contact@agentsecure.fr*
