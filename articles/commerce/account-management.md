---
title: Pages et modules de gestion de compte
description: Cette rubrique couvre les pages et les modules de gestion de compte dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3986505a7e0e8d33d5b8ff2c06f493335731a8d9
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785376"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="94ffd-103">Pages et modules de gestion de compte</span><span class="sxs-lookup"><span data-stu-id="94ffd-103">Account management pages and modules</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="94ffd-104">Cette rubrique couvre les pages et les modules de gestion de compte dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="94ffd-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="94ffd-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="94ffd-105">Overview</span></span>

<span data-ttu-id="94ffd-106">La gestion de compte fait référence à un groupe de pages qui permet de gérer des informations liées à un compte utilisateur dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="94ffd-106">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="94ffd-107">Les pages de gestion de compte incluent la page de destination de la gestion de compte, la page de profil utilisateur, la page d'adresse de l'utilisateur, la page historique de commande, la page des détails de commande, la page de fidélité, et la page de liste de souhaits.</span><span class="sxs-lookup"><span data-stu-id="94ffd-107">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="94ffd-108">Page de destination de gestion de compte</span><span class="sxs-lookup"><span data-stu-id="94ffd-108">Account management landing page</span></span>

<span data-ttu-id="94ffd-109">La page de destination de gestion de compte utilise les modules suivants :</span><span class="sxs-lookup"><span data-stu-id="94ffd-109">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="94ffd-110">**Emplacement de contenu** – Ce module est un module de conteneur contenant tous les modules sur la page de destination de gestion de compte.</span><span class="sxs-lookup"><span data-stu-id="94ffd-110">**Content placement** – This module is a container module that holds all the modules on the account management landing page.</span></span>
- <span data-ttu-id="94ffd-111">**Article de bienvenue de compte** – Ce module permet de fournir un message de bienvenue dans la page de gestion de compte.</span><span class="sxs-lookup"><span data-stu-id="94ffd-111">**Account welcome item** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="94ffd-112">Il inclut des propriétés pour l'en-tête et la taille de vignette.</span><span class="sxs-lookup"><span data-stu-id="94ffd-112">It includes properties for the heading and the tile size.</span></span> <span data-ttu-id="94ffd-113">La propriété **Taille de vignette** définit la largeur du module dans le module de placement de contenu.</span><span class="sxs-lookup"><span data-stu-id="94ffd-113">The **Tile size** property defines the width of the module in the content placement module.</span></span> <span data-ttu-id="94ffd-114">La plage de valeurs de **1** à **12**, où **12** représente la largeur totale du conteneur de placement de contenu.</span><span class="sxs-lookup"><span data-stu-id="94ffd-114">Values range from **1** through **12**, where **12** represents the full width of the content placement container.</span></span>
- <span data-ttu-id="94ffd-115">**Article de placement de commande de compte** – Ce module permet de fournir une synthèse du nombre de commandes passées par compte d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94ffd-115">**Account order placement item** – This module is used to provide a summary of the number of orders that have been placed by the user account.</span></span> <span data-ttu-id="94ffd-116">Il inclut des propriétés pour l'en-tête, la taille de vignette et le lien « détails de la vue ».</span><span class="sxs-lookup"><span data-stu-id="94ffd-116">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="94ffd-117">Le lien « détails de la vue » doit être configuré pour rediriger à la page Historique de l'ordre.</span><span class="sxs-lookup"><span data-stu-id="94ffd-117">The "view details" link should be configured to redirect to the order history page.</span></span>
- <span data-ttu-id="94ffd-118">**Article de placement de profil de compte** – Ce module permet de fournir une synthèse du profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94ffd-118">**Account profile placement item** – This module is used to provide a summary of the user profile.</span></span> <span data-ttu-id="94ffd-119">Il inclut des propriétés pour l'en-tête, la taille de vignette et le lien « détails de la vue ».</span><span class="sxs-lookup"><span data-stu-id="94ffd-119">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="94ffd-120">Le lien « détails de la vue » doit être configuré pour rediriger à la page de profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94ffd-120">The "view details" link should be configured to redirect to the user profile page.</span></span>
- <span data-ttu-id="94ffd-121">**Article de liste de souhaits du compte** – Ce module permet de fournir une synthèse des articles de la liste de souhaits du client.</span><span class="sxs-lookup"><span data-stu-id="94ffd-121">**Account wishlist item** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="94ffd-122">Par exemple, il peut indiquer, « vous avez 10 articles dans votre liste de souhaits ».</span><span class="sxs-lookup"><span data-stu-id="94ffd-122">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="94ffd-123">Il inclut des propriétés pour l'en-tête, la taille de vignette et le lien « détails de la vue ».</span><span class="sxs-lookup"><span data-stu-id="94ffd-123">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="94ffd-124">Le lien « détails de la vue » doit être configuré pour rediriger à la page de liste de souhaits.</span><span class="sxs-lookup"><span data-stu-id="94ffd-124">The "view details" link should be configured to redirect to the wish list page.</span></span>
- <span data-ttu-id="94ffd-125">**Article d'adresse du compte** – Ce module permet de fournir une synthèse des adresses de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94ffd-125">**Account address item** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="94ffd-126">Par exemple, il peut indiquer, « vous avez 2 adresses ajoutées à votre compte. »</span><span class="sxs-lookup"><span data-stu-id="94ffd-126">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="94ffd-127">Il inclut des propriétés pour l'en-tête, la taille de vignette et le lien « détails de la vue ».</span><span class="sxs-lookup"><span data-stu-id="94ffd-127">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="94ffd-128">Le lien « détails de la vue » doit être configuré pour rediriger à la page d'adresse.</span><span class="sxs-lookup"><span data-stu-id="94ffd-128">The "view details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="94ffd-129">**Article de fidélité du compte** – Ce module permet d'afficher et de lier vers les informations du programme de fidélité.</span><span class="sxs-lookup"><span data-stu-id="94ffd-129">**Account loyalty item** – This module is used to show and link to loyalty program information.</span></span> <span data-ttu-id="94ffd-130">Il inclut des propriétés pour l'en-tête, la taille de vignette et le lien « détails de la vue » et le lien « devenir membre ».</span><span class="sxs-lookup"><span data-stu-id="94ffd-130">It includes properties for the heading, the tile size, the "view details" link, and the "become a member" link.</span></span> <span data-ttu-id="94ffd-131">Le lien « détails de la vue » doit être configuré pour rediriger à la page de fidélité.</span><span class="sxs-lookup"><span data-stu-id="94ffd-131">The "view details" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="94ffd-132">Le lien « devenir membre » doit être configuré pour redirection vers une page où les utilisateurs peuvent rejoindre le programme de fidélité.</span><span class="sxs-lookup"><span data-stu-id="94ffd-132">The "become a member" link should be configured to redirect to a page where users can join the loyalty program.</span></span>

### <a name="order-history-page"></a><span data-ttu-id="94ffd-133">Page Historique des commandes</span><span class="sxs-lookup"><span data-stu-id="94ffd-133">Order history page</span></span>

<span data-ttu-id="94ffd-134">La page Historique des commandes utilise le module Historique des commandes pour afficher toutes les commandes récentes que l'utilisateur a passées.</span><span class="sxs-lookup"><span data-stu-id="94ffd-134">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="94ffd-135">Page de détails de la commande</span><span class="sxs-lookup"><span data-stu-id="94ffd-135">Order details page</span></span>

<span data-ttu-id="94ffd-136">La page de détails de la commande fournit des informations détaillées pour chaque commande et est accessible depuis de la page Historique des commandes.</span><span class="sxs-lookup"><span data-stu-id="94ffd-136">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="94ffd-137">Elle utilise le module Détails de la commande, qui nécessite l'ID ventes ou de l'ID transaction pour récupérer les détails de la commande.</span><span class="sxs-lookup"><span data-stu-id="94ffd-137">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="94ffd-138">Page Profil utilisateur</span><span class="sxs-lookup"><span data-stu-id="94ffd-138">User profile page</span></span>

<span data-ttu-id="94ffd-139">La page Profil utilisateur affiche les détails du profil utilisateur, tels que le nom d'utilisateur et l'adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="94ffd-139">The user profile page shows user account details, such as user's name and email address.</span></span> <span data-ttu-id="94ffd-140">Elle utilise le module de profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94ffd-140">It uses the user profile module.</span></span> <span data-ttu-id="94ffd-141">Bien que l'adresse e-mail ne puisse pas être supprimée, elle peut être désactivée.</span><span class="sxs-lookup"><span data-stu-id="94ffd-141">Although the email address can't be removed, it can be edited.</span></span>

### <a name="user-address-page"></a><span data-ttu-id="94ffd-142">Page Adresse de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="94ffd-142">User address page</span></span>

<span data-ttu-id="94ffd-143">Les page d'adresse de l'utilisateur affiche la liste des adresses associées au compte d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94ffd-143">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="94ffd-144">L'utilisateur fournit ces adresses lors du contrôle ou les a ajoutées directement dans cette page.</span><span class="sxs-lookup"><span data-stu-id="94ffd-144">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="94ffd-145">Le module d'adresse de l'utilisateur permet d'ajouter et de modifier des adresses, définir l'adresse principale, et afficher des adresses existantes dans la page.</span><span class="sxs-lookup"><span data-stu-id="94ffd-145">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="94ffd-146">Page Liste de souhaits</span><span class="sxs-lookup"><span data-stu-id="94ffd-146">Wish list page</span></span>

<span data-ttu-id="94ffd-147">La page de liste de souhaits affichent les articles ajoutés à la liste de souhaits du client.</span><span class="sxs-lookup"><span data-stu-id="94ffd-147">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="94ffd-148">Elle utilise le module de liste de souhaits pour afficher des articles de la liste de souhaits.</span><span class="sxs-lookup"><span data-stu-id="94ffd-148">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="94ffd-149">Page du programme de fidélité</span><span class="sxs-lookup"><span data-stu-id="94ffd-149">Loyalty page</span></span>

<span data-ttu-id="94ffd-150">La page de fidélité permet aux clients de rejoindre un programme de fidélité ou, s'ils sont déjà des membres du programme de fidélité, affiche les détails du programme.</span><span class="sxs-lookup"><span data-stu-id="94ffd-150">The loyalty page lets customers join a loyalty program or, if they are already loyalty program members, view their program details.</span></span> <span data-ttu-id="94ffd-151">Ils peuvent également afficher les points qu'il a acquis ou remboursés dans des transactions récentes.</span><span class="sxs-lookup"><span data-stu-id="94ffd-151">They can also view the points that they have earned and redeemed in recent transactions.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="94ffd-152">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="94ffd-152">Additional resources</span></span>

[<span data-ttu-id="94ffd-153">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="94ffd-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="94ffd-154">Module Container</span><span class="sxs-lookup"><span data-stu-id="94ffd-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="94ffd-155">Module Acheter la boîte</span><span class="sxs-lookup"><span data-stu-id="94ffd-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="94ffd-156">Module Panier</span><span class="sxs-lookup"><span data-stu-id="94ffd-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="94ffd-157">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="94ffd-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="94ffd-158">Module Confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="94ffd-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="94ffd-159">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="94ffd-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="94ffd-160">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="94ffd-160">Footer module</span></span>](author-footer-module.md)
