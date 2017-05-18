---
title: Catalogues de centre d&quot;appels
description: "Cet article décrit la fonctionnalité spécifique au centre d&quot;appel des catalogues dans Microsoft Dynamics 365 for Operations."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: e495d5a94e714eb42e04eb12fbd551fa2f552c1f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/26/2017


---

# <a name="call-center-catalogs"></a>Catalogues de centre d'appels

[!include[banner](includes/banner.md)]


Cet article décrit la fonctionnalité spécifique au centre d'appel des catalogues dans Microsoft Dynamics 365 for Operations.

Dans un centre d'appels, vous pouvez utiliser les catalogues de produits vendus au détail pour identifier les produits que vous souhaitez proposer à vos clients. Les centres d'appels utilisent généralement des catalogues imprimés. La conception et la production d'un catalogue imprimé sont gérées en dehors de Dynamics 365 for Operations. Toutefois, vous pouvez créer et stocker un format numérique d'un catalogue dans le module Commerce et vente au détail de Dynamics 365 for Operations à l'aide des mêmes pages que celles que vous utilisez pour paramétrer les catalogues de vente au détail en ligne. Avant de créer un catalogue, vous devez paramétrer des assortiments de produits et affecter les assortiments à un centre d'appels. Vous ajoutez ensuite les produits au catalogue en sélectionnant des produits de ces assortiments. Une fois les produits ajoutés au catalogue, et le catalogue terminé, vous devez valider le catalogue pour vérifier les données. Vous devez ensuite envoyer le catalogue pour révision et approbation. Une fois le catalogue approuvé, il peut être publié. Lorsqu'un catalogue de centre d'appel est créé, vous pouvez prendre un instantané des données du catalogue au moment de la publication du catalogue. Cette fonctionnalité d'instantané permet d'accéder à une version spécifique du catalogue, même si le catalogue est modifié et mis à jour ultérieurement. Les catalogues de centre d'appels peuvent également être paramétrés pour inclure les fonctionnalités optionnelles suivantes :

-   **Codes source** - Les codes source permettent de suivre la réponse du client à des envois de catalogues spécifiques.
-   **Produits gratuits** – Ces produits peuvent être inclus dans la commande d'un client sans frais supplémentaires. Ces produits sont automatiquement ajoutés à une commande lorsque le code source du catalogue est entré dans la commande.
-   **Scripts** – Les scripts sont des textes qu'un collaborateur du centre d'appels lit à un client lorsqu'une commande client est créée. Les scripts peuvent inclure des salutations ou des suggestions d'achat.
-   **Mise en page** – Une mise en page capture la position de page des produits dans le catalogue imprimé. Ces informations sont utilisées pour l'état d'analyse d'une zone de catalogue.





