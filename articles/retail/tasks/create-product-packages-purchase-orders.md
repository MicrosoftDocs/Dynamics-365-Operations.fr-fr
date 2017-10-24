--- 
title: " Créer des modules de produit pour les commandes fournisseur"
description: "Cette procédure vous guide lors de la création d'un ensemble de produits et de son utilisation sur une commande fournisseur."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a3be1e7aca7f0382aea55fa8a371c33c8b53df95
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="create-product-packages-for-purchase-orders"></a> Créer des modules de produit pour les commandes fournisseur

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure vous guide lors de la création d'un ensemble de produits et de son utilisation sur une commande fournisseur. La commande fournisseur sera utilisée pour créer une commande pour un ensemble prédéfini de produits. La société fictive USRT sert d'exemple dans cette procédure.


## <a name="create-a-product-package"></a>Créer un ensemble de produits
1. Accédez à Commerce et vente au détail > Gestion des stocks > Réapprovisionnement > Ensembles de produits.
2. Cliquez sur Nouveau.
3. Dans le champ Numéro d'ensemble, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Cliquez sur Ajouter.
8. Dans le champ Numéro d'article, tapez « 0160 ».
9. Dans le champ Taille, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
10. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
11. Dans le champ Quantité, entrer un numéro.
12. Cliquez sur Ajouter.
13. Dans le champ Numéro d'article, tapez « 0160 ».
14. Dans le champ Numéro de variante, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
15. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
16. Dans le champ Quantité, entrer un numéro.
17. Cliquez sur Ajouter.
18. Dans le champ Numéro d'article, tapez « 0175 ».
19. Dans le champ Quantité, entrer un numéro.
20. Cliquez sur Enregistrer.
21. Fermez la page.

## <a name="add-package-to-puchase-order"></a>Ajouter un ensemble à une commande fournisseur
1. Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.
2. Cliquez sur Nouveau.
3. Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, sélectionnez le même fournisseur pour lequel l'ensemble de produits a été précédemment créé, si un fournisseur a été sélectionné.
5. Activez ou désactivez l'extension de la section Général.
6. Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
10. Cliquez sur OK.
11. Activez ou désactivez l'extension de la section Détails de ligne.
12. Cliquez sur l'onglet Ensembles de produits.
13. Cliquez sur Ligne de commande fournisseur.
14. Cliquez sur Créer des lignes à partir de l'ensemble.
15. Dans la liste, recherchez et sélectionnez l'ensemble de produits créé à l'étape précédente.
16. Entrez un numéro dans le champ Quantité.
17. Cliquez sur Créer.
18. Cliquez sur Enregistrer.


