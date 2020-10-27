---
title: Ajouter des variantes de produits à des commandes fournisseur à l'aide des poids des variantes
description: Cette procédure vous guide au long des étapes permettant d'utiliser les poids des variantes pour renseigner automatiquement des lignes de commande fournisseur pour chaque variante d'un produit.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c099daf888cb2a1740dda3e860b37f88089c5ca
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986453"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a>Ajouter des variantes de produits à des commandes fournisseur à l'aide des poids des variantes

[!include [banner](../../includes/banner.md)]

Cette procédure vous guide au long des étapes permettant d'utiliser les poids des variantes pour renseigner automatiquement des lignes de commande fournisseur pour chaque variante d'un produit. Lorsque vous sélectionné la quantité du produit que vous souhaitez acheter, des lignes de commande fournisseur sont créées pour toutes les variantes de produit, avec des quantités suggérées selon les poids configurés dans les variantes de produit. Cette procédure n'inclut pas les étapes permettant de configurer les valeurs des poids sur les dimensions de produit et les variantes de produit. Cette procédure utilise la société USRT dans les données de démonstration.

1. Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.
2. Cliquez sur Nouveau.
3. Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Activez ou désactivez l'extension de la section Général.
6. Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
10. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
11. Cliquez sur OK.
12. Activez ou désactivez l'extension de la section Détails de ligne.
13. Cliquez sur l'onglet Variantes.
14. Cliquez sur Ajouter une ligne.
15. Dans la liste, marquez la ligne sélectionnée.
16. Dans le champ Numéro d'article, tapez « 0140 ».
17. Définir la Quantité sur « 1000 ».
18. Cliquez sur Enregistrer.

