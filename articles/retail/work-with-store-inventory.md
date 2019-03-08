---
title: Gestion des stocks du magasin
description: Cette rubrique décrit les types de documents qui peuvent être utilisés pour gérer le stock.
author: rubencdelgado
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 02f8afbe3bb6f94c66a8b5aa02531c219adc3963
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "339232"
---
# <a name="store-inventory-management"></a>Gestion des stocks du magasin

[!include [banner](includes/banner.md)]

Cette rubrique décrit les types de documents qui peuvent être utilisés pour gérer le stock.

Les types de documents suivants peuvent être utilisés pour gérer le stock de votre organisation.

Lors de l'utilisation du stock dans Dynamics 365 for Retail et en utilisant l'application du PDV, il est important de noter que le PDV propose un support limité pour les dimensions de stock et certains types d'articles en stock.  

La solution du PDV ne prend pas en charge les configurations d'article suivantes :
- Les articles de la nomenclature (hormis les produits de kit, qui utilisent certains composants du cadre de la nomenclature)
- Articles en poids variable
- Articles contrôlés par lots

L'application du PDV ne prend actuellement pas en charge les dimensions de suivi suivantes dans le PDV :
- Dimension de suivi par lots
- Dimension du propriétaire

La solution pour PDV offre un support limité pour les dimensions suivantes. Le support limité indique que le PDV peut transférer certaines de ces dimensions par défaut dans les transactions de stock automatiquement basées sur la configuration de l'entrepôt/du magasin. Le PDV ne prendra pas intégralement en charge les dimensions si une transaction commerciale est manuellement saisie dans l'ERP. 

- Entrepôt
- Plaque d'immatriculation (applicable uniquement quand **Utiliser les processus de gestion des entrepôts** a été activée sur l'article et l'entrepôt de stockage)
- Numéro de série
- Statut du stock

> [!NOTE]
> Toutes les organisations doivent tester les configurations d'article via le PDV en développement ou les environnements de test avant de les déployer en production. Testez vos articles en effectuant des ventes cash and carry régulièrement en créant et en transférant les commandes client (le cas échéant) via le POS avec vos articles. Les tests doivent inclure l'exécution des processus de validation des relevés dans votre environnement test et la vérification qu'il n'y a pas de problème.
> La configuration des articles de manière non prise en charge par l'application du PDV, sans tests appropriés, peut entraîner l'échec du processus de validation des relevés en production sans méthode facile pour corriger les problèmes. Des personnalisations du partenaire ou du client de l'application peuvent être envisagées pour permettre la réussite de ces processus de validation. Si des personnalisations ne sont pas nécessaires, l'organisation doit s'assurer que la configuration de produit de vos produits a été faite de façon compatible avec l'application de PDV standard/création des commandes/processus de validation des relevés.

## <a name="purchase-orders"></a>Commandes fournisseur

Les commandes fournisseur sont créées au siège social. Si un entrepôt de détail est indiqué dans l'en-tête de la commande fournisseur, la commande peut être reçue au magasin à l'aide de Modern POS (MPOS) ou de Cloud POS dans Microsoft Dynamics 365 for Retail. Une fois entrées, les quantités reçues au magasin peuvent être sauvegardées localement pour des modifications ultérieures. Les quantités peuvent aussi être validées et envoyées au siège social. Au siège social, les quantités qui ont été reçues au magasin sont affichées dans Dynamics 365 for Retail, dans le champ **Recevoir maintenant** de la commande fournisseur.

## <a name="transfer-orders"></a>Ordres de transfert

Un ordre de transfert peut spécifier qu'un magasin particulier est un emplacement à partir duquel les articles peuvent être expédiés. Dans ce cas, l'ordre de transfert s'affiche au magasin comme une requête de prélèvement dans MPOS ou Cloud POS. Après avoir été prélevées, les quantités demandées sont validées et envoyées au siège social. Au siège social, les quantités qui ont été prélevées au magasin sont affichées dans Dynamics 365 for Retail, dans le champ **Ignorer maintenant** de l'ordre de transfert. Un ordre de transfert peut spécifier qu'un magasin particulier est un emplacement vers lequel les articles peuvent être expédiés. Dans ce cas, l'ordre de transfert s'affiche au magasin comme une requête de réception dans MPOS ou Cloud POS. Une fois entrées, les quantités reçues au magasin peuvent être sauvegardées localement pour des modifications ultérieures. Les quantités peuvent aussi être validées et envoyées au siège social. Au siège social, les quantités qui ont été reçues au magasin sont affichées dans Dynamics 365 for Retail, dans le champ **Recevoir maintenant** de l'ordre de transfert.

## <a name="stock-counts"></a>Inventaires

Les inventaires peuvent être planifiés ou non planifiés. Les inventaires planifiés sont engagés par le siège social, qui spécifie les articles à inventorier. Le siège social crée un document d'inventaire qui peut être reçu au magasin, où les quantités du stock réel et disponible sont entrées dans MPOS ou Cloud POS. Les inventaires non planifiés sont effectués dans un magasin et les quantités de stock disponible réelles sont mises à jour dans MPOS ou Cloud POS. Contrairement aux inventaires planifiés, les inventaires non planifiés n'ont pas de liste prédéfinie d'articles. Lorsqu'un inventaire de l'un ou l'autre type est terminé, il est validé et envoyé au siège social. Au siège social, le nombre est contrôlé et validé.

## <a name="inventory-lookup"></a>Recherche de stock

La quantité actuelle disponible de produits pour plusieurs magasins et entrepôts peut être affichée dans la page Recherche de stock. En plus de la quantité actuelle disponible, les futures quantités disponibles à la vente peuvent être affichées pour chaque magasin individuel. Pour ce faire, sélectionnez le magasin dont vous souhaitez afficher les quantités disponibles à la vente, puis cliquez sur **Afficher la disponibilité du magasin**.
