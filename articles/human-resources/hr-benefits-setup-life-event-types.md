---
title: Configurer les types d’événements de vie
description: Microsoft Dynamics 365 Human Resources utilise des types d’événements de vie pour définir les événements où il est valide de mettre à jour l’inscription aux avantages des employés.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c382299014e3f823bc2cd210749aae8c091c5f23
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112546"
---
# <a name="configure-life-event-types"></a>Configurer les types d’événements de vie

Microsoft Dynamics 365 Human Resources utilise des types d’événements de vie pour définir les événements où il est valide de mettre à jour l’inscription aux avantages des employés. Par exemple, se marier ou avoir un enfant. Chaque ID de type d’événement de vie ne peut être associé qu’à un seul type d’événement de vie. Par exemple, si vous créez un ID d’événement de vie appelé Changement d’adresse qui est associé au type d’événement de vie Changement d’adresse d’employé, vous ne pouvez pas créer un autre ID intitulé Changement d’adresse d’employé et l’associer au type d’événement de vie Changement d’adresse d’employé. 

Après avoir créé des types d’événements de vie, vous devez les associer aux types de plan. Pour plus d’informations, voir [Création de types de plan](hr-benefits-setup-plan-types.md).

   > [!NOTE]
   > Lorsque vous créez un événement de vie, vous devez l’associer à un type de plan. Pour plus d’informations, voir [Création de types de plan](hr-benefits-setup-life-event-types.md).

## <a name="create-a-life-event-type"></a>Création d’un type d’événement de vie

1. Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Types d’événement de vie**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **ID du type d’événement de vie** | Identificateur unique pour le type d’événement de vie. |
   | **Description** | Description du type d’événement de vie. |
   | **Type d’événement de vie** | Catalyseur pour mettre à jour l’inscription aux avantages d’un employé. Pour une liste des événements de vie, voir [Événements de vie ](hr-benefits-setup-payment-frequencies.md?life-events) ci-dessous. |

4. Sélectionnez **Enregistrer**.

## <a name="view-attached-plans"></a>Affichage des plans associés

Vous pouvez afficher une liste des plans associés au type d’événement de vie sélectionné. Les événements de vie sont associés à un type de plan et les types de plan sont associés à un plan. 

1. Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Types d’événement de vie**.

2. Sélectionnez **Actions**.

3. Sélectionner **Plans associés**.

## <a name="life-events"></a>Événements de vie

Vous pouvez choisir parmi les événements de vie suivants lorsque vous créez un type d’événement de vie :

| Événement de vie | Emplacement | Déclenchement |
| --- | --- | --- |
| **Modifier la situation de famille** | Collaborateur > Profil> Informations personnelles > Situation de famille| Modification de la situation de famille |
| **Modifier le statut d’emploi** | <ul><li>Collaborateur > Emploi</li><li>Page d’historique des emplois</li></ul> | Modification de la situation professionnelle |
| **Modifier l’adresse de l’employé** | <ul><li>Collaborateur > Profil> Adresses </li><li>Collaborateur > Informations personnelles > Contacts personnels> Adresse</li></ul> Adresse ajoutée, modifiée ou supprimée |
| **Modification personne à charge** | <ul><li>Collaborateur > Profil> Informations personnelles> Contacts personnels> Ajouter ou supprimer une personne à charge</li><li>Libre-service employé</li></ul> | Personne à charge ajoutée ou supprimée. La relation du contact personnel doit être un enfant, un conjoint, un partenaire ou un ex-conjoint. Mise à jour de la date **Valide à partir du** déclenchant l’événement de vie. Si vous ne mettez pas à jour cette date, aucun événement de vie ne se déclenchera. |
| **Naissance ou adoption (personne à charge)** | <ul><li>Collaborateur > Profil> Informations personnelles> Contacts personnels> Détails de la personne à charge</li><li>Libre-service employé</li></ul> | Champ **Date d’adoption** rempli. La date de naissance de l’enfant est obligatoire. |
| **Perte de couverture (conjoint/partenaire local)** | Collaborateur > Profil> Informations personnelles> Contacts personnels > Détails de la personne à charge > Perte de couverture | **Perte de couverture** sélectionnée pour un contact personnel, ainsi que **Date d’effet** |
| Modification de l’emploi du partenaire local | Collaborateur > Profil> Informations personnelles> Contacts personnels> Détails de la personne à charge > Employé. | <ul><li>Enregistrement des détails de la personne à charge créé et zone **Contact personnel employé** = Oui</li><li>Zone **Contact personnel employé** modifiée (oui ou non)</li></ul> |
| **Congé (conjoint/partenaire local)** | Collaborateur > Profil> Informations personnelles> Contacts personnels > Détails de la personne à charge > Congé | <ul><li>Enregistrement des détails de la personne à charge créé et **EhrLOAEffectiveDate** rempli</li><li>**personPrivateDetails.EhrIsLOA** est modifié (Oui ou Non)</li><li>**personPrivateDetails.EhrLOAEffectiveDate** est modifié</li></ul> |
| **Modification de la couverture (poste)** | <ul><li>Collaborateur > Affectation de poste > Affectations de poste du collaborateur</li><li>Postes > Postes</li></ul> | <ul><li>Modification du poste dans les enregistrements d’affectation de poste du collaborateur</li><li>Modification de l’affectation du collaborateur au poste</li></ul> |
| **Assurance-maladie (employé / personne à charge)** | Collaborateur > Profil> Informations personnelles> Contacts personnels > Détails de la personne à charge > Date d’effet assurance-maladie | Non déclenché automatiquement lorsqu’un contact personnel entre une date d’effet. |
| **Prise en charge par décision de justice** | Collaborateur> Profil> Informations personnelles> Contacts personnels> Personne à charge > Prise en charge par décision de justice (QMSCO/QDRO) et dates d’effet | Ne déclenche aucune mise à jour automatique. Cela n’a aucune incidence sur l’admissibilité ; un événement de vie est enregistré. |
| **Décédé** | Collaborateur > Profil> Informations personnelles > Date de décès | Une date de décès est entrée |
| **Preuve d’assurance** | <ul><li>Collaborateur > Collaborateur > Versions > Historique des emplois > Gestionnaire des dates > Détails de l’avantage</li><li> Collaborateur > Emploi> Détails de l’avantage > Date de vérification</li></ul> | <ul><li>Un collaborateur entre une date de vérification</li><li>Un collaborateur définit le champ EvidenceOfInsurability sur **Oui**</li></ul> |
| **Bénéficiaire** | Collaborateur > Profil > Informations personnelles > Contacts personnels | Un contact personnel est ajouté et les zones **Bénéficiaire** et **Date d’effet** sont remplies. Le contact personnel doit être de type **Enfant**, **Conjoint**, **Partenaire local**, **Jumeau**, **Contact familial**, **Autre contact**, **Parent**, **Domaine bénéficiaire**, **Organisation bénéficiaire** ou **Bénéficiaire approuvé**. |
| **Assurance pour l’employé (Medicare)** | Collaborateur > Collaborateur > Versions > Historique des emplois > Gestionnaire des dates > Détails de l’avantage | <ul><li>**EhrMedicareElibilityDate** est modifié</li><li>**MedicareEligibile** est défini sur **Oui**</li></ul> |
| **Anniversaire** | Collaborateur > Profil> Informations personnelles> Contacts personnels> Détails de la personne à charge > Date de naissance. | Une date de naissance est ajoutée ou mise à jour (pas après le traitement du changement d’événement de vie). Exemple : si les **Options d’éligibilité des contacts personnels** d’un enfant sont définies sur Âge : 26 dans Configuration > Avantages > Options d’éligibilité des contacts personnels, et si le personnel des RH exécute un traitement de changement d’événement de vie à tout moment après que la personne à charge a eu 26 ans, un message les alertant que la personne à charge n’est plus admissible à la couverture s’affiche. |
| **Modification de l’admissibilité des collaborateurs (non spécifique aux États-Unis)** | <ul><li>Collaborateur > Emploi</li><li>Collaborateur> Collaborateur> Versions> Historique des emplois</li></ul> | <ul><li>Le type d’employé, la catégorie d’emploi ou les cinq champs d’admissibilité définissables par l’utilisateur changent</li><li>**HcmEmploymentDetail.EhrEmploymentType** change (traité uniquement pour les enregistrements des détails d’emploi *modifiés*, non traité pour les *nouveaux* enregistrements d’emploi, tels que la réembauche ou la démission)</li></ul> |
| **Nouveau remplacement des règles d’admissibilité (non spécifique aux États-Unis)** | Ressources humaines avancées > Avantages> Plans> Avantages> Remplacement des règles d’admissibilité | Utilisation du traitement des événements de vie | EhrBenefitEligibilityRuleOverride.ValidFrom |
| **Modification du remplacement des règles d’admissibilité (non spécifique aux États-Unis)** | Ressources humaines avancées > Avantages> Plans> Avantages> Remplacement des règles d’admissibilité | Utilisation du traitement des événements de vie (ne détecte que les modifications apportées aux champs **Valide à partir du** et **ValidTo** pour le remplacement de la règle d’admissibilité) |
| **Expiration du remplacement des règles d’admissibilité (non spécifique aux États-Unis)** | Ressources humaines avancées > Avantages> Plans> Avantages> Remplacement des règles d’admissibilité | Utilisation du traitement de modification des événements de vie. Par exemple, si vous modifiez la date d’expiration de la règle d’admissibilité d’un plan pour qu’elle soit aujourd’hui à 17 h, à tout moment après 17 h 00 ou les jours suivants, puis exécutez le traitement des modifications d’événement de vie, un message apparaît indiquant que le remplacement de la règle d’admissibilité a expiré. |
| **Nouveau régime de prestations (non spécifique aux États-Unis)** | Ressources humaines avancées > Avantages> Plans> Nouveau | <ul><li>Les options d’admissibilité sont ajoutées à un plan actuel</li><li>Un nouveau plan avec des options d’admissibilité associées est ajouté</li></ul></br></br>Dans ce cas, le personnel RH doit exécuter le traitement de l’admissibilité aux événements de vie. |
| **Modification des règles d’admissibilité (non spécifique aux États-Unis)** | Ressources humaines avancées > Avantages> Règles/options> Règles d’admissibilité | Utilisation du traitement d’admissibilité des événements de vie. Consigné lorsque les valeurs suivantes des enregistrements **EhrBenefitEligibilityRule** ont changé : **UseEmplCategory**, **UseEmplStatus** ou **UseEmplType**. Met à jour uniquement les transactions d’événements de vie qui existent déjà pour une règle ou des critères d’éligibilité modifiés. |
