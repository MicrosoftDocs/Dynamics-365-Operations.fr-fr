---
title: Le lien de connexion redirige vers un site d’e-commerce
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un lien de connexion redirige vers le site d’e-commerce au lieu d’accéder à la page de connexion.
author: Reza-Assadi
manager: AnnBe
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
ms.openlocfilehash: 36f10c9f68570a6c67da6b4b6e4155f4634f633a
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585313"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a>Le lien de connexion redirige vers un site d’e-commerce

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un lien de connexion redirige vers le site d’e-commerce au lieu d’accéder à la page de connexion.

## <a name="description"></a>Description 

Après avoir configuré un nouveau locataire Microsoft Azure Active Directory B2C (Azure AD B2C) dans le générateur de site Commerce, les utilisateurs qui sélectionnent le lien **Connexion** sont redirigés vers la page de destination principale e-commerce sans accéder à la page de connexion.

## <a name="resolution"></a>Résolution

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a>Confirmer que l’URL de réponse est correctement configurée dans l’application Azure AD B2C

Pour confirmer que l’URL de réponse est correctement configurée dans l’application Azure AD B2C, procédez comme suit.

1. Accédez au [Portail Azure](https://portal.azure.com/).
1. Sélectionnez l’application Azure AD B2C que vous avez créée pour accéder à votre site.
1. Sélectionnez l’application que vous avez créée lors de la configuration Azure AD B2C.
1. Sous **URL de réponse**, assurez-vous que la liste comprend des entrées pour l’URL du domaine du site et l’URL générée par e-commerce, comme indiqué dans l’exemple de l’illustration suivante.

    ![Entrées d’URL de réponse Azure AD B2C](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> L’URL du domaine du site et l’URL générée par e-commerce doivent être dans un format d’URL valide qui n’inclut pas de barres obliques de début ou de fin.

## <a name="additional-resources"></a>Ressources supplémentaires

[Inscrire une application web dans Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[Configurer un client B2C dans Commerce](../set-up-b2c-tenant.md)
