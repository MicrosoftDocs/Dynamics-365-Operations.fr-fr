--- 
title: "Créer un état du cycle de vie des produits pour exclure des produits de la planification"
description: "Cette procédure décrit comment créer un état du cycle de vie des produits qui exclut les produits de la planification et du calcul au niveau de la nomenclature."
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
ms.sourcegitcommit: 74606b1378e94e8a6945a408520c8b68648970d8
ms.openlocfilehash: 1685e8eb706e29ef5b195e9163bf19345fee78b6
ms.contentlocale: fr-fr
ms.lasthandoff: 02/07/2018

---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>Créer un état du cycle de vie des produits pour exclure des produits de la planification

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment créer un état du cycle de vie des produits qui exclut les produits de la planification et du calcul au niveau de la nomenclature.


## <a name="create-an-obsolete-state"></a>Créer un état obsolète
1. Accédez à Gestion des informations sur les produits > Paramétrage > État du cycle de vie des produits.
2. Cliquez sur Nouveau.
3. Dans le champ État, tapez une valeur.
4. Sélectionnez Non dans le champ Est actif pour la planification.
5. Dans le champ Description, entrez une valeur.

## <a name="associate-the-obsolete-state-to-a-released-product"></a>Associer l'état obsolète à un produit lancé
1. Fermez la page.
2. Allez à Gestion des informations sur les produits > Produits > Produits lancés.
3. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez le champ Nom de recherche avec la valeur « M00 ».
4. Cliquez sur Modifier.
5. Dans la liste, marquez la ligne sélectionnée.
6. Dans le champ État du cycle de vie des produits, entrez ou sélectionnez une valeur.


