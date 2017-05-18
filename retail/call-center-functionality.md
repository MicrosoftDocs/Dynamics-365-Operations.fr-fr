---
title: "Fonctionnalité de centre d&quot;appels"
description: "Cet article fournit une vue d&quot;ensemble de la fonctionnalité de vente des centres d&quot;appels dans Microsoft Dynamics 365 for Operations."
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
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: b93f406b818655399195bfd5a8c12e939c9a9c77
ms.contentlocale: fr-fr
ms.lasthandoff: 04/26/2017


---

# <a name="call-center-functionality"></a>Fonctionnalité de centre d'appels

[!include[banner](includes/banner.md)]


Cet article fournit une vue d'ensemble de la fonctionnalité de vente des centres d'appels dans Microsoft Dynamics 365 for Operations.

Le module Commerce et vente au détail de Microsoft Dynamics AX prend en charge les centres d'appels comme type de canal de vente au détail. Dans un centre d'appels, les collaborateurs prennent les commandes des clients par téléphone et créent les commandes client. La fonctionnalité de centre d'appels inclut les fonctionnalités conçues pour faciliter la prise de commandes par téléphone et la gestion du service client via le processus d'exécution de commande. Par exemple, les collaborateurs de centre d'appels peuvent entrer des informations de paiement directement dans la commande client, et peuvent afficher un résumé détaillé des frais et des paiements avant d'envoyer la commande. Les collaborateurs disposent également d'options pour contrôler la tarification, et peuvent accéder à diverses données sur les clients, les produits, et les prix à partir de la page **Commande client**. En outre, les centres d'appel disposent d'une fonctionnalité améliorée de suivi de l'historique client et du statut des commandes. Chaque centre d'appels peut avoir ses propres utilisateurs, modes de paiement, groupes de prix, dimensions financières, et modes de livraison. Vous pouvez configurer ces options lorsque vous créez les centres d'appels. Vous pouvez également utiliser la page **Centre d'appels** pour activer ou désactiver les groupes de fonctions suivants, qui sont uniques aux centres d'appels :

-   **Achèvement de commande** – Ce groupe inclut les fonctionnalités liées aux paiements et à l'achèvement des commandes sur la page **Commande client**.
-   **Vente directe** – Ce groupe inclut les fonctionnalités associées aux codes sources, aux scripts, et aux demandes de catalogue.

Une fois que vous avez activé ces fonctionnalités dans les paramètres du centre d'appels, elles sont disponibles sur la page **Commande client** pour les utilisateurs associés au centre d'appels. La plupart de ces fonctions requièrent un paramétrage supplémentaire avant d'être utilisées. Avant que les utilisateurs puissent créer des commandes de centre d'appels, vous devez ajouter ces utilisateurs au centre d'appels en tant qu'utilisateurs du centre d'appels. Cette étape active la configuration et la fonctionnalité spécifiques au canal de centre d'appels. Voici quelques exemples de fonctionnalités qui deviennent disponibles :

-   La vente guidée fournit des options de configuration pour les scripts de téléventes et les images de produits, afin d'aider et guider les commis aux ventes lors de la prise de commandes.
-   Les commandes ne peuvent pas être bouclées tant que les commis aux ventes n'ont pas capturé au moins un mode de paiement.
-   Les règles de vente de gamme supérieure et de vente croisée peuvent être configurés de sorte à inviter les commis aux vente à promouvoir des produits spécifiques auprès des clients.
-   Les commis aux ventes peuvent capturer le code source pour le catalogue à partir duquel un client passe sa commande.
-   Les commis aux ventes peuvent ajouter les coupons d'un détaillant à une commande.
-   Les commis aux ventes peuvent vendre des programmes périodiques.
-   Les commandes peuvent être mise en attente manuellement ou automatiquement, de sorte à indiquer que des recherches complémentaires sont nécessaires avant que la commande puisse être traitée.





