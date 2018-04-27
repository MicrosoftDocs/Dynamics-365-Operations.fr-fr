---
title: Catalogues de centre d'appels
description: "Cet article décrit la fonctionnalité spécifique au centre d'appel des catalogues dans Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7be87496ceaea2d1d5f97a5cc17e50dcddbaf33d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="call-center-catalogs"></a>Catalogues de centre d'appels

[!INCLUDE [banner](includes/banner.md)]

Cet article décrit la fonctionnalité spécifique au centre d'appel des catalogues dans Microsoft Dynamics 365 for Retail.

Dans un centre d'appels, vous pouvez utiliser les catalogues de produits vendus au détail pour identifier les produits que vous souhaitez proposer à vos clients. Les centres d'appels utilisent généralement des catalogues imprimés. La conception et la production d'un catalogue imprimé sont gérées en dehors de Dynamics 365 for Retail. Toutefois, vous pouvez créer et stocker un format numérique d'un catalogue à l'aide des mêmes pages que celles que vous utilisez pour paramétrer les catalogues de vente au détail en ligne. Avant de créer un catalogue, vous devez paramétrer des assortiments de produits et affecter les assortiments à un centre d'appels. Vous ajoutez ensuite les produits au catalogue en sélectionnant des produits de ces assortiments. Une fois les produits ajoutés au catalogue, et le catalogue terminé, vous devez valider le catalogue pour vérifier les données. Vous devez ensuite envoyer le catalogue pour révision et approbation. Une fois le catalogue approuvé, il peut être publié. Lorsqu'un catalogue de centre d'appel est créé, vous pouvez prendre un instantané des données du catalogue au moment de la publication du catalogue. Cette fonctionnalité d'instantané permet d'accéder à une version spécifique du catalogue, même si le catalogue est modifié et mis à jour ultérieurement. Les catalogues de centre d'appels peuvent également être paramétrés pour inclure les fonctionnalités optionnelles suivantes :

-   **Codes source** - Les codes source permettent de suivre la réponse du client à des envois de catalogues spécifiques.
-   **Produits gratuits** – Ces produits peuvent être inclus dans la commande d'un client sans frais supplémentaires. Ces produits sont automatiquement ajoutés à une commande lorsque le code source du catalogue est entré dans la commande.
-   **Scripts** – Les scripts sont des textes qu'un collaborateur du centre d'appels lit à un client lorsqu'une commande client est créée. Les scripts peuvent inclure des salutations ou des suggestions d'achat.
-   **Mise en page** – Une mise en page capture la position de page des produits dans le catalogue imprimé. Ces informations sont utilisées pour l'état d'analyse d'une zone de catalogue.





