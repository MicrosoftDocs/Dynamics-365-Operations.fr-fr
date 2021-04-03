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
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a><span data-ttu-id="bad37-103">Le lien de connexion redirige vers un site d’e-commerce</span><span class="sxs-lookup"><span data-stu-id="bad37-103">Sign-in link redirects back to an e-commerce site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bad37-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un lien de connexion redirige vers le site d’e-commerce au lieu d’accéder à la page de connexion.</span><span class="sxs-lookup"><span data-stu-id="bad37-104">This topic provides troubleshooting guidance that can help when a sign-in link redirects back to the e-commerce site instead of going to the sign-in page.</span></span>

## <a name="description"></a><span data-ttu-id="bad37-105">Description </span><span class="sxs-lookup"><span data-stu-id="bad37-105">Description</span></span>

<span data-ttu-id="bad37-106">Après avoir configuré un nouveau locataire Microsoft Azure Active Directory B2C (Azure AD B2C) dans le générateur de site Commerce, les utilisateurs qui sélectionnent le lien **Connexion** sont redirigés vers la page de destination principale e-commerce sans accéder à la page de connexion.</span><span class="sxs-lookup"><span data-stu-id="bad37-106">After you configure a new Microsoft Azure Active Directory B2C (Azure AD B2C) tenant in Commerce site builder, users who select the **Sign in** link are redirected back to the main e-commerce landing page without going to the sign-in page.</span></span>

## <a name="resolution"></a><span data-ttu-id="bad37-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="bad37-107">Resolution</span></span>

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a><span data-ttu-id="bad37-108">Confirmer que l’URL de réponse est correctement configurée dans l’application Azure AD B2C</span><span class="sxs-lookup"><span data-stu-id="bad37-108">Confirm that the reply URL is correctly configured in the Azure AD B2C application</span></span>

<span data-ttu-id="bad37-109">Pour confirmer que l’URL de réponse est correctement configurée dans l’application Azure AD B2C, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bad37-109">To confirm that the reply URL is correctly configured in the Azure AD B2C application, follow these steps.</span></span>

1. <span data-ttu-id="bad37-110">Accédez au [Portail Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="bad37-110">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="bad37-111">Sélectionnez l’application Azure AD B2C que vous avez créée pour accéder à votre site.</span><span class="sxs-lookup"><span data-stu-id="bad37-111">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="bad37-112">Sélectionnez l’application que vous avez créée lors de la configuration Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="bad37-112">Select the application that you created during the Azure AD B2C setup.</span></span>
1. <span data-ttu-id="bad37-113">Sous **URL de réponse**, assurez-vous que la liste comprend des entrées pour l’URL du domaine du site et l’URL générée par e-commerce, comme indiqué dans l’exemple de l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="bad37-113">Under **Reply URL**, make sure that the list includes entries for both the site domain URL and the e-commerce-generated URL, as shown in the example in the following illustration.</span></span>

    ![Entrées d’URL de réponse Azure AD B2C](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> <span data-ttu-id="bad37-115">L’URL du domaine du site et l’URL générée par e-commerce doivent être dans un format d’URL valide qui n’inclut pas de barres obliques de début ou de fin.</span><span class="sxs-lookup"><span data-stu-id="bad37-115">Both the site domain URL and the e-commerce-generated URL must be in a valid URL format that doesn't include leading or trailing slashes.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bad37-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="bad37-116">Additional resources</span></span>

[<span data-ttu-id="bad37-117">Inscrire une application web dans Azure Active Directory B2C</span><span class="sxs-lookup"><span data-stu-id="bad37-117">Register a web application in Azure Active Directory B2C</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[<span data-ttu-id="bad37-118">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="bad37-118">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
