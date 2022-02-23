---
title: Vente et retourner des produits ne faisant pas partie de l'assortiment d'un magasin
description: Avec Dynamics 365 Commerce, vous pouvez vendre et renvoyer les produits en dehors des assortiments.
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 86c6ecf9ef67ca3ac4ed3c44d930acaa965112b6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412349"
---
# <a name="sell-and-return-products-that-arent-part-of-a-stores-assortment"></a>Vente et retourner des produits ne faisant pas partie de l'assortiment d'un magasin

[!include [banner](includes/banner.md)]

Un scénario courant pour un détaillant est de vendre des produits à ses clients ou d'accepter des retours de ses clients même s'il ne propose pas les produits spécifiques dans son magasin (autrement dit, les produits ne sont pas assortis au magasin).

Voici quelques scénarios classiques :

+ Un détaillant ne propose pas tous ses produits dans un magasin spécifique. Les articles restants sont stockés dans l'entrepôt. L'associé du magasin aide le client en recherchant ou en parcourant les produits dans l'entrepôt, les ajoute au chariot et procède à la validation en sélectionnant un mode de livraison, par exemple expédier le produit une adresse à partir de l'entrepôt ou laisser le client récupérer le produit dans le magasin actuel ou dans un autre magasin.
+ Un détaillant ne propose pas des produits spécifiques dans le magasin ou n'en a pas en stock dans le magasin où le client s'est rendu, mais les produits sont disponibles dans d'autres magasins. L'associé du magasin aide le client en recherchant ou en parcourant les produits dans l'autre magasin, les ajoute au chariot et procède à la validation en sélectionnant un mode de livraison.
+ Un détaillant a plusieurs magasins dans et autour d'une ville ou d'un code postal spécifique et ne souhaite pas obliger les clients à retourner les produits dans le magasin d'achat. À la place, les clients peuvent retourner les produits dans n'importe quel magasin.

Ces scénarios courants sont disponibles aux détaillants qui utilisent Commerce. Avec Commerce, vous pouvez :

+ Rechercher ou parcourir les produits dans d'autres magasins.
+ Rechercher ou parcourir tous les produits lancés.
+ Créer des transactions ou des commandes client avec paiement comptant sans livraison.
+ Sélectionner les options de livraison pour les commandes client.
+ Récupérer les produits dans le magasin actuel ou un autre magasin.
+ Annuler une commande dans le magasin actuel ou un autre magasin.
+ Retourner une commande avec ou sans l'accusé de réception dans le magasin actuel ou un autre magasin.
