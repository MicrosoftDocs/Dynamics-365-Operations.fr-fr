---
title: Retrait de Dynamics 365 Talent – Applications Attract et Onboard
description: Cette rubrique décrit le retrait de Dynamics 365 Talent – Applications Attract et Onboard.
author: twheeloc
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: e17b92621f05ad8483a7c578bfaece58a530df2d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692000"
---
# <a name="dynamics-365-talent-attract-and-onboard-apps-retirement"></a>Retrait des applications Dynamics 365 Talent: Attract et Onboard


En décembre 2019, nous avons annoncé le 1er février 2022 le retrait de Dynamics 365 Talent – applications Attract et Onboard, donnant à nos clients deux ans pour s’y préparer.

Pour plus d’informations sur le retrait de ces applications, consultez :
 - [Suppression des applications Dynamics 365 Talent – Attract et Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/humanresources/b/dynamics365forhumanresources/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)
 - [Renforcer les performances de la main d’œuvre avec Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources)

Nous continuerons à soutenir Dynamics 365 Human Resources, qui aidera nos clients à obtenir les informations nécessaires sur la main-d’œuvre pour créer des expériences d’employés basées sur les données dans plusieurs domaines, tels que :

- Rémunération
- Avantages
- Congé et absence
- Conformité
- Paie
- Commentaires sur les performances
- Formation et certification
- Programmes en libre service

## <a name="dynamics-365-talent-apps-retirement-faq"></a>FAQ sur le retrait des applications Dynamics 365 Talent

### <a name="what-is-the-user-experience-for-both-dynamics-365-talent---attract-and-onboard-apps-starting-february-1-2022"></a>Quelle est l’expérience utilisateur pour les applications Dynamics 365 Talent – applications Attract et Onboard à partir du 1er février 2022 ?

Les utilisateurs ne pourront pas utiliser les applications et seront redirigés vers une page de retrait.

### <a name="can-customers-continue-to-export-data-for-both-dynamics-365-talent---attract-and-onboard-apps-after-february-1-2022"></a>Les clients peuvent-ils continuer à exporter des données pour Dynamics 365 Talent – applications Attract et Onboard après le 1er février 2022 ?
  
Non, le retrait a été annoncé en décembre 2019 et les capacités d’exportation requises ont été fournies jusqu’au 1er février 2022. 

### <a name="will-the-customers-data-related-to-both-dynamics-365-talent---attract-and-onboard-apps-in-dataverse-be-deleted-after-february-1-2022"></a>Les données du client liées à Dynamics 365 Talent – applications Attract et Onboard dans Dataverse seront-elles supprimées après le 1er février 2022 ?

Non, les entités Dataverse resteront dans l’environnement Microsoft Dataverse du client même après le retrait, sauf si la solution Human Capital Management Talent est supprimée ou désinstallée.

### <a name="i-know-the-name-of-the-talent-environment-how-can-i-see-the-attract-and-onboard-data-in-dataverse"></a>Je connais le nom de l’environnement Talent. Comment puis-je voir les données Attract et Onboard dans Dataverse ?

1.  Connectez-vous à Power Apps : https://make.powerapps.com
2.  Sélectionnez l’environnement dans lequel vous souhaitez voir les données Attract et Onboard.
3.  Accédez à **Dataverse > Tables**. 
4.  Saisissez « msdyn_ » dans **Recherche**. Si vous voyez la liste des tables commençant par « msdyn_ » + noms de table (exemple : msdyn_candidate), vous avez trouvé l’environnement avec les données Attract et Onboard.

[![Power Apps](./media/Powerapps.png)](./media/Powerapps.png)

### <a name="i-dont-know-the-name-of-the-talent-environment-how-can-i-find-the-environment-that-has-the-data-for-the-dynamics-365-talent-attract-and-dynamics-365-talent-onboard-applications"></a>Je ne connais pas le nom de l’environnement Talent. Comment puis-je trouver l’environnement qui contient les données pour les applications Dynamics 365 Talent: Attract et Dynamics 365 Talent: Onboard ?

1)  Connectez-vous au centre d’administration Power Platform : https://admin.powerplatform.microsoft.com/
2)  Sélectionner **Environnements**.
3)  Sélectionnez un environnement spécifique à évaluer.
4)  Sélectionnez **Ressources > applications Dynamics 365**.
5)  Si vous voyez la solution **HCM Talent** installée, cet environnement doit contenir des données Attract et Onboard stockées. 

[![Power Platform](./media/HCMTalent.png)](./media/HCMTalent.png)

> [!NOTE] 
> La solution **HCM Talent** est également utilisée dans Dynamics 365 Human Resources.
