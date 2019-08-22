---
title: Créer un nouveau produit
description: Cette rubrique décrit la procédure de création d'un nouveau produit partagé.
author: ShylaThompson
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 722414eee1e738e1438bbb40dbd9b8ca606f9245
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844799"
---
# <a name="create-a-new-product"></a>Créer un nouveau produit

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette rubrique décrit la procédure de création d'un nouveau produit partagé. Elle est généralement effectuée par un concepteur de produit. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.


## <a name="create-a-product"></a>Créer un produit
1. Dans le volet de navigation, allez dans **Modules > Gestion d'informations sur les produits > Produits > Produits**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Numéro du produit**, saisissez une valeur. Si une souche de numéros n'a pas été paramétrée pour le numéro de produit, elle doit être entrée manuellement.  
4. Dans le champ **Nom du produit**, saisissez une valeur. Le nom de produit est par défaut le nom de recherche. Vous pouvez la modifier si nécessaire.  
5. Cliquez sur **OK**.

## <a name="set-up-dimension-groups"></a>Paramétrer des groupes de dimensions
1. Sélectionnez **Groupes de dimensions** pour ouvrir la boîte de dialogue.
2. Saisissez ou sélectionnez une valeur dans le champ **Groupe de dimension de stockage**. Le groupe de dimension de stockage détermine les dimensions de stockage que vous devez entrer dans chaque transaction pour le produit et la manière dont il est suivi dans le stock.  
3. Saisissez ou sélectionnez une valeur dans le champ **Groupe de dimension de suivi**. Le groupe de dimension de suivi détermine les dimensions de suivi que vous devez entrer pour chaque transaction pour le produit et la manière dont il sera géré dans le stock.  
4. Cliquez sur **OK**.

