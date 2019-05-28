---
title: Créer un nouveau produit
description: Cette tâche indique comment créer un nouveau produit partagé.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a603d89749242a4c6039ab83da286ec6ab727d8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548414"
---
# <a name="create-a-new-product"></a>Créer un nouveau produit

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette tâche indique comment créer un nouveau produit partagé. Elle est généralement effectuée par un concepteur de produit. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.

1. Accédez à Gestion des informations sur les produits > Produits > Produits.

## <a name="create-a-product"></a>Créer un produit
1. Cliquez sur Nouveau.
2. Dans le champ Numéro du produit, saisissez une valeur.
    * Si une souche de numéros n'a pas été paramétrée pour le numéro de produit, elle doit être entrée manuellement.  
3. Dans le champ Nom du produit, saisissez une valeur.
    * Le nom de produit est par défaut le nom de recherche. Vous pouvez la modifier si nécessaire.  
4. Cliquez sur OK.

## <a name="set-up-dimension-groups"></a>Paramétrer des groupes de dimensions
1. Cliquez sur Groupes de dimensions pour ouvrir la boîte de dialogue.
2. Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.
    * Le groupe de dimension de stockage détermine les dimensions de stockage que vous devez entrer dans chaque transaction pour le produit et la manière dont il est suivi dans le stock.  
3. Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.
    * Le groupe de dimension de suivi détermine les dimensions de suivi que vous devez entrer pour chaque transaction pour le produit et la manière dont il sera géré dans le stock.  
4. Cliquez sur OK.

