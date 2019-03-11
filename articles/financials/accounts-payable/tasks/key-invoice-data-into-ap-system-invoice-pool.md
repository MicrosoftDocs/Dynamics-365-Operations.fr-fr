---
title: Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'un registre de factures
description: Ce guide de tâche va vous indiquer comment utiliser le registre des factures pour créer des factures.
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b4e9a52a383d4acc0bf2adc669fd88c0c0f7402
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "357448"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'un registre de factures

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche va vous indiquer comment utiliser le registre des factures pour créer des factures.  Utilisez ensuite le regroupement de factures pour mettre en correspondance la facture avec une commande fournisseur et finalisez la dépense dans la page de facture fournisseur.


## <a name="create-a-purchase-order"></a>Créer une commande fournisseur
1. Allez dans Comptabilité fournisseur > Commandes fournisseur > Commandes fournisseur.
2. Cliquez sur Nouveau pour créer une commande fournisseur.
3. Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Sélectionnez le fournisseur dans la liste. Par exemple, fournisseur 1001.
5. Cliquez sur OK.
6. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Recherchez le numéro d'article de services dans la liste. Par exemple, sélectionnez S0001.
8. Cliquez sur le numéro d'article et sélectionnez-le.
    * Le montant HT est de 75,00 €.  Il s'agit du montant attendu sur la facture.  
9. Dans le volet Actions, cliquez sur Achat.
10. Cliquez sur Confirmer.

## <a name="create-and-post-and-invoice"></a>Créer et valider une facture
1. Accédez à Comptabilité fournisseur > Factures > Registre des factures.
2. Cliquez sur Nouveau.
3. Ouvrez la recherche pour sélectionner le nom du registre des factures à utiliser.
4. Sélectionnez le nom du registre des factures à utiliser.
5. Cliquez sur Lignes pour ouvrir le registre, puis entrez des lignes de dépense.
6. Sélectionnez un fournisseur dans le champ de recherche. Par exemple, cliquez sur fournisseur 1001.
7. Entrez le numéro de la facture dans le champ Facture.
8. Tapez une valeur dans le champ Description.
9. Entrez un numéro dans le champ Crédit.
10. Dans le champ Commande fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Sélectionnez la commande fournisseur que vous avez créée précédemment.
12. Dans le champ Approbateur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
13. Mettez un approbateur en surbrillance et cliquez sur Sélectionner pour le sélectionner.
14. Cliquez sur Valider.
15. Permet de fermer l'écran.
16. Permet de fermer l'écran.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>Ouvrez une facture à partir du regroupement et faites-la correspondre à une commande fournisseur pour terminer le processus de facturation.
1. Accédez à Comptabilité fournisseur > Factures > Registre des factures.
2. Cliquez sur Commande fournisseur pour créer une facture fournisseur à partir de la facture dans le registre.
3. Sélectionnez la facture que vous souhaitez réviser.
4. Cliquez sur Mettre à jour le statut de rapprochement pour terminer le rapprochement.
5. Dans le volet Actions, cliquez sur Options.
6. Cliquez sur Changer de vue.
7. Cliquez sur Vue grille.
8. Cliquez sur Valider.
9. Permet de fermer l'écran.
10. Allez dans Comptabilité fournisseur > Fournisseurs > Fournisseurs.
11. Sélectionnez le fournisseur qui était sur la commande fournisseur. Par exemple, sélectionnez fournisseur 1001.
12. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
13. Dans le volet Actions, cliquez sur Fournisseur.
14. Cliquez sur Transactions.
15. Sélectionnez la facture que vous avez créée.
    * La régularisation du registre des factures a été contrepassée et validée dans le compte de dépenses approprié.  

