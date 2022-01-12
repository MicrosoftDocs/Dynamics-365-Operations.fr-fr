---
title: Conseils de visibilité des stocks
description: Cette rubrique fournit quelques conseils que vous devez prendre en compte lorsque vous configurez et utilisez le complément de visibilité des stocks.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: f5fb4c7cb941b352bbc6e2fcf5347244e1c8a40c
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920802"
---
# <a name="inventory-visibility-tips"></a>Conseils de visibilité des stocks

[!include [banner](../includes/banner.md)]

Voici quelques conseils que vous devez prendre en compte lorsque vous configurez et utilisez le complément de visibilité des stocks :

- Actuellement, le complément de visibilité des stocks ne prend en charge que les environnements Microsoft Dataverse créés à l’aide de Microsoft Dynamics Lifecycle Services (LCS). Si votre environnement Dataverse a été créé d’une autre manière (par exemple, en utilisant le centre d’administration Power Apps) et s’il est lié à votre environnement Dynamics 365 Supply Chain Management, vous devez d’abord contacter l’équipe produit de visibilité des stocks pour résoudre le problème de mappage. Vous pouvez contacter l’équipe à l’adresse [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com). L’équipe vous informera lorsque votre environnement sera prêt pour que vous installiez la visibilité des stocks.
- Si vous avez plusieurs environnements LCS, créez une application Azure Active Directory (Azure AD) différente pour chaque environnement. Si vous utilisez le même ID d’application et le même ID de locataire pour installer le complément de visibilité des stocks pour différents environnements, un problème de jeton se produira pour les environnements plus anciens. Seule la dernière instance du complément de visibilité des stocks qui a été installé sera valide.
- La visibilité des stocks n’est actuellement pas prise en charge pour les environnements hébergés dans le cloud. Elle n’est prise en charge que pour les environnements de niveau 2+.
- L’interface de programmation d’applications (API) prend actuellement en charge l’interrogation de jusqu’à 100 éléments individuels par valeur `ProductID`. Plusieurs valeurs `SiteID` et `LocationID` peuvent également être spécifiées dans chaque requête. La limite maximale est définie comme `NumOf(SiteID) * NumOf(LocationID) <= 100`.
- La source de données `fno` est réservée pour Supply Chain Management. Si votre complément de visibilité des stocks est intégré à un environnement Supply Chain Management, nous vous recommandons de ne pas supprimer les configurations liées à `fno` dans la [source de données](inventory-visibility-configuration.md#data-source-configuration).
- La [configuration de la partition](inventory-visibility-configuration.md#partition-configuration) se compose de deux dimensions de base (`SiteId` et `LocationId`) qui indiquent comment les données sont distribuées. Les opérations sous la même partition peuvent offrir des performances supérieures à moindre coût. La solution inclut cette configuration de partition par défaut. Par conséquent, *vous n’avez pas à la définir vous-même*. Ne personnalisez pas la configuration de partition par défaut. Si vous la supprimez ou la modifiez, vous risquez de provoquer une erreur inattendue.
- Les dimensions de base définies dans la configuration de la partition ne doivent pas être définies dans la [configuration de hiérarchie d’index de produits](inventory-visibility-configuration.md#index-configuration).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
