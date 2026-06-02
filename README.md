# Gestion d'Interventions

Application web interne de gestion des interventions techniques pour un prestataire informatique.

Développée en remplacement d'une solution legacy PHP 2014, suite à un audit complet de l'existant.

Repo privé - Code source non public.

# Fonctionnalités

## Page Tableau de bord

- Suivi des interventions réparties en 6 statuts : À faire, En cours, En attente, Terminé, Rendu à facturer, RMA
- Changement de statut directement depuis les cartes en drag and drop
- Affichage d'informations préremplis quand on clique sur l'intervention + commentaire champ libre
- Bouton message Téléphone Pré-definis Bouton SMS pré-definis, bouton ticket impression, bouton urgent pour changer couleur et bouton archivage (seulement dans terminer)
- Bouton nouveau client qui dirige sur la page client, bouton nouvelle intervention qui dirige sur la page création
![TableauDeBord](AppImages/TableauDeBord.png)
-Résumé de l'intervention
-Champ pieces et Champ Main d'oeuvre permettant de mettre un prix.
![CompteRendu](AppImages/CompteRendu.png)
-Affichage d'infos Clients/Materiel
-Possibilité de modifier les infos de l'intervention
![Modification1](AppImages/Modification1.png)
![Modification2](AppImages/Modification2.png)


## Page Création

- Barre de recherche client avec pagination
- Création d'intervention avec informations apres avoir séléctionner un materiel
![Création](AppImages/Création.png)
- Ajout de plusieurs materiels par catégories etg par types dans une catégorie en montrant les champs précis au type choisis.
- Création/Modification/Supression Materiel
![Materiel](AppImages/Materiel.png)
-Création de l'intervention avec différents champs 
![Intervention](AppImages/Intervention.png)



## Page Client

- Barre de recherche client avec pagination
- Création/Modification/Supression Client
- Ajout d'informations
- Champs ayant des restrictions précises
![Clients](AppImages/Clients.png)

- Selection Particulier/Professionnel

![ChampParticuler](AppImages/ChampParticulier.png)
![ChampProfessionnel](AppImages/ChampProfessionnel.png)


## Page Archives

- Barre de recherche client avec pagination
- Affichage d'interventions archivées avec possibilité de la modifier/suprimmer
- Affichage des informations sur l'intervention


![Archives](AppImages/Archives.png)

## Page Ordinateurs

- Barre de recherche Ordinateurs avec pagination
- Créer les ordinateurs que la boite reçois et stock
![Ordinateurs](AppImages/Ordinateurs.png)
- Assigner l'ordinateur vendu à la personne
![AssignerOrdi](AppImages/AssignerOrdi.png)


## Page SMS

-Recherche de clients par filtre(de tel mois/années à tel mois/années)/nom/numéro libre
-Envoie de Sms avec OVH

![Sms](AppImages/Sms.png)


## Page Paramètres

- Gestion des techniciens (admin uniquement)
- 
![Techniciens](AppImages/Techniciens.png)
- Configuration des référentiels (Ajout et supression)

![Referentiels](AppImages/Referentiels.png)
- Configuration des Materiels (Catégories, Types, Champs)

![MaterielParam](AppImages/MaterielParam.png)
- COnfiguration des SMS prédéfinis et messages téléphoniques

![SMS-Telephone](AppImages/SMS-Telephone.png)
- Configuration des Statuts (Ajout, supression, Message public)

![Statut](AppImages/Statut.png)


## Page Imprimmer

- Imprimmer un ticket avec informations materiel/client + id unique
![ImprimmerTicket](AppImages/ImprimmerTicket.png)

## Page Suivi(public)

-Rentrer Son id unique pour suivre son intervention
-Savoir ou en est l'intervention

![Suivi](AppImages/Suivi.png)
![SuiviEx](AppImages/SuiviEx.png)


## Page Mon Profil

- Modifier son nom prénom et adresse mail
- Modifier son mot de passe

![Compte](AppImages/Compte.png)

![Profil](AppImages/Profil.png)


## Page Se connecter

- Entrer Mail et Mot de passe
- Possibilité de reinitialiser son mot de passe et de se souveir des ids

![SeConnecter](AppImages/SeConnecter.png)
![MdpOublié](AppImages/MdpOublié.png)



# Stack technique

| Côté | Technologie |
| --- | --- |
| Backend | Laravel 12 (PHP 8.2) |
| Frontend | Vue.js 3 + Inertia.js |
| Style | Tailwind CSS |
| Base de données | MySQL |
| Emails | Resend (SMTP transactionnel) |
| Versioning | Git / GitHub |

# Schéma de base de données

L'application repose sur 23 tables métier couvrant :

- Utilisateurs & clients : techniciens, clients, materiels
- Interventions : interventions, intervention_accessoires, intervention_main_oeuvre, intervention_pieces, intervention_problemes
- Données liées : compte_rendus, identifiants (stockage chiffré des accès clients)
- Logs : appels_log, sms_log
- Référentiels configurables : accessoires, antivirus, marques, messages_telephone, problemes_recurrents, sms_predefinis, statuts, systemes_exploitation, tailles_ecran, types_materiel

# Contexte

Ce projet est en cours de développement dans le cadre d'un stage / projet professionnel pour Island Informatique. Il remplace une application interne vieillissante après un audit de sécurité complet ayant identifié des failles d'authentification, des données sensibles non chiffrées et des dépendances obsolètes.
