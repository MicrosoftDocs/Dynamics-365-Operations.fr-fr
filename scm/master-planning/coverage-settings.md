---
title: "Paramètres de couverture"
description: "Le calcul PDP/MRP utilise les paramètres de couverture pour calculer les demandes d'articles."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b42f0515823bd42ec260aa1d175855a923162b62
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017

---

# <a name="coverage-settings"></a>Paramètres de couverture

[!include[banner](../includes/banner.md)]


Le calcul PDP/MRP utilise les paramètres de couverture pour calculer les demandes d'articles. 

Vous pouvez spécifier des paramètres de couverture de plusieurs façons :

-   Spécifiez des paramètres de couverture pour un groupe de couverture. Vous pouvez créer un groupe de couverture contenant des paramètres pour tous les produits qui lui sont liés. Cliquez sur **Planification &gt; Paramétrage &gt; Couverture &gt; Groupes de couverture** pour créer un groupe de couverture. Vous pouvez lier un groupe de couverture à un produit. Si le lien est spécifique à un site, un entrepôt ou une dimension de produit, utilisez le champ **Groupe de couverture** dans la page **Couverture de l'article**. Si le lien est générique, indépendamment des dimensions de produit, utilisez le champ **Groupe de couverture** sous l'organisateur **Plan** de la page **Détails de produit**. Si vous ne liez pas de groupe de couverture à un produit, la planification utilise par défaut le **Groupe de couverture général** spécifié dans la page **Paramètres de planification**.

-   Spécifiez des paramètres de couverture pour un produit. Vous pouvez créer des paramètres de couverture pour un produit spécifique. Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Sélectionnez le produit, dans le **volet Actions**, sous l'onglet **Plan**, dans le champ **Groupe de couverture**, cliquez sur **Couverture de l'article** pour ouvrir la page **Couverture de l'article**. Si le produit est déjà lié à un groupe de couverture, vous pouvez remplacer les paramètres de groupe de couverture à l'aide du champ **Remplacer**. Les paramètres de couverture de la page**Couverture de l'article** prévalent sur les paramètres de la page **Groupe de couverture**.

<!-- -->

-   Spécifiez des paramètres de couverture pour un produit à l'aide d'un Assistant. L'Assistant fournit des instructions détaillées sur la définition des principaux paramètres de couverture de l'article. Dans la page **Couverture de l'article**, cliquez sur **Assistant** pour ouvrir l'**Assistant Couverture d'article**.

<!-- -->

-   Spécifiez des paramètres de couverture pour un groupe de dimensions. Cliquez sur **Gestion des informations sur les produits &gt; Commun &gt; Produits lancés**. Dans la page **Détails des produits lancés**, sous l'onglet **Général**, dans le groupe **Administration**, cliquez sur le lien **Groupe de dimension de stockage**. Dans la page **Groupe de dimensions de stockage**, sélectionnez le champ **Plan de couverture par dimension** pour créer les paramètres de couverture d'une dimension dans le groupe de dimensions de stockage. Le champ **Plan de couverture par dimension** doit être sélectionné pour toutes les dimensions de produit, telles que la configuration, la couleur, la taille et le style.



<a name="see-also"></a>Voir également :
--------

[Plans généraux](master-plans.md)




