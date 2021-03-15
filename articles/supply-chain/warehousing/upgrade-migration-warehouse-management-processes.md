---
title: Mise à niveau de la gestion des entrepôts depuis Microsoft Dynamics AX 2012 vers Supply Chain Management
description: Cette rubrique fournit une vue d'ensemble des options de migration de produits et des stocks.
author: perlynne
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 45d9809d4bbf1b5a68c3f799ce5d51f9709d276b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970279"
---
# <a name="upgrade-warehouse-management-from-microsoft-dynamics-ax-2012-to-supply-chain-management"></a>Mise à niveau de la gestion des entrepôts depuis Microsoft Dynamics AX 2012 vers Supply Chain Management 


[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d'ensemble du processus de mise à niveau depuis Microsoft Dynamics AX 2012 R3, en exécutant le module WMSII, vers Supply Chain Management.

Supply Chain Management ne prend plus en charge le module **WMSII** hérité de Microsoft Dynamics AX 2012. À la place, vous pouvez utiliser le module **Gestion des entrepôts**. Dans le module WMSII, les dimensions de stock Emplacement et ID palette peuvent être sélectionnées pour le stock financier. Cependant, la dimension de stock ID palette ne peut pas être utilisée pour le stock financier dans Supply Chain Management.

Lors d'une mise à niveau, tous les produits associés à un groupe de dimensions de stockage qui utilise la dimension de stock ID palette sont identifiés, marqués comme bloqués et non traités pour la mise à niveau.

## <a name="upgrading-to-supply-chain-management-when-ax-2012-r3-wmsii-is-used"></a>Mise à niveau vers Supply Chain Management lorsque AX 2012 R3 WMSII est utilisé
Après la mise à niveau, vous pouvez utiliser un ensemble d'options dans l'écran **Modifier le groupe de dimensions de stockage pour les articles** pour débloquer les produits qui ont été bloqués pendant la mise à niveau, puis traiter les transactions pour ces produits.

### <a name="enabling-items-in-supply-chain-management"></a>Activation des articles dans Supply Chain Management 
Cette modifications est requise, car la traçabilité des articles fait partie des processus de gestion des entrepôts dans Supply Chain Management. Pour ces processus, tous les entrepôts et leurs emplacements doivent être associés à un profil d'emplacement. Si vous souhaitez utiliser les processus de gestion des entrepôts, les éléments suivants doivent être configurés :
-   Les entrepôts existants doivent être activés pour utiliser les processus de gestion des entrepôts 
-   Les produits lancés existants doivent être associés à un groupe de dimensions de stockage qui utilise les processus de gestion des entrepôts 

Si les groupes de dimensions de stockage source utilisent la dimension de stock ID palette, les emplacements du stock disponible existant qui utilisaient la dimension de stock ID palette doivent être associés à un profil d'emplacement dans lequel le paramètre **Utiliser le suivi des contenants** est sélectionné. Si les entrepôts existants ne doivent pas être activés pour utiliser les processus de gestion des entrepôts, vous pouvez modifier les groupes de dimensions de stockage du stock disponible existant en groupes qui gèrent uniquement les dimensions de stock Site, Entrepôt et Emplacement. 

> [!NOTE] 
>  Vous pouvez modifier le groupe de dimensions de stockage pour les articles même si des mouvements de stock en cours existent.

## <a name="find-products-that-were-blocked-because-of-pallet-id"></a>Rechercher des produits qui ont été bloqués en raison de l'ID palette
Pour afficher la liste des produits lancés qui ont été bloqués pendant la mise à niveau et ne peuvent pas être traités, cliquez sur **Gestion des stocks** &gt; **Paramétrage** &gt; **Stock** &gt; **Articles bloqués pour les mises à jour de stock**.

## <a name="change-storage-dimension-group-for-blocked-products"></a>Modifier le groupe de dimensions de stockage pour les produits bloqués 
 
Pour pouvoir être utilisé dans le cadre d'un processus de gestion des entrepôts, un article doit être associé à un groupe de dimensions de stockage dans lequel la dimension de stock Emplacement est active et le paramètre **Utiliser les processus de gestion des entrepôts** est sélectionné. Lorsque ce paramètre est sélectionné, les dimensions de stock Site, Entrepôt, Statut du stock, Emplacement et Contenant deviennent actives.

Pour débloquer les produits qui ont été bloqués pendant la mise à niveau, vous devez sélectionner un nouveau groupe de dimensions de stockage pour les produits. Notez que vous pouvez modifier le groupe de dimensions de stockage même si des mouvements de stock en cours existent. Pour utiliser les articles qui ont été bloqués pendant la mise à niveau, vous avez deux options :

-   Modifiez le groupe de dimensions de stockage de l'article en un groupe de dimensions de stockage qui utilise uniquement les dimensions de stock Site, Entrepôt et Emplacement. Suite à cette modification, la dimension de stock ID palette n'est plus utilisée.
-   Modifiez le groupe de dimensions de stockage de l'article en un groupe de dimensions de stockage qui utilise les processus de gestion des entrepôts. Suite à cette modification, la dimension de stock Contenant est à présent utilisée.

## <a name="configure-warehouse-management-processes"></a>Configurer les processus de gestion des entrepôts
Pour pouvoir utiliser des produits lancés dans le module **Gestion des entrepôts**, les produits doivent utiliser un groupe de dimensions de stockage dans lequel le paramètre **Utiliser les processus de gestion des entrepôts** est sélectionné.

### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>Activer les entrepôts pour utiliser les processus de gestion des entrepôts

1.  Créez au moins un profil d'emplacement.
2.  Cliquez sur **Gestion des entrepôts** &gt; **Paramétrage** &gt; **Activer les processus de gestion des entrepôts** &gt; **Activer le paramétrage des entrepôts**.
3.  Dans la page **Activer le paramétrage des entrepôts**, ajoutez les entrepôts à activer. Vous pouvez effectuer cette étape directement sur la page ou à l'aide de l'intégration Microsoft Office.
4.  Affectez un profil d'emplacement à tous les emplacements. Vous pouvez facilement effectuer cette étape à l'aide de l'intégration Microsoft Office directement à partir de la page. Vous pouvez exporter et importer les données, ou utiliser le traitement de l'entité de données dans [Gestion des données](../../dev-itpro/data-entities/data-entities.md).
5.  Validez les modifications. Dans le cadre du processus de validation, différentes validations de l'intégrité des données se produisent. Dans le cadre d'un processus de mise à niveau plus vaste, les problèmes qui se produisent doivent être ajustés sur l'implémentation source. Dans ce cas, une mise à niveau supplémentaire des données sera nécessaire.
6.  Traitez les modifications.

### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>Modifier le groupe de dimensions de stockage pour les articles, afin qu'il utilise les processus de gestion des entrepôts

1.  Créez une valeur **Statut du stock**, puis définissez-la comme **ID statut de stock par défaut** dans les **Paramètres de gestion des entrepôts**.
2.  Créez un groupe de dimensions de stockage dans lequel le paramètre **Utiliser les processus de gestion des entrepôts** est sélectionné.
3.  Dans la page **Hiérarchie de réservation**, définissez une nouvelle hiérarchie de réservation en fonction des groupes de dimensions de stockage et de suivi de l'article.
4.  Créez un ou plusieurs groupes de séquences d'unités contenant au moins les mêmes unités que celles utilisées pour les unités de stock des articles.
5.  Cliquez sur **Gestion des entrepôts** &gt; **Paramétrage** &gt; **Activer les processus de gestion des entrepôts** &gt; **Modifier le groupe de dimensions de stockage pour les articles**.
6.  Dans la page **Modifier le groupe de dimensions de stockage pour les articles**, ajoutez les numéros d'article, les groupes de dimensions de stockage et les groupes de séquences d'unités. Vous pouvez effectuer cette étape directement sur la page, à l'aide de l'intégration Microsoft Office, ou en utilisant le traitement de l'entité de données dans [Gestion des données](../../dev-itpro/data-entities/data-entities.md).
7.  Validez les modifications. Dans le cadre du processus de validation, différentes validations de l'intégrité des données se produisent. Dans le cadre d'un processus de mise à niveau plus vaste, les problèmes qui se produisent doivent être ajustés sur l'implémentation source. Dans ce cas, une mise à niveau supplémentaire des données sera nécessaire.
8.  Traitez les modifications. Une mise à jour de toutes les dimensions de stock peut prendre un certain temps. Vous pouvez surveiller la progression à l'aide des tâches de traitement par lots.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]