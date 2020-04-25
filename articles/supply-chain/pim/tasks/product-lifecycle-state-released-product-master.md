---
title: Affecter un état du cycle de vie des produits à un produit générique lancé
description: Cette procédure décrit comment affecter un état du cycle de vie des produits à un produit générique lancé et ses variantes.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab8c4e02a064fe84446fa54cc05b9a6a902c1860
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213145"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>Affecter un état du cycle de vie des produits à un produit générique lancé

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment affecter un état du cycle de vie des produits à un produit générique lancé et ses variantes. Conditions préalables : vous devez d'abord lire le guide de tâche « Créer un état du cycle de vie des produits » pour vérifier qu'au moins un état du cycle de vie des produits a été créé avant de lire ce guide de tâche.


## <a name="find-a-released-product-master"></a>Rechercher un produit générique lancé
1. Allez à Gestion des informations sur les produits > Produits > Produits lancés.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.

> [!NOTE]
> Un produit générique a le sous-type Produit.  

## <a name="update-the-lifecycle-state"></a>Mettre à jour l'état du cycle de vie
1. Cliquez sur Modifier.
2. Dans le champ État du cycle de vie des produits, entrez ou sélectionnez une valeur.
3. Cliquez sur Enregistrer.
4. Cliquez sur Oui.

> [!NOTE]
> Si Oui est sélectionné, toutes les variantes de produit associées ayant le même statut d'origine que le produit générique lancé sont également mises à jour vers le nouvel état du cycle de vie des produits. Si Non est sélectionné, toutes les variantes conservent leur état réel. Les variantes dont l'état du cycle de vie des produits est différent de celui du produit générique lancé ne sont pas mises à jour.  

## <a name="verify-the-lifecycle-state-of-the-variants"></a>Vérifier l'état du cycle de vie des variantes
1. Cliquez sur Variantes de produit lancé.

> [!NOTE]
> Notez que toutes les variantes ont hérité l'état du cycle de vie sélectionné du produit générique lancé.  

2. Dans la liste, marquez la ligne sélectionnée.
3. Dans le champ État du cycle de vie des produits, entrez ou sélectionnez une valeur.

