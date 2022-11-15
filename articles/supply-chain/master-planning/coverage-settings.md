---
title: Paramètres de couverture
description: Cet article fournit des informations sur les paramètres de couverture que le calcul PDP/MRP utilise pour calculer les demandes d’articles.
author: t-benebo
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard, ReqItemTableSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fcbf053a32ef2921aab9a81de68e5844f5cb6527
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740246"
---
# <a name="coverage-settings"></a>Paramètres de couverture

[!include [banner](../includes/banner.md)]

Le calcul PDP/MRP utilise les paramètres de couverture pour calculer les demandes d’articles.

Vous pouvez spécifier des paramètres de couverture de plusieurs façons :

- Spécifiez des paramètres de couverture pour un groupe de couverture.

    Vous pouvez créer un groupe de couverture contenant des paramètres pour tous les produits qui lui sont liés. Pour créer un groupe de couverture, accédez à **Planification &gt; Paramétrage &gt; Couverture &gt; Groupes de couverture**. Vous pouvez lier un groupe de couverture à un produit. Si le lien est spécifique à un site, un entrepôt ou une dimension de produit, utilisez le champ **Groupe de couverture** dans la page **Couverture de l’article**. Si le lien est générique, indépendamment des dimensions de produit, utilisez le champ **Groupe de couverture** sous l’organisateur **Plan** de la page **Détails de produit**. Par défaut, si vous ne liez pas de groupe de couverture à un produit, la planification utilise le groupe de couverture général spécifié dans la page **Paramètres de planification**.

- Spécifiez des paramètres de couverture pour un produit.

    Vous pouvez créer des paramètres de couverture pour un produit spécifique. Allez à **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Sélectionnez le produit, puis dans le volet Actions, sous l’onglet **Plan**, dans le champ **Groupe de couverture**, cliquez sur **Couverture de l’article** pour ouvrir la page **Couverture de l’article**. Si le produit est déjà lié à un groupe de couverture, vous pouvez remplacer les paramètres de groupe de couverture à l’aide du champ **Remplacer**. Les paramètres de couverture de la page **Couverture de l’article** prévalent sur les paramètres de la page **Groupe de couverture**.

- Spécifiez des paramètres de couverture pour un produit à l’aide d’un Assistant.

    L’Assistant vous guide étape par étape via le processus de paramétrage des principaux paramètres de couverture de l’article. Dans la page **Couverture de l’article**, dans le volet Action, cliquez sur **Assistant** pour ouvrir l’**Assistant Couverture d’article**.

- Spécifiez des paramètres de couverture pour un groupe de dimensions.

    Allez à **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Dans la page **Détail du produit lancé**, sous l’organisateur **Général**, dans la section **Administration**, sélectionnez le lien dans le champ **Groupe de dimension de stockage**. Dans la page **Groupes de dimensions de stockage**, activez la case à cocher **Plan de couverture par dimension** pour créer les paramètres de couverture d’une dimension dans le groupe de dimensions de stockage. Le champ **Plan de couverture par dimension** doit être sélectionné pour toutes les dimensions de produit, telles que la configuration, la couleur, la taille et le style.


## <a name="coverage-codes"></a>Codes de couverture

La planification générique peut être configurée pour utiliser plusieurs méthodes de réapprovisionnement. Les méthodes de réapprovisionnement ou de calibrage sont des techniques utilisées par le système pour déterminer la taille de lot pour les articles achetés ou les articles produits. 

Chaque méthode de réapprovisionnement se voit attribuer un des codes de couverture suivants :

- **Manuel** : méthode de calibrage pour laquelle le système ne suggère pas les ordres de fabrication, de transfert ou d’achat pour l’article. Le planificateur de l’article est chargé de créer les commandes requises pour le réapprovisionnement de l’article.
- **Par besoin** : méthode de calibrage dans laquelle le système crée un ordre de fabrication, de transfert ou d’achat planifié selon les besoins pour l’article. Elle est généralement utilisée pour les articles coûteux avec une demande intermittente.  
- **Par période** : méthode de calibrage qui associe toutes les demandes pour une période en une commande pour l’article. La commande sera planifiée pour le premier jour de la période et sa quantité répondra aux besoins nets pendant la période définie. La période commence avec la première demande de l’article et couvre la plage définie dans le temps. La période suivante commencera avec les prochains besoins de l’article.
- **Min/Max** : méthode de calibrage qui contient le réapprovisionnement du stock jusqu’à un certain niveau quand le disponible prévisionnel est inférieur à un seuil. La quantité de réapprovisionnement sera la différence entre le niveau maximum et le niveau disponible prévisionnel.


## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des plans généraux](master-plans.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]