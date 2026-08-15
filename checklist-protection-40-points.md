# Checklist Protection — 40 points pour sécuriser vos agents IA

> **AgentSecure — Pack Protection (49 €)**
> 40 points d'action concrets, classés en 8 catégories. Cochez ce qui est fait, planifiez le reste.
> Méthode : 1 point = 1 action vérifiable. Un agent est sécurisé quand les 40 points sont cochés **et** revus chaque trimestre.

---

## 1. Accès — 5 points

- [ ] **1.1 Inventaire des accès** — Je tiens à jour la liste complète des agents et des services auxquels chacun se connecte.
- [ ] **1.2 Comptes dédiés** — Chaque agent utilise un compte unique, jamais un identifiant partagé ou générique.
- [ ] **1.3 Authentification renforcée** — Le MFA (ou équivalent) est activé sur tous les comptes utilisés par les agents.
- [ ] **1.4 Coffre de secrets** — Les clés API et mots de passe sont stockés dans un coffre, jamais en clair dans le code ou les fichiers de configuration.
- [ ] **1.5 Rotation des secrets** — Les clés d'accès sont renouvelées régulièrement et immédiatement après un départ ou un doute.

## 2. Données — 5 points

- [ ] **2.1 Classification des données** — J'ai identifié quelles données sont sensibles (clients, RH, paiement, secrets) et lesquelles ne le sont pas.
- [ ] **2.2 Cloisonnement par finalité** — Chaque agent n'accède qu'aux données nécessaires à sa mission, jamais à l'ensemble des données de l'entreprise.
- [ ] **2.3 Chiffrement** — Les données manipulées par les agents sont chiffrées en transit **et** au repos.
- [ ] **2.4 Minimisation** — Les agents n'ont accès ni aux données ni aux champs inutiles pour leur tâche (colonnes, pièces jointes, historiques).
- [ ] **2.5 Sauvegardes** — Les données critiques sont sauvegardées et la restauration est testée au moins une fois par an.

## 3. Permissions — 5 points

- [ ] **3.1 Moindre privilège** — Chaque agent a le niveau de droits le plus bas possible pour accomplir sa mission.
- [ ] **3.2 Revue des droits** — Les permissions de chaque agent sont revues au minimum chaque trimestre.
- [ ] **3.3 Pas d'admin par défaut** — Aucun agent n'est créé avec des droits administrateur ; les élévations sont exceptionnelles et temporaires.
- [ ] **3.4 Révocation rapide** — L'accès d'un agent peut être révoqué en moins d'une heure (départ, fin de mission, suspicion).
- [ ] **3.5 Séparation des rôles** — Un agent ne cumule pas des droits qui, réunis, permettent une action à fort impact (lire + modifier + envoyer).

## 4. Validation humaine — 5 points

- [ ] **4.1 Actions à fort impact** — Toute action sensible (envoi groupé, paiement, suppression, export) exige une validation humaine.
- [ ] **4.2 Règle des deux yeux** — Les opérations les plus critiques nécessitent l'approbation de deux personnes.
- [ ] **4.3 Liste des actions bloquées** — J'ai une liste écrite des actions qu'un agent ne peut jamais faire sans humain.
- [ ] **4.4 Trace d'approbation** — Chaque validation est journalisée : qui a validé, quoi, quand.
- [ ] **4.5 Mode dégradé** — En cas de doute (agent qui insiste, demande inhabituelle), la règle est de bloquer et de demander à un humain, pas d'accepter.

## 5. Monitoring & journaux — 5 points

- [ ] **5.1 Journaux activés** — Toutes les actions des agents sont journalisées : appel, destination, volume, résultat.
- [ ] **5.2 Horodatage et conservation** — Les journaux sont horodatés, conservés au moins 12 mois et protégés contre la modification.
- [ ] **5.3 Revu régulier** — Une personne désignée consulte les journaux chaque semaine.
- [ ] **5.4 Alertes anormales** — Des alertes existent pour : service inconnu, volume inhabituel, horaire étrange, échecs répétés.
- [ ] **5.5 Tableau de bord** — Je dispose d'une vue d'ensemble des agents actifs, de leurs dernières actions et de leur état de santé.

## 6. Tests de sécurité — 5 points

- [ ] **6.1 Test avant mise en production** — Tout nouvel agent passe un test de sécurité avant d'être déployé.
- [ ] **6.2 Scénarios adverses** — J'ai testé la réaction de l'agent face à une demande malveillante ou une injection dans ses instructions.
- [ ] **6.3 Test des permissions** — Je vérifie que l'agent ne peut pas accéder à ce qui lui est interdit (test d'élévation).
- [ ] **6.4 Tests après mise à jour** — Chaque mise à jour de modèle, d'outil ou de configuration déclenche une nouvelle passe de tests.
- [ ] **6.5 Calendrier de tests** — Les tests de sécurité sont planifiés (au minimum trimestriel) et leurs résultats documentés.

## 7. Réponse à incident — 5 points

- [ ] **7.1 Plan écrit** — J'ai un plan de réponse : qui est alerté, dans quel ordre, avec quels moyens.
- [ ] **7.2 Procédure d'isolation** — Je sais couper un agent en moins de 10 minutes : révoquer ses accès, suspendre ses connecteurs.
- [ ] **7.3 Analyse des journaux** — La procédure précise comment reconstituer ce que l'agent a fait (journaux, traces, captures).
- [ ] **7.4 Notification** — Le plan définit qui doit être informé : direction, clients concernés, CNIL le cas échéant, assureur.
- [ ] **7.5 Post-mortem** — Après chaque incident, un retour d'expérience est écrit et les mesures correctives sont suivies.

## 8. Gouvernance — 5 points

- [ ] **8.1 Politique écrite** — J'ai une politique de gestion des agents IA : création, permissions, validation, révocation.
- [ ] **8.2 Responsable désigné** — Chaque agent a un responsable nommé, qui répond de ses accès et de son comportement.
- [ ] **8.3 Qui crée, qui modifie** — Seules des personnes clairement identifiées peuvent créer, modifier ou connecter un agent.
- [ ] **8.4 Revue trimestrielle** — La politique et l'inventaire des agents sont revus chaque trimestre.
- [ ] **8.5 Formation des équipes** — Les collaborateurs sont formés aux réflexes de sécurité : qui valide quoi, que faire en cas de doute.

---

## Comment utiliser cette checklist

1. **Faites un premier passage complet** : cochez uniquement ce qui est **réellement en place**, pas ce qui est prévu.
2. **Comptez vos points** : 40 points = 40 actions. Moins de 24 points, votre exposition est critique ; 24 à 31, des fondations existent mais des trous restent ; 32 et plus, vous êtes sur la bonne voie.
3. **Priorisez** : commencez par les catégories 3 (permissions), 4 (validation) et 5 (monitoring) — ce sont les trois piliers qui stoppent l'essentiel des incidents.
4. **Planifiez les 30 prochains jours** : 3 à 5 points par semaine est un rythme réaliste pour une PME.
5. **Revoyez chaque trimestre** : un agent sécurisé aujourd'hui ne l'est plus après la prochaine mise à jour ou le prochain recrutement.

## En complément

- **Vous ne savez pas par où commencer ?** Faites d'abord l'audit gratuit en 15 questions : [audit.html](audit.html) — il calcule votre score /100 et vous donne 5 recommandations personnalisées.
- **Besoin d'aller plus loin ?** Le Pack Entreprise (149 €) ajoute un audit complet de vos agents, un plan de correction priorisé et une lettre de conformité pour vos clients et partenaires.

---

*AgentSecure — Sécurisez vos agents IA · expert indépendant cybersécurité × agents IA · contact@agentsecure.fr*
