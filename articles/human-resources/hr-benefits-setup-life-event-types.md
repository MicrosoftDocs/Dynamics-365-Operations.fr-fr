---
title: Configurer les types d’événements de vie
description: Microsoft Dynamics 365 Human Resources utilise des types d’événements de vie pour définir des événements pour mettre à jour les avantages sociaux des employés.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f8f81d6cc00154ca85b41294f4ae2ecb52c908c4
ms.sourcegitcommit: 8592c661b41f9cef8b7ef2863a3b97bf49a4e6f9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "7423355"
---
# <a name="configure-life-event-types"></a>Configurer les types d’événements de vie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources utilise des types d’événements de la vie pour définir quand il est justifié de mettre à jour l’inscription aux avantages sociaux des employés, comme se marier ou avoir un enfant. Chaque ID de type d’événement de vie ne peut être associé qu’à un seul type d’événement de vie. Par exemple, si vous créez un ID d’événement de vie appelé Changement d’adresse qui est associé au type d’événement de vie Changement d’adresse d’employé, vous ne pouvez pas créer un autre ID intitulé Changement d’adresse d’employé et l’associer au type d’événement de vie Changement d’adresse d’employé. Si un type d'événement de la vie n'est pas associé à un type de plan, il ne déclenchera pas d'événement de la vie. Pour plus d’informations, voir [Création de types de plan](hr-benefits-setup-plan-types.md).

## <a name="create-a-life-event-type"></a>Création d’un type d’événement de vie

1. Dans l’espace de travail **Gestion des avantages**, sous **Paramétrage**, sélectionnez **Types d’événement de vie**.

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

1. Dans l’espace de travail **Gestion des avantages**, sous **Paramétrage**, sélectionnez **Types d’événement de vie**.

2. Sélectionnez **Actions**.

3. Sélectionner **Plans associés**.

## <a name="life-events"></a>Événements de vie

Vous pouvez choisir parmi les événements de vie suivants lorsque vous créez un type d’événement de vie :

| Événement de vie | Emplacement | Déclenchement |
| --- | --- | --- |
| **Modifier la situation de famille** | Collaborateur > Profil> Informations personnelles > Situation de famille| Modification de la situation de famille |
| **Modifier le statut d'emploi** |<br><ul><li>Collaborateur > Emploi</li><li>Page d’historique des emplois</li></ul> | Pour un collaborateur avec un détail d'emploi existant, la création d'un nouveau détail d'emploi avec un statut d'emploi différent déclenchera un événement de la vie.  La mise à jour d'un détail d'emploi existant avec un statut d'emploi différent déclenchera également un événement de la vie.  |
| **Modifier l'adresse de l'employé** |<br><ul><li>Collaborateur > Profil> Adresses</li><li>Collaborateur > Informations personnelles > Contacts personnels> Adresse</li></ul> | Changement d'adresse. L’adresse doit être **Principale** pour déclencher un événement de vie. |
| **Modification personne à charge** |<br><ul><li>Collaborateur > Profil > Informations personnelles > Contacts personnels/li><li>Espace collaborateur</li></ul> | Ajoutez un contact personnel en le spécifiant comme personne à charge et en définissant le champ **Valide à partir du**. Mettez à jour les informations du champ **Valide jusqu’au** de la personne à charge d'un contact personnel. La relation du contact personnel doit être un enfant, un conjoint, un partenaire ou un ex-conjoint.  |
| **Naissance ou adoption (personne à charge)** |<br><ul><li>Collaborateur > Profil > Informations personnelles > Contacts personnels</li><li>Libre-service employé > Modifier les détails personnels > Contacts personnels</li></ul>| La **Date de naissance** ou la **Date d'adoption** sont ajoutées ou mises à jour. La **Date de naissance** de l’enfant est obligatoire. |
| **Perte de couverture (conjoint/partenaire local)** | Collaborateur > Profil> Informations personnelles> Contacts personnels > Détails de la personne à charge > Perte de couverture | **Perte de couverture** sélectionnée pour un contact personnel, ainsi que **Date d’effet** |
| Modification de l’emploi du partenaire local | Collaborateur > Profil> Informations personnelles> Contacts personnels > Détails de la personne à charge > Employé | Création d'un contact personnel et définition du champ **Employé** sur **Oui**. Mise à jour d'un contact personnel et modification du champ **Employé**.  |
| **Congé (conjoint/partenaire local)** | Collaborateur > Profil> Informations personnelles> Contacts personnels > Détails de la personne à charge > Congé | Le contact personnel est créé et le champ **Date d'entrée en vigueur du congé** est défini. Le champ **Congé** du contact personnel est mis à jour. Le champ **Date d'entrée en vigueur du congé** du contact personnel est mis à jour.  |
| **Modification de la couverture (poste)** |<br><ul><li>Collaborateur > Affectation de poste > Affectations de poste du collaborateur</li><li>Postes > Postes</li></ul>| Modification du poste dans les dossiers d’affectation de poste du collaborateur. Modification de l’affectation du collaborateur au poste. |
| **Modification de la couverture (salaire)** |<br><ul><li>Collaborateur > Rémunération > Plan fixe</li><li>Collaborateur > Informations personnelles > Salaire annuel avec avantages</li></ul>| Si les champs Gestion des avantages > Paramètres partagés de Human Resources > Avantages sociaux > Salaire annuel avec avantages ne sont pas activés, le fait de mettre à jour les champs Collaborateur > Rémunération > Régime fixe va créer un événement de la vie. Si les champs Gestion des avantages > Paramètres partagés de Human Resources > Avantages sociaux > Salaire annuel avec avantages sont activés, le fait de mettre à jour les champs Collaborateur > Informations personnelles > Salaire annuel avec avantages va créer un événement de la vie. |
| **Assurance-maladie (employé / personne à charge)** | Collaborateur > Profil> Informations personnelles> Contacts personnels > Détails de la personne à charge > Date d’effet assurance-maladie | L'ajout ou la mise à jour de la date du champ **Date d’effet assurance-maladie** d'un contact personnel crée cet événement de la vie. |
| **Prise en charge par décision de justice** | Collaborateur> Profil> Informations personnelles> Contacts personnels> Personne à charge > Prise en charge par décision de justice (QMSCO/QDRO) et dates d’effet | Lors de la création d'un contact personnel, un événement de la vie sera créé si le champ **Prise en charge par décision de justice** est défini sur **Oui**. La mise à jour du champ **Prise en charge par décision de justice** ou **Date d'expiration par décision de justice** déclenchera également un événement de la vie. |
| **Décédé** | Collaborateur > Profil> Informations personnelles > Date de décès | Une **date de décès** est entrée ou mise à jour. |
| **Preuve d'assurance** | Collaborateur > Collaborateur > Versions > Historique des emplois > Gestionnaire des dates > Détails de l’avantage | **Preuve d'assurabilité** est défini sur **Oui**. **Preuve de la date de vérification d'assurabilité** est défini. |
| **Bénéficiaire** | Collaborateur > Profil > Informations personnelles > Contacts personnels | Un contact personnel est ajouté et les champs **Bénéficiaire** et **Date d’effet** sont remplis. Le contact personnel doit être de type **Enfant**, **Conjoint**, **Compagnon**, **Jumeau**, **Contact familial**, **Autre contact** ou **Parent**. |
| **Assurance pour l'employé (Medicare)** | Collaborateur > Collaborateur > Versions > Historique des emplois > Gestionnaire des dates > Détails de l’avantage | Le champ **Admissible à l'assurance maladie** est défini sur **Oui**. Le champ **Date d'admissibilité à l'assurance maladie** a été modifié. |
| **Anniversaire** | Gestion des avantages sociaux > Traitement du changement d'événement de la vie | Ces événements de la vie sont créés à partir du champ **Traitement du changement d'événement de la vie**. Le processus analyse la période choisie et l'entité juridique et trouve les collaborateurs associés. Il calcule leur dernier anniversaire et crée un événement de la vie associé s'il n'a pas déjà été créé. |
| **Modification de l’admissibilité des collaborateurs (non spécifique aux États-Unis)** |<br><ul><li>Collaborateur > Emploi</li><li>Collaborateur> Collaborateur> Versions> Historique des emplois</li></ul>| Crée un événement de la vie lors des événements suivants :<br><ul><li>Création d'un nouvel emploi, s'il y a un emploi précédent, et si le type du collaborateur change.</li><li>Création d'un détail d'emploi, s'il y a un détail d'emploi précédent, et si le type d'emploi ou la catégorie d’emploi change.</li><li>La mise à jour d'un dossier d'emploi et un type de collaborateur différent sont définis.</li><li>La mise à jour d'un dossier détaillé d'emploi et d'un type ou d'une catégorie d'emploi différent est spécifiée.</li></ul> |
| **Nouveau remplacement des règles d’admissibilité (non spécifique aux États-Unis)** | Ressources humaines avancées > Avantages> Plans> Avantages> Remplacement des règles d’admissibilité | Utilisation du traitement des événements de vie<br>La création d'un nouveau remplacement d'admissibilité au régime d'avantages sociaux pour un collaborateur déclenche cet événement de la vie.<br>BenefitEligibilityRuleOverride.ValidFrom. |
| **Modification du remplacement des règles d’admissibilité (non spécifique aux États-Unis)** | Ressources humaines avancées > Avantages> Plans> Avantages> Remplacement des règles d’admissibilité | La mise à jour du champ **Valide à partir du** ou du champ **Valide jusqu’au** sur un remplacement d'admissibilité à un régime d'avantages sociaux déclenche cet événement de la vie. |
| **Expiration du remplacement des règles d’admissibilité (non spécifique aux États-Unis)** | Gestion des avantages sociaux > Traitement du changement d'événement de la vie  | Ces événements de la vie sont créés à partir du champ **Traitement du changement d'événement de la vie**. Le processus analyse la période choisie et l'entité juridique et trouve les remplacement d'admissibilité au régime d'avantages sociaux associés. Il crée des événements de la vie si les remplacements ont expiré. |
| **Nouveau régime d'avantages sociaux (non spécifique aux États-Unis)** | Ressources humaines avancées > Avantages> Plans> Nouveau | Les options d’admissibilité sont ajoutées à un régime actuel. Un nouveau régime avec des options d’admissibilité associées est ajouté.</br></br>Dans ce cas, le personnel RH doit exécuter le traitement de l’admissibilité aux événements de vie. |
| **Modification des règles d’admissibilité (non spécifique aux États-Unis)** | Gestion des avantages sociaux > Règles d’admissibilité | Utilisation du traitement d’admissibilité des événements de vie. Consigné lorsque les valeurs suivantes des dossiers **BenefitEligibilityRule** ont changé : **UseEmplCategory**, **UseEmplStatus** ou **UseEmplType**. Met à jour uniquement les transactions d’événements de vie qui existent déjà pour une règle ou des critères d’éligibilité modifiés. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
