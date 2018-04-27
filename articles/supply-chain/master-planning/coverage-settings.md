---
title: "Paramètres de couverture"
description: "Le calcul PDP/MRP utilise les paramètres de couverture pour calculer les demandes d'articles."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 591b1cd739bb3be61299f33f180ca7c264d21a35
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="coverage-settings"></a>Paramètres de couverture

[!INCLUDE [banner](../includes/banner.md)]

Le calcul PDP/MRP utilise les paramètres de couverture pour calculer les demandes d'articles. 

Vous pouvez spécifier des paramètres de couverture de plusieurs façons :

-   Spécifiez des paramètres de couverture pour un groupe de couverture. Vous pouvez créer un groupe de couverture contenant des paramètres pour tous les produits qui lui sont liés. Cliquez sur **Planification &gt; Paramétrage &gt; Couverture &gt; Groupes de couverture** pour créer un groupe de couverture. Vous pouvez lier un groupe de couverture à un produit. Si le lien est spécifique à un site, un entrepôt ou une dimension de produit, utilisez le champ **Groupe de couverture** dans la page **Couverture de l'article**. Si le lien est générique, indépendamment des dimensions de produit, utilisez le champ **Groupe de couverture** sous l'organisateur **Plan** de la page **Détails de produit**. Si vous ne liez pas de groupe de couverture à un produit, la planification utilise par défaut le **Groupe de couverture général** spécifié dans la page **Paramètres de planification**.

-   Spécifiez des paramètres de couverture pour un produit. Vous pouvez créer des paramètres de couverture pour un produit spécifique. Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**. Sélectionnez le produit, dans le **volet Actions**, sous l'onglet **Plan**, dans le champ **Groupe de couverture**, cliquez sur **Couverture de l'article** pour ouvrir la page **Couverture de l'article**. Si le produit est déjà lié à un groupe de couverture, vous pouvez remplacer les paramètres de groupe de couverture à l'aide du champ **Remplacer**. Les paramètres de couverture de la page**Couverture de l'article** prévalent sur les paramètres de la page **Groupe de couverture**.

<!-- -->

-   Spécifiez des paramètres de couverture pour un produit à l'aide d'un Assistant. L'Assistant fournit des instructions détaillées sur la définition des principaux paramètres de couverture de l'article. Dans la page **Couverture de l'article**, cliquez sur **Assistant** pour ouvrir l'**Assistant Couverture d'article**.

<!-- -->

- Spécifiez des paramètres de couverture pour un groupe de dimensions. Cliquez sur <strong>Gestion des informations sur les produits &gt; Commun &gt; Produits lancés</strong>. Dans la page <strong>Détails des produits lancés**, sous l'onglet **Général</strong>, dans le groupe <strong>Administration</strong>, cliquez sur le lien <strong>Groupe de dimension de stockage</strong>. Dans la page <strong>Groupe de dimensions de stockage</strong>, sélectionnez le champ <strong>Plan de couverture par dimension</strong> pour créer les paramètres de couverture d'une dimension dans le groupe de dimensions de stockage. Le champ <strong>Plan de couverture par dimension</strong> doit être sélectionné pour toutes les dimensions de produit, telles que la configuration, la couleur, la taille et le style.



<a name="see-also"></a>Voir également :
--------

[Plans généraux](master-plans.md)




