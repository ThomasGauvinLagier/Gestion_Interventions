# Gestion d'Interventions

Application web interne de gestion des interventions techniques pour un prestataire informatique.

Développée en remplacement d'une solution legacy PHP 2014, suite à un audit complet de l'existant.

Repo privé — Code source non public.

# Fonctionnalités

## Page Tableau de bord
![TableauDeBord](AppImages/TableauDeBord.png)
- Suivi des interventions réparties en 6 statuts : À faire, En cours, En attente, Terminé, Rendu à facturer, RMA
- Changement de statut directement depuis les cartes en drag and drop
- Affichage d'informations préremplis dans création Client
- Ajout commentaire dans l'intervention
- Affichage mot de passe (demande interne)
- Bouton message Téléphone Pré-definis Bouton SMS pré-definis, bouton ticket impression et bouton archivage (seulement dans terminer)
- Bouton nouveau client qui dirige sur la page client, bouton nouvelle intervention qui dirige sur la page création

## Page Création

- Barre de recherche client
- Ajout de plusieurs materiels par client avec leurs informations
- Création d'intervention avec informations apres avoir séléctionner un materiel

## Page Client

- Barre de recherche client
- Selection Particulier/Professionnel
- Création/Modification/Supression Client
- Ajout d'informations

## Page Archives

- Barre de recherche client
- Affichage d'interventions archivées avec possibilité de la modifier/suprimmer
- Affichage des informations sur l'intervention

## Page Paramètres

- Gestion des techniciens (admin uniquement)
- Configuration des référentiels (Ajout et supression)
- Gestion des SMS prédéfinis et messages téléphoniques
- Configuration des Statuts (Ajout et supression)

## Page Imprimmer

- Imprimmer un ticket avec informations materiel/client + id unique

## Page Mon Profil

- Modifier son nom prénom et adresse mail
- Modifier son mot de passe

## Page Se connecter

- Entrer Mail et Mot de passe
- Possibilité de reinitialiser son mot de passe et de se souveir des ids

A FAIRE

## Page Intervention site vitrine

- Le client pourra en rentrant son ID d'intervention voir ou en est son intervention via les statuts.

## Mettre en place OVH SMS + Stelogy pour tracer les appels

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
