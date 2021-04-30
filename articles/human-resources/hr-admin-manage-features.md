---
title: Gérer les fonctionnalités dans Human Resources
description: Découvrez comment activer ou désactiver de nouvelles fonctionnalités dans Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 038e741978bce033621bad428321a4b14ac90650
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889834"
---
# <a name="manage-features-in-human-resources"></a>Gérer les fonctionnalités dans Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dans le cadre de notre lancement continu de nouvelles fonctionnalités pour Microsoft Dynamics 365 Human Resources, nous souhaitons que nos clients expérimentent de nouvelles fonctionnalités dès que possible. Nous fournissons des fonctionnalités d’aperçu, presque prêtes pour la mise à disposition générale et qui ont fait l’objet de tests étendus. Nous attendons les derniers commentaires et validations des clients avant leur publication pour une disponibilité générale.

Pour plus d’informations sur les nouvelles fonctions dans Human Resources, voir [Nouveautés dans Human Resources](hr-admin-whats-new.md) et [Notes de publication de la Power Platform et Dynamics 365](/dynamics365/release-plans/?panel=products1#pivot=products).

L’espace de travail **Gestion des fonctions** fournit une liste des fonctions fournies dans chaque lancement. Par défaut, les nouvelles fonctionnalités sont désactivées. Vous pouvez utiliser l’espace de travail pour les activer et consulter la documentation les concernant. Pour plus d’informations sur la gestion des fonctions, voir [Présentation de la gestion des fonctions](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Toutes les nouvelles fonctionnalités restent dans la version préliminaire pendant au moins 30 jours, et généralement entre 30 et 60 jours. Les fonctionnalités principales sont généralement disponibles en octobre et en avril chaque année suivant la période de version préliminaire. Dès que vous voyez de nouvelles fonctionnalités dans l’espace de travail **Gestion des fonctions**, vous pouvez les activer. Certaines fonctionnalités peuvent être activées par défaut.

Une fois qu’une fonction est généralement disponible, elle peut être activée ou désactivée dans les environnements de production. L’espace de travail **Gestion des fonctions** indique quand une fonction d’aperçu devient obligatoire. Cette date est généralement le 1er octobre ou le 1er avril pour s’aligner avec les plans de lancement semi-annuels. Vous ne pouvez pas désactiver les fonctions obligatoires. Tant qu’elle n’est pas obligatoire, vous pouvez activer et désactiver une fonction dans tous les environnements.

## <a name="enable-or-disable-preview-features"></a>Activer ou désactiver les fonctionnalités d’aperçu

Pour accéder aux fonctionnalités d’aperçu, vous devez commencer par les activer dans votre environnement. L’activation ou la désactivation des fonctionnalités d’aperçu est propre à l’environnement.

> [!IMPORTANT]
> Les fonctions d’aperçu sont disponibles uniquement dans des environnements de **bac à sable**. En activant une fonctionnalité d’aperçu, vous l’activez pour tous les utilisateurs de votre organisation qui se trouvent dans cet environnement. En désactivant la fonctionnalité d’aperçu, vous la désactivez et la rendez inaccessible à vos utilisateurs. Les fonctionnalités d’aperçu ont une prise en charge limitée dans Human Resources. Elles peuvent utiliser moins de mesures de confidentialité et de sécurité, et elles ne sont pas incluses dans le contrat de niveau de service de Human Resources (SLA). Vous ne devez pas utiliser les fonctionnalités d’aperçu pour traiter des données personnelles (c’est-à-dire, toute information susceptible de vous identifier), ou pour traiter d’autres données soumises à des exigences de conformité juridique ou réglementaire.

1. Dans Human Resources, sélectionnez **Administration du système**.

2. Sélectionnez la vignette **Gestion des fonctionnalités**.

3. Pour activer une fonction d’aperçu, sélectionnez-la dans la liste, puis sélectionnez **Activer**. Pour désactiver une fonction d’aperçu, sélectionnez-la dans la liste, puis sélectionnez **Désactiver**.

## <a name="enable-or-disable-benefits-management"></a>Activation ou désactivation de la gestion des avantages

Pour activer la gestion des avantages, utilisez la même procédure figurant dans [Activer ou désactiver les fonctionnalités d’aperçu](hr-admin-manage-features.md?enable-or-disable-preview-features).

> [!IMPORTANT]
> Vous ne pouvez pas désactiver la gestion des avantages dans un environnement de type **Production** après l’avoir activé. En revanche, vous pouvez désactiver la gestion des avantages dans les environnements de type **Bac à sable**.

Pour plus d’informations sur la configuration et l’utilisation de la gestion des avantages, voir [Présentation de la gestion des avantages](hr-benefits-management-overview.md).

La gestion des avantages remplace la fonctionnalité de l’espace de travail **Avantages**. Lorsque vous activez la fonction d’aperçu de la gestion des avantages, vous ne pouvez plus accéder aux écrans suivants dans l’espace de travail **Avantages** :

- **Avantages**
- **Détails des avantages**
- **Taux de calcul des contributions**
- **Résultats de l’inscription à l’avantage**
- **Résultats de l’expiration et de l’extension des avantages**
- **Types de règles de stratégie de droit aux avantages**
- **Stratégies de droit aux avantages**
- **Événements de droit**

Vous pouvez afficher les informations de ces écrans en mode lecture seule. Si vous souhaitez modifier les informations, vous devez d’abord désactiver la fonction d’aperçu de la gestion des avantages (applicable uniquement aux environnements de type **Bac à sable**).

## <a name="enable-or-disable-leave-and-absence"></a>Activer ou désactiver Congés et absences

Pour activer Congés et absences, utilisez la même procédure dans [Activer ou désactiver les fonctionnalités d’aperçu](hr-admin-manage-features.md?enable-or-disable-preview-features).

> [!IMPORTANT]
> Vous ne pouvez pas désactiver la fonction **Plusieurs types de congés** dans Congés et absences après l’avoir activé. Cela vaut pour les deux environnements de type **Bac à sable** et **Production**.

Pour en savoir plus sur les fonctionnalités d’aperçu dans Congés et absences, voir [Fonctionnalités d’aperçu de Congés et absences](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

## <a name="send-us-feedback"></a>Envoyez-nous vos commentaires

Nous voulons connaître votre avis sur votre expérience avec les fonctionnalités d’aperçu. Nous vous encourageons à publier régulièrement vos commentaires sur les sites suivants lorsque vous utilisez ces fonctionnalités ou d’autres :

- [Communauté](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Ce site est une ressource utile où les utilisateurs peuvent discuter de cas d’utilisation, poser des questions et obtenir l’aide de la communauté.
- Faites-nous part des fonctionnalités que vous souhaitez voir dans le produit ou des modifications qui, selon vous, doivent être apportées aux fonctionnalités. Suggérez des idées sur les produits dans [Idées pour Human Resources](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources).
    
N’ajoutez pas des données personnelles (toute information susceptible de vous identifier) dans vos commentaires ou vos demandes d’évaluation du produit. Les informations collectées peuvent être analysées davantage, et ne sont pas utilisées pour répondre à des demandes aux termes des lois applicables sur la confidentialité. Les données personnelles qui sont collectées séparément dans le cadre de ces programmes sont soumises à la [Déclaration de confidentialité Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Voir également :

- [Nouveautés dans Human Resources](hr-admin-whats-new.md)
- [Notes de publication de la Power Platform et Dynamics 365](/dynamics365/release-plans/?panel=products1#pivot=products)

[!INCLUDE[footer-include](../includes/footer-banner.md)]