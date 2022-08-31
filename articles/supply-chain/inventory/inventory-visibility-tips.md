---
title: Conseils Inventory Visibility
description: Cet article fournit quelques conseils que vous devez prendre en compte lorsque vous configurez et utilisez le complément de visibilité des stocks.
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
ms.openlocfilehash: 3bdd161815a15d5c39b3c0afc176a288c8d9055a
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306083"
---
# <a name="inventory-visibility-tips"></a>Conseils de visibilité des stocks

[!include [banner](../includes/banner.md)]

Voici quelques conseils que vous devez prendre en compte lorsque vous configurez et utilisez le complément de visibilité des stocks :

- Actuellement, le complément de visibilité des stocks ne prend en charge que les environnements Microsoft Dataverse créés à l’aide de Microsoft Dynamics Lifecycle Services (LCS). Si votre environnement Dataverse a été créé d’une autre manière (par exemple, en utilisant le centre d’administration Power Apps) et s’il est lié à votre environnement Dynamics 365 Supply Chain Management, vous devez d’abord contacter l’équipe produit de visibilité des stocks pour résoudre le problème de mappage. Vous pouvez contacter l’équipe à l’adresse [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com). L’équipe vous informera lorsque votre environnement sera prêt pour que vous installiez la visibilité des stocks.
- Si vous avez plusieurs environnements LCS, créez une application Azure Active Directory (Azure AD) différente pour chaque environnement. Si vous utilisez le même ID d’application et le même ID de locataire pour installer le complément de visibilité des stocks pour différents environnements, un problème de jeton se produira pour les environnements plus anciens. Seule la dernière instance du complément de visibilité des stocks qui a été installé sera valide.
- La visibilité des stocks n’est actuellement pas prise en charge pour les environnements hébergés dans le cloud. Elle n’est prise en charge que pour les environnements de niveau 2+.
- L’interface de programmation d’applications (API) prend actuellement en charge l’interrogation de jusqu’à 100 éléments individuels par valeur `ProductID`. Plusieurs valeurs `SiteID` et `LocationID` peuvent également être spécifiées dans chaque requête. La limite maximale est définie comme `NumOf(SiteID) * NumOf(LocationID) <= 100`.
- L’API en masse peut renvoyer un maximum de 512 enregistrements pour chaque requête.
- La source de données `fno` est réservée pour Supply Chain Management. Si votre complément de visibilité des stocks est intégré à un environnement Supply Chain Management, nous vous recommandons de ne pas supprimer les configurations liées à `fno` dans la [source de données](inventory-visibility-configuration.md#data-source-configuration).
- La visibilité du stock ne peut modifier aucune donnée pour la source de données `fno`. Le flux de données est unidirectionnel, ce qui signifie que toutes les quantités changent pour la source de données `fno` doit provenir de votre environnement Supply Chain Management. Par conséquent, vous ne pouvez pas utiliser l’API pour envoyer des demandes de modification ou de réservation en main pour la source de données `fno`.
- Si vous ajoutez une ou plusieurs nouvelles mesures à votre environnement Supply Chain Management, vous devez également les ajouter dans la visibilité du stock. Cependant, toutes les modifications de quantité pour les nouvelles mesures doivent provenir de votre environnement Supply Chain Management.
- La [configuration de la partition](inventory-visibility-configuration.md#partition-configuration) se compose de deux dimensions de base (`SiteId` et `LocationId`) qui indiquent comment les données sont distribuées. Les opérations sous la même partition peuvent offrir des performances supérieures à moindre coût. La solution inclut cette configuration de partition par défaut. Par conséquent, *vous n’avez pas à la définir vous-même*. Ne personnalisez pas la configuration de partition par défaut. Si vous la supprimez ou la modifiez, vous risquez de provoquer une erreur inattendue.
- Les dimensions de base définies dans la configuration de la partition ne doivent pas être définies dans la [configuration de hiérarchie d’index de produits](inventory-visibility-configuration.md#index-configuration).
- Votre [configuration de hiérarchie d'index de produit](inventory-visibility-configuration.md#index-configuration) doit avoir au moins une hiérarchie d'index (par exemple, contenant la dimension de base `Empty`), sinon les requêtes échoueront avec l'erreur "Aucune hiérarchie d'index n'a été définie".
- La source de données `@iv` est une source de données prédéfinie et les mesures physiques définies dans `@iv` avec préfixe `@` sont des mesures prédéfinies. Ces mesures sont une configuration prédéfinie pour la fonctionnalité de répartition, donc ne les modifiez pas ou ne les supprimez pas ou vous risquez de rencontrer des erreurs inattendues lors de l’utilisation de la fonctionnalité de répartition.
- Vous pouvez ajouter de nouvelles mesures physiques à la mesure calculée prédéfinie `@iv.@available_to_allocate`, mais vous ne devez pas modifier son nom.
- Si vous restaurez une base de données de Supply Chain Management, votre base de données restaurée peut contenir des données qui ne sont plus cohérentes avec les données précédemment synchronisées par Inventory Visibility sur Dataverse. Cette incohérence des données peut entraîner des erreurs système et d’autres problèmes. Par conséquent, il est important que vous nettoyiez toujours toutes les données liées à Inventory Visibility de Dataverse avant toute restauration d'une base de données de Supply Chain Management. Pour plus de détails, voir [Nettoyer les données de Inventory Visibility de Dataverse avant de restaurer la base de données de Supply Chain Management](inventory-visibility-setup.md#restore-environment-database).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
