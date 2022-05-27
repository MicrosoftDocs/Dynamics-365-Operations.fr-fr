---
title: Indexer les données de facturation dans la comptabilité fournisseur à l’aide d’un registre de factures
description: Cette rubrique décrit comment utiliser le registre des factures pour créer des factures.
author: abruer
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf781089469f87dc0a98279003c94fd1e8bf9dbe
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717332"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>Indexer les données de facturation dans la comptabilité fournisseur à l’aide d’un registre de factures

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment utiliser le registre des factures pour créer des factures. Utilisez ensuite le regroupement de factures pour mettre en correspondance la facture avec une commande fournisseur et finalisez la dépense dans la page de facture fournisseur.


## <a name="create-a-purchase-order"></a>Créer une commande fournisseur
1. Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Commandes fournisseur > Commandes fournisseur**.
2. Sélectionnez **Nouveau** pour créer une commande fournisseur.
3. Dans le champ **Compte fournisseur**, sélectionnez un fournisseur depuis la liste déroulante. Par exemple, sélectionnez le fournisseur **1001**.
4. Cliquez sur **OK**.
5. Dans le champ **Numéro d’article**, sélectionnez le numéro d’article de services dans la liste déroulante. Par exemple, sélectionnez **S0001**. Le montant HT est de 75,00 €.  Il s’agit du montant attendu sur la facture.  
6. Dans le volet Actions, sélectionnez **Achat**.
7. Sélectionnez **Confirmer**.

## <a name="create-and-post-and-invoice"></a>Créer et valider une facture
1. Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Factures > Registre des factures**.
2. Sélectionnez **Nouveau**.
3. Ouvrez la recherche pour sélectionner le nom du registre des factures à utiliser.
4. Sélectionnez le nom du registre des factures à utiliser.
5. Sélectionnez **Lignes** pour ouvrir le registre, puis entrez des lignes de dépense.
6. Sélectionnez un fournisseur dans le champ de recherche. Par exemple, sélectionnez le fournisseur **1001**.
7. Entrez le numéro de la facture dans le champ **Facture**.
8. Tapez une valeur dans le champ **Description**.
9. Dans le champ **Crédit**, entrez un numéro.
10. Dans le champ **Commande fournisseur**, ouvrez la liste déroulante pour sélectionner la commande fournisseur créée précédemment.
11. Dans le champ **Approuvé par**, sélectionnez un approbateur dans la liste déroulante et cliquez sur **Sélectionner** pour sélectionner l’approbateur.
12. Sélectionnez **Valider**.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>Ouvrez une facture à partir du regroupement et faites-la correspondre à une commande fournisseur pour terminer le processus de facturation.
1. Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Factures > Registre des factures**.
2. Sélectionnez **Commande fournisseur** pour créer une facture fournisseur à partir de la facture dans le registre.
3. Sélectionnez la facture que vous souhaitez réviser.
4. Sélectionnez **Mettre à jour le statut de rapprochement** pour terminer le rapprochement.
5. Dans le volet Actions, sélectionnez **Options**.
6. Sélectionnez **Modifier la vue**.
7. Sélectionnez **Vue Grille**.
8. Sélectionnez **Valider**.
9. Fermez la page.
10. Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Fournisseurs > Fournisseurs**.
11. Sélectionnez le fournisseur qui était sur la commande fournisseur. Par exemple, sélectionnez le fournisseur **1001**.
12. Dans la volet Actions, sélectionnez **Fournisseur**.
13. Sélectionnez les **transactions**.
14. Sélectionnez la facture que vous avez créée. La régularisation du registre des factures a été contrepassée et validée dans le compte de dépenses approprié.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
