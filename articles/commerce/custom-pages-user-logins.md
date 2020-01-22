---
title: Paramétrer des pages personnalisées pour les connexions utilisateur
description: Cette rubrique décrit la procédure pour générer des pages personnalisées dans Microsoft Dynamics 365 Commerce qui gèrent les connexions personnalisées des utilisateurs des clients entreprise-client (B2C) Azure Active Directory (Azure AD).
author: brianshook
manager: annbe
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 20bfacbc2374003814e12e7737644d118d404cc0
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945557"
---
# <a name="set-up-custom-pages-for-user-logins"></a><span data-ttu-id="43bfb-103">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="43bfb-103">Set up custom pages for user logins</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="43bfb-104">Cette rubrique décrit la procédure pour générer des pages personnalisées dans Microsoft Dynamics 365 Commerce qui gèrent les connexions personnalisées des utilisateurs des clients entreprise-client (B2C) Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="43bfb-104">This topic describes how to build custom pages in Microsoft Dynamics 365 Commerce that handle customized sign-ins for users of Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants.</span></span>

## <a name="overview"></a><span data-ttu-id="43bfb-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="43bfb-105">Overview</span></span>

<span data-ttu-id="43bfb-106">Pour utiliser les pages personnalisés créés dans Dynamics 365 Commerce pour gérer les flux de connexions utilisateur, vous devez paramétrer les stratégies Azure AD qui seront référencées dans l'environnement de Commerce.</span><span class="sxs-lookup"><span data-stu-id="43bfb-106">To use custom pages that are authored in Dynamics 365 Commerce to handle user sign-in flows, you must set up the Azure AD policies that will be referenced in the Commerce environment.</span></span> <span data-ttu-id="43bfb-107">Vous pouvez configurer les stratégie B2C Azure AD « S'inscrire et se connecter », « Modification de profil, » et « Mot de passe réinitialisé » à l'aide de l'application Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="43bfb-107">You can configure the "Sign up and sign in," "Profile editing," and "Password reset" Azure AD B2C policies by using the Azure AD B2C application.</span></span> <span data-ttu-id="43bfb-108">Les noms de client et de stratégie Azure AD B2C peuvent être référencés lors de le processus de mise en service effectué pour l'environnement de Commerce à l'aide de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="43bfb-108">The Azure AD B2C tenant and policy names can then be referenced during the provisioning process that is done for the Commerce environment by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="43bfb-109">Les pages Commerce personnalisées peuvent être générées en utilisant l'inscription, la connexion, la modification de profil de compte ou le module de réinitialisation du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="43bfb-109">The custom Commerce pages can be built by using the sign in, sign up, account profile edit, or password reset module.</span></span> <span data-ttu-id="43bfb-110">Les URL de page publiés pour ces pages personnalisées doivent être référencées dans les configurations de stratégie Azure AD B2C dans le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="43bfb-110">The page URLs that are published for these custom pages should then be referenced in Azure AD B2C policy configurations in the Azure portal.</span></span>

## <a name="set-up-b2c-policies"></a><span data-ttu-id="43bfb-111">Paramétrer des stratégies B2C</span><span class="sxs-lookup"><span data-stu-id="43bfb-111">Set up B2C policies</span></span>

<span data-ttu-id="43bfb-112">Après avoir paramétré votre client Azure AD B2C et l'avoir associé à votre environnement Commerce, cliquez sur la page **Azure AD B2C** dans le portail Azure, puis, dans le menu, sous **Stratégies**, sélectionnez **Flux utilisateurs (stratégies)**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-112">After you set up your Azure AD B2C tenant and associate it with your Commerce environment, go to the **Azure AD B2C** page in the Azure portal, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

![Commande Flux utilisateurs (stratégie) dans le menu](./media/B2C_CustomPage_PoliciesMenu.png)

<span data-ttu-id="43bfb-114">Vous pouvez désormais configurer les flux de connexion utilisateur « Inscription et connexion », « Modification de profil » et « Réinitialisation du mot de passe ».</span><span class="sxs-lookup"><span data-stu-id="43bfb-114">You can now configure the "Sign up and sign in," "Profile editing," and "Password reset" user sign-in flows.</span></span>

### <a name="configure-the-sign-up-and-sign-in-policy"></a><span data-ttu-id="43bfb-115">Configuration de la stratégie « Inscription et connexion »</span><span class="sxs-lookup"><span data-stu-id="43bfb-115">Configure the "Sign up and sign in" policy</span></span>

<span data-ttu-id="43bfb-116">Pour configurer la stratégie « Inscription et connexion », procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="43bfb-116">To configure the "Sign up and sign in" policy, follow these steps.</span></span>

1. <span data-ttu-id="43bfb-117">Sélectionnez **Nouveau flux utilisateur**, puis, dans l'onglet **Recommandé**, sélectionnez la stratégie **Inscription et connexion**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-117">Select **New user flow**, and then, on the **Recommended** tab, select the **Sign up and sign in** policy.</span></span>
1. <span data-ttu-id="43bfb-118">Entrez un nom pour la stratégie (par exemple, **B2C\_1\_SignInSignUp**).</span><span class="sxs-lookup"><span data-stu-id="43bfb-118">Enter a name for the policy (for example, **B2C\_1\_SignInSignUp**).</span></span>
1. <span data-ttu-id="43bfb-119">Dans la section **Fournisseurs d'identification**, sélectionnez les fournisseurs d'identification à utiliser pour la stratégie.</span><span class="sxs-lookup"><span data-stu-id="43bfb-119">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="43bfb-120">**E-mail d'inscription** doit être au moins être sélectionné.</span><span class="sxs-lookup"><span data-stu-id="43bfb-120">At a minimum, **Email signup** must be selected.</span></span>
1. <span data-ttu-id="43bfb-121">Dans la colonne **Attribut de collecte**, activez les cases à cocher pour, **Adresse e-mail**, **Prénom**et **Nom de famille**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-121">In the **Collect attribute** column, select the check boxes for **Email Address**, **Given Name**, and **Surname**.</span></span>
1. <span data-ttu-id="43bfb-122">Dans la colonne **Réclamation de retour**, activez les cases à cocher pour **Adresse e-mail**, **Prénom**, **Fournisseur d'identification**, **Nom de famille** et **ID objet de l'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-122">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>

    ![Attributs et réclamations sélectionnés](./media/B2C_SignInSignUp_Attributes.png)

1. <span data-ttu-id="43bfb-124">Cliquez sur **OK** pour créer la stratégie.</span><span class="sxs-lookup"><span data-stu-id="43bfb-124">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="43bfb-125">Double-cliquez sur le nom de la stratégie, puis, dans le volet de navigation, sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-125">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="43bfb-126">Définissez l'option **Activer l'application de la disposition de page Javascript** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-126">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

    ![La page de propriétés de la nouvelle stratégie](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> <span data-ttu-id="43bfb-128">Le nom de la stratégie est entièrement référencé dans l'environnement Commerce.</span><span class="sxs-lookup"><span data-stu-id="43bfb-128">The policy name will be fully referenced in the Commerce environment.</span></span> <span data-ttu-id="43bfb-129">(Le préfixe **B2C\_1\_** sera inclus dans la référence.) Les stratégies ne peuvent pas être renommées après leur création.</span><span class="sxs-lookup"><span data-stu-id="43bfb-129">(The **B2C\_1\_** prefix will be included in the reference.) Policies can't be renamed after they are created.</span></span> <span data-ttu-id="43bfb-130">Si vous remplacez une stratégie existante pour votre environnement Commerce, vous pouvez supprimer la stratégie d'origine et créer une stratégie qui a le même nom.</span><span class="sxs-lookup"><span data-stu-id="43bfb-130">If you're replacing an existing policy for your Commerce environment, you can delete the original policy and build a new policy that has the same name.</span></span> <span data-ttu-id="43bfb-131">Sinon, si l'environnement a déjà été mis en service, vous pouvez envoyer le nouveau nom de stratégie via une demande de service.</span><span class="sxs-lookup"><span data-stu-id="43bfb-131">Alternatively, if the environment has already been provisioned, you can submit the new policy name through a service request.</span></span>

<span data-ttu-id="43bfb-132">Vous reviendrez à cette stratégie pour terminer le paramétrage après avoir généré les pages personnalisées.</span><span class="sxs-lookup"><span data-stu-id="43bfb-132">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="43bfb-133">Pour maintenant, clôturez la stratégie pour revenir à la page **Flux utilisateurs (stratégies)** dans le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="43bfb-133">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-profile-editing-policy"></a><span data-ttu-id="43bfb-134">Configurer la stratégie « Modification de profil »</span><span class="sxs-lookup"><span data-stu-id="43bfb-134">Configure the "Profile editing" policy</span></span>

<span data-ttu-id="43bfb-135">Pour configurer la stratégie « Modification de profil », procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="43bfb-135">To configure the "Profile editing" policy, follow these steps.</span></span>

1. <span data-ttu-id="43bfb-136">Sélectionnez **Nouveau flux utilisateur**, puis, dans l'onglet **Recommandé**, sélectionnez la stratégie **Modification de profil**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-136">Select **New user flow**, and then, on the **Recommended** tab, select the **Profile editing** policy.</span></span>
1. <span data-ttu-id="43bfb-137">Entrez un nom pour la stratégie (par exemple, **B2C\_1\_EditProfile**).</span><span class="sxs-lookup"><span data-stu-id="43bfb-137">Enter a name for the policy (for example, **B2C\_1\_EditProfile**).</span></span>
1. <span data-ttu-id="43bfb-138">Dans la section **Fournisseurs d'identification**, sélectionnez les fournisseurs d'identification à utiliser pour la stratégie.</span><span class="sxs-lookup"><span data-stu-id="43bfb-138">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="43bfb-139">Au minimum, **Connexion au compte local** doit être sélectionné.</span><span class="sxs-lookup"><span data-stu-id="43bfb-139">At a minimum, **Local Account SignIn** must be selected.</span></span>
1. <span data-ttu-id="43bfb-140">Dans la colonne **Attribut de collecte**, activez les cases à cocher pour **Adresses e-mail** et **Nom de famille**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-140">In the **Collect attribute** column, select the check boxes for **Email Addresses** and **Surname**.</span></span>
1. <span data-ttu-id="43bfb-141">Dans la colonne **Réclamation de retour**, activez les cases à cocher pour **Adresse e-mail**, **Prénom**, **Fournisseur d'identification**, **Nom de famille** et **ID objet de l'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-141">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>
1. <span data-ttu-id="43bfb-142">Cliquez sur **OK** pour créer la stratégie.</span><span class="sxs-lookup"><span data-stu-id="43bfb-142">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="43bfb-143">Double-cliquez sur le nom de la stratégie, puis, dans le volet de navigation, sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-143">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="43bfb-144">Définissez l'option **Activer l'application de la disposition de page Javascript** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-144">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="43bfb-145">Vous reviendrez à cette stratégie pour terminer le paramétrage après avoir généré les pages personnalisées.</span><span class="sxs-lookup"><span data-stu-id="43bfb-145">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="43bfb-146">Pour maintenant, clôturez la stratégie pour revenir à la page **Flux utilisateurs (stratégies)** dans le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="43bfb-146">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-password-reset-policy"></a><span data-ttu-id="43bfb-147">Configurez la stratégie « Mot de passe réinitialisé »</span><span class="sxs-lookup"><span data-stu-id="43bfb-147">Configure the "Password reset" policy</span></span>

<span data-ttu-id="43bfb-148">Pour configurer la stratégie « Réinitialisation de mot de passe », procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="43bfb-148">To configure the "Password reset" policy, follow these steps.</span></span>

1. <span data-ttu-id="43bfb-149">Sélectionnez **Nouveau flux utilisateur**, puis, dans l'onglet **Aperçu**, sélectionnez la stratégie **Réinitialisation de mot de passe v1.1**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-149">Select **New user flow**, and then, on the **Preview** tab, select the **Password reset v1.1** policy.</span></span>

    ![Stratégie Réinitialisation de mot de passe v1.1 sélectionnée sous l'onglet Aperçu](./media/B2C_ForgetPassword_Menu.png)

1. <span data-ttu-id="43bfb-151">Entrez un nom pour la stratégie (par exemple, **B2C\_1\_ForgetPassword**).</span><span class="sxs-lookup"><span data-stu-id="43bfb-151">Enter a name for the policy (for example, **B2C\_1\_ForgetPassword**).</span></span>
1. <span data-ttu-id="43bfb-152">Dans la section **Fournisseurs d'identification**, sélectionnez **Réinitialiser le mot de passe à l'aide de l'adresse e-mail**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-152">In the **Identity Providers** section, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="43bfb-153">Dans la colonne **Réclamation de retour**, activez les cases à cocher pour **Adresse e-mail**, **Prénom**, **Nom de famille** et **ID objet de l'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-153">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Surname**, and **User's Object ID**.</span></span>

    ![Réclamations sélectionnées](./media/B2C_ForgetPassword_Attributes.png)

1. <span data-ttu-id="43bfb-155">Cliquez sur **OK** pour créer la stratégie.</span><span class="sxs-lookup"><span data-stu-id="43bfb-155">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="43bfb-156">Double-cliquez sur le nom de la stratégie, puis, dans le volet de navigation, sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-156">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="43bfb-157">Définissez l'option **Activer l'application de la disposition de page Javascript** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-157">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="43bfb-158">Vous reviendrez à cette stratégie pour terminer le paramétrage après avoir généré les pages personnalisées.</span><span class="sxs-lookup"><span data-stu-id="43bfb-158">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="43bfb-159">Pour maintenant, clôturez la stratégie pour revenir à la page **Flux utilisateurs (stratégies)** dans le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="43bfb-159">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

## <a name="build-the-custom-pages"></a><span data-ttu-id="43bfb-160">Générer des pages personnalisées</span><span class="sxs-lookup"><span data-stu-id="43bfb-160">Build the custom pages</span></span>

<span data-ttu-id="43bfb-161">Pour générer des pages personnalisés pour gérer les connexions des utilisateurs, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="43bfb-161">To build the custom pages to handle user sign-ins, follow these steps.</span></span>

1. <span data-ttu-id="43bfb-162">Dans l'outil de création de Commerce, accédez à votre site.</span><span class="sxs-lookup"><span data-stu-id="43bfb-162">In the Commerce authoring tools, go to your site.</span></span>
1. <span data-ttu-id="43bfb-163">Générez les cinq modèles et cinq pages suivants :</span><span class="sxs-lookup"><span data-stu-id="43bfb-163">Build the following five templates and five pages:</span></span>

    - <span data-ttu-id="43bfb-164">Un modèle et une page **Connexion** qui utilisent le module de connexion.</span><span class="sxs-lookup"><span data-stu-id="43bfb-164">A **Sign In** template and page that use the sign in module.</span></span>
    - <span data-ttu-id="43bfb-165">Un modèle et une page **Inscription** qui utilisent le module d'inscription.</span><span class="sxs-lookup"><span data-stu-id="43bfb-165">A **Sign Up** template and page that use the sign up module.</span></span>
    - <span data-ttu-id="43bfb-166">Un modèle et une page **Réinitialisation du mot de passe** qui utilisent le module de réinitialisation de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="43bfb-166">A **Password Reset** template and page that use the password reset module.</span></span>
    - <span data-ttu-id="43bfb-167">Un modèle et une page **Vérification de la réinitialisation du mot de passe** qui utilisent le module de vérification de la réinitialisation de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="43bfb-167">A **Password Reset verification** template and page that use the password reset verification module.</span></span>
    - <span data-ttu-id="43bfb-168">Un modèle et une page **Modification de profil** qui utilisent le module de modification de profil de compte</span><span class="sxs-lookup"><span data-stu-id="43bfb-168">A **Profile Edit** template and page that use the account profile edit module</span></span>

<span data-ttu-id="43bfb-169">Lorsque vous générez des pages, suivez les instructions :</span><span class="sxs-lookup"><span data-stu-id="43bfb-169">When you build the pages, follow these guidelines:</span></span>

- <span data-ttu-id="43bfb-170">Pour chaque page ou module, utilisez la disposition et le style qui s'adaptent le mieux à vos besoins commerciaux.</span><span class="sxs-lookup"><span data-stu-id="43bfb-170">For each page or module, use the layout and style that best suit your business requirements.</span></span>
- <span data-ttu-id="43bfb-171">Publiez tous les pages et URL à utiliser dans le paramétrage de Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="43bfb-171">Publish all pages and URLs that must be used in the Azure AD B2C setup.</span></span>
- <span data-ttu-id="43bfb-172">Une fois les pages et les URL publiées, collecte des URL à utiliser pour les configurations de stratégie Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="43bfb-172">After the pages and URLs are published, collect the URLs that must be used for the Azure AD B2C policy configurations.</span></span> <span data-ttu-id="43bfb-173">Un suffixe **?preloadscripts=true** sera ajouté à chaque URL utilisée.</span><span class="sxs-lookup"><span data-stu-id="43bfb-173">A **?preloadscripts=true** suffix will be added to every URL when it's used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43bfb-174">Ne réutilisez pas les en-têtes et pieds de page universels avec des liens associés.</span><span class="sxs-lookup"><span data-stu-id="43bfb-174">Don't reuse universal headers and footers that have relative links.</span></span> <span data-ttu-id="43bfb-175">Comme ces pages sont hébergées dans le domaine Azure AD B2C lorsqu'elles sont utilisées, seules les URL absolues doivent être utilisées pour tous les liens.</span><span class="sxs-lookup"><span data-stu-id="43bfb-175">Because these pages will be hosted in the Azure AD B2C domain when they are used, only absolute URLs should be used for all links.</span></span>

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a><span data-ttu-id="43bfb-176">Configurer des stratégies Azure AD B2C avec des informations personnalisées de page</span><span class="sxs-lookup"><span data-stu-id="43bfb-176">Configure Azure AD B2C policies with custom page information</span></span> 

<span data-ttu-id="43bfb-177">Dans le portail Azure, revenez à la page **Azure AD B2C**, puis, dans le menu, sous **Stratégies**, sélectionnez **Flux utilisateurs (stratégies)**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-177">In the Azure portal, return to the **Azure AD B2C** page, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a><span data-ttu-id="43bfb-178">Mettez à jour la stratégie « Inscription et connexion » avec les informations personnalisées de page</span><span class="sxs-lookup"><span data-stu-id="43bfb-178">Update the "Sign up and sign in" policy with custom page information</span></span>

<span data-ttu-id="43bfb-179">Pour mettre à jour la stratégie « Inscription et connexion » avec les informations personnalisées de page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="43bfb-179">To update the "Sign up and sign in" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="43bfb-180">Dans la stratégie **Inscription et connexion** que vous avez définie précédemment, dans le volet de navigation, sélectionnez **Dispositions de page**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-180">In the **Sign in and sign up** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="43bfb-181">Sélectionnez la disposition **Page d'inscription ou de connexion unifiée**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-181">Select the **Unified sign up or sign in page** layout.</span></span>
1. <span data-ttu-id="43bfb-182">Définissez l'option **Utiliser le contenu de la page personnalisé** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-182">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="43bfb-183">Dans le champ **URI de page personnalisée**, entrez l'URL d'inscription complète.</span><span class="sxs-lookup"><span data-stu-id="43bfb-183">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="43bfb-184">Incluez le suffixe **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-184">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="43bfb-185">Par exemple, entrez ``www.<my domain>.com/sign-in?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="43bfb-185">For example, enter ``www.<my domain>.com/sign-in?preloadscripts=true``.</span></span>
1. <span data-ttu-id="43bfb-186">Dans le champ **Version de la disposition de la page (aperçu)**, sélectionnez **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-186">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="43bfb-187">Sélectionnez la disposition **Page de connexion au compte local**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-187">Select the **Local account sign up page** layout.</span></span>
1. <span data-ttu-id="43bfb-188">Définissez l'option **Utiliser le contenu de la page personnalisé** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-188">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="43bfb-189">Dans le champ **URI de page personnalisée**, entrez l'URL d'inscription complète.</span><span class="sxs-lookup"><span data-stu-id="43bfb-189">In the **Custom page URI** field, enter the full sign-up URL.</span></span> <span data-ttu-id="43bfb-190">Incluez le suffixe **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-190">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="43bfb-191">Par exemple, entrez ``www.<my domain>.com/sign-up?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="43bfb-191">For example, enter ``www.<my domain>.com/sign-up?preloadscripts=true``.</span></span>
1. <span data-ttu-id="43bfb-192">Dans le champ **Version de la disposition de la page (aperçu)**, sélectionnez **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-192">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="43bfb-193">Dans la section **Attributs utilisateur**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="43bfb-193">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="43bfb-194">Pour les attributs **Adresse e-mail**, **Prénom**, et **Nom de famille**, sélectionnez **Non** dans le champ **Nécessite une vérification**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-194">For the **Email Address**, **Given Name**, and **Surname** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="43bfb-195">Pour les attributs **Prénom** et **Nom de famille**, sélectionnez **Non** dans le champ **Facultatif**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-195">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

    ![Configuration de la stratégie de page de connexion au compte local](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a><span data-ttu-id="43bfb-197">Mettez à jour la stratégie « Modification de profil » avec les informations personnalisées de page</span><span class="sxs-lookup"><span data-stu-id="43bfb-197">Update the "Profile editing" policy with custom page information</span></span>

<span data-ttu-id="43bfb-198">Pour mettre à jour la stratégie « Modification de profil » avec les informations personnalisées de page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="43bfb-198">To update the "Profile editing" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="43bfb-199">Dans la stratégie **Modification de profil** que vous avez définie précédemment, dans le volet de navigation, sélectionnez **Dispositions de page**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-199">In the **Profile Editing** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="43bfb-200">Sélectionnez la disposition **Page Modification de profil**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-200">Select the **Profile edit page** layout.</span></span>
1. <span data-ttu-id="43bfb-201">Définissez l'option **Utiliser le contenu de la page personnalisé** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-201">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="43bfb-202">Dans le champ **URI de page personnalisée**, entrez l'URL de modification de profil complète.</span><span class="sxs-lookup"><span data-stu-id="43bfb-202">In the **Custom page URI** field, enter the full profile edit URL.</span></span> <span data-ttu-id="43bfb-203">Incluez le suffixe **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-203">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="43bfb-204">Par exemple, entrez ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="43bfb-204">For example, enter ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span></span>
1. <span data-ttu-id="43bfb-205">Dans le champ **Version de la disposition de la page (aperçu)**, sélectionnez **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-205">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="43bfb-206">Dans la section **Attributs utilisateur**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="43bfb-206">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="43bfb-207">Pour les attributs **Adresse e-mail** et **Prénom**, sélectionnez **Non** dans le champ **Nécessite une vérification**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-207">For the **Email Address**, **Given Name** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="43bfb-208">Pour les attributs **Prénom** et **Nom de famille**, sélectionnez **Non** dans le champ **Facultatif**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-208">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

### <a name="update-the-password-reset-policy-with-custom-page-information"></a><span data-ttu-id="43bfb-209">Mettez à jour la stratégie « Réinitialisation du mot de passe » avec les informations personnalisées de page</span><span class="sxs-lookup"><span data-stu-id="43bfb-209">Update the "Password reset" policy with custom page information</span></span>

<span data-ttu-id="43bfb-210">Pour mettre à jour la stratégie « Réinitialisation du mot de passe » avec les informations personnalisées de page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="43bfb-210">To update the "Password reset" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="43bfb-211">Dans la stratégie **Réinitialisation du mot de passe** que vous avez définie précédemment, dans le volet de navigation, sélectionnez **Dispositions de page**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-211">In the **Password Reset** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="43bfb-212">Sélectionnez la disposition **Page Nouveau mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-212">Select the **New password page** layout.</span></span>
1. <span data-ttu-id="43bfb-213">Définissez l'option **Utiliser le contenu de la page personnalisé** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-213">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="43bfb-214">Dans le champ **URI de page personnalisée**, entrez l'URL de réinitialisation de mot de passe complète.</span><span class="sxs-lookup"><span data-stu-id="43bfb-214">In the **Custom page URI** field, enter the full password reset URL.</span></span> <span data-ttu-id="43bfb-215">Incluez le suffixe **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-215">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="43bfb-216">Par exemple, entrez ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="43bfb-216">For example, enter ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span></span>
1. <span data-ttu-id="43bfb-217">Dans le champ **Version de la disposition de la page (aperçu)**, sélectionnez **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-217">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="43bfb-218">Sélectionnez la disposition **Page de vérification de compte**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-218">Select the **Account verification page** layout.</span></span>
1. <span data-ttu-id="43bfb-219">Définissez l'option **Utiliser le contenu de la page personnalisé** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-219">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="43bfb-220">Dans le champ **URI de page personnalisée**, entrez l'URL de vérification de la réinitialisation de mot de passe complète.</span><span class="sxs-lookup"><span data-stu-id="43bfb-220">In the **Custom page URI** field, enter the full password reset verification URL.</span></span> <span data-ttu-id="43bfb-221">Incluez le suffixe **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-221">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="43bfb-222">Par exemple, entrez ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="43bfb-222">For example, enter ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span></span>
1. <span data-ttu-id="43bfb-223">Dans le champ **Version de la disposition de la page (aperçu)**, sélectionnez **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-223">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a><span data-ttu-id="43bfb-224">Personnaliser les chaînes de texte par défaut pour les étiquettes et les descriptions</span><span class="sxs-lookup"><span data-stu-id="43bfb-224">Customize default text strings for labels and descriptions</span></span>

<span data-ttu-id="43bfb-225">Dans le kit de démarrage, les modules de connexion sont préremplis avec des chaînes de texte par défaut pour les étiquettes et les descriptions.</span><span class="sxs-lookup"><span data-stu-id="43bfb-225">In the starter kit, sign in modules are prefilled with default text strings for the labels and descriptions.</span></span> <span data-ttu-id="43bfb-226">Vous pouvez personnaliser ces chaînes dans le kit de développement logiciel (SDK) en mettant à jour les valeurs dans le fichier global.json pour le module de connexion.</span><span class="sxs-lookup"><span data-stu-id="43bfb-226">You can customize these strings in the software development kit (SDK) by updating the values in the global.json file for the sign in module.</span></span>

<span data-ttu-id="43bfb-227">Par exemple, le texte par défaut pour le lien de mot de passe oublié est **Mot de passe oublié ?**.</span><span class="sxs-lookup"><span data-stu-id="43bfb-227">For example, the default text for the forgotten password link is **Forgotten password?**.</span></span> <span data-ttu-id="43bfb-228">Ce qui suit présente ce texte par défaut dans la page de connexion.</span><span class="sxs-lookup"><span data-stu-id="43bfb-228">The following shows this default text on the sign-in page.</span></span>

![Texte par défaut pour le lien de mot de passe oublié sur la page Connexion](./media/B2C_SignUp_ModuleFace.png)

<span data-ttu-id="43bfb-230">Toutefois, dans le fichier global.json pour le module de connexion du kit de démarrage, vous pouvez modifier le texte **Mot de passe oublié ?**, comme l'indique l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="43bfb-230">However, in the global.json file for the starter kit sign in module, you can edit the text to **Forgot Password?**, as shown in the following illustration.</span></span>

![Texte du lien mis à jour dans le fichier global.json du module de connexion](./media/B2C_CustomizingStringsForModule.png)

<span data-ttu-id="43bfb-232">Après avoir mis à jour le fichier global.json et publié vos modifications, le nouveau texte du lien s'affiche dans le module de connexion de la page de connexion à Commerce et en direct.</span><span class="sxs-lookup"><span data-stu-id="43bfb-232">After you update the global.json file and publish your changes, the new link text appears in the sign in module in both Commerce and on the live sign-in page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="43bfb-233">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="43bfb-233">Additional resources</span></span>

[<span data-ttu-id="43bfb-234">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="43bfb-234">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="43bfb-235">Déploiement d'un nouveau site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="43bfb-235">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="43bfb-236">Création d'un site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="43bfb-236">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="43bfb-237">Association d'un site en ligne avec un canal</span><span class="sxs-lookup"><span data-stu-id="43bfb-237">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="43bfb-238">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="43bfb-238">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="43bfb-239">Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="43bfb-239">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="43bfb-240">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="43bfb-240">Enable location-based store detection</span></span>](enable-store-detection.md)
