---
title: Options de génération d’états
description: Cette rubrique explique comment personnaliser les rapports Microsoft Dynamics 365 Human Resources ou en créer de nouveaux.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4649005d6944c05310fc40f0dfd10519b2739ff0
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693974"
---
# <a name="reporting-options"></a>Options de génération d’états


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



**Détails de l’environnement**

Ce problème s’applique à tous les environnements.

**Symptôme**

Le client souhaite personnaliser des états Microsoft Dynamics 365 Human Resources ou créer des états.

**Sortie**

L’utilisateur ne peut pas personnaliser les états Microsoft Power BI intégrés.

**Solution**

- Les données Human Resources qui arrivent dans Dataverse peuvent être déclarées via le connecteur Power Apps Dataverse sur Power BI Desktop. Notez que Dataverse contient un sous-ensemble de données Human Resources. Pour en savoir plus sur Power BI et les tableaux de bord, voir [Créer des rapports et des tableaux de bord Power BI avec Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- La gestion des états électroniques (ER) est disponible pour certains états dans Human Resources. Les personnalisations effectuées par les clients peuvent être réalisées via les options de configuration d’ER.
- Les données peuvent être exportées vers Microsoft Excel ou Microsoft Word à l’aide de différentes entités de données fournies par Human Resouces via l’intégration à Microsoft Office.

**Solution à long terme**

Des options Power BI supplémentaires seront disponibles, et des données et entités supplémentaires feront partie de Dataverse.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
