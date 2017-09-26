--- 
title: "Créer un accord commercial"
description: "Cette procédure vous indique comment créer un accord commercial dans lequel vous enregistrer un prix de vente de produit dont vous avez convenu avec un client spécifique."
author: omulvad
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 1178c7a5db129801f83afa8b4caf9357ccf76b71
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-new-trade-agreement"></a>Créer un accord commercial

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous indique comment créer un accord commercial dans lequel vous enregistrer un prix de vente de produit dont vous avez convenu avec un client spécifique. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Si vous utilisez vos propres données, vous devez vous assurer qu'un nom de Journal d'accords commerciaux existe dans lequel la relation par défaut est définie sur « Prix (ventes) » avant de lancer ce guide.


## <a name="create-and-post-a-new-trade-agreement-journal"></a>Créer et valider un journal d'accords commerciaux
1. Accédez à Ventes et marketing > Prix et remises > Journaux des accords commerciaux.
2. Cliquez sur Nouveau.
3. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Cliquez sur Lignes.
7. Dans le champ Code de compte, sélectionnez « Table ».
    * Dans cet exemple, vous mettez à jour le prix pour un client spécifique, ce qui signifie que vous devez choisir Table. Si vous mettez les prix du produit, sélectionnez Tout, afin que le nouveau prix soit valide pour tous les clients. Si vous différenciez des prix entre différents segments de clients, sélectionnez Groupe. Pour sélectionner Groupe, vous devez avoir configuré des Groupes de prix client.  
8. Dans le champ Sélection du compte, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
10. Dans le champ Code d'article, sélectionnez « Table ».
    * Lorsque vous entrez un accord commercial de type « Prix (ventes) », vous devez sélectionner uniquement « Table » dans le champ Code article. Cela est dû au fait qu'un prix est une valeur absolue et qu'il ne peut pas être identique pour tous les produits ou pour un groupe de produits.  
11. Dans le champ Relation d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
12. Dans la liste, sélectionnez le produit que vous souhaitez inclure dans l'accord.
    * Notez le produit que vous avez sélectionné.  
13. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
14. Dans le champ De, entrez une quantité minimale.
    * Si le client doit commander une quantité minimale avant de pouvoir bénéficier du nouveau prix, vous devez spécifier la quantité ici.  
    * Entrez une valeur dans le champ À pour spécifier la quantité maximale au-dessus de laquelle le prix de l'accord n'est pas valide. Si vous proposez des prix et des remises par quantité, spécifiez chaque parenthèse de quantité comme paire de quantité minimale et maximale dans les champs « De » et « À », respectivement.  
15. Dans le champ Montant en devise, entrez un prix.
16. Dans le champ Date de début, entrez une date à partir de laquelle cet accord est valide.
17. Cliquez sur Enregistrer.
18. Cliquez sur Valider.
19. Cliquez sur Valider les lignes sélectionnées.
20. Cliquez sur OK.
21. Cliquez sur Valider.
22. Cliquez sur OK.

## <a name="view-trade-agreements-for-a-product"></a>Afficher les accords commerciaux d'un produit
1. Allez à Gestion des informations sur les produits > Produits > Produits lancés.
2. Dans la liste, localisez et sélectionnez le produit dont vous venez de mettre à jour le prix.
3. Cliquez sur Vendre dans le volet Actions.
4. Cliquez sur Afficher les accords commerciaux.
    * Examinez les détails de l'accord commercial de prix que vous venez de créer.    
5. Fermez la page.


