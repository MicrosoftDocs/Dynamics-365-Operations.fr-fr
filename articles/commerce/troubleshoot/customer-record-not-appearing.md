---
title: Les enregistrements client ne s’affichent pas dans Commerce Headquarters
description: Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque les enregistrements client ne s’affichent pas immédiatement dans Commerce Headquarters.
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
ms.openlocfilehash: 5cdc96c9829be4d34e9346b2c99d300c2349bc41
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876543"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a>Les enregistrements client ne s’affichent pas dans Commerce Headquarters

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque les enregistrements client ne s’affichent pas immédiatement dans Commerce Headquarters.

## <a name="description"></a>Description

Lorsque vous créez un enregistrement client à l’aide du flux d’inscription dans la vitrine d’e-commerce, l’enregistrement client correspondant ne s’affiche pas immédiatement dans Commerce Headquarters.

## <a name="resolution"></a>Résolution

### <a name="disable-customer-creation-in-async-mode"></a>Désactiver la création de client en mode asynchrone

> [!IMPORTANT]
> Si vous désactivez la création de client asynchrone, les performances du système peuvent être affectées, car la création de chaque enregistrement produit une demande en temps réel à Commerce Headquarters. De plus, si Commerce Headquarters n’est pas opérationnel (par exemple, pendant les flux de maintenance), tout nouveau flux de création client produira des erreurs.

Pour désactiver la création de client en mode asynchrone dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage du magasin en ligne \> Profils de fonctionnalité**.
1. Si vous n’utilisez pas encore de profil de fonctionnalité pour votre canal en ligne, créez-en un.
1. Assurez-vous que l’option **Créer un client en mode asynchrone** est définie sur **Non**.
1. Accédez à **Commerce et vente au détail \> Canaux \> Magasins en ligne**.
1. Sélectionnez la boutique en ligne pour laquelle désactiver la création de clients asynchrones.
1. Sur l’onglet **Général**, assurez-vous que le champ **Profil de fonctionnalité** est défini sur le profil de fonctionnalité que vous utilisez pour votre canal en ligne.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un client B2C dans Commerce](../set-up-b2c-tenant.md)
