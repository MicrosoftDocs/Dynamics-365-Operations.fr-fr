---
title: Passer rapidement des commandes de site Web B2B
description: Cet article décrit les fonctionnalités de Microsoft Dynamics 365 Commerce qui permettent aux utilisateurs de sites interentreprises (B2B) de passer rapidement des commandes groupées et répétées.
author: ShalabhjainMSFT
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.23
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: a153be1da43b63e8d29d6ece3dcbf47d5bbec487
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275118"
---
# <a name="place-b2b-website-orders-quickly"></a>Passer rapidement des commandes de site Web B2B

[!include [banner](../../includes/banner.md)]

Cet article décrit les fonctionnalités de Microsoft Dynamics 365 Commerce qui permettent aux utilisateurs de sites interentreprises (B2B) de passer rapidement des commandes groupées et répétées.

Les sites e-commerce B2B Dynamics 365 Commerce permettent aux utilisateurs d’effectuer des opérations standard telles que la découverte de nouveaux produits via la recherche et la navigation, l’affichage des détails du produit, l’ajout d’articles au panier et le paiement. Cependant, alors que les clients des sites business-to-consumer (B2C) commandent généralement des articles en petites quantités et ne les commandent qu’une seule fois, les clients B2B commandent généralement des articles en grande quantité et les recommandent plusieurs fois. Parce que ces clients savent généralement exactement quels articles ils veulent acheter, ils sautent souvent la phase de découverte du produit et passent directement à la commande. Pour répondre aux besoins de ces clients, les sites e-commerce Commerce B2B offrent diverses fonctionnalités qui les aident à passer des commandes rapidement.

## <a name="bulk-order-by-item-number"></a>Commande groupée par numéro d’article

Les sites e-commerce B2B permettent aux utilisateurs du site d’ajouter des articles au panier en saisissant les numéros d’articles des produits ainsi que la quantité souhaitée.

L’illustration suivante montre un exemple de saisie rapide de commande par numéro d’article de produit.

![Saisie rapide des commandes par numéro d’article du produit.](../media/QuickAddByItem.png)

## <a name="bulk-order-by-variant"></a>Commande groupée par variante

Les sites e-commerce B2B de Commerce permettent aux utilisateurs du site d’ajouter rapidement différentes variantes du même produit dans une vue unique qui affiche la disponibilité des stocks par taille, couleur et style. De plus, les utilisateurs du site peuvent facilement entrer la même quantité pour tous les produits en stock en sélectionnant **Saisir toutes les quantités**.

L’illustration suivante montre un exemple de saisie rapide de commande dans laquelle la fonctionnalité "saisir toutes les quantités" est utilisée.

![Saisie de commande rapide qui utilise la fonctionnalité "saisir toutes les quantités".](../media/MatrixView.png)

## <a name="use-order-templates-for-quick-order-entry"></a>Utilisez des modèles de commande pour une saisie rapide des commandes

Les acheteurs sur les sites Web B2B commandent souvent des articles spécifiques ensemble. Par exemple, si vous passez des commandes pour un chantier de construction, vous voudrez peut-être commander ensemble des chemises, des vestes, des pantalons, des chaussures et des chapeaux. Si vous passez des commandes pour un hôpital, où les médecins, les infirmières et le personnel de nettoyage ont des uniformes différents, vous souhaiterez peut-être regrouper chaque type d’uniforme pour faciliter la commande. Pour ces types de scénarios, les sites Commerce B2B permettent de créer des modèles de commande. Les utilisateurs du site peuvent créer n’importe quel nombre de modèles personnalisés, puis commander tout ou partie des éléments de ces modèles selon leurs besoins.

L’illustration suivante montre un exemple de modèle de commande.

![Exemple d’un modèle de commande.](../media/OrderTemplateHeader.png)

L’illustration suivante présente un exemple de la vue Détails d’un modèle de commande.gabarit

![Exemple de vue détaillée d’un modèle de commande.](../media/OrderTemplateLines.png)

## <a name="reorder-from-order-history"></a>Réorganiser à partir de l’historique des commandes

Les sites e-commerce B2B permettent aux utilisateurs du site de commander rapidement des articles à partir de leur historique de commandes. Les utilisateurs du site peuvent soit acheter des articles sélectionnés à partir de leur historique de commandes, soit ajouter tous les articles précédemment achetés au panier.

L’illustration suivante montre un exemple de l’historique des commandes d’un utilisateur et les options permettant de réorganiser les articles à partir de celui-ci.

![Réorganisation à partir de l’historique des commandes.](../media/Reorder.png)

Cet article a décrit quelques-unes des façons dont les sites Commerce B2B aident les utilisateurs à trouver, commander et réorganiser rapidement les produits qu’ils souhaitent. D’autres fonctionnalités sont en cours de développement pour simplifier davantage le processus de capture des commandes groupées.
