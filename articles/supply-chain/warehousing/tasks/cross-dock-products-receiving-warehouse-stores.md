---
title: Produits croisés entre l'entrepôt de réception et les magasins
description: Cette procédure décrit les étapes pour créer et traiter un cross-docking afin de distribuer les produits depuis l'emplacement de réception d'une commande fournisseur vers un ou plusieurs magasins.
author: ShylaThompson
manager: tfehr
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailBuyersPushPerPackage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac93806bc85be92840548e160ddf803e63adbbc4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977186"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a>Produits croisés entre l'entrepôt de réception et les magasins

[!include [banner](../../includes/banner.md)]

Cette procédure décrit les étapes pour créer et traiter un cross-docking afin de distribuer les produits depuis l'emplacement de réception d'une commande fournisseur vers un ou plusieurs magasins. L'utilisateur peut définir plusieurs configurations et laisser le système décider de la distribution des produits, ou saisir manuellement l'emplacement de distribution des produits et la quantité distribuée dans chaque magasin. La procédure n'inclut pas le paramétrage des données pouvant être utilisées dans le cross-docking, telles que les règles de réapprovisionnement, les hiérarchies organisationnelles et les poids des magasins. La société fictive USRT sert d'exemple dans la procédure.

1. Allez dans Toutes les commandes fournisseur.
2. Sélectionnez une commande fournisseur dans la liste et cliquez sur le lien pour ouvrir la commande.
3. Dans le volet Actions, cliquez sur Commerce et vente au détail.
4. Cliquez sur Cross-docking.
5. Cliquez sur Modifier.
    * La catégorie peut être utilisée pour filtrer les articles de la section Lignes.  
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans le champ Quantité de cross-docking, entrez une valeur pour spécifier quelle proportion de la quantité achetée du produit sélectionné doit être distribuée.
8. Dans le champ Quantité de cross-docking supplémentaire, saisissez une valeur pour spécifier les quantités à distribuer pour les produits disponibles achetés.
9. Dans le champ Distribution, saisissez « Priorité de l'entrepôt ».
    * Vous pouvez sélectionner les autres types pour utiliser différentes règles de distribution.  
10. Dans le champ Hiérarchie des réapprovisionnements, sélectionnez une valeur.
11. Sélectionnez Oui dans le champ Respecter les assortiments.
12. Cliquez sur Calculer les quantités.
13. Cliquez sur Créer une commande.
14. Cliquez sur Oui.
15. Dans la liste, recherchez et sélectionnez un entrepôt qui a reçu des produits
16. Cliquez sur Commande pour afficher les commandes créées pour l'entrepôt sélectionné



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]