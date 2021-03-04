---
title: Envoyer des produits du centre de distribution au magasin à l'aide de la procédure de réassort magasin
description: Cette procédure décrit les étapes pour créer et traiter un réassort magasin afin de distribuer les produits depuis un emplacement vers un ou plusieurs magasins.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailBuyersPush, InventLocationIdLookup, InventItemIdLookupSimple, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dad74855ab9a9c225a5cd64a8c27663aedcd21e4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412302"
---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a> Envoyer des produits du centre de distribution au magasin à l'aide de la procédure de réassort magasin

[!include [banner](../includes/banner.md)]

Cette procédure décrit les étapes pour créer et traiter un réassort magasin afin de distribuer les produits depuis un emplacement vers un ou plusieurs magasins. L'utilisateur peut définir plusieurs configurations et laisser le système décider de la distribution des produits, ou saisir manuellement l'emplacement de distribution des produits et la quantité distribuée dans chaque magasin. Cette procédure n'inclut pas le paramétrage des données pouvant être utilisées dans le réassort magasin, telles que les règles de réapprovisionnement, les hiérarchies organisationnelles et les poids des magasins. La société fictive USRT sert d'exemple dans cette procédure.

1. Accédez à Réassort magasin.
2. Cliquez sur Nouveau.
3. Dans le champ Description, entrez une valeur.
4. Saisissez ou sélectionnez une valeur dans le champ Site.
5. Dans le champ Entrepôt, saisissez ou sélectionnez un entrepôt contenant des produits avec des quantités disponibles.
6. Cliquez sur Ajouter.
7. Dans la liste, marquer la ligne sélectionnée.
8. Dans le champ Numéro d'article, saisissez ou sélectionnez un produit.
9. Cliquez sur Ajouter.
10. Dans la liste, marquer la ligne sélectionnée.
11. Dans le champ Numéro d'article, saisissez ou sélectionnez une variante de produit.
    * Lors de la saisie d'une variante de produit, des lignes sont créées pour chaque variante.  
12. Dans la liste, marquez une ligne.
13. Dans le champ Quantité proposée, saisissez la quantité du produit sélectionné que vous souhaitez distribuer.
14. Dans le champ Quantité supplémentaire à proposer, saisissez la quantité des produits ayant une quantité disponible à distribuer.
15. Dans le champ Distribution, saisissez « Priorité de l'entrepôt ».
    * Vous pouvez sélectionner les autres types pour utiliser d'autres règles de distribution.  
16. Dans le champ Hiérarchie des réapprovisionnements, sélectionnez une valeur.
17. Sélectionnez Oui dans le champ Respecter les assortiments.
18. Cliquez sur Calculer les quantités et examinez les quantités ajoutées aux lignes de la section Entrepôt.
19. Cliquez sur Créer une commande.
20. Cliquez sur Oui.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]