---
title: Entités Common Data Service
description: Microsoft Dynamics 365 Human Resources utilise Common Data Service pour permettre des scénarios d'extensibilité et d'intégration.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 85dd95e8209fff28f214986f7960372db200351b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009063"
---
# <a name="common-data-service-entities"></a>Entités Common Data Service

Microsoft Dynamics 365 Human Resources utilise Common Data Service pour permettre des scénarios d'extensibilité et d'intégration.

Pour plus d'informations sur Common Data Service, voir [Qu'est-ce que Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Les entités Human Resources suivantes sont disponibles dans Common Data Service.

## <a name="benefit-entities"></a>Entités Avantage

**Fréquence de calcul des avantages**

| **Champs**        | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------------|---------------|--------------|----------------|
| Description       | Texte          |              | O              |
| Contrôle de la fréquence | Jeu d'options    | O            | O              |
| Est inaltérable      | Deux options   |              | O              |
| Nom              | Texte          | O            | O              |


**Taux de calcul des avantages**

| **Champs**  | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------|---------------|--------------|----------------|
| Description | Texte          |              | O              |
| Nom        | Texte          | O            | O              |
| Type de niveau    | Jeu d'options    | O            | O              |


**Détails du taux de calcul des avantages**

| **Champs**                             | **Type de données**  | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|----------------------------------------|----------------|--------------|----------------|
| Numéro de détails du taux de calcul des avantages | Texte           | O            | O              |
| ID du taux de calcul                    | Recherche         | O            | O              |
| Méthode de contribution                    | Jeu d'options     | O            | O              |
| Date d'effet                              | Date uniquement      | O            | O              |
| Contribution de l'employeur                  | Nombre de décimales |              | O              |
| Expiration                             | Date uniquement      | O            | O              |
| Retenue des collaborateurs                        | Nombre de décimales |              | O              |


**Type d'avantage**

| **Champs**           | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|----------------------|---------------|--------------|----------------|
| Inscription simultanée | Jeu d'options    |              | O              |
| Description          | Texte          |              | O              |
| Nom                 | Texte          | O            | O              |
| Catégorie de salaire      | Jeu d'options    |              | O              |


**Plan d'avantages**

| **Champs**                               | **Type de données**  | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|------------------------------------------|----------------|--------------|----------------|
| Méthode des limites d'arriérés                      | Jeu d'options     |              | O              |
| Type d'avantage                             | Recherche         | O            | O              |
| Méthode de limite de contribution                | Jeu d'options     |              | O              |
| Méthode de contribution                      | Jeu d'options     |              | O              |
| Devise                                 | Recherche         |              | O              |
| Priorité de la déduction                       | Nombre entier   |              | O              |
| Montant de la limite de contribution par défaut        | Devise       |              | O              |
| Montant de limite de contribution par défaut (base) | Devise       |              | O              |
| Période de la limite de contribution par défaut        | Jeu d'options     |              | O              |
| Montant de la limite de déduction par défaut           | Devise       |              | O              |
| Montant de limite de déduction par défaut (base)    | Devise       |              | O              |
| Période de la limite de déduction par défaut           | Jeu d'options     |              | O              |
| Description                              | Texte           |              | O              |
| Taux de change                            | Nombre de décimales |              | O              |
| Est une exécution supplémentaire de la paie                | Deux options    |              | O              |
| Est à déclarer sur les soins abordables        | Deux options    |              | O              |
| Est généré par les arriérés                      | Deux options    |              | O              |
| Est majoré                              | Deux options    |              | O              |
| Est principal                               | Deux options    |              | O              |
| Nom                                     | Texte           | O            | O              |
| Impact sur la paie                           | Jeu d'options     |              | O              |
| Type de retraite                          | Jeu d'options     |              | O              |


**Entité emploi**

| **Champs**                     | **Type de données**  | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|--------------------------------|----------------|--------------|----------------|
| Date de début ajustée du collaborateur     | Date et heure  |              | O              |
| Société                        | Recherche         | O            | O              |
| Montant de l'unité de préavis de l'employeur | Nombre de décimales |              | O              |
| Unité de préavis de l'employeur        | Jeu d'options     |              | O              |
| Date de fin de l'emploi            | Date et heure  |              | O              |
| Nombre d'emplois              | Texte           | O            | O              |
| Date de début de l'emploi          | Date et heure  |              | O              |
| Dernier jour de travail              | Date et heure  |              | O              |
| Date de transition                | Date et heure  |              | O              |
| Valide à partir du                     | Date et heure  | O            | O              |
| Valide jusqu'au                       | Date et heure  |              | O              |
| Collaborateur                         | Recherche         | O            | O              |
| Montant du préavis du collaborateur           | Nombre de décimales |              | O              |
| Date de début du collaborateur             | Date et heure  |              | O              |
| Type de collaborateur                    | Jeu d'options     | O            | O              |
| Unité de préavis du collaborateur          | Jeu d'options     |              | O              |

## <a name="worker-entities"></a>Entités de collaborateurs

**Origine ethnique**

| **Champs**         | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|--------------------|---------------|--------------|----------------|
| Description        | Texte          |              | O              |
| Nom d'origine ethnique | Texte          | O            | O              |


**Langue**

| **Champs**    | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|---------------|---------------|--------------|----------------|
| Description   | Texte          |              | O              |
| Nom de langue | Texte          | O            | O              |


**Statut de vétéran**

| **Champs**           | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|----------------------|---------------|--------------|----------------|
| Description          | Texte          |              | O              |
| Est un vétéran protégé | Deux options    |              | O              |
| Nom de langue        | Texte          | O            | O              |


**Collaborateur**

| **Champs**                | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|---------------------------|---------------|--------------|----------------|
| Date de naissance                 | Date uniquement     |              | O              |
| Description               | Texte          |              | O              |
| Adresse e-mail 1           | Courrier électronique         |              | O              |
| Adresse e-mail 2           | Courrier électronique         |              | O              |
| Identité Facebook         | Texte          |              | O              |
| Prénom                | Texte          |              | O              |
| Nom complet                 | Texte          |              | O              |
| Sexe                    | Jeu d'options    |              | O              |
| Génération                | Texte          |              | O              |
| Contact pas e-mail autorisé  | Deux options   |              | O              |
| Contact pas téléphone autorisé  | Deux options   |              | O              |
| Nom                 | Texte          |              | O              |
| Identité LinkedIn         | Texte          |              | O              |
| Directeur                   | Recherche        |              | O              |
| Deuxième prénom               | Texte          |              | O              |
| Téléphone portable              | Téléphone         |              | O              |
| Identificateur Office Graph   | Texte          |              | O              |
| Adresse de messagerie principale     | Courrier électronique         |              | O              |
| Téléphone principal         | Téléphone         |              | O              |
| Profession                | Texte          |              | O              |
| Réseau social 1          | Jeu d'options    |              | O              |
| Réseau social 2          | Jeu d'options    |              | O              |
| Identité du réseau social 1 | Texte          |              | O              |
| Identité du réseau social 2 | Texte          |              | O              |
| Source                    | Jeu d'options    | O            | O              |
| État                     | Jeu d'options    | O            | O              |
| Numéro de téléphone 1               | Téléphone         |              | O              |
| Numéro de téléphone 2               | Téléphone         |              | O              |
| Numéro de téléphone 3               | Téléphone         |              | O              |
| Identité Twitter          | Texte          |              | O              |
| Utilisateur                      | Recherche        |              | O              |
| URL du site Web               | URL           |              | O              |
| Matricule du collaborateur             | Texte          | O            | O              |
| Type de collaborateur               | Jeu d'options    | O            | O              |
| Prénom Yomi           | Texte          |              | O              |
| Nom complet Yomi            | Texte          |              | O              |
| Nom Yomi            | Texte          |              | O              |
| Deuxième prénom Yomi          | Texte          |              | O              |


**Adresse du collaborateur**

| **Champs**           | **Type de données**  | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|----------------------|----------------|--------------|----------------|
| Numéro       | Texte           | O            | O              |
| Type d'adresse         | Jeu d'options     | O            | O              |
| Ville                 | Texte           |              | O              |
| Pays ou région    | Texte           |              | O              |
| Département               | Texte           |              | O              |
| Télécopie                  | Téléphone          |              | O              |
| Est préféré         | Deux options    |              | O              |
| Latitude             | Nombre de décimales |              | O              |
| Ligne 1               | Texte           |              | O              |
| Ligne 2               | Texte           |              | O              |
| Ligne 3               | Texte           |              | O              |
| Longitude            | Nombre de décimales |              | O              |
| Code postal          | Texte           |              | O              |
| Boîte postale      | Texte           |              | O              |
| Code de mode d'expédition | Nombre entier   |              | O              |
| Région ou province    | Texte           |              | O              |
| Numéro de téléphone 1          | Téléphone          |              | O              |
| Numéro de téléphone 2          | Téléphone          |              | O              |
| Numéro de téléphone 3          | Téléphone          |              | O              |
| Zone de transport             | Texte           |              | O              |
| Décalage UTC           | Nombre entier   |              | O              |
| Collaborateur               | Recherche         | O            | O              |


**Détails personnels du collaborateur**

| Champs                             | Type de données    | Obligatoire | Peut faire l'objet d'une recherche |
|------------------------------------|--------------|----------|------------|
| Ville natale                         | Texte         |          | O          |
| Pays ou région de naissance            | Jeu d'options   |          | O          |
| Date de naissance                          | Date uniquement    |          | O          |
| Pays ou région de citoyenneté      | Jeu d'options   |          | O          |
| Date de décès                      | Date uniquement    |          | O          |
| Date de vérification d'ancien combattant handicapé | Date uniquement    |          | O          |
| Formation                          | Texte         |          | O          |
| Origine ethnique                     | Recherche       |          | O          |
| Date de fin d'expatriation                  | Date uniquement    |          | O          |
| Date de début d'expatriation                | Date uniquement    |          | O          |
| Pays ou région d'origine du père     | Jeu d'options   |          | O          |
| Sexe                             | Jeu d'options   |          | O          |
| Est désactivé                        | Deux options  |          | O          |
| Est ancien combattant désactivé                | Deux options  |          | O          |
| Est une règle d'expatriation applicable    | Deux options  |          | O          |
| Est étudiant à temps plein               | Deux options  |          | O          |
| Situation de famille                     | Jeu d'options   |          | O          |
| Date de fin du service militaire          | Date uniquement    |          | O          |
| Date de début du service militaire        | Date uniquement    |          | O          |
| Pays ou région d'origine de la mère     | Jeu d'options   |          | O          |
| Pays ou région de nationalité      | Jeu d'options   |          | O          |
| Langue maternelle                    | Recherche       |          | O          |
| Nombre de personnes à charge               | Nombre entier |          |            |
| Statut d'ancien combattant                     | Recherche       |          | O          |
| Collaborateur                             | Recherche       | O        | O          |
| Numéro de détail du personnel du collaborateur      | Texte         | O        | O          |


**Compte bancaire du collaborateur**

| **Champs**                 | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|----------------------------|---------------|--------------|----------------|
| Titulaire du compte             | Texte          |              | O              |
| Identification de compte     | Texte          |              | O              |
| Description de l'adresse        | Texte          |              | O              |
| Type de compte bancaire          | Jeu d'options    |              | O              |
| Code d'emplacement de la banque         | Texte          |              | O              |
| Nom de la branche                | Texte          |              | O              |
| Numéro d'agence              | Texte          |              | O              |
| Ville                       | Texte          |              | O              |
| Pays ou région          | Texte          |              | O              |
| Département                     | Texte          |              | O              |
| Description                | Texte          |              | O              |
| Nom du secteur              | Texte          |              | O              |
| Courrier électronique                      | Texte          |              | O              |
| Extension                  | Texte          |              | O              |
| Télécopie                        | Texte          |              | O              |
| IBAN                       | Texte          |              | O              |
| Ligne 1                     | Texte          |              | O              |
| Ligne 2                     | Texte          |              | O              |
| Ligne 3                     | Texte          |              | O              |
| Téléphone portable               | Texte          |              | O              |
| Nom de la personne             | Texte          |              | O              |
| Code postal                | Texte          |              | O              |
| Boîte postale            | Texte          |              |                |
| Numéro d'acheminement             | Texte          |              | O              |
| Type de numéro d'acheminement        | Jeu d'options    |              | O              |
| Région ou province          | Texte          |              | O              |
| Code SWIFT                 | Texte          |              | O              |
| Téléphone                  | Texte          |              | O              |
| Numéro de télex               | Texte          |              | O              |
| URL du site Web                | Texte          |              | O              |
| Collaborateur                     | Recherche        | O            | O              |
| Numéro de compte bancaire du collaborateur | Texte          |              | O              |
| Numéro de compte bancaire du collaborateur | Texte          | O            | O              |

**Rémunération fixe du collaborateur**

| Champs                                | Type de données      | Obligatoire | Peut faire l'objet d'une recherche |
|---------------------------------------|----------------|----------|------------|
| Société                               | Recherche         | O        | O          |
| Type de rémunération                     | Jeu d'options     |          | O          |
| Devise                              | Recherche         |          | O          |
| Date d'effet                        | Date uniquement      |          | O          |
| Droit                                 | Recherche         | O        | O          |
| Taux de change                         | Nombre de décimales |          | O          |
| Date d'expiration                       | Date uniquement      |          | O          |
| Numéro de ligne                           | Nombre de décimales |          | O          |
| Fréquence de paiement                         | Recherche         | O        | O          |
| Taux de salaire                              | Devise       |          | O          |
| Taux de salaire (base)                       | Devise       |          | O          |
| Plan                                  | Recherche         | O        | O          |
| Poste                              | Recherche         | O        | O          |
| Type de processus                          | Jeu d'options     | O        | O          |
| Ligne du paramétrage du point de référence            | Recherche         |          | O          |
| Collaborateur                                | Recherche         | O        | O          |
| Numéro de rémunération fixe du collaborateur      | Texte           | O        | O          |

**Numéro d'identification personnel du collaborateur**

| Champs                 | Type de données   | Obligatoire | Peut faire l'objet d'une recherche |
|------------------------|-------------|----------|------------|
| Description            | Texte        |          | O          |
| Type de saisie             | Texte        |          | O          |
| Date d'expiration        | Date uniquement   |          | O          |
| Numéro d'identification  | Texte        | O        | O          |
| Type d'identification    | Recherche      | O        | O          |
| Est principal             | Deux options |          | O          |
| Date d'émission             | Date uniquement   |          | O          |
| Agence émettrice         | Recherche      | O        | O          |
| Collaborateur                 | Recherche      | O        | O          |


## <a name="position-entities"></a>Entités de poste

**Poste**

| **Champs**               | **Type de données**  | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|--------------------------|----------------|--------------|----------------|
| Activation               | Date et heure  |              | O              |
| Disponible pour affectation | Date et heure  |              | O              |
| Département               | Recherche         |              | O              |
| Description              | Texte           |              | O              |
| Équivalent temps plein     | Nombre de décimales |              | O              |
| Mission                      | Recherche         | O            | O              |
| Numéro de poste      | Texte           | O            | O              |
| Poste parent      | Recherche         |              | O              |
| Type de poste            | Recherche         |              | O              |
| Retraite               | Date et heure  |              | O              |
| Titre                    | Jeu d'options     |              | O              |
| Valide à partir du               | Date et heure  | O            | O              |
| Valide jusqu'au                 | Date et heure  |              | O              |


**Type de poste**

| **Champs**         | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|--------------------|---------------|--------------|----------------|
| Classification     | Jeu d'options    |              | O              |
| Description        | Texte          |              | O              |
| Nom du type de poste | Texte          | O            | O              |


**Affectation du collaborateur au poste**

| **Champs**                        | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------------------------|---------------|--------------|----------------|
| Poste                      | Recherche        | O            | O              |
| Numéro d'affectation de poste du collaborateur | Texte          | O            | O              |
| Valide à partir du                        | Texte          | O            | O              |
| Valide jusqu'au                          |               |              | O              |
| Collaborateur                            |               | O            | O              |

## <a name="job-entities"></a>Entités de poste

**Tâche**

| **Champs**                   | **Type de données**  | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|------------------------------|----------------|--------------|----------------|
| Autoriser des postes illimités    | Deux options    |              | O              |
| Équivalent temps plein par défaut | Nombre de décimales |              | O              |
| Description                  | Texte           |              | O              |
| Description du poste              | Texte           |              | O              |
| Fonction de tâche                 | Recherche         |              | O              |
| Type de tâche                     | Recherche         |              | O              |
| Nombre maximal de postes  | Nombre entier   |              | O              |
| Nom                         | Texte           | O            | O              |
| Titre                        | Jeu d'options     |              | O              |
| Valide à partir du                   | Date et heure  | O            | O              |
| Valide jusqu'au                     | Date et heure  |              | O              |


**Fonction du poste**

| **Champs**        | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------------|---------------|--------------|----------------|
| Description       | Texte          | O            | O              |
| Nom de la fonction de tâche | Texte          | O            | O              |


**Type de poste**

| **Champs**    | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|---------------|---------------|--------------|----------------|
| Description   | Texte          | O            | O              |
| Statut de l'exemption | Jeu d'options    | O            | O              |
| Nom du type de tâche | Texte          | O            | O              |

## <a name="leave-and-absence-entities"></a>Entités liées aux congés et absences

**Inscription aux congés**

| **Champs**            | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------------|---------------|--------------|----------------|
| Base pour la date de régularisation    | Date uniquement     | O            | O              |
| Date de début de régularisation    | Date uniquement     | O            | O              |
| Date personnalisée           | Date uniquement     | O            | O              |
| Régularisation suspendue  | Deux options   |              | O              |
| Numéro d'inscription de congé | Texte          | O            | O              |
| Plan de congé            | Recherche        | O            | O              |
| Date de début             | Date uniquement     | O            | O              |
| Base de niveau            | Jeu d'options    | O            | O              |
| Collaborateur                | Recherche        | O            | O              |


**Transaction bancaire de congé**

| **Champs**                    | **Type de données**  | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------------------------|----------------|--------------|----------------|
| Montant                        | Nombre de décimales | O            | O              |
| Société                       | Recherche         | O            | O              |
| Numéro de transaction bancaire de congé | Texte           | O            | O              |
| Plan de congé                    | Recherche         |              | O              |
| Type de congé                    | Recherche         | O            | O              |
| Date de transaction              | Date uniquement      | O            | O              |
| Numéro de transaction            | Nombre de décimales | O            | O              |
| Type de transaction              | Jeu d'options     | O            | O              |
| Collaborateur                        | Recherche         | O            | O              |


**Plan de congé**

| **Champs**        | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------------|---------------|--------------|----------------|
| Fréquence de régularisation | Jeu d'options    | O            | O              |
| Société           | Recherche        | O            | O              |
| Description       | Texte          |              | O              |
| Type de congé        | Recherche        | O            | O              |
| Nom              | Texte          | O            | O              |
| Date de début         | Date uniquement     | O            | O              |


**Demande de congé**

| **Champs**           | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|----------------------|---------------|--------------|----------------|
| Commentaire              | Texte          | O            | O              |
| Société              | Recherche        | O            | O              |
| Numéro de demande de congés | Texte          |              | O              |
| Date de demande         | Date et heure | O            | O              |
| État                | Jeu d'options    | O            | O              |
| Collaborateur               | Recherche        | O            | O              |


**Détails de la demande de congés**

| **Champs**                  | **Type de données**  | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------------------|----------------|--------------|----------------|
| Montant                      | Nombre de décimales | O            | O              |
| Date de congé                  | Date et heure  | O            | O              |
| Demande de congé               | Recherche         | O            | O              |
| Numéro de détails de la demande de congé | Texte           | O            | O              |
| Type de congé                  | Recherche         | O            | O              |


**Type de départ**

| **Champs**      | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------|---------------|--------------|----------------|
| Société         | Recherche        | O            | O              |
| Description     | Texte          |              | O              |
| Code de rémunération    | Recherche        |              | O              |
| Nom du type de congé | Texte          | O            | O              |


**Calendrier de travail**

| **Champs**  | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------|---------------|--------------|----------------|
| Société     | Recherche        | O            | O              |
| Description | Texte          |              | O              |
| Nom        | Texte          | O            | O              |


**Jours de calendrier de travail**

| **Champs**               | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|--------------------------|---------------|--------------|----------------|
| Date de calendrier            | Date uniquement     | O            | O              |
| Société                  | Recherche        |              | O              |
| État                    | Texte          |              | O              |
| Calendrier de travail            | Recherche        | O            | O              |
| Nombre de jours de calendrier de travail | Texte          | O            | O              |


**Congé du calendrier de travail**

| **Champs**  | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------|---------------|--------------|----------------|
| Nom        | Texte          |              | O              |
| Description | Texte          | O            | O              |


**Ligne de congé du calendrier de travail**

| **Champs**                        | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------------------------|---------------|--------------|----------------|
| Date de congés                      | Date uniquement     | O            | O              |
| Nom                              | Texte          |              | O              |
| Congé du calendrier de travail             | Recherche        | O            | O              |
| Numéro de ligne de congé du calendrier de travail | Texte          | O            | O              |


**Intervalle de temps du calendrier de travail**

| **Champs**                         | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|------------------------------------|---------------|--------------|----------------|
| Société                            | Recherche        |              | O              |
| Heure de fin                           | Nombre entier  |              | O              |
| Heure de début                         | Nombre entier  |              | O              |
| Calendrier de travail                      | Recherche        | O            | O              |
| Jours de calendrier de travail                  | Recherche        | O            | O              |
| Numéro d'intervalle de temps du calendrier de travail | Texte          | O            | O              |

## <a name="organization-entities"></a>Entités Organisation

**Société**

| **Champs**   | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|--------------|---------------|--------------|----------------|
| Code société | Texte          | O            | O              |
| Nom         | Texte          | O            | O              |


**Département**

| **Champs**        | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------------|---------------|--------------|----------------|
| Numéro du département | Texte          | O            | O              |
| Description       | Texte          |              | O              |
| Nom              | Texte          | O            | O              |
| Département parent | Recherche        |              | O              |


**Devise**

| **Champs**         | **Type de données**  | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|--------------------|----------------|--------------|----------------|
| Code de la devise      | Texte           | O            | O              |
| Nom de la devise      | Texte           | O            | O              |
| Précision de devise | Nombre entier   | O            | O              |
| Symbole de devise    | Texte           | O            | O              |
| Image d'entité       | Image          |              |                |
| Taux de change      | Nombre de décimales | O            | O              |
| Organisation       | Recherche         | O            | O              |
| État              | Jeu d'options     |              | O              |

## <a name="payroll-entities"></a>Entités de paie

**Cycle de paie**

| **Champs**  | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------|---------------|--------------|----------------|
| Description | Texte          | O            | O              |
| Fréquence   | Jeu d'options    | O            | O              |
| Nom        | Texte          | O            | O              |


**Période de rémunération**

| **Champs**           | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|----------------------|---------------|--------------|----------------|
| Date de paiement par défaut | Date uniquement     |              | O              |
| Description          | Texte          |              | O              |
| Cycle de paie            | Apparence          | O            | O              |
| Numéro de période de paie    | Texte          | O            | O              |
| Date de fin de la période      | Date uniquement     | O            | O              |
| Date de début de la période    | Date uniquement     | O            | O              |
| État                | Jeu d'options    |              | O              |


**Code de rémunération de la paie**

| **Champs**              | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------------------|---------------|--------------|----------------|
| Description             | Texte          | O            | O              |
| Inclure dans le type de paiement  | Jeu d'options    | O            | O              |
| Est productif           | Deux options   | O            | O              |
| Nom                    | Texte          |              | O              |
| Unité de quantité           | Jeu d'options    |              | O              |
| Suivre les heures FMLA        | Deux options   |              | O              |


**Zone fiscale**

| **Champs**        | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------------|---------------|--------------|----------------|
| Ville              | Texte          |              | O              |
| Pays ou région | Texte          |              | O              |
| Département            | Texte          |              | O              |
| Nom              | Texte          | O            | O              |
| Région ou province | Texte          |              | O              |


**Fréquence de calcul des avantages de la période de rémunération**

| **Champs**                                      | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------------------------------------------|---------------|--------------|----------------|
| Fréquence de calcul des avantages                   | Recherche        | O            | O              |
| Fréquence de calcul des avantages du numéro de période de rémunération | Texte          | O            | O              |
| Période de rémunération                                      | Recherche        | O            | O              |


**Décaissements du compte en banque**

| **Champs**                       | **Type de données**  | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|----------------------------------|----------------|--------------|----------------|
| Montant                           | Devise       |              | O              |
| Montant (de base)                    | Devise       |              | O              |
| Compte bancaire                     | Recherche         | O            | O              |
| Numéro de décaissements du compte en banque | Texte           | O            | O              |
| Société                          | Recherche         | O            | O              |
| Devise                         | Recherche         |              | O              |
| Taux de change                    | Nombre de décimales |              | O              |
| Est restant                     | Deux options    |              | O              |
| Priorité                         | Nombre entier   |              | O              |

**Administration émettrice de l'identification des personnes**

| **Champs**           | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|----------------------|---------------|--------------|----------------|
| Description de l'adresse  | Texte          |              | O              |
| Ligne d'adresse 1       | Texte          |              | O              |
| Ligne d'adresse 2       | Texte          |              | O              |
| Ligne d'adresse 3       | Texte          |              | O              |
| Ville                 | Texte          |              | O              |
| Pays ou région    | Jeu d'options    |              | O              |
| Département               | Texte          |              | O              |
| Description          | Texte          |              | O              |
| Courrier électronique                | Texte          |              | O              |
| Extension            | Texte          |              | O              |
| Télécopie                  | Texte          |              | O              |
| Nom de l'agence émettrice  | Texte          | O            | O              |
| Téléphone portable         | Texte          |              | O              |
| Page                 | Texte          |              | O              |
| Code postal          | Texte          |              | O              |
| Boîte postale      | Texte          |              | O              |
| SMS                  | Texte          |              | O              |
| Région ou province    | Texte          |              | O              |
| Téléphone            | Texte          |              | O              |
| Télex                | Texte          |              | O              |
| URL du site Web          | Texte          |              | O              |

**Type d'identification personnel du collaborateur**

| **Champs**                        | **Type de données**  | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------------------------|----------------|--------------|----------------|
| Valeurs autorisées                    | Jeu d'options     |              | O              |
| Pays ou région                 | Texte           |              | O              |
| Description                       | Texte           |              | O              |
| Longueur fixe                      | Nombre entier   |              | O              |
| Format du numéro d'identification      | Texte           |              | O              |
| Type                              | Jeu d'options     |              | O              |
| Type d'identification personnel du collaborateur | Texte           | O            | O              |

## <a name="fixed-compensation-entities"></a>Entités de rémunération fixe

**Régime fixe de rémunération**

| **Champs**                  | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------------------|---------------|--------------|----------------|
| Société                     | Recherche        | O            | O              |
| Grille de rémunération           | Recherche        |              | O              |
| Devise                    | Recherche        | O            | O              |
| Description                 | Texte          | O            | O              |
| Date d'effet              | Date uniquement     | O            | O              |
| Date d'expiration             | Date uniquement     | O            | O              |
| Règle d'embauche                   | Jeu d'options    | O            | O              |
| Nom                        | Texte          | O            | O              |
| Tolérance des valeurs hors limite      | Jeu d'options    | O            | O              |
| Fréquence de paiement               | Recherche        | O            | O              |
| Recommandation autorisée      | Deux options   | O            | O              |
| Paramétrage de la ligne du point de référence  | Recherche        |              | O              |
| Type                        | Jeu d'options    | O            | O              |

**Grille de rémunération**

| **Champs**                  | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------------------|---------------|--------------|----------------|
| Société                     | Recherche        | O            | O              |
| Devise                    | Recherche        |              | O              |
| Description                 | Texte          | O            | O              |
| Date d'effet              | Date uniquement     |              | O              |
| Date d'expiration             | Date uniquement     |              | O              |
| Nom                        | Texte          | O            | O              |
| Paramétrage du point de référence       | Recherche        | O            | O              |
| Type                        | Jeu d'options    | O            | O              |

**Niveau de rémunération**

| **Champs**      | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------|---------------|--------------|----------------|
| Description     | Texte          |              | O              |
| Nom            | Texte          | O            | O              |
| Type            | Jeu d'options     | O            | O              |

**Fréquence de paiement de la rémunération**

| **Champs**                  | **Type de données**   | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------------------|-----------------|--------------|----------------|
| Facteur de conversion annuel    | Nombre de décimales  |              | O              |
| Société                     | Recherche          | O            | O              |
| Description                 | Texte            |              | O              |
| Facteur de conversion horaire    | Nombre de décimales  |              | O              |
| Facteur de conversion mensuel   | Nombre de décimales  |              | O              |
| Nom                        | Texte            | O            | O              |
| Période                      | Jeu d'options      |              | O              |
| Facteur de conversion hebdomadaire    | Jeu d'options      |              | O              |


**Paramétrage des points de référence de rémunération**

| **Champs**          | **Type de données**   | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|---------------------|-----------------|--------------|----------------|
| Société             | Recherche          | O            | O              |
| Type de rémunération   | Jeu d'options      | O            | O              |
| Description         | Texte            | O            | O              |
| Nom                | Texte            | O            | O              |

**Ligne de paramétrage des points de référence de rémunération**

| **Champs**            | **Type de données**   | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------------|-----------------|--------------|----------------|
| Société               | Recherche          | O            | O              |
| Description           | Texte            | O            | O              |
| Numéro de ligne           | Nombre de décimales  | O            | O              |
| Nom                  | Texte            | O            | O              |
| Paramétrage du point de référence | Recherche          | O            | O              |

**Région de rémunération**

| **Champs**      | **Type de données** | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------|---------------|--------------|----------------|
| Description     | Texte          | O            | O              |
| Nom            | Texte          | O            | O              |

**Structure des rémunérations**

| **Champs**                    | **Type de données**   | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-------------------------------|---------------  |--------------|----------------|
| Montant                        | Devise        |              | O              |
| Base du montant                   | Devise        |              | O              |
| Société                       | Recherche          | O            | O              |
| Numéro de structure des rémunérations | Texte            | O            | O              |
| Devise                      | Recherche          |              | O              |
| Taux de change                 | Nombre de décimales  |              | O              |
| Grille                          | Recherche          | O            | O              |
| Niveau                         | Recherche          | O            | O              |
| Point de référence               | Recherche          | O            | O              |
| Paramétrage de la ligne du point de référence    | Recherche          | O            | O              |

**Événement de rémunération fixe**

| **Champs**            | **Type de données**   | **Obligatoire** | **Peut faire l'objet d'une recherche** |
|-----------------------|-----------------|--------------|----------------|
| Société               | Recherche          | O            | O              |
| Description           | Texte            | O            | O              |
| Type d'événement            | Jeu d'options      | O            | O              |
| Est active             | Deux options     | O            |                |
| Nom                  | Texte            | O            | O              |

## <a name="entity-relationship-models"></a>Modèles de relation d'entité

### <a name="worker"></a>Collaborateur
![Collaborateur](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Emploi et poste
![Emploi et poste](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Avantages
![Avantages](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Rémunération
![Rémunération](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Quitter
![Quitter](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Calendrier de travail
![Calendrier de travail](./media/HCMCommon-work-calendar-entity-diagram.png)
