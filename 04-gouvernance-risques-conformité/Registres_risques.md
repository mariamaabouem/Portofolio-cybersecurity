
Registre des risques informatiques

Version : 1.0
Statut : Étude de cas pédagogique
Périmètre : Active Directory, comptes administrateurs et serveur de fichiers
Contexte : Entreprise fictive de 50 employés

1. Objectif

Ce document présente l’identification, l’évaluation et le traitement d’un risque lié à la gestion des comptes administrateurs.

Cette analyse est réalisée dans un contexte pédagogique. Elle ne constitue pas un audit d’une entreprise réelle.

2. Description de l’environnement

L’entreprise fictive dispose :

* d’un serveur Windows avec Active Directory ;
* de postes de travail Windows ;
* d’un serveur de fichiers contenant des documents confidentiels ;
* d’un accès à Internet ;
* d’un système de sauvegarde.

Trois techniciens utilisent un compte administrateur de domaine partagé pour leurs tâches quotidiennes et administratives. L’authentification multifacteur (MFA) n’est pas activée sur ce compte.

3. Identification du risque

Identifiant : R-001

Intitulé : Compromission ou utilisation abusive d’un compte administrateur partagé.

Actif concerné : Active Directory, systèmes du domaine et serveur de fichiers.

Vulnérabilités identifiées :

* partage d’un compte administrateur entre plusieurs techniciens ;
* absence de MFA sur ce compte ;
* séparation insuffisante entre les usages quotidiens et les tâches administratives.

Scénario de risque :

Un attaquant obtient les identifiants du compte administrateur partagé, par exemple à la suite d’une campagne d’hameçonnage. Il utilise ce compte pour effectuer des actions non autorisées sur le domaine.

Le partage des identifiants complique l’attribution des actions à une personne précise et peut faciliter l’accès à plusieurs systèmes.

Conséquences potentielles :

* accès non autorisé aux ressources du domaine ;
* modification des comptes et des privilèges ;
* accès à des documents confidentiels ;
* perturbation des services ;
* difficulté à reconstituer précisément les actions réalisées.

4. Évaluation du risque initial

L’évaluation utilise une échelle pédagogique de 1 à 5.

Critère	Note	Justification
Vraisemblance	4/5	Le partage d’un compte privilégié et l’absence de MFA augmentent l’exposition au risque.
Impact	4/5	Une compromission du compte pourrait affecter plusieurs systèmes et des données confidentielles.
Score	16/25	4 × 4 = 16

Niveau de risque initial : élevé selon l’échelle retenue pour cet exercice.

Les notes sont des estimations pédagogiques. Dans une organisation réelle, elles devraient être justifiées par des éléments vérifiables et par une méthode de cotation approuvée.

5. Mesures de traitement recommandées

Mesure	Objectif
Créer un compte administrateur individuel pour chaque technicien	Améliorer la traçabilité des actions.
Séparer les comptes quotidiens des comptes administratifs	Réduire l’exposition des privilèges élevés.
Activer le MFA sur les accès privilégiés	Renforcer la protection contre le vol de mots de passe.
Examiner les droits et les groupes privilégiés	Limiter les privilèges aux besoins professionnels.
Centraliser et surveiller les journaux de sécurité	Détecter les activités suspectes et faciliter les investigations.
Encadrer et documenter les modifications sensibles	Réduire les modifications non autorisées.

Précaution : le compte partagé ne doit être désactivé qu’après vérification de ses dépendances et préparation de la migration vers les comptes individuels.

6. Vérification de l’efficacité des mesures

La mise en place des mesures ne suffit pas. Leur efficacité doit être vérifiée.

Les contrôles suivants sont proposés :

* vérifier que chaque technicien possède son propre compte administrateur ;
* confirmer que le compte partagé n’est plus utilisé pour les opérations courantes ;
* vérifier l’activation du MFA sur les accès privilégiés concernés ;
* examiner les droits réellement accordés aux techniciens ;
* vérifier que les événements de sécurité sont collectés et attribuables à des comptes individuels ;
* tester le déclenchement et le traitement des alertes pertinentes ;
* conserver les preuves des contrôles et des corrections effectuées.

Les journaux permettent d’associer des événements à un compte, mais ne prouvent pas nécessairement l’identité réelle de la personne qui a effectué l’action.

7. Plan d’action proposé

Action	Responsable proposé	Échéance indicative	Preuve attendue
Recenser les comptes et privilèges existants	Administrateur systèmes	Semaine 1	Inventaire des comptes et des groupes
Créer les comptes administrateurs individuels	Administrateur systèmes	Semaine 2	Comptes créés et tests réalisés
Configurer le MFA	Responsable informatique	Semaine 2	Configuration vérifiée et test documenté
Examiner les privilèges accordés	Responsable sécurité	Semaine 3	Revue des accès et corrections
Mettre en place la surveillance des événements	Responsable sécurité	Semaines 3 à 4	Alertes testées et procédure de traitement
Contrôler l’application des mesures	Responsable sécurité	Après déploiement	Rapport de vérification

Les échéances sont indicatives et doivent être adaptées aux ressources et aux priorités de l’organisation.

8. Risque résiduel et suivi

Le risque résiduel correspond au risque qui subsiste après la mise en œuvre des mesures de traitement.

À ce stade, le risque résiduel n’est pas coté, car les mesures proposées n’ont pas encore été mises en œuvre ni testées dans ce scénario.

Après leur déploiement, une nouvelle évaluation devra tenir compte des résultats des contrôles, des éventuelles faiblesses restantes et de l’efficacité réelle des mesures.

Le suivi devra documenter :

* l’état d’avancement des actions ;
* les preuves recueillies ;
* les écarts constatés ;
* les corrections nécessaires ;
* la réévaluation du risque résiduel.

9. Conclusion

Le partage d’un compte administrateur, associé à l’absence de MFA, expose potentiellement l’entreprise à une compromission des accès privilégiés et complique la traçabilité des actions.

Les mesures recommandées visent à renforcer la gestion des identités, à limiter les privilèges, à améliorer la détection des activités suspectes et à vérifier l’efficacité des contrôles.

Cette étude de cas illustre une démarche structurée d’analyse et de traitement des risques informatiques.
