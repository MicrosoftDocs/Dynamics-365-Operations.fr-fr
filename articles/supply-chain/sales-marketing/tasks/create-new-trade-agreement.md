---
title: Créer un accord commercial
description: Cette procédure vous indique comment créer un accord commercial dans lequel vous enregistrer un prix de vente de produit dont vous avez convenu avec un client spécifique.
author: omulvad
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 58ad2a5571138f1a82b021af63cdae9d567b92d8
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835583"
---
# <a name="create-a-new-trade-agreement"></a>Créer un accord commercial

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous indique comment créer un accord commercial dans lequel vous enregistrer un prix de vente de produit dont vous avez convenu avec un client spécifique. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Si vous utilisez vos propres données, vous devez vous assurer qu'un nom de Journal d'accords commerciaux existe dans lequel la relation par défaut est définie sur « Prix (ventes) » avant de lancer ce guide.


## <a name="create-and-post-a-new-trade-agreement-journal"></a>Créer et valider un journal d'accords commerciaux
1. Accédez à **Volet de navigation > Modules > Ventes et marketing > Prix et remises > Journaux des accords commerciaux**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Nom**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans le volet **Action**, cliquez sur **Lignes**.
6. Dans le champ **Code de compte**, sélectionnez « Table ».
    
    Dans cet exemple, vous mettez à jour le prix pour un client spécifique, ce qui signifie que vous devez choisir Table. Si vous mettez à jour les prix du produit, sélectionnez « Tout », afin que le nouveau prix soit valide pour tous les clients. Si vous différenciez des prix entre différents segments de clients, sélectionnez Groupe. Pour sélectionner Groupe, vous devez avoir configuré des Groupes de prix client.  

7. Dans le champ **Sélection du compte**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
9. Dans le champ **Code d'article**, sélectionnez « Table ».
    
    Lorsque vous entrez un accord commercial de type « Prix (ventes) », vous devez sélectionner uniquement « Table » dans le champ **Code article**. Cela est dû au fait qu'un prix est une valeur absolue et qu'il ne peut pas être identique pour tous les produits ou pour un groupe de produits.
    
10. Dans le champ **Relation d'article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans la liste, sélectionnez le produit que vous souhaitez inclure dans l'accord. Notez le produit que vous avez sélectionné.  
12. Dans le champ **De**, entrez une quantité minimale.
    - Si le client doit commander une quantité minimale pour bénéficier du nouveau prix, vous devez spécifier la quantité ici.  
    - Entrez une valeur dans le champ **À** pour spécifier la quantité maximale au-dessus de laquelle le prix de l'accord n'est pas valide. Si vous proposez des prix et des remises par quantité, spécifiez chaque seuil de quantité comme paire de quantité minimale et maximale dans les champs **De** et **À**, respectivement.
13. Dans le champ **Montant en devise**, entrez un prix.
14. Dans la section **Détails**, dans le champ **Date de début**, entrez une date à partir de laquelle cet accord est valide.
15. Cliquez sur **Enregistrer**.
16. Cliquez sur **Valider**.
17. Cliquez sur **Valider les lignes sélectionnées**.
18. Cliquez sur **OK**.
19. Cliquez sur **Valider**.
20. Cliquez sur **OK**.

## <a name="view-trade-agreements-for-a-product"></a>Afficher les accords commerciaux d'un produit
1. Accédez à **Volet de navigation > Modules > Gestion d'informations sur les produits > Produits > Produits lancés**.
2. Dans la liste, localisez et sélectionnez le produit dont vous venez de mettre à jour le prix.
3. Dans le volet **Action**, cliquez sur **Vendre**.
4. Cliquez sur **Afficher les accords commerciaux**.
    
    Examinez les détails de l'accord commercial de prix que vous venez de créer.    

5. Fermez la page.

## <a name="additional-resources"></a>Ressources supplémentaires
### <a name="community-blogs"></a>Blogs de la communauté
- [Prix de vente dans Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)
