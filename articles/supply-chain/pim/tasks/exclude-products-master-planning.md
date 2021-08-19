---
title: Créer un état du cycle de vie des produits pour exclure des produits de la planification
description: Cette procédure décrit comment créer un état du cycle de vie des produits qui exclut les produits de la planification et du calcul au niveau de la nomenclature.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1050aeb3f7acf9902f86aac60dae7fe89bbd847016c95e2acce3e539812c7023
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772518"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>Créer un état du cycle de vie des produits pour exclure des produits de la planification

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment créer un état du cycle de vie des produits qui exclut les produits de la planification et du calcul au niveau de la nomenclature.


## <a name="create-an-obsolete-state"></a>Créer un état obsolète
1. Accédez à Gestion des informations sur les produits > Paramétrage > État du cycle de vie des produits.
2. Cliquez sur Nouveau.
3. Dans le champ État, tapez une valeur.
4. Sélectionnez Non dans le champ Est actif pour la planification.
5. Dans le champ Description, entrez une valeur.

## <a name="associate-the-obsolete-state-to-a-released-product"></a>Associer l’état obsolète à un produit lancé
1. Fermez la page.
2. Allez à Gestion des informations sur les produits > Produits > Produits lancés.
3. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez le champ Nom de recherche avec la valeur « M00 ».
4. Cliquez sur Modifier.
5. Dans la liste, marquez la ligne sélectionnée.
6. Dans le champ État du cycle de vie des produits, entrez ou sélectionnez une valeur.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]