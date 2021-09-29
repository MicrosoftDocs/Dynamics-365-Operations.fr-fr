---
title: Rendre unique le délimiteur du plan de comptes
description: Cette rubrique explique comment vous ne pouvez pas avoir le même séparateur pour le plan de comptes et les valeurs de dimension. Vous devez modifier les valeurs de délimiteur après la mise à niveau.
author: panolte
ms.date: 09/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: a19dc8926df0efeac242e2e42ac37fdad91df9f8
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500501"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>Rendre unique le délimiteur du plan de comptes

[!include [banner](../includes/banner.md)]

Dans Microsoft Dynamics AX 2012, vous pouviez utiliser le même délimiteur pour votre plan de comptes et les valeurs de dimension. Dans les versions actuelles de Finance and Operations, vous ne pouvez pas avoir le même délimiteur pour le plan de comptes et les valeurs de dimension. Si un délimiteur est en double, vous pouvez le modifier après la mise à niveau. 

## <a name="update-delimiter"></a>Mettre à jour le délimiteur
En cas de conflit avec le plan de comptes, le délimiteur de plan de comptes et le format de l’ID de projet/sous-projet peut être modifié. Aucun autre délimiteur de dimension ne peut être modifié. 
- Vous pouvez modifier le séparateur de plan de comptes après la mise à niveau dans **Paramètres de comptabilité** > **Plan de comptes et dimensions** > **Modifier le délimiteur**. 
- Si le seul conflit est avec le format d’ID de projet/sous-projet, vous pouvez modifier cette valeur dans **Paramètres de gestion et comptabilité des projets** > **Général** > **Modifier le format du sous-projet**. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Procédure pour déterminer si votre environnement nécessite des délimiteurs mis à jour 
Si les délimiteurs de votre environnement mis à niveau sont en conflit, vous pouvez rencontrer de l’instabilité en entrant des valeurs dans un contrôle d’accès segmenté et un contrôle d’entrée de dimension. Cela signifie que vous devez toujours utiliser les recherches ou un menu volant pour la saisie des combinaisons de compte et de dimensions.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
