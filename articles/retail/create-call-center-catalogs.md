---
title: "Créer un catalogue de centre d'appels"
description: "Cet article fournit une vue d'ensemble du processus pour créer un catalogue destiné à un centre d'appels."
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
ms.custom: 16212
ms.assetid: c9d1b9df-82e8-4b3a-a13c-166df8b9718e
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 94ff6d74d4a11b3b04be6b69f85e778c3b45de92
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-call-center-catalog"></a>Créer un catalogue de centre d'appels

[!INCLUDE [banner](includes/banner.md)]

Cet article fournit une vue d'ensemble du processus pour créer un catalogue destiné à un centre d'appels. 

Dans un centre d'appels, vous pouvez utiliser les catalogues de produits vendus au détail pour identifier les produits que vous souhaitez proposer à vos clients. Les centres d'appels utilisent généralement des catalogues imprimés. La conception et la production d'un catalogue imprimé sont gérées en dehors de Microsoft Dynamics 365 for Retail. Toutefois, vous pouvez créer et stocker un format numérique d'un catalogue à l'aide des mêmes écrans que ceux que vous utilisez pour paramétrer les catalogues de vente au détail en ligne. Avant de créer un catalogue, vous devez paramétrer des assortiments de produits et affecter les assortiments à un centre d'appels. Vous ajoutez ensuite les produits au catalogue en sélectionnant des produits de ces assortiments. Une fois les produits ajoutés au catalogue, et le catalogue terminé, vous devez valider le catalogue pour vérifier les données. Vous devez ensuite envoyer le catalogue pour révision et approbation. Une fois le catalogue approuvé, il peut être publié. Lorsqu'un catalogue de centre d'appel est créé, vous pouvez prendre un instantané des données du catalogue au moment de la publication du catalogue. Cette fonctionnalité d'instantané permet d'accéder à une version spécifique du catalogue, même si le catalogue est modifié et mis à jour ultérieurement. Les catalogues de centre d'appels peuvent également être paramétrés pour inclure les fonctionnalités optionnelles suivantes.

-   **Codes source** - Ces codes permettent de suivre la réponse du client à des envois de catalogues particuliers.
-   **Produits gratuits** – Ces produits sont inclus dans la commande d'un client sans frais supplémentaires. Ces produits sont automatiquement ajoutés à la commande lorsque le code source du catalogue est entré dans la commande.
-   **Scripts** – Textes qu'un collaborateur du centre d'appels lit à un client lorsqu'une commande client est créée. Les scripts peuvent inclure des salutations ou des suggestions d'achat.
-   **Articles de vente de gamme supérieure/croisée** - Articles affichés comme suggestion lorsqu'un produit spécifique est ajouté à la commande.

Ces options doivent être définies avant l'approbation et la publication du catalogue.

## <a name="prerequisites"></a>Logiciels requis
Les tâches suivantes doivent être effectuées avant de commencer :

-   Paramétrez des produits et des assortiments de produits.
-   Paramétrez les produits vendus au détail.
-   Paramétrez un assortiment.
-   Créez un centre d'appels.
-   Configurez un centre d'appels.
-   Ajoutez le centre d'appels à une hiérarchie d'organisation.
-   Créez ou modifiez une hiérarchie d'organisation.

## <a name="create-a-catalog"></a>Création d'un catalogue
Vous devez d'abord créer un catalogue, ajouter des produits au catalogue, puis revoir et mettre à jour les attributs des produits.

## <a name="validate-the-catalog"></a>Validation du catalogue
Après avoir terminé le paramétrage du catalogue, vous devez le valider. Le processus de validation vérifie que les données requises pour les attributs de canal et les attributs de produit sont complètes et valides, et que le catalogue peut être publié.

## <a name="submit-the-catalog-for-review-and-approval"></a>Envoi du catalogue pour révision et approbation
Une fois le catalogue validé, vous pouvez le soumettre pour révision et approbation. Un catalogue doit être approuvé pour pouvoir être publié. Vous pouvez configurer un workflow pour que les catalogues soient automatiquement approuvés ou demander une approbation manuelle.

## <a name="optional-add-source-codes-free-products-and-scripts"></a>Facultatif : Ajoutez des codes source, des produits gratuits et des scripts
Vous pouvez également ajouter les articles suivants à un catalogue de centre d'appels. Ces articles sont facultatifs.

-   **Codes source** : ils peuvent être utilisés par les sociétés qui fournissent des catalogues imprimés pour suivre la réponse des clients à des catalogues particuliers. Les codes source sont souvent imprimés au dos d'un catalogue et sont entrés dans la commande client lorsqu'un client effectue un achat. Pour ajouter un code source au catalogue, vous devez d'abord créer un marché cible. Le marché cible est généralement mis en correspondance avec une liste de publipostage détenue ou louée.
-   **Produits gratuits** : ce sont des articles en promotion qui sont ajoutés gratuitement à la commande client lorsque le catalogue est référencé.
-   **Scripts** : ils permettent de guider les interactions du collaborateur avec les clients dans le contexte d'un catalogue ou d'un produit dans un catalogue.

## <a name="publish-the-catalog"></a>Publication du catalogue
En publiant un catalogue pour un centre d'appels, vous finalisez les informations sur les produits dans le catalogue. La publication indique également que le catalogue est prêt pour les actions supplémentaires à exécuter. Par exemple, vous pouvez créer un catalogue imprimé. Vous pouvez publier vos catalogues manuellement ou utiliser un processus de traitement par lots pour publier selon un programme. Pour être publié, un catalogue doit être validé et approuvé. Pour modifier le catalogue après sa publication, vous pouvez retirer le catalogue puis le republier.




