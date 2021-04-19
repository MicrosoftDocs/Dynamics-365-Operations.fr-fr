---
title: Les articles en rupture de stock peuvent être achetés
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider les clients à ajouter des articles en rupture de stock à leur panier et procéder au paiement.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: af44def901d3aa7d4b24ab6abfac60d066a8d1a3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801745"
---
# <a name="items-without-inventory-can-be-checked-out"></a>Les articles en rupture de stock peuvent être achetés

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider les clients à ajouter des articles en rupture de stock à leur panier et procéder au paiement.

## <a name="description"></a>Description

Les utilisateurs peuvent ajouter un article à leur panier, même s’il n’y a pas de stock disponible dans le magasin, puis accéder à la page de paiement.

## <a name="resolution"></a>Résolution

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a>Activer la propriété Afficher les erreurs de rupture de stock dans le générateur de site Commerce

Pour activer la propriété **Afficher les erreurs de rupture de stock** dans le générateur de site Commerce, procédez comme suit.

1. Sélectionnez le site sur lequel vous travaillez.
1. Dans le volet de navigation de gauche, sélectionnez **Pages**.
1. Sélectionnez **CartPage** pour l’ouvrir.
1. Sélectionnez l’emplacement **Panier 1**, sélectionnez **Modifier**, puis, dans le volet des propriétés, cochez la case **Afficher les erreurs de rupture de stock**.
1. Enregistrez et publiez la page.

## <a name="additional-resources"></a>Ressources supplémentaires

[Appliquer les paramètres de stock](../inventory-settings.md)

[Calculer la disponibilité des stocks pour les canaux de vente au détail](../calculated-inventory-retail-channels.md)

[Configurer des marges de stock et des niveaux de stock](../inventory-buffers-levels.md)
