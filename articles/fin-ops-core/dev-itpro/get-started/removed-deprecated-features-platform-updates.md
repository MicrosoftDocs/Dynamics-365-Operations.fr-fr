---
title: Fonctions de plateforme supprimées ou obsolètes
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer dans les mises à jour de plateforme des applications Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: d394f5ca84efc5beb943d349e45a3d2c9639d83c
ms.sourcegitcommit: 75974ae567bb0eacf0f65cac992b34ce5c680b93
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2020
ms.locfileid: "3095772"
---
# <a name="removed-or-deprecated-platform-features"></a>Fonctions de plateforme supprimées ou obsolètes

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer dans les mises à jour de plateforme des applications Finance and Operations.

- Une fonction *supprimée* n'est plus disponible dans le produit.
- Une fonction *déconseillée* n'est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification. 

> [!NOTE]
> Des informations détaillées sur les objets dans les applications Finance and Operations sont disponibles dans les [États de référence technique](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés dans chaque version des applications Finance and Operations.

## <a name="platform-update-32"></a>Platform update 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>La boîte de dialogue de demande de modification du workflow n'inclut plus de liste déroulante de sélection de l'utilisateur
|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | Il s'agissait d'un problème de sécurité, car la demande de modification pouvait être envoyée à un utilisateur indésirable. Il s'agissait également d'un problème d'utilisation, car cela obligeait l'utilisateur à déterminer le créateur du workflow et à le sélectionner manuellement.  |
| **Remplacé par une autre fonctionnalité ?**   | Non |
| **Zones de produit affectées**         | Workflow |
| **Option de déploiement**              | Tous |
| **État**                         | La liste déroulante de sélection de l'utilisateur a été supprimée de la boîte de dialogue de demande de modification dans Platform update 32. Les demandes de modification seront automatiquement envoyées à l'expéditeur comme prévu. Pour plus d'informations sur cette fonctionnalité, consultez [Actions dans les processus d'approbation de workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Les liens de suivi intégrés ne sont plus pris en charge dans les documents paginés rendus par le service hébergé par le cloud 
|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | Les URL de navigation intégrées dans des documents rendus par le service peuvent contenir des données de l'entreprise sensibles. Nous supprimons le support des liens de suivi intégrés dans les documents par mesure de prudence pour protéger davantage les données des clients. Les utilisateurs bénéficieront de performances améliorées tout en produisant des documents interactivement suite à ce changement.  |
| **Remplacé par une autre fonctionnalité ?**   | N° |
| **Zones de produit affectées**         | Génération d'états |
| **Option de déploiement**              | Tout |
| **État**                         | Cette fonctionnalité est supprimée activement du service.<br><br>Le client moderne offre de nombreuses options pour produire des vues qui comprennent des liens générés automatiquement pour contribuer à la navigation dans l'application. Les documents paginés rendus par le service sont recommandés pour les communications externes qui sont envoyées par courrier électronique, archivées et imprimées pour les destinataires. Nous avons amélioré l'expérience de prévisualisation des documents directement dans le navigateur, ce qui offre un accès direct aux imprimantes locales. Pour plus d'informations, voir [Afficher un aperçu des documents PDF avec une visionneuse intégrée](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/preview-pdf-documents). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annonces précédentes sur les fonctions supprimées ou obsolètes
Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../migration-upgrade/deprecated-features.md).

