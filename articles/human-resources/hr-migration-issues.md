---
title: Problèmes connus avec la fusion de l’infrastructure de Dynamics 365 Human Resources
description: Cet article répertorie les problèmes susceptibles de survenir lors de la fusion de l’infrastructure de Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5f5981801317ad9647f57a0f68f9b67b592256ab
ms.sourcegitcommit: f96e5dec5a808d9819d2a23b8e15ce00aeff475b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2022
ms.locfileid: "9752688"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-known-issues"></a>Problèmes connus avec la fusion de l’infrastructure de Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="shared-dataverse-environments"></a>Environnements Dataverse partagés

La structure de la double écriture ne prend pas en charge la liaison de deux environnements d’applications de finances et d’opérations au même environnement Dataverse. Si vous avez un environnement Dataverse partagé avec les deux éléments suivants, vous devez soit dupliquer l’environnement Dataverse, soit le fractionner :

- Une application de finances et d’opérations
- Un environnement Human Resources actuel

## <a name="environment-type-requirements"></a>Conditions préalables relatives aux types d’environnement

Les types d’environnement suivants sont requis avant de pouvoir effectuer la migration :

- Si vous n’avez pas d’environnements autonomes bac à sable, vous devez en créer un pour valider la migration.
- Si vous disposez de plusieurs environnements autonomes de production, l’un d’entre eux peut être migré. Contactez le support Microsoft pour marquer les autres environnements comme environnements bac à sable.

## <a name="teams-integration"></a>Intégration de Teams

L’application Human Resources existante dans Teams est actuellement déplacée vers une solution Microsoft Power Platform. Pour plus d’informations, voir [Application Human Resources dans Teams](hr-admin-teams-leave-app.md).

