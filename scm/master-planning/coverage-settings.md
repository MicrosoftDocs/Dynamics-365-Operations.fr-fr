---
title: "Paramètres de couverture"
description: "Le calcul PDP/MRP utilise les paramètres de couverture pour calculer les demandes d&quot;articles."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c1c5654afa6b592e178af052e3e4a7e246a94c9f
ms.lasthandoff: 03/31/2017


---

# <a name="coverage-settings"></a>Paramètres de couverture

Le calcul PDP/MRP utilise les paramètres de couverture pour calculer les demandes d'articles. 

Vous pouvez spécifier des paramètres de couverture de plusieurs façons :

-   Spécifiez des paramètres de couverture pour un groupe de couverture. Vous pouvez créer un groupe de couverture contenant des paramètres pour tous les produits qui lui sont liés. Cliquez sur ** planification &gt; paramétrez &gt; les groupes &gt; de couverture de couverture ** pour créer un groupe de couverture. Vous pouvez lier un groupe de couverture à un produit. Si le lien est spécifique à un site, un entrepôt ou une dimension de produit, utilisez le champ **Groupe de couverture** dans la page **Couverture de l'article**. Si le lien est générique, indépendamment des dimensions de produit, utilisez le champ **Groupe de couverture** sous l'organisateur **Plan** de la page **Détails de produit**. Si vous ne liez pas de groupe de couverture à un produit, la planification utilise par défaut le **Groupe de couverture général** spécifié dans la page **Paramètres de planification**.

-   Spécifiez des paramètres de couverture pour un produit. Vous pouvez créer des paramètres de couverture pour un produit spécifique. Cliquez sur ** produits lancés de produits &gt; de gestion &gt; des informations sur le produit **. Sélectionnez le produit, sous ** volet Actions **, sous ** plan ** onglet dans, ** groupe de couverture **, cliquez sur ** couverture de l'article ** pour ouvrir ** couverture de l'article ** la page. Si le produit est déjà lié à un groupe de couverture, vous pouvez remplacer les paramètres de groupe de couverture à l'aide du champ **Remplacer**. Les paramètres de couverture de la page** Couverture de l'article** prévalent sur les paramètres de la page **Groupe de couverture**.

<!-- -->

-   Spécifiez des paramètres de couverture pour un produit à l'aide d'un Assistant. L'Assistant fournit des instructions détaillées sur la définition des principaux paramètres de couverture de l'article. Dans la page **Couverture de l'article**, cliquez sur **Assistant** pour ouvrir l'**Assistant Couverture d'article**.

<!-- -->

-   Spécifiez des paramètres de couverture pour un groupe de dimensions. Cliquez sur ** produits lancés courants &gt; Gestion &gt; des informations produit **. Sous ** détail des produits lancés ** page, sous ** général, ** Divers ** administration ** au groupe, cliquez sur ** groupe de dimensions de stockage ** le lien. Dans la page **Groupe de dimensions de stockage**, sélectionnez le champ **Plan de couverture par dimension** pour créer les paramètres de couverture d'une dimension dans le groupe de dimensions de stockage. Toutes les dimensions de produit, telles que la configuration, la couleur, la taille, dénomment, doivent être sélectionner ** Plan de couverture par dimension ** le champ.



<a name="see-also"></a>Voir également :
--------

[Master plans](master-plans.md)


