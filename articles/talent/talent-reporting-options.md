---
title: Options de génération d'états dans Talent
description: Cette rubrique explique comment résoudre le problème où un client souhaite personnaliser des états Microsoft Dynamics 365 for Talent ou créer des états.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304424"
---
# <a name="reporting-options-in-talent"></a>Options de génération d'états dans Talent

[!include [banner](includes/banner.md)]

**Détails de l'environnement**

Ce problème s'applique à tous les environnements.

**Symptôme**

Le client souhaite personnaliser des états Microsoft Dynamics 365 for Talent ou créer des états.

**Problème**

L'utilisateur ne peut pas personnaliser les états Microsoft Power BI intégrés.

**Solution**

- Les données Core HR qui arrivent dans Common Data Service pour les applications peuvent être déclarées via le connecteur CDS PowerApps sur Power BI Desktop. Notez que Common Data Service pour les applications contient un sous-ensemble de données Core HR. Pour en savoir plus sur Power BI et les tableaux de bord, voir [Créer des rapports et des tableaux de bord Power BI avec PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).
- La gestion des états électroniques (ER) est disponible pour certains états dans Talent. Les personnalisations effectuées par les clients peuvent être réalisées via les options de configuration d'ER.
- Les données peuvent être exportées vers Microsoft Excel ou Microsoft Word à l'aide de différentes entités de données fournies par Talent via l'intégration à Microsoft Office.

**Solution à long terme**

Des options Power BI supplémentaires seront disponibles, et des données et entités supplémentaires feront partie de Common Data Service pour les applications.
