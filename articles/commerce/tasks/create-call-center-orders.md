---
title: Créer des commandes de centre d’appels
description: Cette procédure décrit la recherche d’un client, la création d’une commande, la recherche d’un produit et la collecte du paiement auprès du client.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 78cccabb206d938b850e70b7e8057e20cc6158e1d154fc4876de7918dbe44d87
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730657"
---
# <a name="create-call-center-orders"></a>Créer des commandes de centre d’appels

[!include [banner](../includes/banner.md)]

Cette procédure décrit la recherche d’un client, la création d’une commande, la recherche d’un produit et la collecte du paiement auprès du client. Cette procédure utilise la société fictive USRT et est destinée au commis aux commandes client. Conditions préalables : l’utilisateur exécutant la procédure est configuré en tant qu’utilisateur du centre d’appels et le catalogue semi-annuel de Fabrikam est publié avec au moins un code source.

1. Accédez à **Retail et Commerce \> Clients \> Service client**.
2. Dans le champ **SearchText**, saisissez les critères de recherche du client.
    * Pour cet exemple de procédure, saisissez « Karen », puis sélectionnez **Onglet**.  
3. Sélectionnez Rechercher.
    * Comme il n’existe qu’un seul client nommé "Karen" dans les données de démonstration, le résultat est automatiquement sélectionné.  
4. Sélectionnez **Nouvelle commande client**.
5. Développez ou réduisez la section d’en-tête de **Commande client**.
6. Sélectionnez le code source du catalogue.
    * Si aucun code source n’est actif, vous pouvez ignorer cette étape.  
7. Sélectionnez **Ajouter la ligne**.
8. Pour **Numéro d’article**, saisissez le terme de recherche de l’article.
    * Pour cet exemple de procédure, entrez le numéro d’article partiel « 8111 » et appuyez sur l’onglet. Cette action fera apparaître la fenêtre de recherche d’élément.  
9. Sélectionnez le produit à ajouter à la commande client.
10. Saisissez la quantité vendue.
11. Sélectionnez **Créer**.
12. Cliquez sur **Terminer** pour capturer le paiement du client.
13. Sélectionnez **Ajouter**.
    * Le lien Ajouter figure dans l’onglet Paiements. Développez l’onglet Paiements s’il est réduit.  
14. Sélectionnez le mode de paiement.
    * Pour cette procédure, sélectionnez le mode de paiement au comptant.  
15. Fermez la page.
16. Entrez le montant.
    * Pour cette procédure, saisissez un montant égal au solde de la commande qui s’affiche dans la page Résumé de la commande client à gauche du champ de montant. Cette action vous permet de terminer la commande comme étant intégralement payée.  
17. Cliquez sur **OK**.
18. Sélectionnez **Soumettre**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Personnalisez les e-mails transactionnels par mode de livraison](../customize-email-delivery-mode.md)

[Modifier le mode de livraison dans le PDV](../pos-change-delivery-mode.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]