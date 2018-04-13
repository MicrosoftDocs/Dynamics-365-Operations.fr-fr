---
title: "Migration de produits et gestion des entrepôts depuis AX 2012 vers Finance and Operations"
description: Cette rubrique fournit une vue d'ensemble des options de migration de produits et des stocks.
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 92d0b4dd9611de4d717f30dc8736c673835bea29
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="migrate-products-and-warehouse-management-from-ax-2012-to-finance-and-operations"></a>Migration de produits et gestion des entrepôts depuis AX 2012 vers Finance and Operations

[!INCLUDE [banner](../includes/banner.md)]

Cette rubrique donne une vue d'ensemble des options de migration de la gestion des produits et des entrepôts dans Microsoft Dynamics 365 for Finance and Operations.

<a name="introduction"></a>Introduction
------------

Lors d'une mise à niveau vers Finance and Operations, les produits sont bloqués s'ils sont associés à un groupe de dimensions de stockage dont les paramètres ne correspondent pas à la configuration requise pour les paramètres du groupe de dimensions de stockage dans Finance and Operations. Toutefois, après la mise à niveau, vous pouvez utiliser un ensemble d'options de migration dans le processus **Modifier le groupe de dimensions de stockage pour les articles** pour débloquer les produits qui ont été bloqués pendant la mise à niveau. Vous pouvez ensuite traiter les transactions associés à ces produits. Certains articles sont peut-être déjà associés à des groupes de dimensions de stockage dans lesquels les dimensions de stock Site, Entrepôt et Emplacement sont actives et physiquement suivies. Dans ce cas, vous pouvez utiliser le processus **Modifier le groupe de dimensions de stockage pour les articles** pour pouvoir utiliser ces articles dans les processus de gestion des entrepôts. Cette fonction est utile si vous souhaitez utiliser la fonctionnalité de gestion des entrepôts pour les articles existants.

## <a name="upgrading-to-finance-and-operations-when-ax-2012-r3-wmsii-is-used"></a>Mise à niveau vers Finance and Operations lorsque AX 2012 R3 WMSII est utilisé
Finance and Operations ne prend plus en charge le module **WMSII** hérité de Microsoft Dynamics AX 2012. À la place, vous pouvez utiliser le nouveau module **Gestion des entrepôts**. Dans les versions précédentes, les dimensions de stock Emplacement et ID palette pouvaient être sélectionnées pour le stock financier. Toutefois, dans le cadre du processus de mise à niveau, la dimension de stock ID palette ne peut plus être activée pour le stock financier. Tous les produits associés à un groupe de dimensions de stockage qui utilise la dimension de stock ID palette seront bloqués et ne seront pas traités.

### <a name="enabling-items-in-finance-and-operations"></a>Activation des articles dans Finance and Operations

Dans Finance and Operations, les articles qui sont utilisés dans le cadre des processus de gestion des entrepôts doivent être associés à un groupe de dimensions de stockage dans lequel le paramètre **Utiliser les processus de gestion des entrepôts** est sélectionné. Lorsque ce paramètre est sélectionné, les dimensions de stock Site, Entrepôt, Statut du stock, Emplacement et Contenant deviennent actives. Vous pouvez utiliser ce type de groupe de dimensions de stockage uniquement pour les articles qui sont déjà associés à des groupes de dimensions de stockage dans lesquels la dimension de stock Emplacement est active.

### <a name="items-that-are-blocked-for-inventory-updates"></a>Articles bloqués pour les mises à jour de stock

Pour afficher la liste des produits lancés qui ont été bloqués pendant la mise à niveau et ne peuvent pas être traités, cliquez sur **Gestion des stocks** &gt; **Paramétrage** &gt; **Stock** &gt; **Articles bloqués pour les mises à jour de stock**.

### <a name="reapplying-blocked-products"></a>Réapplication des produits bloqués

Pour débloquer les produits qui ont été bloqués pendant la mise à niveau, vous devez sélectionner un nouveau groupe de dimensions de stockage pour les produits. Notez que vous pouvez modifier le groupe de dimensions de stockage même si des mouvements de stock en cours existent. Pour utiliser les articles qui ont été bloqués pendant la mise à niveau, vous avez deux options :

-   Modifiez le groupe de dimensions de stockage de l'article en un groupe de dimensions de stockage qui utilise uniquement les dimensions de stock Site, Entrepôt et Emplacement. Suite à cette modification, la dimension de stock ID palette n'est plus utilisée.
-   Modifiez le groupe de dimensions de stockage de l'article en un groupe de dimensions de stockage qui utilise les processus de gestion des entrepôts. Suite à cette modification, la dimension de stock Contenant est à présent utilisée.

### <a name="migration-processes"></a>Processus de migration

Dans Finance and Operations, la traçabilité des articles fait partie des processus de gestion des entrepôts. Pour ces processus, tous les entrepôts et leurs emplacements doivent être associés à un profil d'emplacement. Conceptuellement, si vous souhaitez utiliser les processus de gestion des entrepôts, deux processus doivent être gérés :

-   Les entrepôts existants doivent être activés pour utiliser les processus de gestion des entrepôts.
-   Les produits lancés existants doivent être associés à un nouveau groupe de dimensions de stockage qui utilise les processus de gestion des entrepôts.

Si les groupes de dimensions de stockage source utilisent la dimension de stock ID palette, les emplacements du stock disponible existant qui utilisaient la dimension de stock ID palette doivent être associés à un profil d'emplacement dans lequel le paramètre **Utiliser le suivi des contenants** est sélectionné. Si les entrepôts existants ne doivent pas être activés pour utiliser les processus de gestion des entrepôts, vous pouvez modifier les groupes de dimensions de stockage du stock disponible existant en groupes qui gèrent uniquement les dimensions de stock Site, Entrepôt et Emplacement.

### <a name="using-the-warehouse-management-processes"></a>Utilisation des processus de gestion des entrepôts

Pour pouvoir utiliser des produits lancés dans le module **Gestion des entrepôts**, les produits doivent utiliser un groupe de dimensions de stockage dans lequel le paramètre **Utiliser les processus de gestion des entrepôts** est sélectionné.

#### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>Activer les entrepôts pour utiliser les processus de gestion des entrepôts

1.  Créez au moins un profil d'emplacement.
2.  Cliquez sur **Gestion des entrepôts** &gt; **Paramétrage** &gt; **Activer les processus de gestion des entrepôts** &gt; **Activer le paramétrage des entrepôts**.
3.  Dans la page **Activer le paramétrage des entrepôts**, ajoutez les entrepôts à activer. Vous pouvez effectuer cette étape directement sur la page ou à l'aide de l'intégration Microsoft Office.
4.  Affectez un profil d'emplacement à tous les emplacements. Vous pouvez facilement effectuer cette étape à l'aide de l'intégration Microsoft Office directement à partir de la page. Vous pouvez exporter et importer les données, ou utiliser le traitement de l'entité de données dans [Gestion des données](../../dev-itpro/data-entities/data-entities.md).
5.  Validez les modifications. Dans le cadre du processus de validation, différentes validations de l'intégrité des données se produisent. Dans le cadre d'un processus de mise à niveau plus vaste, les problèmes qui se produisent doivent être ajustés sur l'implémentation source. Dans ce cas, une mise à niveau supplémentaire des données sera nécessaire.
6.  Traitez les modifications.

#### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>Modifier le groupe de dimensions de stockage pour les articles, afin qu'il utilise les processus de gestion des entrepôts

1.  Créez une valeur **Statut du stock**, puis définissez-la comme **ID statut de stock par défaut** dans les **Paramètres de gestion des entrepôts**.
2.  Créez un groupe de dimensions de stockage dans lequel le paramètre **Utiliser les processus de gestion des entrepôts** est sélectionné.
3.  Dans la page **Hiérarchie de réservation**, définissez une nouvelle hiérarchie de réservation en fonction des groupes de dimensions de stockage et de suivi de l'article.
4.  Créez un ou plusieurs groupes de séquences d'unités contenant au moins les mêmes unités que celles utilisées pour les unités de stock des articles.
5.  Cliquez sur **Gestion des entrepôts** &gt; **Paramétrage** &gt; **Activer les processus de gestion des entrepôts** &gt; **Modifier le groupe de dimensions de stockage pour les articles**.
6.  Dans la page **Modifier le groupe de dimensions de stockage pour les articles**, ajoutez les numéros d'article, les groupes de dimensions de stockage et les groupes de séquences d'unités. Vous pouvez effectuer cette étape directement sur la page, à l'aide de l'intégration Microsoft Office, ou en utilisant le traitement de l'entité de données dans [Gestion des données](../../dev-itpro/data-entities/data-entities.md).
7.  Validez les modifications. Dans le cadre du processus de validation, différentes validations de l'intégrité des données se produisent. Dans le cadre d'un processus de mise à niveau plus vaste, les problèmes qui se produisent doivent être ajustés sur l'implémentation source. Dans ce cas, une mise à niveau supplémentaire des données sera nécessaire.
8.  Traitez les modifications. Une mise à jour de toutes les dimensions de stock peut prendre un certain temps. Vous pouvez surveiller la progression à l'aide des tâches de traitement par lots.



