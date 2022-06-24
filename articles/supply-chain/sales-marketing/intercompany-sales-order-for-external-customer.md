---
title: Création et facturation d’une commande client intersociétés pour un client externe
description: Cet article explique comment créer et facturer une commande client intersociétés pour un client externe
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: cd42551730ab0123813a3b5a0b5a4b1c334e9d30
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852155"
---
# <a name="create-and-invoice-an-intercompany-sales-order-for-an-external-customer"></a>Création et facturation d’une commande client intersociétés pour un client externe

[!include [banner](../../includes/banner.md)]

Vous pouvez utiliser le commerce intersociétés pour enregistrer la vente d’un produit d’une entité juridique à une autre entité juridique située dans la même organisation.

Lorsque vous créez la commande client originale, vous pouvez automatiquement créer une commande fournisseur intersociétés pour le fournisseur intersociétés. Cela crée automatiquement une commande client intersociétés dans l’entité juridique du fournisseur intersociétés.

La figure suivante illustre le flux des transactions lorsque vous créez une commande client pour un client externe, mais le produit doit être commandé depuis une autre entité juridique de votre organisation avant de pouvoir livrer le produit au client. Dans ce cas, une commande fournisseur intersociétés est créée pour le compte fournisseur qui représente l’autre entité juridique. Consécutivement, une commande client intersociétés est créée dans l’autre entité juridique du compte client qui représente votre entité juridique. Lorsqu’une commande fournisseur intersociétés est facturée, la facture pour la commande client originale est automatiquement validée s’il s’agit d’une livraison directe.

![Processus de vente externe intersociétés](media/intercompanyexternalsalesprocess.png)

Si vous utilisez la livraison directe et sélectionnez **Bon de livraison** dans le champ **Quantité** de l’écran sur la page **Validation de la facture**, la facture fournisseur intersociétés est basée sur l’accusé de réception de marchandises intersociétés précédemment validé.

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer, vérifiez que les conditions requises suivantes sont respectées automatiquement pour valider et imprimer les factures intersociétés.

1. Allez dans **Ventes et marketing \> Clients \> Tous les clients**.
1. Dans le volet Actions, sous l’onglet **Général**, sélectionnez **Intersociétés**.
1. Accédez à **Approvisionnements \> Fournisseurs \> Tous les fournisseurs**.
1. Dans le volet Actions, sous l’onglet **Général**, sélectionnez **Intersociétés**.
1. Sur la page **Intersociété** pour le fournisseur ou le client, dans la zone **Politiques de bons de commande**, dans le groupe de champs **Bon de commande intersociétés (livraison directe)**, sélectionnez la case à cocher **Valider la facture automatiquement**.
1. Dans la zone **Politiques de bons de commande**, dans le groupe de champs **Commande client d’origine (livraison directe)**, cochez la case **Valider la facture automatiquement**. Activez cette case à cocher si vous voulez que la facture pour la commande client d’origine soit automatiquement imprimée lorsque vous validez la facture fournisseur intersociétés.

> [!NOTE]
> Les paramètres d’impression de la facture sont déterminés par le paramétrage du module, du document ou de la transaction sur la page **Paramétrage de la gestion de l’impression**.

## <a name="create-an-original-sales-order-for-an-external-customer"></a>Création d’une commande client d’origine pour un client externe

Procédez comme suit dans l’entité juridique A. Cette procédure correspond à la zone marquée 1 dans le graphique.

1. Accédez à **Comptabilité client \> Commandes client \> Toutes les commandes client**.
1. Dans la page de liste **Toutes les commandes client**, créez la commande client d’origine. Les valeurs de champs sont copiées du compte client vers la commande client.
1. Sur la page **Commande client**, sélectionnez **Vue de l’en-tête** dans le volet Actions.
1. Dans le raccourci **Paramètres intersociétés**, cochez la case **Créer automatiquement des commandes intersociétés**.
1. Si vous souhaitez que le fournisseur intersociétés fournisse l’article directement au client externe, activez la case à cocher **Livraison directe**.
1. Lorsque vous avez terminé d’entrer la commande client, fermez la page **Commande client**.

La commande fournisseur intersociétés est créée automatiquement pour tous les articles affectés à un fournisseur intersociétés, puis la commande client intersociétés est créée. Un message d’information indique qu’une commande fournisseur intersociétés et une commande client intersociétés ont été créées. Le message inclut également des liens vers ces commandes. Si un article n’a pas été trouvé, un avertissement rouge s’affiche, ce qui signifie que le processus de création de la commande n’a pas été terminé.

> [!NOTE]
> Si vous créez plusieurs commandes dans plusieurs entités juridiques, et que les articles ne sont pas trouvés dans une des entités juridiques, le processus de création de commandes s’arrête, même pour les entités juridiques qui pourraient honorer leurs commandes.

## <a name="invoice-an-intercompany-sales-order"></a>Facturation d’une commande client intersociétés

Lorsqu’une commande client intersociétés est facturée, la commande fournisseur intersociétés correspondante est automatiquement facturée. Ensuite, si la commande client originale est un bon de livraison directe, la commande client d’origine est automatiquement facturée.

Procédez comme suit dans l’entité juridique B. Cette procédure correspond à la zone marquée 2 dans le graphique.

1. Accédez à **Comptabilité client \> Commandes client \> Toutes les commandes client**.
1. Dans la page de liste **Toutes les commandes client**, sélectionnez une commande client intersociétés.
1. Dans le volet Actions, sélectionnez l’onglet **Facture**, puis sélectionnez à nouveau **Facture**.
1. Cochez la case **Validation**.
1. Sélectionnez la commande client, puis sélectionnez **OK**.

La facture client pour la commande client intersociétés est automatiquement validée dans l’entité juridique B. La facture fournisseur intersociétés est ensuite automatiquement créée et validée dans l’entité juridique A. Si la commande client originale est paramétrée comme livraison directe, la facture client est créée pour la commande client originale dans l’entité juridique A.

> [!NOTE]
> Auparavant, pour les scénarios de vente intersociétés, si le workflow de facturation fournisseur était configuré dans la société d’achat intersociétés, la commande client intersociétés ne pouvait pas être facturée avec succès. Par conséquent, le workflow de facturation fournisseur devait être désactivé pour la société d’achat intersociétés. 
> 
> Cette limitation a été corrigée par une fonctionnalité récente de la version 10.0.25. Les commandes client intersociétés peuvent désormais être facturées lorsque le workflow de facturation fournisseur est configuré dans la société d’achat intersociétés.
> 
> Pour activer cette fonctionnalité, procédez comme suit.
>
> 1. Sélectionnez l’entité juridique dans le vente intersociétés.  
> 2. Allez dans **Comptabilité client \> Clients \> Tous les clients**.
> 3. Sélectionnez le client pour la société d’achat intersociétés.
> 4. Accédez à **Général \> Mise en place \> Intersociétés**.
> 5. Sur l’onglet **Politiques de bon de commande**, sélectionnez le paramètre **Ignorer le flux de travail des factures fournisseur pour les factures fournisseur intersociétés**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
