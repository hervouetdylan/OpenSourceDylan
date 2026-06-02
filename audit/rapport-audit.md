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
