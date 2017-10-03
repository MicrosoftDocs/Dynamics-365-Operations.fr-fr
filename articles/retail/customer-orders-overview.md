---
title: Vue d'ensemble des commandes client
description: "Cette rubrique fournit des informations sur les commandes client dans Retail Modern POS (MPOS). Les commandes client sont également appelées commandes spéciales. La rubrique inclut une discussion sur les paramètres associés et les flux de transaction."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 89e79c7227e05eec539d9bb142b8f41de092f01b
ms.contentlocale: fr-fr
ms.lasthandoff: 06/20/2017



---

# <a name="customer-orders-overview"></a>Vue d'ensemble des commandes client

[!include[banner](includes/banner.md)]


Cette rubrique fournit des informations sur les commandes client dans Retail Modern POS (MPOS). Les commandes client sont également appelées commandes spéciales. La rubrique inclut une discussion sur les paramètres associés et les flux de transaction.

Dans le monde de la vente au détail dans plusieurs canaux, de nombreux détaillants offrent la possibilité que les commandes client ou les commandes spéciales répondent à diverses exigences de produit et de traitement. Voici quelques scénarios classiques :

-   Un client souhaite que les produits soient livrés à une adresse spécifique à une date spécifique.
-   Un client souhaite prélever les produits dans un magasin ou un emplacement qui diffère du magasin ou de l'emplacement où il a acheté ces produits.
-   Un client souhaite qu'une autre personne prélève les produits qu'il a achetés.

Les détaillants utilisent également les commandes client pour réduire les ventes perdues que les pénuries de stock peuvent causer, car les marchandises peuvent être livrées ou prélevées à un autre moment ou emplacement.

## <a name="set-up-customer-orders"></a>Paramétrer les commandes client
Voici quelques paramètres qui peuvent être définis dans la page **Paramètres des ventes au détail** pour définir la façon dont les commandes client sont honorées :

-   **Pourcentage de dépôt par défaut** – Spécifiez le montant que le client doit payer comme dépôt avant qu'un ordre puisse être confirmé. Le montant de dépôt par défaut est calculé sous forme de pourcentage de la valeur de la commande. Selon les privilèges, un associé du magasin peut remplacer le montant à l'aide de l'option **Remplacement de dépôt**.
-   **Pourcentage de frais d'annulation** – Si des frais sont appliqués lorsqu'une commande client est annulée, spécifiez le montant de ces frais.
-   **Code frais d'annulation** – Si des frais sont appliqués lorsqu'une commande client est annulée, ces frais sont indiqués dans un code frais sur la commande client. Utilisez ce paramètre pour définir un code frais d'annulation.
-   **Code frais d'expédition** – Les détaillants peuvent facturer des frais supplémentaires pour expédier les marchandises à un client. Le montant de ces frais d'expédition sera indiqué dans un code frais sur la commande client. Utilisez ce paramètre pour mettre en correspondance le code frais d'expédition avec les frais d'expédition de la commande client.
-   **Rembourser les frais d'expédition** – Spécifiez si les frais d'expédition associés à une commande client sont remboursables.
-   **Montant maximal sans approbation** – Si les frais d'expédition sont remboursables, spécifiez le montant maximal du remboursement des frais d'expédition pour plusieurs ordres de retour. Si ce montant est dépassé, le remplacement par le responsable est nécessaire pour procéder au remboursement. Pour prendre en charge les scénarios suivants, le remboursement des frais d'expédition peut dépasser le montant initialement payé :
    -   Les frais sont appliqués au niveau de l'en-tête de commande client et, lorsqu'une certaine quantité d'une ligne de produit est renvoyée, le remboursement maximal des frais d'expédition qui est autorisé pour les produits et la quantité ne peut pas être déterminé de manière appropriée pour tous les clients de vente au détail.
    -   Des frais d'expédition sont générés pour chaque instance d'expédition. Si un client retourne des produits à plusieurs reprises, et la stratégie du détaillant spécifie que le coût des frais d'expédition de retour sera à la charge du détaillant, les frais d'expédition de retour seront supérieurs aux frais d'expédition réels.

## <a name="transaction-flow-for-customer-orders"></a>Flux de transaction pour les commandes client
### <a name="create-a-customer-order-in-retail-modern-pos"></a>Créer une commande client dans Retail Modern POS

1.  Ajoutez un client à la transaction.
2.  Ajoutez des produits dans le chariot.
3.  Cliquez sur **Créer une commande client**, puis sélectionnez le type de commande. Le type de commande peut être **Commande client** ou **Devis**.
4.  Cliquez sur **Expédition sélectionnée** ou sur **Expédier tout** pour expédier les produits à une adresse indiquée sur le compte client, spécifier la date d'expédition demandée et spécifier les frais d'expédition.
5.  Cliquez sur **Prélèvement sélectionné** ou sur **Prélever tout** pour sélectionner les produits qui seront prélevés du magasin actuel ou d'un autre magasin à une date spécifique.
6.  Prélevez le montant de dépôt, si un dépôt est requis.

### <a name="edit-an-existing-customer-order"></a>Modifier une commande client existante

1.  Sur la page d'accueil, cliquez sur **Rechercher une commande**.
2.  Recherchez et sélectionnez la commande à modifier. En bas de la page, cliquez sur **Modifier**.

### <a name="pick-up-an-order"></a>Prélever une commande

1.  Sur la page d'accueil, cliquez sur **Rechercher une commande**.
2.  Sélectionnez la commande à prélever. En bas de la page, cliquez sur **Prélèvement et conditionnement**.
3.  Cliquez sur **Prélever**.

### <a name="cancel-an-order"></a>Annuler une commande

1.  Sur la page d'accueil, cliquez sur **Rechercher une commande**.
2.  Sélectionnez la commande à annuler. En bas de la page, cliquez sur **Annuler**.

#### <a name="create-a-return-order"></a>Créer un ordre de retour

1.  Sur la page d'accueil, cliquez sur **Rechercher une commande**.
2.  Sélectionnez la commande à retourner, sélectionnez la facture pour la commande, puis sélectionnez la ligne de produit pour les marchandises à retourner.
3.  En bas de la page, cliquez sur **Ordre de retour**.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Flux de transaction asynchrone pour les commandes client
Les commandes client peuvent être créées à partir du client de point de vente (PDV) en mode synchrone ou asynchrone.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Activer les commandes client à créer en mode asynchrone

1.  Cliquez sur **Vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **Profil POS** &gt; **Profils de fonctionnalité**.
2.  Dans l'organisateur **Général**, définissez l'option **Créer une commande client en mode asynchrone** sur **Oui**.

Lorsque l'option **Créer une commande client en mode asynchrone** est définie sur **Oui**, les commandes client sont toujours créées en mode asynchrone, même si Retail Transaction Service (RTS) est disponible. Si vous définissez cette option sur **Non**, les commandes client sont toujours créées en mode synchrone à l'aide de RTS. Lorsque les commandes client sont créées en mode asynchrone, elles sont extraites et insérées dans Dynamics AX par les tâches de traction Retail (P). Les commandes client correspondantes sont créées dans Retail lorsque l'option **Synchroniser les commandes** est exécutée manuellement ou via un processus de traitement par lots.

<a name="see-also"></a>Voir également :
--------

[Commandes client hybrides](hybrid-customer-orders.md)



