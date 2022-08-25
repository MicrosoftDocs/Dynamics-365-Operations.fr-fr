---
title: Produits et catégories manquants après la copie de l’environnement
description: Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque des produits et des catégories sont manquants après la copie d’un site d’un environnement à un autre ou dans le même environnement.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: d8df3f4cca6a7aaad98ffb7f2d284211a4f9589b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277904"
---
# <a name="products-and-categories-missing-after-environment-copy"></a>Produits et catégories manquants après la copie de l’environnement

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque des produits et des catégories sont manquants après la copie d’un site d’un environnement à un autre ou dans le même environnement.

## <a name="description"></a>Description

Une fois qu’un site a été copié d’un environnement à un autre, ou dans le même environnement, des produits et des catégories sont manquants du site. Les produits et catégories seront absents de la vitrine e-commerce et de l’onglet **Produits** du générateur de site Commerce.

## <a name="resolution"></a>Résolution

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a>Mapper le numéro d’unité opérationnelle du canal à un site nouvellement copié dans le générateur de site Commerce

Pour mapper le numéro d’unité opérationnelle du canal (OUN) à un site nouvellement copié dans le générateur de site Commerce, suivez ces étapes.

1. Sélectionnez le site nouvellement copié.
1. Sous **Paramètres de site**, sélectionnez **Canaux**.
1. À côté du nom du canal, sélectionnez les points de suspension (**...**), puis sélectionnez **Changer le canal du magasin en ligne**.
1. Dans la boîte de dialogue **Changer le canal du magasin en ligne**, sélectionnez le canal à mapper sur le site nouvellement copié, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer et publier**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Associer un site Dynamics 365 Commerce avec un canal en ligne](../associate-site-online-store.md)
