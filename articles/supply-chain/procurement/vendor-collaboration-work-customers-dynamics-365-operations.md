---
title: Collaboration fournisseur avec des clients
description: "Cette rubrique décrit comment utiliser la collaboration fournisseur dans Finance and Operations pour utiliser des CF et surveiller le stock de consignation."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 6119f1c85b68e6ed5dce01a266c4e681dfc4cd30
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="vendor-collaboration-with-customers"></a>Collaboration fournisseur avec des clients

[!include[banner](../includes/banner.md)]


Cette rubrique décrit comment utiliser la collaboration fournisseur dans Finance and Operations pour utiliser des CF et surveiller le stock de consignation.

Cette rubrique décrit comment utiliser la collaboration fournisseur avec les clients dans Microsoft Finance and Operations. Elle inclut des informations sur la manière de surveiller les commandes fournisseur et d'y répondre, et sur la manière de surveiller le stock de consignation. Il est également possible d'utiliser la collaboration du fournisseur avec les factures. Pour plus d'informations, voir [Espace de travail de facturation de collaboration fournisseur](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md).

## <a name="working-with-purchase-orders"></a>Utilisation des commandes fournisseur
L'espace de travail **Confirmation de commande fournisseur** vous permet de répondre aux CF soumises à vous pour révision. Il permet également d'afficher des informations sur les CF qui attendent une action du client, et les CF qui ont été confirmées, mais qui sont toujours en cours. Il existe trois listes dans l'espace de travail **Confirmation de commande fournisseur** :

-   **Commandes fournisseur pour examen** - Cette liste affiche les CF qui vous ont été soumises et attendent une réponse de vous. Lorsque vous répondez, la CF disparaît de la liste. Si le client vous envoie une nouvelle version de la CF avant d'avoir répondu à la précédente, seule la dernière version s'affiche.
-   **En attente d'une action du client** - Cette liste vous permet de visualiser les CF auxquelles vous avez répondu, mais qui n'ont pas encore été confirmées par le client. Si vous validez la CF, vous pouvez la surveiller dans cette liste jusqu'à ce que son statut passe à **Confirmée**. Si vous refusé la CF ou que vous l'acceptez avec des modifications, vous pouvez surveiller la CF ici jusqu'à ce que le client envoie une nouvelle version.
-   **Commandes fournisseurs confirmées** - Cette liste contient toutes CF de votre compte ayant le statut **Confirmée**. Lorsque des produits ou services sont entièrement reçus par rapport à la CF, la CF disparaît de la liste.

La liste suivante affiche les quatre pages que vous pouvez utiliser pour des commandes fournisseur, dont deux contiennent les mêmes informations que les listes de l'espace de travail :

-   **Commandes fournisseur pour examen** (voir ci-dessus)
-   **Historique des confirmations de commandes fournisseur** - Cette page contient toutes les CF et toutes les versions des CF envoyées au fournisseur, et toutes les réponses qui ont été renvoyées de la part du fournisseur.
-   **Commandes fournisseurs confirmées** (voir-ci dessus)
-   **Toutes les commandes fournisseur confirmées** - Cette page contient toutes les CF qui ont été confirmées, y compris celles où les produits ou services ont été reçus. Vous pouvez utiliser cette liste pour surveiller pour quelle CF vous pouvez envoyer des factures.

### <a name="responding-to-purchase-orders"></a>Réponse aux commandes fournisseur

Les commandes fournisseur que le client vous a envoyées pour examen sont visibles dans l'espace de travail **Confirmation de commande fournisseur** et dans la page **Commandes fournisseur pour examen**. Après avoir ouvert une CF, vous pouvez choisir de l'accepter, de la rejeter ou de l'accepter avec des modifications. Il peut y avoir des documents joints dans l'en-tête de la CF ou sur des lignes individuelles. Vous pouvez également associer des informations à votre réponse dans l'en-tête de la CF ou des lignes individuelles. Par exemple, vous pouvez proposer un article de remplacement pour l'une des lignes. Vous pouvez prévisualiser et imprimer la CF comme fichier PDF à l'aide de l'option **Aperçu/Imprimer**. Vous pouvez masquer ou afficher les colonnes de dimension suivantes à l'aide de l'action **Dimensions d'affichage** : site, entrepôt, couleur, taille, style, configuration. Si vous utilisez l'option **Accepter avec des modifications**, vous pouvez accepter ou rejeter des lignes séparément. Vous pouvez également apporter les modifications suivantes aux lignes :

-   Modifier les dates ou les quantités. Si vous souhaitez mettre à jour la date de livraison confirmée sur toutes les lignes, utilisez l'option **Mettre à jour la date de livraison** sur l'en-tête de la CF.
-   Fractionner des lignes pour différentes dates de livraison ou quantités
-   Remplcez un article. Pour ce faire, entrez une description d'article et votre numéro d'article dans le champ **Externe** dans la section **Détails de ligne**.

Vous ne pouvez pas modifier les informations ou des frais de tarification, mais vous pouvez effectuer des suggestions pour modifier ces derniers avec des notes. Si votre client vous envoie une nouvelle version d'une CF, celle-ci un suffixe de version pour indiquer qu'il s'agit d'une version modifiée d'une CF qui a été précédemment communiquée. La page **Historique des confirmations de commandes fournisseur** vous permet de suivre l'historique de chaque commande.

## <a name="monitoring-consignment-inventory"></a>Surveillance du stock de consignation
Si vous utilisez le stock de consignation, vous pouvez utiliser l'interface de collaboration fournisseur pour afficher les informations sur les pages suivantes :

-   **Commandes fournisseur consommant le stock de consignation** - Les commandes fournisseur pour le stock de consignation sont générées lorsqu'un client prend la propriété du stock. Ces commandes fournisseur de consignation sont affichées uniquement sur la page **Commandes fournisseur consommant le stock de consignation**. Elles ne sont pas incluses dans la page **Toutes les commandes fournisseur confirmées**.
-   **Produits reçus du stock de consignation** - Cette page affiche la liste de toutes les transactions dont la propriété des produits a été transférée à la société qui consomme le stock. Ces informations vous permettent de facturer le client.
-   **Stock de consignation disponible** - Cette page affiche le stock de consignation disponible appartenant à votre société qui est disponible dans l'entrepôt du client.


<a name="see-also"></a>Voir également :
--------

[Gérer les utilisateurs de la fonctionnalité de collaboration du fournisseur](manage-vendor-collaboration-users.md)




