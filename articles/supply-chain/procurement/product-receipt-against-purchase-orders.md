---
title: "Accusé de réception de marchandises et commandes fournisseur"
description: "Cette rubrique décrit les différentes options d'enregistrement des marchandises comme étant reçues."
author: FrankDahl
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 93113
ms.assetid: d4ec3e86-fce2-4546-911b-e0acf64c8887
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 09432d278c51301f8b01fef8cbd3353af75a88f3
ms.openlocfilehash: fea28da19c0aa1e9083091d0693404e0d8cb173c
ms.contentlocale: fr-fr
ms.lasthandoff: 12/04/2018

---

# <a name="product-receipt-against-purchase-orders"></a>Accusé de réception de marchandises et commandes fournisseur

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Cette rubrique décrit les différentes options d'enregistrement des marchandises comme étant reçues.

L'accusé de réception de machandises est le processus permettant d'enregistrer que les produits commandés ont été reçus, afin que les lignes de commande fournisseur (CF) puissent ensuite être traitées pour la facturation. Dans certains cas, les produits passent par le préenregistrement, où des informations supplémentaires du fournisseur sont enregistrées avant que les produits soient réceptionnés. Lors de l’arrivée des produits, ils sont tout d’abord marqués comme **Enregistrés**. Les produits peuvent ensuite passer par des processus supplémentaires, tels que la gestion de la qualité, avant d'être enfin marqués comme **Reçus**.

## <a name="preregistration-asn"></a>Préenregistrement (APE)
Les fournisseurs peuvent partager des informations sur les produits qui seront livrés. Dans ce cas, vous pouvez préenregistrer les produits pour enregistrer ces informations avant que les produits soient réceptionnés. En préenregistrant les produits, vous réduisez la quantité de travail qui est nécessaire lors de la réception et l’enregistrement d’articles. Les fournisseurs peuvent fournir des informations sur les produits par voie électronique via un avis préalable d'expédition (APE) qui est alors enregistré automatiquement dans le système. Les informations de l’APE incluent la quantité de produits qui sera livrée et la date à laquelle ils seront livrés. L’APE peut-être également inclure des informations telles que les numéros de série ou de lot. L’enregistrement de l'APE se produit dans le module **Gestion du transport**.

## <a name="registration"></a>Enregistrement
L'enregistrement de l'accusé de réception de marchandises se produit souvent sur les quais d'un entrepôt. Il est effectué à l’aide d’un appareil portable ou par l’intermédiaire de journaux d’arrivées. Vous pouvez manuellement enregistrer l'accusé de réception à l’aide de l'action **Enregistrement** sur la page **Commande fournisseur**. Dans les deux cas, les produits sont marqués comme **Enregistrés**. Notez que les produits ne sont pas encore marqués comme **Reçus**.  

Les produits qui sont reçus dans un entrepôt peuvent passer par contrôle de la qualité avant d'être rangés dans le stock. Les ordres de qualité ou les ordres de contrôle peuvent servir à effectuer des inspections de qualité. Si des ordres de qualité sont utilisés, vous pouvez configurer le processus pour bloquer temporairement des produits via une réservation pendant qu’ils sont inspectés. Si des ordres de contrôle sont utilisés, les produits sont déplacés vers un autre entrepôt pour l’inspection. Cet entrepôt est appelé l'entrepôt de contrôle. Dans les deux processus d’inspection de la qualité, certaines des marchandises peuvent être mises au rebut, parce qu’elles ne répondent pas aux attentes de qualité ou parce que l’inspection de la qualité implique des tests destructifs d’échantillons de produits.

## <a name="product-receipt"></a>Accusé de réception de marchandises
Le plus souvent, l'action **Accusé de réception de marchandises** sur la page **Commandes fournisseur** sert à marquer des produits comme **Reçus** sur la commande fournisseur. La page **Validation de l'accusé de réception de produits** comporte diverses options pour la quantité qui est prises en compte comme reçue. Par exemple, vous pouvez définir le champ **Quantité** sur **Quantité commandée** ou **Quantité à recevoir maintenant**. Sinon, si un processus d’arrivée à l'entrepôt a été utilisé, vous définirez souvent ce champ sur **Quantité enregistrée**. Vous pouvez modifier les quantités sur chaque ligne de commande qui seront marquées comme **Reçues**, pour tenir compte de toutes les différences, par exemple de livraison excédentaire et de livraison incomplète. Lors de la réception des marchandises, vous devez spécifier un identificateur de l'accusé de réception de marchandises, qui fait généralement référence au bon de livraison du fournisseur. Cet identificateur est nécessaire pour la comptabilité, car il permet de contrôler ou d'auditer les bons de livraison des fournisseurs par rapport à ce qui a été reçu, et le stock et les frais comptabilisés.  

Des CF peuvent être créés pour les marchandises qui ne sont pas destinées au stock mais qui sont considérées comme une dépense. Cette catégorie comprend les lignes de commande où les marchandises sont marquées comme **Non stockés** par leur groupe de modèles de stock et les lignes qui utilisent des catégories d’approvisionnement. Dans ce cas, les articles ne peuvent pas passer par l'enregistrement des arrivées et l’accusé de réception dans l’entrepôt. Au lieu de cela, l'action **Accusé de réception de marchandises** est utilisée pour enregistrer la réception directement sur la CF et l’accusé de réception est basé sur la quantité commandée, pas sur une quantité enregistrée.  

Vous pouvez créer des lignes de CF où l'option **Nouvelle immobilisation** est activée. Cette option indique que l’achat doit être considéré comme une immobilisation au lieu du stock. Dans ce cas, les règles de détermination des immobilisations qui ont été configurées déterminent si l’achat du produit ou la catégorie dépasse des seuils spécifiques et doit par conséquent être prises en compte en tant qu’actif et passer par la gestion des immobilisations. Les achats peuvent également être effectués avec une immobilisation existante. Dans ce cas, le montant est ajusté selon le cas.  

Vous pouvez sélectionner plusieurs commandes et traiter la réception de toutes ces commandes ensemble. Cette approche n’est pas très souvent utilisée, mais vous pouvez l’utiliser si un fournisseur a consolidé des expéditions pour vous en un seul chargement. Lors de la réception de la marchandises à l’achat, il existe une fonction pour effectuer des mises à jour récapitulatives. Les mises à jour récapitulatives vous permettent de valider un bon de livraison unique du fournisseur plusieurs CF.  

Les CF peuvent être créées à partir d’une commande client où l'option **Livraison directe** a été sélectionnée. Si la livraison directe est utilisée, les marchandises n'arrivent jamais dans votre entrepôt mais sont livrés directement du fournisseur au client. Dans ce cas, la réception est en général enregistrée directement sur la CF. La réception peut être faite automatiquement, notamment grâce à l’intégration de l'échange de données informatisé (EDI) avec le fournisseur. Sinon, si la CF est une CF intersociétés, Microsoft Dynamics 365 for Finance and Operations automatise la réception de la commande client intersociétés lors de l’expédition. Lors de la livraison directe est utilisée, les marchandises sont toujours prises en compte en tant que stock, même si elles n’arrivent pas physiquement dans l’entrepôt. Par conséquent, lorsque la réception de marchandises est enregistrée sur la CF, la commande client est automatiquement mis à jour avec un bon de livraison, afin que les modifications globales d’inventaire soient à 0 (zéro). Dans les scénarios de livraison directe, vous ne devez pas exiger de préenregistrement. Si vous utilisez des entrepôts qui sont activés pour la gestion des entrepôts, vous pouvez contourner l’obligation d’enregistrement des plaques d’immatriculation en spécifiant un entrepôt virtuel à la place. Vous spécifiez cet entrepôt dans le champ **Entrepôt des livraisons directes** sur le produit. 

Une fois l’accusé de réception de marchandises traitée sur la CF, le statut de la CF est défini sur **Reçue** pour indiquer que la facture peut être traitée pour la commande. Vous pouvez consulter les détails sur les marchandises qui ont déjà été reçues à l’aide de la page **Journaux d'accusés de réception de marchandises**.  

Vous pouvez accéder à cette page à partir du groupe d'actions **Réception** sur la page **Commande fournisseur**. Les informations contenues dans les journaux incluent des détails sur les quantités, les dates et les dimensions.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Vue d'ensemble des commandes fournisseur](purchase-order-overview.md)

[Création de commandes fournisseur](purchase-order-creation.md)

[Approbation et confirmation de la commande fournisseur](purchase-order-approval-confirmation.md)

[Vue d'ensemble des factures fournisseur](../../financials/accounts-payable/vendor-invoices-overview.md)




