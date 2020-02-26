---
title: Gérer les fonctionnalités
description: Découvrez comment activer ou désactiver de nouvelles fonctionnalités dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 84ff11e8237ce0669f7f6ac70c5b4411c5d4b466
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008985"
---
# <a name="manage-features"></a>Gérer les fonctionnalités

Dans le cadre de notre lancement continu de nouvelles fonctionnalités pour Microsoft Dynamics 365 Human Resources, nous souhaitons que nos clients expérimentent de nouvelles fonctionnalités dès que possible. Nous fournissons des fonctionnalités d'aperçu, presque prêtes pour la mise à disposition générale et qui ont fait l'objet de tests étendus. Nous attendons les derniers commentaires et validations des clients avant leur publication pour une disponibilité générale.

Pour plus d'informations sur les nouvelles fonctions dans Human Resources, voir [Nouveautés dans Human Resources](hr-admin-whats-new.md) et [Notes de publication de la Power Platform et Dynamics 365](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1).

L'espace de travail **Gestion des fonctions** fournit une liste des fonctions fournies dans chaque lancement. Par défaut, les nouvelles fonctionnalités sont désactivées. Vous pouvez utiliser l'espace de travail pour les activer et consulter la documentation les concernant. Pour plus d'informations sur la gestion des fonctions, voir [Présentation de la gestion des fonctions](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Toutes les nouvelles fonctionnalités restent dans la version préliminaire pendant au moins 30 jours, et généralement entre 30 et 60 jours. Les fonctionnalités principales sont généralement disponibles en octobre et en avril chaque année suivant la période de version préliminaire. Dès que vous voyez de nouvelles fonctionnalités dans l'espace de travail **Gestion des fonctions**, vous pouvez les activer. Certaines fonctionnalités peuvent être activées par défaut.

Une fois qu'une fonction est généralement disponible, elle peut être activée ou désactivée dans les environnements de production. L'espace de travail **Gestion des fonctions** indique quand une fonction d'aperçu devient obligatoire. Cette date est généralement le 1er octobre ou le 1er avril pour s'aligner avec les plans de lancement semi-annuels. Vous ne pouvez pas désactiver les fonctions obligatoires. Tant qu'elle n'est pas obligatoire, vous pouvez activer et désactiver une fonction dans tous les environnements.

## <a name="enable-or-disable-preview-features"></a>Activer ou désactiver les fonctionnalités d'aperçu

Pour accéder aux fonctionnalités d'aperçu, vous devez commencer par les activer dans votre environnement. L'activation ou la désactivation des fonctionnalités d'aperçu est propre à l'environnement.

> [!IMPORTANT]
> Les fonctions d'aperçu sont disponibles uniquement dans des environnements de **bac à sable**. En activant une fonctionnalité d'aperçu, vous l'activez pour tous les utilisateurs de votre organisation qui se trouvent dans cet environnement. En désactivant la fonctionnalité d'aperçu, vous la désactivez et la rendez inaccessible à vos utilisateurs. Les fonctionnalités d'aperçu ont une prise en charge limitée dans Human Resources. Elles peuvent utiliser moins de mesures de confidentialité et de sécurité, et elles ne sont pas incluses dans le contrat de niveau de service de Human Resources (SLA). Vous ne devez pas utiliser les fonctionnalités d'aperçu pour traiter des données personnelles (c'est-à-dire, toute information susceptible de vous identifier), ou pour traiter d'autres données soumises à des exigences de conformité juridique ou réglementaire.

1. Dans Human Resources, sélectionnez **Administration du système**.

2. Sélectionnez la vignette **Gestion des fonctionnalités**.

3. Pour activer une fonction d'aperçu, sélectionnez-la dans la liste, puis sélectionnez **Activer**. Pour désactiver une fonction d'aperçu, sélectionnez-la dans la liste, puis sélectionnez **Désactiver**.

## <a name="preview-feature-benefits-management"></a>Fonctionnalité d'aperçu : gestion des avantages

La gestion des avantages vous offre une solution flexible qui prend en charge une grande variété d'options, ainsi qu'une expérience utilisateur facile à utiliser qui met en valeur vos offres. Pour plus d'informations sur la configuration et l'utilisation de la gestion des avantages, voir [Présentation de la gestion des avantages](hr-benefits-management-overview.md).

La gestion des avantages remplace la fonctionnalité de l'espace de travail **Avantages**. Lorsque vous activez la fonction d'aperçu de la gestion des avantages, vous ne pouvez plus accéder aux écrans suivants dans l'espace de travail **Avantages** :

- **Avantages**
- **Détails des avantages**
- **Taux de calcul des contributions**
- **Résultats de l'inscription à l'avantage**
- **Résultats de l'expiration et de l'extension des avantages**
- **Types de règles de stratégie de droit aux avantages**
- **Stratégies de droit aux avantages**
- **Événements de droit**

Vous pouvez afficher les informations de ces écrans en mode lecture seule. Si vous souhaitez modifier les informations, vous devez d'abord désactiver la fonction d'aperçu de la gestion des avantages.

### <a name="benefits-management-known-issues"></a>Problèmes connus liés à la gestion des avantages

#### <a name="life-events"></a>Événements de vie

Lors du traitement des événements de vie, l'utilisateur recevra une erreur :

La date de début de la couverture doit être comprise entre *début de la période du plan* et *fin de la période du plan*. 

L'événement de vie continuera de se dérouler comme prévu.

#### <a name="eligibility-processing"></a>Traitement de l'éligibilité

Lors de l'exécution de l'admissibilité aux avantages qui utilisent un salaire de 1 à 5X, un pourcentage du salaire et un montant forfaitaire, la date de détail des avantages doit être définie sur la date de début d'emploi dans **Historique des emplois**, avec les heures travaillées, la fréquence des versements et le montant du salaire annuel. S'il existe une rémunération fixe pour le collaborateur, entrez les heures travaillées ainsi que la fréquence de paiement, et le montant du salaire annuel sera calculé. Si l'employé est salarié, les heures travaillées ne sont pas nécessaires. Nous recommandons que lors de la création de nouveaux employés, vous entriez d'abord la rémunération fixe. Pour mettre à jour l'enregistrement des détails des avantages : accédez à **Collaborateur > Historique du collaborateur > Détails de l'emploi**. Ajustez la date selon la date de début des collaborateurs.

#### <a name="employee-self-service"></a>Libre-service employé

Les employés peuvent sélectionner un plan pour lequel ils ne sont pas qualifiés et le mettre dans le panier. Par exemple : un collaborateur n'a pas de personnes à charge, mais il est autorisé à sélectionner un plan médical avec une option de couverture familiale.

Le montant de l'employé n'est pas calculé lors de la mise à jour du montant de la couverture d'assurance-vie. Par exemple, lorsqu'un employé se voit proposer un régime d'assurance-vie, il peut sélectionner jusqu'à 50 000 $ de couverture au coût de 0,36 $ par 1 000 $ de couverture.  Lorsque l'employé met à jour le montant de la couverture, le coût associé pour l'employé reste nul.

Pour un plan d'avantages qui ne permet qu'une seule sélection de ce type de plan, l'utilisateur recevra une erreur s'il tente de renoncer à un plan après l'avoir sélectionné. Par exemple, un utilisateur sélectionne un plan médical et le place dans son panier. L'utilisateur sélectionne ensuite **Renoncer** pour un autre plan médical. L'utilisateur recevra une erreur.

## <a name="preview-features-in-leave-and-absence"></a>Aperçu des fonctionnalités dans Congé et absence

Les fonctionnalités dans Congé et absence comprennent :

- **Calendrier des congés et des absences** - Les paramètres de congé et d'absence passeront des **Paramètres des ressources humaines** vers un nouvel écran appelé **Paramètres de congé et d'absence**. Le nouvel écran comprend un nouvel onglet **Calendrier**. Cet aperçu n'active qu'un sous-ensemble des paramètres. Vous pouvez accéder au nouvel écran depuis l'onglet **Liens** de l'espace de travail **Congé et absence**. Les calendriers comprennent :
  - **Calendrier d'entreprise** - Affiche toutes les demandes de congé des employés. Les personnes avec le rôle **Human Resources** peuvent accéder à ce calendrier à partir de l'onglet **Liens** de l'espace de travail **Congé et absence**.
  - **Calendrier de l'équipe de gestion** - Affiche les demandes de congés de tous les subordonnés directs. Les gestionnaires peuvent accéder au calendrier à partir de l'onglet **Mon équipe** dans le Libre-service employé sous **Congé et absence**. 

- **Calendriers des jours fériés - Congé et absence** - Les types de congé incluent une nouvelle option **Jour férié**, utilisée en conjonction avec le calendrier du temps de travail. Les jours définis comme des jours fériés et de fermeture sont désormais désignés comme **Jour férie** lorsque les jours ouvrables sont générés. Lorsque les provisions sont traitées, des ajustements sont apportés aux employés affectés au calendrier pour tenir compte des jours fériés tombant un jour ouvrable.

- **Vérification des provisions de congé** - Un nouvel écran vous permet de vérifier quand les provisions ont été traitées et supprimées, à la fois pour tous les employés et pour un employé spécifique. Vous pouvez accéder à ce nouvel écran depuis l'onglet **Liens** de l'espace de travail **Congé et absence**.

- **Suppression de la provision de congé** - Vous pouvez désormais supprimer les enregistrements de provision pour des plans de congé spécifiques. Vous pouvez accéder à cette option depuis l'onglet **Liens** de l'espace de travail **Congé et absence**. Pour les employés individuels, cette option apparaît dans le regroupement **Congé et absence** dans le profil de l'employé. 

- **Arrondi de provision de congé** - De nouvelles options pour le **Type de congé** définissent le type d'arrondi à utiliser pour une provision, ainsi que la précision décimale de l'arrondi appliqué à la provision. Lorsque les provisions sont traitées, l'arrondi et la précision décimale sont appliqués aux enregistrements de provision. 

- **Configurer plusieurs types de congés sur un seul plan de congés** - Une nouvelle colonne dans le calendrier de provision des congés pour les types de congés vous permet de définir plusieurs types de congés sur un plan de congés et d'absences avec différents calendriers de provision. L'ancien champ **Type de congé** est supprimé. Lors de l'inscription des employés, les soldes des types de congés s'affichent désormais dans un tableau plutôt qu'en haut de l'écran.

  > [!IMPORTANT]
  > Vous ne pouvez pas désactiver cette fonctionnalité après l'avoir activée.

- **Utiliser l'équivalence à temps plein (ETP) d'un employé pour la provision** - Une nouvelle colonne sur le calendrier de provision des congés permet d'utiliser l'ETP pour la provision. Lorsque les provisions sont traitées, la demande utilise le poste principal de l'employé et l'ETP défini pour déterminer le montant des provisions au prorata.

  > [!NOTE]
  > Cette fonctionnalité n'est disponible que si vous activez **Configurer plusieurs types de congés par plan de congé**. 

## <a name="feedback"></a>Rétroaction

Nous voulons connaître votre avis sur votre expérience avec les fonctionnalités d'aperçu. Nous vous encourageons à publier régulièrement vos commentaires sur les sites suivants lorsque vous utilisez ces fonctionnalités ou d'autres :

- [Communauté](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Ce site est une ressource utile où les utilisateurs peuvent discuter de cas d'utilisation, poser des questions et obtenir l'aide de la communauté.
- Faites-nous part des fonctionnalités que vous souhaitez voir dans le produit ou des modifications qui, selon vous, doivent être apportées aux fonctionnalités. Suggérez des idées sur les produits dans [Idées pour Human Resources](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    
N'ajoutez pas des données personnelles (toute information susceptible de vous identifier) dans vos commentaires ou vos demandes d'évaluation du produit. Les informations collectées peuvent être analysées davantage, et ne sont pas utilisées pour répondre à des demandes aux termes des lois applicables sur la confidentialité. Les données personnelles qui sont collectées séparément dans le cadre de ces programmes sont soumises à la [Déclaration de confidentialité Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Voir également :

- [Nouveautés dans Human Resources](hr-admin-whats-new.md)
- [Notes de publication de la Power Platform et Dynamics 365](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1)