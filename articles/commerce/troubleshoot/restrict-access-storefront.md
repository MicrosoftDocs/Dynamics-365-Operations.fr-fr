---
title: Restreindre l’accès à une vitrine pendant les tests ou le développement
description: Cette rubrique explique comment restreindre l’accès à une vitrine Microsoft Dynamics 365 Commerce pendant les tests ou le développement internes.
author: Reza-Assadi
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
ms.openlocfilehash: f5cba6b7ff3aa65441c932e72fa458bda0d0fc69
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801529"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a><span data-ttu-id="de287-103">Restreindre l’accès à une vitrine pendant les tests ou le développement</span><span class="sxs-lookup"><span data-stu-id="de287-103">Restrict access to a storefront during testing or development</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="de287-104">Cette rubrique explique comment restreindre l’accès à une vitrine Microsoft Dynamics 365 Commerce pendant les tests ou le développement internes.</span><span class="sxs-lookup"><span data-stu-id="de287-104">This topic explains how to restrict access to a Microsoft Dynamics 365 Commerce storefront while internal testing or development is occurring.</span></span>

## <a name="description"></a><span data-ttu-id="de287-105">Description</span><span class="sxs-lookup"><span data-stu-id="de287-105">Description</span></span>

<span data-ttu-id="de287-106">Pendant les tests internes ou le développement actif, vous souhaiterez peut-être restreindre l’accès à votre site pour empêcher les utilisateurs externes d’accéder aux pages de vitrine publiées.</span><span class="sxs-lookup"><span data-stu-id="de287-106">During internal testing or active development, you might want to restrict access to your site to prevent external users from accessing the published storefront pages.</span></span>

## <a name="resolution"></a><span data-ttu-id="de287-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="de287-107">Resolution</span></span>

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a><span data-ttu-id="de287-108">Installation d’Azure AD B2C à l’aide des flux d’utilisateurs standard</span><span class="sxs-lookup"><span data-stu-id="de287-108">Set up Azure AD B2C by using standard user flows</span></span>

<span data-ttu-id="de287-109">Pour plus d’informations sur la configuration d’Azure Active Directory B2C (Azure AD B2C) pour votre site d’e-commerce, voir [Configurer un locataire B2C dans Commerce](../set-up-b2c-tenant.md).</span><span class="sxs-lookup"><span data-stu-id="de287-109">For information about how to configure Azure Active Directory B2C (Azure AD B2C) for your e-commerce site, see [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md).</span></span>

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a><span data-ttu-id="de287-110">Restreindre l’accès des utilisateurs aux pages de la vitrine et bloquer la création de nouveaux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="de287-110">Restrict user access to storefront pages and block the creation of new users</span></span>

<span data-ttu-id="de287-111">Pour restreindre l’accès des utilisateurs aux pages de vitrine dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="de287-111">To restrict user access to storefront pages in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="de287-112">Accédez à votre site.</span><span class="sxs-lookup"><span data-stu-id="de287-112">Go to your site.</span></span>
1. <span data-ttu-id="de287-113">Sélectionnez **Pages**, puis sélectionnez la page pour laquelle restreindre l’accès des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="de287-113">Select **Pages**, and then select the page to restrict user access for.</span></span>
1. <span data-ttu-id="de287-114">Sélectionnez le module ou l’emplacement de fragment, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="de287-114">Select the module or fragment slot, and then select **Edit**.</span></span>
1. <span data-ttu-id="de287-115">Dans le volet de propriétés, sélectionnez **Nécessite une connexion ?**, puis **Terminer la modification**.</span><span class="sxs-lookup"><span data-stu-id="de287-115">In the properties pane, select **Requires sign-in?**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="de287-116">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="de287-116">Select **Publish**.</span></span>

<span data-ttu-id="de287-117">Pour bloquer la création de nouveaux utilisateurs dans Azure AD, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="de287-117">To block the creation of new users in Azure AD, follow these steps.</span></span>

1. <span data-ttu-id="de287-118">Accédez au [Portail Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="de287-118">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="de287-119">Sélectionnez l’application Azure AD B2C que vous avez créée pour accéder à votre site.</span><span class="sxs-lookup"><span data-stu-id="de287-119">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="de287-120">Dans le volet de navigation de gauche, sélectionnez **Flux d’utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="de287-120">In the left navigation, select **User flows**.</span></span>
1. <span data-ttu-id="de287-121">En haut de la page **Flux d’utilisateurs**, sélectionnez **Nouveau flux d’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="de287-121">At the top of the **User Flows** page, select **New user flow**.</span></span>
1. <span data-ttu-id="de287-122">Sur la page **Sélectionner un type de flux d’utilisateurs**, sélectionnez **Aperçu**.</span><span class="sxs-lookup"><span data-stu-id="de287-122">On the **Select a user flow type** page, select **Preview**.</span></span>
1. <span data-ttu-id="de287-123">Au milieu de la page, sélectionnez **se connecter v2**.</span><span class="sxs-lookup"><span data-stu-id="de287-123">In the middle of the page, select **Sign in v2**.</span></span> <span data-ttu-id="de287-124">Suivez ensuite les étapes de [Configurer un client B2C dans Commerce](../set-up-b2c-tenant.md) pour configurer le flux en tant que flux d’utilisateurs standard de votre site pour Azure AD B2C pendant les tests ou le développement.</span><span class="sxs-lookup"><span data-stu-id="de287-124">Then follow the steps in [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md) to configure the flow as your site's standard user flow for Azure AD B2C during testing or development.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="de287-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="de287-125">Additional resources</span></span>

[<span data-ttu-id="de287-126">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="de287-126">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)

[<span data-ttu-id="de287-127">Paramétrer des pages personnalisées pour les connexions utilisateur</span><span class="sxs-lookup"><span data-stu-id="de287-127">Set up custom pages for user sign-ins</span></span>](../custom-pages-user-logins.md)
