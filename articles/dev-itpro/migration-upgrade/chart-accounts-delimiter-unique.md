---
title: Rendre unique le délimiteur du plan de comptes
description: Dans Dynamics 365 for Finance and Operations, vous ne pouvez pas avoir le même séparateur pour le plan de comptes et les valeurs de dimension. Vous devez modifier les valeurs de délimiteur après la mise à niveau.
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: e197a1b44e038a97b8bf6db692dcc2eef2bc5f7b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "335851"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>Rendre unique le délimiteur du plan de comptes

[!include [banner](../includes/banner.md)]

Dans Microsoft Dynamics AX 2012, vous pouviez utiliser le même délimiteur pour votre plan de comptes et les valeurs de dimension. Dans Dynamics 365 for Finance and Operations, vous ne pouvez pas avoir le même séparateur pour le plan de comptes et les valeurs de dimension. Si un délimiteur est en double, vous pouvez le modifier après la mise à niveau. 

Cette fonctionnalité est disponible dans :
- Dynamics 365 for Finance and Operations version 8.0
- Dynamics 365 for Finance and Operations version 7.1, KB 4094701 Impossible d'entrer des dimensions financières lorsque les valeurs de la dimension contiennent le délimiteur de plan de comptes
- Dynamics 365 for Finance and Operations version 7.2, KB 4092967 Impossible de choisir un sous-projet lorsque comme dimension lorsque le format de celui-ci contient le délimiteur de dimension

## <a name="update-delimiter"></a>Mettre à jour le délimiteur
En cas de conflit avec le plan de comptes, le délimiteur de plan de comptes et le format de l'ID de projet/sous-projet peut être modifié. Aucun autre délimiteur de dimension ne peut être modifié. 
- Vous pouvez modifier le séparateur de plan de comptes après la mise à niveau vers Finance and Operations dans **Paramètres de comptabilité** > **Plan de comptes et dimensions** > **Modifier le délimiteur**. 
- Si le seul conflit est avec le format d'ID de projet/sous-projet, vous pouvez modifier cette valeur dans **Paramètres de gestion et comptabilité des projets** > **Général** > **Modifier le format du sous-projet**. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Procédure pour déterminer si votre environnement nécessite des délimiteurs mis à jour 
Si les délimiteurs de votre environnement mis à niveau sont en conflit, vous pouvez rencontrer de l'instabilité en entrant des valeurs dans un contrôle d'accès segmenté et un contrôle d'entrée de dimension. Cela signifie que vous devez toujours utiliser les recherches ou un menu volant pour la saisie des combinaisons de compte et de dimensions.
