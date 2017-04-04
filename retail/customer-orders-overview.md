---
title: Vue d&quot;ensemble des commandes client
description: "Cette rubrique fournit des informations sur les commandes client dans le Retail Modern POS (MPOS). Les commandes client sont également désigné comme commandes spéciales. La rubrique inclut une discussion des paramètres associés et la transaction est transmise."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2f466dfe53ccf0be15ed0793b4a6dd371bdacc0d
ms.lasthandoff: 03/31/2017


---

# <a name="customer-orders-overview"></a>Vue d'ensemble des commandes client

Cette rubrique fournit des informations sur les commandes client dans le Retail Modern POS (MPOS). Les commandes client sont également désigné comme commandes spéciales. La rubrique inclut une discussion des paramètres associés et la transaction est transmise.

Dans un monde de vente au détail d'omni- canal, de nombreux détaillants fournissent l'option les commandes client, ou des commandes spéciales, de répondre à plusieurs demandes de produits et d'exécution. Voici quelques scénarios exemple :

-   Un client veut des produits à livrer à une adresse spécifique à une date spécifique.
-   Un client souhaite prélever cumulé les produits d'un magasin ou d'un emplacement qui diffère du magasin ou de l'emplacement dans lequel le client a acheté ces produits.
-   Un client souhaite un tiers pour prélever cumulé les produits que le client ait achetés.

Les détaillants utilisent également les commandes client pour réduire les ventes perdues que les pannes courantes peuvent donc être à l'origine, car les marchandises peuvent être fournies ou prélevées à un temps ou à un emplacement différent.

## <a name="set-up-customer-orders"></a>Commandes client de paramétrage
Voici quelques paramètres peuvent être définis sous ** les paramètres des ventes au détail ** la page de définir la manière dont les commandes client sont atteintes :

-   ** Pourcentage disposition par défaut ** – Permet de spécifier le montant que le client doit payer comme un dépôt avant qu'un ordre puisse être confirmé. Montant disposition par défaut est calculée comme un pourcentage de la valeur de commande. Selon les privilèges, un Associé du magasin peut puissiez remplacer le montant à l'aide de ** remplacement de dépôt **.
-   ** Le pourcentage de frais d'annulation ** – Si les frais sont appliqués lorsqu'une commande client est annulée, spécifiez le montant de ces frais.
-   ** Code frais d'annulation ** – Si les frais sont appliqués lorsqu'une commande client est annulée, ces frais est affiché sous code frais sur la commande client dans Microsoft Dynamics AX. Ce paramètre permet de définir un code frais d'annulation.
-   ** Le code frais d'expédition ** – des détaillants qui mettent en boîte facturer des frais supplémentaires pour les articles de expédition à un client. Montant de ces frais d'expédition sera affiché sous code frais sur la commande client dans Dynamics AX. Ce paramètre permet de mettre en correspondance le code frais d'expédition aux frais d'expédition de la commande client.
-   ** Les frais d'expédition de remboursement ** – spécifient si les frais d'expédition qui sont associés à une commande client sont remboursables.
-   ** Montant maximal sans approbation ** – Si les frais d'expédition sont remboursables, spécifiez le montant maximal de remboursements de frais d'expédition sur plusieurs ordres de retour. Si ce montant est dépassé, le remplacement du responsable est requis pour poursuivre le remboursement. Pour adapter les scénarios suivants, un remboursement des frais d'expédition peut dépasser le montant qui a été payé :
    -   Les frais sont appliqués au niveau de l'en-tête de commande client et, lorsqu'une certaine quantité d'une ligne de produit est renvoyée, le remboursement maximale des frais d'expédition autorisé pour les produits et la quantité ne peut pas être déterminé de la manière qui s'exécute pour tous les clients au détail.
    -   Les frais d'expédition sont générés pour chaque instance de l'expédition. Si un client retourne la plusieurs fois de produits, et la stratégie du détaillant spécifie que le détaillant soutiendra le coût de frais d'expédition de retour, les frais d'expédition de retour sont plus que les frais d'expédition réels.

## <a name="transaction-flow-for-customer-orders"></a>Flux de transaction pour les commandes client
### <a name="create-a-customer-order-in-retail-modern-pos"></a>Créez une commande client dans le Retail Modern POS

1.  Ajoutez un client à la transaction.
2.  Ajout de produits au chariot.
3.  Cliquez sur ** créez la commande client **, puis sélectionnez le type de commande. Type de commande peut être ou ** commande client ** ou ** devis **.
4.  Cliquez sur ** expédition sélectionnée ** ou ** expédition entière ** vers l'expédition des produits à une adresse sur le compte client, spécifiez la date d'expédition demandée, et de spécifier les frais d'expédition.
5.  Cliquez sur ** prélevez vers le haut de sélectionné ** ou ** ramassez tous ** pour sélectionner les produits qui sont prélevés du magasin actuel ou d'un magasin autre une date spécifique.
6.  Collecte le montant de dépôt, si un dépôt est requis.

### <a name="edit-an-existing-customer-order"></a>Modification d'une commande client existante

1.  Sur la page d'accueil, cliquez sur ** recherchez un ordre **.
2.  Recherche et sélectionnez la commande à modifier. En bas de la page, cliquez sur ** modifiez **.

### <a name="pick-up-an-order"></a>Prélevez vers le haut d'une commande

1.  Sur la page d'accueil, cliquez sur ** recherchez un ordre **.
2.  Sélectionnez l'ordre de prélèvement. En bas de la page, cliquez sur ** prélèvement et emballage **.
3.  Cliquez sur ** prélevez **.

### <a name="cancel-an-order"></a>Permet d'annuler un ordre

1.  Sur la page d'accueil, cliquez sur ** recherchez un ordre **.
2.  Sélectionnez la commande à annuler. En bas de la page, cliquez sur ** annuler **.

#### <a name="create-a-return-order"></a>Création d'un ordre de retour

1.  Sur la page d'accueil, cliquez sur ** recherchez un ordre **.
2.  Sélectionnez l'ordre de retourner, sélectionnez la facture pour la commande, puis sélectionnez la ligne de produit pour des marchandises à retourner.
3.  En bas de la page, cliquez sur ** ordre de retour **.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Flux asynchrone de transaction pour les commandes client
Les commandes client peuvent être créées du client de (POS) de point de vente en mode synchrone ou mode asynchrone.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Activez les commandes client doit être créé en mode asynchrone

1.  Dans Dynamics AX, cliquez sur ** au détail et commerce ** &gt; ** le canal paramétré ** &gt; ** la configuration ** &gt; ** profil du PDV ** &gt; ** des profils de fonctionnalité **.
2.  Sous ** général ** l'organisateur, définissez ** créez la commande client en mode d'async ** l'option ** Oui **.

Lorsque ** créez la commande client en mode d'async ** l'option est définie ** Oui **, les commandes client sont toujours créées en mode asynchrone, même si le Retail Transaction Service (RTS) est disponible. Si vous définissez cette option ** aucune **, les commandes client sont toujours créé en mode synchrone à l'aide de RTS. Lorsque des commandes client sont créées en mode asynchrone, elles sont extraites et insérées dans Dynamics AX par tâches de la extraction (P). Les commandes client correspondantes sont créées dans Dynamics AX lorsque ** synchronisez les ordres ** est effectué manuellement ou via un processus de traitement par lots.

<a name="see-also"></a>Voir également :
--------

[Commandes client hybrides] (hybrid-customer-orders.md)


