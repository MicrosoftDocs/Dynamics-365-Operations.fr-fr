---
title: Pages et modules de gestion de compte
description: Cette rubrique couvre les pages et les modules de gestion de compte dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6c465b8883438eee886b177274bf89ddb86aa00b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980554"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="04d3e-103">Pages et modules de gestion de compte</span><span class="sxs-lookup"><span data-stu-id="04d3e-103">Account management pages and modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="04d3e-104">Cette rubrique couvre les pages et les modules de gestion de compte dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="04d3e-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="04d3e-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="04d3e-105">Overview</span></span>

<span data-ttu-id="04d3e-106">La gestion de compte fait référence à un groupe de pages qui permet de gérer des informations liées à un compte utilisateur dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="04d3e-106">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="04d3e-107">Les pages de gestion de compte incluent la page de destination de la gestion de compte, la page de profil utilisateur, la page d'adresse de l'utilisateur, la page historique de commande, la page des détails de commande, la page de fidélité, et la page de liste de souhaits.</span><span class="sxs-lookup"><span data-stu-id="04d3e-107">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="04d3e-108">Page de destination de gestion de compte</span><span class="sxs-lookup"><span data-stu-id="04d3e-108">Account management landing page</span></span>

<span data-ttu-id="04d3e-109">La page de destination de gestion de compte utilise les modules suivants :</span><span class="sxs-lookup"><span data-stu-id="04d3e-109">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="04d3e-110">**Conteneur** - Tous les modules de page de destination de gestion de compte doivent être placés dans un conteneur.</span><span class="sxs-lookup"><span data-stu-id="04d3e-110">**Container** - All account management landing page modules should be placed within a container.</span></span> 
- <span data-ttu-id="04d3e-111">**Vignette de bienvenue de compte** – Ce module permet de fournir un message de bienvenue dans la page de gestion de compte.</span><span class="sxs-lookup"><span data-stu-id="04d3e-111">**Account welcome tile** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="04d3e-112">Il inclut des propriétés pour l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="04d3e-112">It includes properties for the heading.</span></span>
- <span data-ttu-id="04d3e-113">**Vignette générique de compte** - Ce module peut être utilisé pour fournir des en-têtes et des liens vers des pages de gestion de compte, telles que les pages « Historique des commandes » ou « Mon profil ».</span><span class="sxs-lookup"><span data-stu-id="04d3e-113">**Account generic tile** - This module can be used to provide headings and links to account management pages, such as the "Order history" or "My profile" pages.</span></span> <span data-ttu-id="04d3e-114">Le module de vignette générique peut être utilisé pour configurer une vignette pour n'importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="04d3e-114">The generic tile module can be used to configure a tile for any page.</span></span> <span data-ttu-id="04d3e-115">Dans Fabrikam, ce module est utilisé pour les liens vers la page « Historique des commandes » et « Mon profil » sur la page de destination de la gestion des comptes.</span><span class="sxs-lookup"><span data-stu-id="04d3e-115">In Fabrikam, this module is used for "Order history" and "My profile" page links on the account management landing page.</span></span>
- <span data-ttu-id="04d3e-116">**Vignette de liste de souhaits du compte** – Ce module permet de fournir une synthèse des articles de la liste de souhaits du client.</span><span class="sxs-lookup"><span data-stu-id="04d3e-116">**Account wishlist tile** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="04d3e-117">Par exemple, il peut indiquer, « vous avez 10 articles dans votre liste de souhaits ».</span><span class="sxs-lookup"><span data-stu-id="04d3e-117">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="04d3e-118">Elle inclut des propriétés pour l'en-tête et le lien « Afficher les détails ».</span><span class="sxs-lookup"><span data-stu-id="04d3e-118">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="04d3e-119">Le lien « Afficher les détails » doit être configuré pour rediriger vers la page de liste de souhaits.</span><span class="sxs-lookup"><span data-stu-id="04d3e-119">The "View details" link should be configured to redirect to the wish list page.</span></span> 
- <span data-ttu-id="04d3e-120">**Vignette d'adresse du compte** – Ce module permet de fournir une synthèse des adresses de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="04d3e-120">**Account address tile** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="04d3e-121">Par exemple, il peut indiquer, « vous avez 2 adresses ajoutées à votre compte. »</span><span class="sxs-lookup"><span data-stu-id="04d3e-121">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="04d3e-122">Elle inclut des propriétés pour l'en-tête et le lien « Afficher les détails ».</span><span class="sxs-lookup"><span data-stu-id="04d3e-122">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="04d3e-123">Le lien « Afficher les détails » doit être configuré pour rediriger à la page d'adresse.</span><span class="sxs-lookup"><span data-stu-id="04d3e-123">The "View details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="04d3e-124">**Vignette de fidélité du compte** – Ce module permet d'afficher et de lier vers les informations du programme de fidélité.</span><span class="sxs-lookup"><span data-stu-id="04d3e-124">**Account loyalty tile** – This module is used to display and link to loyalty program information.</span></span> <span data-ttu-id="04d3e-125">Cette vignette a deux états : un état affiche des liens pour rejoindre un programme de fidélité si l'utilisateur n'est pas déjà membre.</span><span class="sxs-lookup"><span data-stu-id="04d3e-125">This tile has two states: one state shows links to join a loyalty progam if the user is not a member already.</span></span> <span data-ttu-id="04d3e-126">L'autre état affiche des liens pour afficher la page des détails de fidélité lorsque l'utilisateur est déjà membre.</span><span class="sxs-lookup"><span data-stu-id="04d3e-126">The other state shows links to view the loyalty details page when the user is already a member.</span></span> <span data-ttu-id="04d3e-127">Les propriétés incluent l'en-tête, le lien « S'inscrire » et le lien « Afficher la fidélité ».</span><span class="sxs-lookup"><span data-stu-id="04d3e-127">Properties include the heading, the "Sign-up" link, and the "View loyalty" link.</span></span> <span data-ttu-id="04d3e-128">Le lien « Afficher la fidélité » doit être configuré pour rediriger vers la page de fidélité.</span><span class="sxs-lookup"><span data-stu-id="04d3e-128">The "View loyalty" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="04d3e-129">Le lien « S'inscrire » doit être configuré pour rediriger vers une page où les utilisateurs peuvent rejoindre le programme de fidélité.</span><span class="sxs-lookup"><span data-stu-id="04d3e-129">The "Sign-up" link should be configured to redirect to a page where users can join the loyalty program.</span></span> 

### <a name="order-history-page"></a><span data-ttu-id="04d3e-130">Page Historique des commandes</span><span class="sxs-lookup"><span data-stu-id="04d3e-130">Order history page</span></span>

<span data-ttu-id="04d3e-131">La page Historique des commandes utilise le module Historique des commandes pour afficher toutes les commandes récentes que l'utilisateur a passées.</span><span class="sxs-lookup"><span data-stu-id="04d3e-131">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="04d3e-132">Page de détails de la commande</span><span class="sxs-lookup"><span data-stu-id="04d3e-132">Order details page</span></span>

<span data-ttu-id="04d3e-133">La page de détails de la commande fournit des informations détaillées pour chaque commande et est accessible depuis de la page Historique des commandes.</span><span class="sxs-lookup"><span data-stu-id="04d3e-133">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="04d3e-134">Elle utilise le module Détails de la commande, qui nécessite l'ID ventes ou de l'ID transaction pour récupérer les détails de la commande.</span><span class="sxs-lookup"><span data-stu-id="04d3e-134">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="04d3e-135">Page Profil utilisateur</span><span class="sxs-lookup"><span data-stu-id="04d3e-135">User profile page</span></span>

<span data-ttu-id="04d3e-136">La page Profil utilisateur affiche les détails du profil utilisateur, tels qu'un nom d'utilisateur et l'adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="04d3e-136">The user profile page shows user account details, such as a user's name and email address.</span></span> <span data-ttu-id="04d3e-137">Il utilise les détails du profil utilisateur et les modules de modification du profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="04d3e-137">It uses the user profile details and user profile edit modules.</span></span> <span data-ttu-id="04d3e-138">Bien que l'adresse e-mail ne puisse pas être supprimée, elle peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="04d3e-138">Although the email address can't be removed, it can be edited.</span></span> <span data-ttu-id="04d3e-139">La page du profil utilisateur affiche également les préférences de l'utilisateur qui permettent à un utilisateur d'activer ou de désactiver certaines fonctionnalités, telles que la personnalisation des listes de recommandations.</span><span class="sxs-lookup"><span data-stu-id="04d3e-139">The user profile page also shows user preferences that enable a user to opt in or opt out from certain features, such as personalization of recommendation lists.</span></span> 

### <a name="user-address-page"></a><span data-ttu-id="04d3e-140">Page Adresse de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="04d3e-140">User address page</span></span>

<span data-ttu-id="04d3e-141">Les page d'adresse de l'utilisateur affiche la liste des adresses associées au compte d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="04d3e-141">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="04d3e-142">L'utilisateur fournit ces adresses lors du contrôle ou les a ajoutées directement dans cette page.</span><span class="sxs-lookup"><span data-stu-id="04d3e-142">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="04d3e-143">Le module d'adresse de l'utilisateur permet d'ajouter et de modifier des adresses, définir l'adresse principale, et afficher des adresses existantes dans la page.</span><span class="sxs-lookup"><span data-stu-id="04d3e-143">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="04d3e-144">Page Liste de souhaits</span><span class="sxs-lookup"><span data-stu-id="04d3e-144">Wish list page</span></span>

<span data-ttu-id="04d3e-145">La page de liste de souhaits affichent les articles ajoutés à la liste de souhaits du client.</span><span class="sxs-lookup"><span data-stu-id="04d3e-145">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="04d3e-146">Elle utilise le module de liste de souhaits pour afficher des articles de la liste de souhaits.</span><span class="sxs-lookup"><span data-stu-id="04d3e-146">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="04d3e-147">Page du programme de fidélité</span><span class="sxs-lookup"><span data-stu-id="04d3e-147">Loyalty page</span></span>

<span data-ttu-id="04d3e-148">La page de fidélité permet aux clients d'afficher les détails de leur programme s'ils sont déjà des membres du programme de fidélité.</span><span class="sxs-lookup"><span data-stu-id="04d3e-148">The loyalty page lets customers view their loyalty details if they are already loyalty program members.</span></span> <span data-ttu-id="04d3e-149">Ils peuvent également afficher les points qu'il a acquis ou remboursés dans des transactions récentes.</span><span class="sxs-lookup"><span data-stu-id="04d3e-149">They can also view the points that they have earned and redeemed in recent transactions.</span></span> <span data-ttu-id="04d3e-150">La page utilise le module de détails du programme de fidélité pour présenter les détails de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="04d3e-150">The page uses the loyalty details module to showcase the loyalty details.</span></span> 

<span data-ttu-id="04d3e-151">Pour rejoindre le programme de fidélité, une page marketing peut être créée avec des modules d'inscription et de conditions de fidélité.</span><span class="sxs-lookup"><span data-stu-id="04d3e-151">To join loyalty program, a marketing page can be created with loyalty sign up and loyalty terms modules.</span></span> <span data-ttu-id="04d3e-152">Si l'utilisateur n'est pas membre d'un programme de fidélité, ces modules permettront à l'utilisateur de s'inscrire.</span><span class="sxs-lookup"><span data-stu-id="04d3e-152">If the user is not a member of a loyalty program, these modules will enable the user to sign up.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="04d3e-153">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="04d3e-153">Additional resources</span></span>

[<span data-ttu-id="04d3e-154">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="04d3e-154">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="04d3e-155">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="04d3e-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="04d3e-156">Module Zone d’achat</span><span class="sxs-lookup"><span data-stu-id="04d3e-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="04d3e-157">Module Panier</span><span class="sxs-lookup"><span data-stu-id="04d3e-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="04d3e-158">Module Validation</span><span class="sxs-lookup"><span data-stu-id="04d3e-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="04d3e-159">Module Confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="04d3e-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="04d3e-160">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="04d3e-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="04d3e-161">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="04d3e-161">Footer module</span></span>](author-footer-module.md)
