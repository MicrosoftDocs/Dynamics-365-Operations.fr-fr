---
title: Options de génération d’états
description: Cet article explique comment résoudre le problème où un client souhaite personnaliser des états Microsoft Dynamics 365 Human Resources ou créer des états.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 66581331dceacc1c0fa1816bf336339693db5339
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463284"
---
# <a name="reporting-options"></a>Options de génération d’états

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

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