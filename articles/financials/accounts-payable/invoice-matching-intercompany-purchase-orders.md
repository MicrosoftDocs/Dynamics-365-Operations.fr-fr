---
title: Rapprochement de factures et commandes fournisseur intersociétés
description: L'entité juridique acheteuse impliquée dans une transaction commerciale intersociétés peut être paramétrée pour utiliser le rapprochement de factures d'Achats. Dans ce cas, les conditions de validation pour le commerce intersociétés et le rapprochement de factures d'Achats doivent être remplies pour que les factures fournisseur intersociétés puissent être validées.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchLineMatchingPolicy
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3101
ms.assetid: 9c7c2e44-45f8-4325-b6de-a09fe790f9cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d22d6352f179919666d39df816f04bab340017dc
ms.sourcegitcommit: dd1e1636d351a15f9c1b6808bea359417a9bd690
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2019
ms.locfileid: "897107"
---
# <a name="invoice-matching-and-intercompany-purchase-orders"></a>Rapprochement de factures et commandes fournisseur intersociétés

[!include [banner](../includes/banner.md)]

L'entité juridique acheteuse impliquée dans une transaction commerciale intersociétés peut être paramétrée pour utiliser le rapprochement de factures d'Achats. Dans ce cas, les conditions de validation pour le commerce intersociétés et le rapprochement de factures d'Achats doivent être remplies pour que les factures fournisseur intersociétés puissent être validées.

Les exemples de cette rubrique utilisent le paramétrage de commerce intersociétés suivant :
-   Fabrikam Purchase est l'entité juridique acheteuse.
-   Fabrikam Sales est l'entité juridique vendeuse.
-   Le client 4020 existe dans Fabrikam Sales.
-   Le fournisseur 3024 existe dans Fabrikam Purchase.
-   Dans Fabrikam Purchase, les informations intersociétés sont spécifiées pour le fournisseur 3024. Fabrikam Sales est spécifiée comme société du client, et le client 4020 est spécifié comme le compte client correspondant à l'entité juridique Fabrikam Purchase.
-   Dans Fabrikam Sales, les informations intersociétés sont spécifiées pour le client 4020. Fabrikam Purchase est spécifiée comme société du fournisseur, et le fournisseur 3024 est spécifié comme le compte fournisseur correspondant à l'entité juridique Fabrikam Sales.

Les exemples utilisent le paramétrage de rapprochement de factures d'Achats suivant pour Fabrikam Purchase :
-   L'option Activer le contrôle de rapprochement de factures est sélectionnée sur la page Paramètres de la comptabilité fournisseur.
-   Le champ Valider la facture avec les non-correspondances est défini sur Demander une approbation sur la page Paramètres de la comptabilité fournisseur.
-   Le pourcentage de tolérance de prix pour l'entité juridique est de 2 pour cent.

## <a name="example-price-matching-and-intercompany-trade"></a>Exemple : rapprochement de prix et commerce intersociétés
Les montants nets pour la facture fournisseur intersociétés et la facture client intersociétés doivent être égaux. Cette condition prime sur n'importe quel pourcentage de tolérance de prix et n'importe quelle approbation de rapprochement de factures applicable. Par exemple, procédez comme suit :
1.  Chez Fabrikam Purchase, créez une commande client CC888 pour le client 4020. La commande fournisseur intersociétés CFIS222 est créée automatiquement pour le fournisseur 3024 pour Fabrikam Purchase, et la commande client CCIS888 est créée automatiquement dans Fabrikam Sales.
2.  Dans Fabrikam Sales, enregistrez la réception des articles et validez un bon de livraison. Le statut de CCIS888 devient Livré. Le statut de CFIS222 devient Reçu.
3.  Mettez à jour une facture pour CCIS888 dans Fabrikam Sales. Le prix unitaire est de 0,45 et 100 articles sont mis à jour.
4.  Créez une facture pour CFIS222 dans Fabrikam Purchase. Modifiez accidentellement le prix net de 45,00 en 54,00. Une icône indiquant que le prix dépasse la tolérance de prix autorisée de 2 pour cent s'affiche.
5.  Sélectionnez l'option permettant d'approuver la validation avec des écarts de rapprochement sur la page Détails de rapprochement de factures. Sur la page Facture fournisseur cliquez sur OK. Si la facture fournisseur n'est pas une facture fournisseur intersociétés, la validation a réussi. Toutefois, comme vous utilisez une facture fournisseur intersociétés, la validation échoue. Pour le commerce intersociétés, les totaux de la facture sur la commande client intersociétés doivent être égaux aux totaux de la facture sur la commande fournisseur intersociétés correspondante. Pour résoudre ce problème, vous devez corriger le prix net de la facture en revenant au montant par défaut de 45,00.

## <a name="example-quantity-matching-with-intercompany-trade"></a>Exemple : mise en correspondance de la quantité avec le commerce intersociétés
Les quantités de la commande fournisseur intersociétés et de la commande client intersociétés doivent être égales. Cette exigence prévaut sur toutes les approbations de rapprochement de facture applicables. Cet exemple utilise le paramétrage de commerce intersociétés supplémentaire suivant :
-   Dans Fabrikam Purchase, la stratégie d'action de commande fournisseur pour le fournisseur 3024 est paramétrée pour valider automatiquement la facture client originale et la facture fournisseur intersociétés.

Cet exemple utilise le paramétrage de rapprochement de factures d'Achats supplémentaire suivant pour Fabrikam Purchase :
-   L'option Conditions préalables à la réception est activée sur la page Groupes de modèles d'article du groupe de modèles utilisé par l'article P-R14.
-   La quantité disponible de l'article P-R14 est 0 (zéro).

Par exemple, procédez comme suit :
1.  Dans Fabrikam Purchase, créez la commande client SO999 pour le client 4020. La commande contient une ligne : 100 piles (article P-R14) à un prix unitaire de 1,00 EUR chacune. La commande fournisseur intersociétés CFIS333 est créée automatiquement pour le fournisseur 3024 dans Fabrikam Purchase et la commande client CCIS999 est créée automatiquement dans Fabrikam Sales.
2.  Mettez à jour la facture pour CCIS999 dans Fabrikam Sales. La validation échoue, car l'article est indisponible et n'a pas encore été reçu. Par conséquent, les informations financières ne peuvent pas être mises à jour.
3.  Dans Fabrikam Sales, enregistrez la réception des articles et validez un bon de livraison pour CCIS999. Un accusé de réception de marchandises pour CFIS333 est automatiquement validé dans Fabrikam Purchase. La quantité reçue de l'article P-R14 dans Fabrikam Purchase passe à 100.
4.  Mettez à jour la facture pour CCIS999 dans Fabrikam Sales. La validation est réussie dans les deux entités juridiques. La quantité achetée pour l'article P-R14 dans Fabrikam Purchase passe à 100.





