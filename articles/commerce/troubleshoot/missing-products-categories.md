---
title: Produits et catégories manquants après la copie de l’environnement
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque des produits et des catégories sont manquants après la copie d’un site d’un environnement à un autre ou dans le même environnement.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 4964b9623a91286d4f8260bcae7941feb48f8962
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022396"
---
# <a name="products-and-categories-missing-after-environment-copy"></a>Produits et catégories manquants après la copie de l’environnement

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque des produits et des catégories sont manquants après la copie d’un site d’un environnement à un autre ou dans le même environnement.

## <a name="description"></a>Description

Une fois qu’un site a été copié d’un environnement à un autre, ou dans le même environnement, des produits et des catégories sont manquants. Les produits et catégories ne sont pas présents dans la vitrine e-commerce ni dans l’onglet **Produits** du générateur de site Commerce.

## <a name="resolution"></a>Résolution

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a>Mapper le numéro d’unité opérationnelle du canal à un site nouvellement copié dans le générateur de site Commerce

Pour mapper le numéro d’unité opérationnelle du canal à un site nouvellement copié dans le générateur de site Commerce, procédez comme suit.

1. Sélectionnez le site nouvellement copié.
1. Sous **Paramètres du site**, sélectionnez **Canaux**.
1. À côté du nom du canal, sélectionnez les points de suspension (**...**), puis sélectionnez **Changer le canal de la boutique en ligne**.
1. Dans la boîte de dialogue **Changer le canal de la boutique en ligne**, sélectionnez le canal à mapper sur le site nouvellement copié, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer et publier**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Associer un site Dynamics 365 Commerce avec un canal en ligne](../associate-site-online-store.md)
