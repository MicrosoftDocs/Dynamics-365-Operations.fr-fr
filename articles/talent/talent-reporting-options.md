---
title: Options de génération d'états dans Talent
description: Cette rubrique explique comment résoudre le problème où un client souhaite personnaliser des états Microsoft Dynamics 365 Talent ou créer des états.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 50342c847200d015a66c6f22007070bb26c6caef
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009350"
---
# <a name="reporting-options-in-talent"></a>Options de génération d'états dans Talent

[!include [banner](includes/banner.md)]

**Détails de l'environnement**

Ce problème s'applique à tous les environnements.

**Symptôme**

Le client souhaite personnaliser des états Microsoft Dynamics 365 Talent ou créer des états.

**Problème**

L'utilisateur ne peut pas personnaliser les états Microsoft Power BI intégrés.

**Solution**

- Les données Core HR qui arrivent dans Common Data Service peuvent être déclarées via le connecteur PowerApps Common Data Service sur Power BI Desktop. Notez que Common Data Service contient un sous-ensemble de données Core HR. Pour en savoir plus sur Power BI et les tableaux de bord, voir [Créer des rapports et des tableaux de bord Power BI avec PowerApps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- La gestion des états électroniques (ER) est disponible pour certains états dans Talent. Les personnalisations effectuées par les clients peuvent être réalisées via les options de configuration d'ER.
- Les données peuvent être exportées vers Microsoft Excel ou Microsoft Word à l'aide de différentes entités de données fournies par Talent via l'intégration à Microsoft Office.

**Solution à long terme**

Des options Power BI supplémentaires seront disponibles, et des données et entités supplémentaires feront partie de Common Data Service.
