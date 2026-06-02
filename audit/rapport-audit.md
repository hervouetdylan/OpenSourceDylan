Tableau d'audit OpenSSF Scorecard

Critère		Nextcloud	Keycloak	Suricata
Score global	6.6/10	8.7/10	8.6/10
Maintained	10	10	10
Code Review	10	10	10
Security Policy	10	10	10
CI Tests	10	10	10
Dependency Update Tool	10	10	10
Fuzzing	0	10	10
SAST	7	10	10
Dangerous Workflow	0	10	10
Vulnerabilities	0	0	10

Sources : Nextcloud , Keycloak , Suricata

Analyse de risques


🟢 Keycloak (8.7/10)

Projet le plus mature du lot.

Forces :

Fuzzing activé
SAST activé
Revue de code systématique
Releases signées
Politique sécurité documentée

Faiblesses :

12 vulnérabilités ouvertes détectées
Certaines dépendances ne sont pas complètement verrouillées


🟢 Suricata (8.6/10)

Très bon niveau de sécurité.

Forces :

Aucune vulnérabilité ouverte détectée
Fuzzing activé
SAST activé
CI mature
Maintenance active
	
Faiblesses :

Dépendances insuffisamment verrouillées
Permissions GitHub Actions trop larges
Releases non signées détectées par Scorecard


🟡 Nextcloud (6.6/10)

Projet mature mais avec davantage de risques.

Forces :

Très actif
Revue de code systématique
Politique sécurité présente
Mise à jour des dépendances automatisée

Faiblesses :

18 vulnérabilités ouvertes détectées
Pas de fuzzing
Workflows GitHub Actions jugés risqués
Protection de branches perfectible


# CVE critiques identifiées

## Nextcloud – CVE-2026-45810

**Criticité : Medium**

**CVSS : 6.8/10**

**Description :**
Une vulnérabilité de contournement d'autorisation dans Nextcloud Server permet à un utilisateur authentifié ayant accès à un commentaire de fichier de consulter le contenu de l'ensemble des commentaires du système. Cette faille est causée par l'absence d'un contrôle de relation lors de la récupération des commentaires.

**Impact :**

* Exposition d'informations sensibles.
* Violation de la confidentialité des données.
* Contournement des restrictions d'accès aux commentaires.

**Versions affectées :**

* 31.0.0 à < 31.0.12
* 32.0.0 à < 32.0.3

**Correctif :**
Mettre à jour vers Nextcloud 31.0.12 ou 32.0.3 (ou version ultérieure).

---

## Keycloak – CVE-2026-9803

**Criticité : Medium**

**CVSS : 5.3/10**

**Description :**
Une faille dans le composant ClientRegistrationAuth de Keycloak permet à un attaquant distant non authentifié d'envoyer une requête POST spécialement conçue avec un en-tête Authorization malformé. Cela provoque une exception et peut entraîner un déni de service (DoS).

**Impact :**

* Déni de service.
* Interruption potentielle du service d'authentification.
* Affecte la disponibilité de l'infrastructure IAM.

**Versions affectées :**
Versions vulnérables du composant ClientRegistrationAuth publiées avant le correctif officiel.

**Correctif :**
Mettre à jour vers la dernière version stable de Keycloak intégrant le correctif de sécurité.

---

## Suricata – CVE-2026-31937

**Criticité : High**

**Description :**
Une inefficacité dans le mécanisme de buffering DCERPC de Suricata peut entraîner une forte dégradation des performances et provoquer un déni de service.

**Impact :**

* Dégradation importante des performances.
* Risque de déni de service.
* Réduction de la capacité de détection du moteur IDS/IPS.

**Versions affectées :**
Versions antérieures à Suricata 7.0.15.

**Correctif :**
Mettre à jour vers Suricata 7.0.15 ou une version plus récente.





| Projet    | CVE            | Criticité | Impact principal                               | Correctif                                   |
| --------- | -------------- | --------- | ---------------------------------------------- | ------------------------------------------- |
| Nextcloud | CVE-2026-45810 | Medium    | Contournement d'autorisation                   | Mise à jour vers 31.0.12 / 32.0.3           |
| Keycloak  | CVE-2026-9803  | Medium    | Déni de service                                | Mise à jour vers la dernière version stable |
| Suricata  | CVE-2026-31937 | High      | Déni de service / dégradation des performances | Mise à jour vers 7.0.15                     |
