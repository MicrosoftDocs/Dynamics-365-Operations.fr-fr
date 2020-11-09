---
title: Cartes de fidélité et points de fidélité
description: Cette rubrique décrit l'intégration des données sur les cartes de fidélité client et les points de récompense entre les applications Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 24ce08bb6cba9c74075151bafe0b07509fbdf73d
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3998012"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Cartes de fidélité et points de fidélité

[!include [banner](../../includes/banner.md)]



Les entreprises classent les clients et fournissent des services sophistiqués, basés sur les habitudes d'achat et les dépenses des clients. Dans la suite d'applications Microsoft Dynamics 365, Dynamics 365 Commerce possède l'infrastructure et les fonctions nécessaires pour faciliter et gérer les cartes de fidélité des clients, les points de récompense, les prix basés sur la fidélité et les expériences d'achat basées sur les récompenses. Lorsque les données sur les cartes de fidélité des clients et les points de récompense dans Commerce sont synchronisées avec le service Common Data, les applications basées sur des modèles dans Dynamics 365 peuvent utiliser ces données. Par exemple, les utilisateurs de Dynamics 365 Customer Service peuvent utiliser les données pour fournir les mêmes services sophistiqués via le service d'assistance.

## <a name="templates"></a>Modèles

| Applications Finance and Operations | Applications pilotées par modèle dans Dynamics 365 | Description  |
|-----------------------------|-----------------------------------|-------------|
| Carte de fidélité                | msdyn\_loyaltycards               | Ce modèle synchronise les informations concernant les cartes de fidélité des clients. |
| Points de récompense de fidélité       | msdyn\_loyaltyrewardpoints        | Ce modèle synchronise les informations concernant les points de fidélité des clients. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
