---
title: Cartes de fidélité et points de fidélité
description: Cette rubrique décrit l’intégration des données sur les cartes de fidélité client et les points de récompense dans la double écriture.
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
ms.openlocfilehash: 28872e9510394cf3d5cee151798d4130b8b6fe27
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683496"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Cartes de fidélité et points de fidélité

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Les entreprises classent les clients et fournissent des services sophistiqués, basés sur les habitudes d’achat et les dépenses des clients. Par exemple, Dynamics 365 Commerce possède l’infrastructure et les fonctions nécessaires pour faciliter et gérer les cartes de fidélité des clients, les points de récompense, les prix basés sur la fidélité et les expériences d’achat basées sur les récompenses. Lorsque les données sur les cartes de fidélité des clients et les points de récompense dans Commerce sont synchronisées avec Dataverse, les applications d’engagement client peuvent utiliser ces données. Par exemple, les utilisateurs de Dynamics 365 Customer Service peuvent utiliser les données pour fournir les mêmes services sophistiqués via le service d’assistance.

## <a name="templates"></a>Modèles

| Applications Finance and Operations | Applications pilotées par modèle dans Dynamics 365 | Description |
|-----------------------------|-----------------------------------|-------------|
| Carte de fidélité                | msdyn\_loyaltycards               | Ce modèle synchronise les informations concernant les cartes de fidélité des clients. |
| Points de récompense de fidélité       | msdyn\_loyaltyrewardpoints        | Ce modèle synchronise les informations concernant les points de fidélité des clients. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]