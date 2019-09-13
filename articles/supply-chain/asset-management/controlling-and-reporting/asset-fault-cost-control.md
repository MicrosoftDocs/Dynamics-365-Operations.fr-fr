---
title: Contrôle des coûts de problème de l'actif
description: Cette rubrique explique le contrôle des coûts de défaillance d'un actif dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2fe75c327cdc2bdd76173430ed551895f5941c7b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918301"
---
# <a name="asset-fault-cost-control"></a>Contrôle des coûts de problème de l'actif

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Dans le module Gestion des actifs, vous pouvez calculer les coûts des enregistrements de défaillance des actifs pour obtenir une vue d'ensemble des coûts réels comparés aux coûts budgétaires des défaillances. Les coûts réels sont basés sur des transactions validées. La date est la date de défaillance à laquelle le symptôme a été enregistré.

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Défaillances des actifs** > **Contrôle des coûts de défaillance d'un actif**.

2. Dans la boîte de dialogue **Contrôle des coûts de défaillance d'actif**, sélectionnez un ensemble de dimension financière à inclure dans le calcul, si nécessaire.

4. Sélectionnez « Oui » sur le bouton bascule **Ignorer lignes nulles** si vous ne souhaitez pas afficher les résultats ayant des coûts supérieurs à zéro.

5. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de contrôle de coût en fonction des postes techniques. Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes de contrôle des coûts de défaillance d'un actif pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter des heures à partir des postes techniques situés à un niveau inférieur. Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de contrôle des coûts de défaillance d'un actif sur tous les niveaux du poste technique auquel elles sont liées.

6. Pour limiter la recherche, vous pouvez sélectionner des actifs, des dates de défaillance et des causes de défaillance spécifiques sur l'organisateur **Enregistrements à inclure**.

7. Cliquez sur **OK** pour démarrer le calcul.

8. Dans les groupes de volet Actions **Grouper par…**, cliquez sur les boutons appropriés à afficher le niveau requis de détail du calcul. Les boutons sélectionnés du volet Actions sont mis en surbrillance. Cliquez sur un bouton pour l'activer ou le désactiver.

L'illustration suivante présente un exemple de calcul de contrôle des coûts de défaillance d'actif.

![Figure 1](media/05-controlling-and-reporting.png)

Reportez-vous à la section [Gestion des défaillances](../setup-for-work-orders/fault-management.md) pour obtenir des informations sur la procédure de paramétrage des défaillances.

>[!NOTE]
>Le champ **Budget d'origine** indique les coûts budgétaires à partir des prévisions de l'ordre de travail. Le champ **Coût réel** indique les coûts validés sur les ordres de travail. Le champ **Coût engagé** indique les coûts totaux dans lesquels votre société s'engage en termes d'ordres de travail.

