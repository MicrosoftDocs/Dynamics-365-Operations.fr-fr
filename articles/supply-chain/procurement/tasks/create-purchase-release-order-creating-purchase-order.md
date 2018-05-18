--- 
title: "Créer un ordre de lancement d'achat à la création de la commande fournisseur"
description: "Cette procédure indique comment utiliser un contrat d'achat lorsque vous créez une commande fournisseur."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 194d811da09c746167bd9489ce39ae6a6f810ec0
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-purchase-release-order-when-creating-the-purchase-order"></a>Créer un ordre de lancement d'achat à la création de la commande fournisseur

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment utiliser un contrat d'achat lorsque vous créez une commande fournisseur. Le contrat d'achat doit être appliqué lorsque vous créez la commande fournisseur car il existe des conditions générales qui doivent être copiées dans l'en-tête de la commande fournisseur. Cette tâche est généralement effectuée par un agent des achats. Comme préalable à ce guide, vous devez posséder un contrat d'achat effectif avec un engagement de quantité de produits pour un fournisseur et des articles. La même procédure peut être utilisée si vous avez un contrat d'achat avec d'autres types d'engagements. Vous pouvez exécuter ce guide dans les données de démonstration de la société fictive USMF. Si vous utilisez USMF, vous pouvez d'abord exécuter le guide « Créer un contrat d'achat » pour paramétrer les conditions préalables nécessaires pour ce guide.


## <a name="create-a-purchase-order"></a>Créer une commande fournisseur
1. Ouvrez l'espace de travail de préparation des commandes fournisseur.
2. Cliquez sur Nouvelle commande fournisseur.
3. Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Activez ou désactivez l'extension de la section Général.
7. Dans le champ Contrats d'achat, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Tous les accords disponibles pour le fournisseur sont répertoriés ici. Trouver l'accord effectif que vous souhaitez utiliser.  
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Cliquez sur Oui.
10. Cliquez sur OK.

## <a name="add-a-line"></a>Ajouter une ligne
1. Tapez une valeur dans le champ Numéro d'article.
    * S'il existe des dimensions spécifiques de stock ou d'emplacement de l'engagement, vous devez entrer les mêmes valeurs dans la ligne de commande fournisseur pour utiliser l'accord.  
2. Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Le site peut être déjà rempli avec la valeur par défaut de la commande ou du fournisseur. Si c'est le cas, ignorez cette étape.  
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Dans le champ Quantité, entrer un numéro.
    * Validez que le prix est copié à partir de l'engagement.  

## <a name="look-up-the-commitment"></a>Rechercher l'engagement
1. Cliquez sur Mettre à jour la ligne.
2. Cliquez sur Joint.
    * Ici, vous pouvez obtenir des détails sur le contrat d'achat. Par exemple, vous pouvez afficher le prix et savoir si le prix et la remise sont fixes, ce qui signifie que si vous modifiez le prix ou la remise sur la commande fournisseur sur une valeur différente de celle de l'engagement, le système supprimera le lien de sorte que la ligne de commande fournisseur n'honore pas l'engagement. Vous pouvez également voir si l'option Le max. est appliqué est sélectionnée, ce qui signifie que la quantité présente sur l'engagement ne peut pas être dépassée en additionnant tous les achats qui honorent l'engagement.  
3. Fermez la page.

## <a name="look-up-the-purchase-agreement"></a>Rechercher le contrat d'achat
1. Cliquez sur Général dans le volet Actions.
2. Cliquez sur Contrats d'achat.
3. Fermez la page.
4. Fermez la page.


