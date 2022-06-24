---
title: Produits et catégories manquants après la copie de l’environnement
description: Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque des produits et des catégories sont manquants après la copie d’un site d’un environnement à un autre ou dans le même environnement.
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
ms.openlocfilehash: 0c094f6da7756d2a6a3b80ebdb211d7b78148813
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851103"
---
# <a name="products-and-categories-missing-after-environment-copy"></a>Produits et catégories manquants après la copie de l’environnement

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque des produits et des catégories sont manquants après la copie d’un site d’un environnement à un autre ou dans le même environnement.

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
