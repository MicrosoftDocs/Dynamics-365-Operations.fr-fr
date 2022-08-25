---
title: Créer des commandes de centre d’appels
description: Cet article présente un exemple de procédure dans laquelle un utilisateur du centre d’appels recherche un client, crée une nouvelle commande, recherche un produit et encaisse le paiement du client dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 08/05/2022
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
ms.openlocfilehash: 16d483896ce131e9a7bc60ab5ea7b8fa01a3bea8
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228508"
---
# <a name="create-call-center-orders"></a>Créer des commandes de centre d’appels

[!include [banner](../includes/banner.md)]

Cet article présente un exemple de procédure dans laquelle un utilisateur du centre d’appels recherche un client, crée une nouvelle commande, recherche un produit et encaisse le paiement du client dans Microsoft Dynamics 365 Commerce. Cette procédure utilise les données démographiques de la société USRT et est destinée au commis aux commandes client. 

## <a name="prerequisites"></a>Conditions préalables

L’utilisateur qui effectue la procédure doit être configuré comme un utilisateur de centre d’appels. Si vous le souhaitez, le catalogue semestriel Fabrikam peut être publié avec au moins un code source.

### <a name="add-yourself-as-a-call-center-user"></a>Ajoutez-vous en tant qu’utilisateur du centre d’appels

Pour vous ajouter en tant qu’utilisateur de centre d’appels, procédez comme suit.

1. Dans Commerce headquarters, accédez à **Retail et Commerce \> Canaux \> Centres d’appels \> Tous les centres d’appels**.
1. Dans le champ **Utilisateurs**, sélectionnez **Utilisateurs du canal**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **ID utilisateur**, entrez votre ID utilisateur.
1. Dans le champ **Nom**, saisissez votre nom d’utilisateur. Le nom d’utilisateur peut être identique à l’ID utilisateur.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Revenez à **Vente au détail et commerce \> Canaux \> Centres d’appel \> Tous les centres d’appels**.
1. Sélectionnez l’ID du canal de vente au détail du centre d’appels.
1. Vérifiez que l’option **Activer l’achèvement de la commande** est définie sur **Oui**. Si cette option n’est pas visible, vous pouvez ignorer cette étape.

## <a name="complete-the-example-call-center-procedure"></a>Terminer l’exemple de procédure de centre d’appels

Pour terminer l’exemple de procédure de centre d’appels, procédez comme suit.

1. Accédez à **Retail et Commerce \> Clients \> Service client**.
1. Sur l’onglet **Recherche de clients**, saisissez les critères de recherche du client. Pour cet exemple de procédure, saisissez **Karen**.
1. Sélectionnez **Rechercher**. La boîte de dialogue **Recherche de clients** apparaît et répertorie les résultats de la recherche.
1. Sélectionnez la fiche client pour **Karen Berg** dont le numéro de compte client est **2001**, puis sélectionnez **Sélectionner**.
1. Sélectionnez **Nouvelle commande client** dans le volet Actions.
1. Sur la droite, sélectionnez l’onglet **En-tête**.
1. Dans le raccourci **Livraison**, dans le champ **Mode de livraison**, sélectionnez **99 Standard**.

    ![Sélectionner un mode de livraison.](../media/Select_Mode_of_Delivery.png)

1. Sur la droite, sélectionnez l’onglet **Lignes**.
1. Dans la section **Lignes de commande client**, sur la nouvelle rangée de la nouvelle ligne de vente, dans le champ **Numéro d’article**, saisissez le numéro de l’article à rechercher. Pour cet exemple de procédure, saisissez **81327**, puis sélectionnez le produit dans la liste déroulante pour l’ajouter à la commande client.
1. Dans le champ **Quantité**, entrez la quantité de la vente.
1. Dans le champ **Code source**, sélectionnez le code source du catalogue. Si aucun code source n’est actif, vous pouvez ignorer cette étape.
1. Dans le volet Action, sélectionnez **Terminer** pour capturer le paiement du client. Cette action ouvre la boîte de dialogue **Résumé de la commande client**, qui affiche le montant total dû. L’action déclenche également le calcul de tous les frais, tels que l’expédition et la manutention, et les affiche dans la boîte de dialogue **Résumé de la commande client**.

    ![Bouton Terminer.](../media/Complete_button.png)

1. Dans la boîte de dialogue **Résumé de la commande client**, sur le raccourci **Paiements**, sélectionnez **Ajouter** pour capturer les paiements.

    ![Boîte de dialogue Récapitulatif de la commande client.](../media/order_summary.png)

1. Dans la boîte de dialogue **Saisir les informations de paiement du client**, dans le champ **Moyen de paiement**, sélectionnez le moyen de paiement. Pour cet exemple de procédure, sélectionnez **Espèces**.
1. Dans le champ **Montant du paiement**, entrez le montant du paiement. Pour cet exemple, entrez **120,00**, ce qui correspond au solde de la commande indiqué dans la boîte de dialogue **Résumé de la commande client**. Saisir ce montant vous permet de terminer la commande comme étant intégralement payée.
1. Cliquez sur **OK**.
1. Sélectionnez **Soumettre**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Personnalisez les e-mails transactionnels par mode de livraison](../customize-email-delivery-mode.md)

[Modifier le mode de livraison dans le PDV](../pos-change-delivery-mode.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
