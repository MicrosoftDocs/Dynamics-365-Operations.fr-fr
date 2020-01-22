---
title: Nouveautés ou modifications dans Dynamics 365 Talent (5 novembre 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 48de07178acfaccf11e0a02b2848bf24e6ccc117
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896771"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (5 novembre 2019)

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2598. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="copy-a-core-hr-instance"></a>Copier une instance Core HR

Dans la version de cette semaine, vous pouvez utiliser Microsoft Dynamics Lifecycle Services (LCS) pour copier une base de données Microsoft Dynamics 365 Talent: Core HR dans un environnement de bac à sable. Si vous avez un autre environnement de bac à sable, vous pouvez également copier la base de données de cet environnement vers un environnement cible de bac à sable. Pour plus d'informations, voir :

- [Gestion de l'environnement plus étendue](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) dans Dynamics 365 : 2e partie du lancement 2019.

- [Copier une instance Core HR](hr-copy-instance.md) dans la documentation Talent

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a>Les traitements par lots d'intégration Common Data Service ne sont pas créés lorsque l'intégration Common Data Service est activée (388030)

Cette modification créera des traitements par lots pour l'intégration de Common Data Service lorsqu'elle s'est activée.

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a>HcmPersonImageEntity ne redimensionne pas l'image de la personne une fois téléchargée (369469)

La publication de cette semaine modifie comment les images sont redimensionnées pour de meilleures performances lors de l'importation via la gestion des données.

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a>Une Date disponible pour affectation du poste peut être antérieure à la Date d'activation (340103)

Avec cette modification, un avertissement s'affichera si vous sélectionnez une **Date disponible pour affectation** antérieure à la **Date d'activation** du poste.

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a>Impossible de créer une demande de modification de rémunération dans le libre-service pour les employés pour les plans basés sur des étapes (376872)

Cette version corrige un problème lors de la demande des modifications de rémunération via le libre-service des employés pour les plans basés sur des étapes. 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a>Le code de motif ne se synchronise pas à Common Data Service si la description est supérieure à 30 caractères, Core HR en autorise 60 (352682)

à cette modification, les codes de motif avec plus de 30 caractères sont mis à jour dans Common Data Service. Les modifications effectuées dans Common Data Service seront également répercutées dans Talent.

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a>Intégration des adresses depuis Talent dans Finance and Operations (351961)

Cette version fixe un problème où les adresses mises à jour dans Talent n'étaient pas mises à jour dans Finance and Operations. Les modifications apportées aux blocs d'adresse seront désormais à jour.

## <a name="coming-soon"></a>Prochainement

### <a name="print-performance-reviews"></a>Imprimer les évaluations des performances

Voir [Imprimer les examens des performances](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) dans Dynamics 365 : 2e partie du lancement 2019.

### <a name="feature-management-workspace"></a>Espace de travail Gestion des fonctionnalités

Les fonctionnalités sont ajoutées et mises à jour dans chaque version. L'expérience de gestion de la fonctionnalité fournit un espace de travail dans lequel vous pouvez afficher une liste des fonctionnalités fournies dans chaque version. Par défaut, les nouvelles fonctionnalités sont désactivées. Vous pouvez utiliser l'espace de travail pour les activer et consulter la documentation les concernant.

Pour en savoir plus sur les modifications venant avec la gestion des fonctionnalités, voir [Vue d'ensemble de la gestion des fonctionnalités](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
