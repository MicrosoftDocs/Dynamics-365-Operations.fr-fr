---
title: "Présentation des commandes fournisseur"
description: "Cet article fournit des informations générales sur les commandes fournisseur (CF) et des liens vers d’autres articles qui sont liés aux différentes étapes par lesquelles passe CF."
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 93083
ms.assetid: e9b7bc5b-1d7e-4ec2-97be-d655274b0613
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: c36795a071cc72721558bfa8984ecf1f47501c91
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="purchase-order-overview"></a>Présentation des commandes fournisseur

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Cet article fournit des informations générales sur les commandes fournisseur (CF) et des liens vers d’autres articles qui sont liés aux différentes étapes par lesquelles passe CF.

Une commande fournisseur (CF) est un document qui représente un contrat avec un fournisseur pour acheter des biens ou des services. Ce document permet également de garder une trace des accusés de réception de marchandises qui sont effectuées vis-à-vis de la commande et, plus tard, la comptabilisation des factures fournisseur que le fournisseur facture par rapport à la commande.  

La page **Commandes founisseur** contient une vue d’ensemble des commandes disponibles et vous permet de modifier celles-ci. Lorsque vous ouvrez une CF, vous pouvez sélectionner la vue **En-tête**, qui contient des informations spécifiées une seule fois pour chaque CF, telles que les détails du fournisseur. Vous pouvez également sélectionner la vue **Lignes**, dans laquelle vous pouvez modifier les lignes de commande. En règle générale, vous allez vous déplacer entre ces deux vues lorsque vous modifiez les CF. Les frais ne figurent pas directement sur la page **Commandes fournisseur**, mais ils sont accessibles via les menus de l’en-tête et des lignes de la commande.  

Il existe de nombreux états, où vous pouvez afficher des informations sur les CF, les accusés de réception de marchandises et les factures fournisseur. Ces états sont trouvent dans les modules **Approvisionnements** et **Comptabilité fournisseur**.  

Les espaces de travail **Préparation des commandes fournisseur** et **Réception et suivi de commande fournisseur** vous permettent d’afficher des listes des CF dans les différents états dans lesquels elles sont passés. Ils fournissent également un résumé des actions qui doivent être prises. L'espace de travail **Préparation des commandes fournisseur** se concentre sur la création et la révision de la CF, le traitement de la commande par approbation et la confirmation auprès du fournisseur. L'espace de travail **Réception et suivi de commande fournisseur** se concentre sur le traitement de la réception des marchandises ou des services par rapport aux CF. Il inclut des listes des réceptions qui sont en retard ou qui seront bientôt attendues du fournisseur. Ces espaces de travail ne sont pas utilisés pour effectuer les activités de réception connexes qui sont effectuées dans l’entrepôt. Ces activités sont effectuées à l’aide de pages des modules **Gestion des stocks** et **Gestion des entrepôts**. Le traitement des factures fournisseur doit être effectué à l’aide de l'espace de travail **Saisie de facture fournisseur** et les paiements doivent être effectués à l’aide de l'espace de travail **Paiements fournisseur**.  

Les articles suivants fournissent une vue d’ensemble des diverses étapes par lesquelles passe une commande fournisseur :

-   [Création de commandes fournisseur](purchase-order-creation.md)
-   [Approbation et confirmation de la commande fournisseur](purchase-order-approval-confirmation.md)
-   [Accusé de réception de marchandises et commandes fournisseur](product-receipt-against-purchase-orders.md)
-   [Vue d'ensemble des factures fournisseur](../../financials/accounts-payable/vendor-invoices-overview.md)

## <a name="types-of-purchase-orders"></a>Types de commandes fournisseur
Il existe trois types de CF. Lorsque vous créez une CF, vous devez indiquer le type. Vous pouvez définir un type de commande par défaut pour les nouvelles commandes sur la page **Paramètres d’approvisionnement**.

| Type de CF        | Description                                                                                                                                                                                                                                                                           |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Journal        | Utilisez ce type pour créer un brouillon de commande. Ce type n'a aucune incidence sur les quantités de stock et ne génère pas de transactions de stock. Les lignes du journal de CF ne sont pas incluses dans le calcul PDP/MRP.                                                                                                       |
| Commande fournisseur | Utilisez ce type pour créer des CF lorsque les commandes sont confirmées avec un fournisseur, et que les commandes sont traitées par l’intermédiaire de la réception et de la facturation avant que le paiement soit effectué au fournisseur. Ce type de CF est le plus courant.                                                                          |
| Commande retournée | Utilisez ce type en cas de retour de marchandises au fournisseur. Ce type de commande nécessite que vous spécifiez le numéro d’autorisation de retour de marchandise que le fournisseur vous attribue. Vous spécifiez le numéro de retour de marchandises dans l'onglet **Général** de la CF. Les lignes de commande doivent avoir des quantités négatives. |

## <a name="purchase-order-statuses"></a>Statuts de la commande fournisseur
Les CF incluent plusieurs champs d’état indiquant la progression de la commande. Tous ces champs sont visibles dans la vue **En-tête** de la commande et certains d'entre eux sont également visibles dans la vue d’ensemble de la grille de toutes les commandes. Le champ **État** affiche le statut des quantités de la commande. Les valeurs disponibles sont les suivantes :

-   **Commande en cours** : Les commandes ont été créées et des quantités figurent sur la commande.
-   **Reçue** : certaines des quantités ont été reçues, mais elles n’ont pas encore été facturées.
-   **Facturée** : la quantité totale sur la commande a été facturée. **Remarque :** si une commande a été *partiellement* facturée, ni le statut **Reçue** ni le statut **Facturée** n'est approprié. Par conséquent, la commande aura toujours le statut **Commande en cours**.
-   **Annulée** : une commande a été confirmée mais annulée ultérieurement. Par conséquent, cet état indique qu’il n'existe plus de quantités sur la commande.

Le champ **Statut du document** vous permet de passer rapidement en revue la progression de la commande en ce qui concerne les documents qui ont été traités. Il affiche le statut du document terminé le plus récemment pour la commande. Les valeurs disponibles sont les suivantes :

-   **Aucun** : aucun document n’a encore été traité pour la commande.
-   **Demande de renseignements sur les achats** : une demande de renseignements sur les achats a été générée et la commande est en attente de commentaires du fournisseur.
-   **Commande fournisseur** : la confirmation a été traitée dans la commande.
-   **Accusé de réception de marchandises** : l'accusé de réception de marchandises a été traité dans la commande.
-   **Facture** : une facture a été prise en compte avec la commande.

Le champ **Statut d’approbation** est utilisé lorsqu'une CF passe par un processus de révision ou un workflow. Les valeurs disponibles sont les suivantes :

-   **Brouillon**, **En cours de révision**, et **Rejetée** : ces statuts sont utilisés uniquement si un workflow d’approbation est utilisé pour la CF.
-   **Approuvée** : ce statut est affecté aux commandes qui ont terminé le workflow d’approbation. Les commandes créées sans l’aide d’un workflow d’approbation reçoivent le statut **Approuvée** immédiatement.
-   **Fait l'objet d'une révision externe** : ce statut est utilisé dans les scénarios où une demande de renseignements sur les achats est envoyée au fournisseur, afin que le fournisseur puisse confirmer les conditions de la CF. Ce statut est également utilisé dans le processus qui est initié par l'action **Demande de confirmation**. Pour ce processus, le fournisseur est invité à confirmer les conditions de la CF en se connectant à votre système et en inscrivant s’il confirme ou refuse la commande.
-   **Confirmée** : ce statut est attribué une fois que la commande a été confirmée. En général, cet état est le dernier état qui est affecté à une commande.


<a name="see-also"></a>Voir également :
--------

[Création de commandes fournisseur](purchase-order-creation.md)

[Approbation et confirmation de la commande fournisseur](purchase-order-approval-confirmation.md)

[Accusé de réception de marchandises et commandes fournisseur](product-receipt-against-purchase-orders.md)

[Vue d'ensemble des factures fournisseur](../../financials/accounts-payable/vendor-invoices-overview.md)




