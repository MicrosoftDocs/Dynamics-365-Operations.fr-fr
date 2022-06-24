---
title: Restreindre l’accès à une vitrine pendant les tests ou le développement
description: Cet article explique comment restreindre l’accès à une vitrine Microsoft Dynamics 365 Commerce pendant les tests ou le développement internes.
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
ms.openlocfilehash: 77b652aafa6aea807ab11fe02209bc7de43fa446
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898882"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a>Restreindre l’accès à une vitrine pendant les tests ou le développement

[!include [banner](../../includes/banner.md)]

Cet article explique comment restreindre l’accès à une vitrine Microsoft Dynamics 365 Commerce pendant les tests ou le développement internes.

## <a name="description"></a>Description

Pendant les tests internes ou le développement actif, vous souhaiterez peut-être restreindre l’accès à votre site pour empêcher les utilisateurs externes d’accéder aux pages de vitrine publiées.

## <a name="resolution"></a>Résolution

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a>Installation d’Azure AD B2C à l’aide des flux d’utilisateurs standard

Pour plus d’informations sur la configuration d’Azure Active Directory B2C (Azure AD B2C) pour votre site d’e-commerce, voir [Configurer un locataire B2C dans Commerce](../set-up-b2c-tenant.md).

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a>Restreindre l’accès des utilisateurs aux pages de la vitrine et bloquer la création de nouveaux utilisateurs

Pour restreindre l’accès des utilisateurs aux pages de vitrine dans le générateur de site Commerce, procédez comme suit.

1. Accédez à votre site.
1. Sélectionnez **Pages**, puis sélectionnez la page pour laquelle restreindre l’accès des utilisateurs.
1. Sélectionnez le module ou l’emplacement de fragment, puis sélectionnez **Modifier**.
1. Dans le volet de propriétés, sélectionnez **Nécessite une connexion ?**, puis **Terminer la modification**.
1. Sélectionnez **Publier**.

Pour bloquer la création de nouveaux utilisateurs dans Azure AD, procédez comme suit.

1. Accédez au [Portail Azure](https://portal.azure.com/).
1. Sélectionnez l’application Azure AD B2C que vous avez créée pour accéder à votre site.
1. Dans le volet de navigation de gauche, sélectionnez **Flux d’utilisateurs**.
1. En haut de la page **Flux d’utilisateurs**, sélectionnez **Nouveau flux d’utilisateur**.
1. Sur la page **Sélectionner un type de flux d’utilisateurs**, sélectionnez **Aperçu**.
1. Au milieu de la page, sélectionnez **se connecter v2**. Suivez ensuite les étapes de [Configurer un client B2C dans Commerce](../set-up-b2c-tenant.md) pour configurer le flux en tant que flux d’utilisateurs standard de votre site pour Azure AD B2C pendant les tests ou le développement.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un client B2C dans Commerce](../set-up-b2c-tenant.md)

[Paramétrer des pages personnalisées pour les connexions utilisateur](../custom-pages-user-logins.md)
