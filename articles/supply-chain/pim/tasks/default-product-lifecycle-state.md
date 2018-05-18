--- 
title: "Créer un état du cycle de vie des produits par défaut"
description: "Cette procédure décrit comment créer un état du cycle de vie des produits par défaut. Elle indique aussi comment associer l'état par défaut à des produits lancés."
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d445ea2f2362f146a1e3e7bcf747898dc2cc89ba
ms.openlocfilehash: 06a6c7c8fa767edf6fdf50c3c971b6d767f8755f
ms.contentlocale: fr-fr
ms.lasthandoff: 02/08/2018

---
# <a name="create-a-default-product-lifecycle-state"></a>Créer un état du cycle de vie des produits par défaut

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment créer un état du cycle de vie des produits par défaut. Elle indique aussi comment associer l'état par défaut à des produits lancés.


## <a name="create-a-default-lifecycle-state"></a>Créer un état du cycle de vie par défaut
1. Accédez à Gestion des informations sur les produits > Paramétrage > État du cycle de vie des produits.
2. Cliquez sur Nouveau.
3. Dans le champ État, tapez une valeur.
4. Sélectionnez Oui dans le champ Valeur par défaut en cas de lancement dans une entité juridique.
5. Dans le champ Description, entrez une valeur.
6. Sélectionnez Non dans le champ Est actif pour la planification.

> [!NOTE]
> Si un nouveau produit lancé ne doit pas être inclus dans la planification, sélectionnez Non. Dans le cas contraire, laissez le contrôle sur sa valeur par défaut Oui.  

## <a name="create-a-new-released-product"></a>Créer un produit lancé
1. Fermez la page.
2. Allez à Gestion des informations sur les produits > Produits > Produits lancés.
3. Cliquez sur Nouveau.
4. Dans le champ Numéro du produit, saisissez une valeur.
5. Dans le champ Nom du produit, saisissez une valeur.
6. Dans le champ Rechercher, tapez une valeur.
7. Saisissez ou sélectionnez une valeur dans le champ Groupe de modèles d'article.
8. Dans le champ Groupe d'articles, entrez ou sélectionnez une valeur.
9. Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de stockage.
10. Saisissez ou sélectionnez une valeur dans le champ Groupe de dimension de suivi.
11. Cliquez sur OK.

> [!NOTE]
> L'état du cycle de vie des produits par défaut est une définition globale.  

## <a name="change-the-product-to-an-active-state"></a>Modifier le produit sur un état actif
1. Dans le champ État du cycle de vie des produits, entrez ou sélectionnez une valeur.

> [!NOTE]
> Supposons que vous ayez paramétré un état actif, vous pouvez désormais sélectionner l'état actif pour pouvoir utiliser le produit dans la planification et le calcul au niveau de la nomenclature. Évidemment, cette utilisation n'a de sens que si tous les détails du produit nécessaires à une planification cohérente sont spécifiés.  


