---
title: Conformité des cookies
description: Cette rubrique décrit les considérations relatives à la conformité des cookies et les stratégies par défaut incluses dans Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 06/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e1fa016dc9f46b048220f0f83e4b0783087de91e
ms.sourcegitcommit: c66c4c67a21e7d7d3a94a3fd766c3184b6e65c4e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2020
ms.locfileid: "3446911"
---
# <a name="cookie-compliance"></a><span data-ttu-id="46784-103">Conformité des cookies</span><span class="sxs-lookup"><span data-stu-id="46784-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="46784-104">Cette rubrique décrit les considérations relatives à la conformité des cookies et les stratégies par défaut incluses dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="46784-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="46784-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="46784-105">Overview</span></span>

<span data-ttu-id="46784-106">La confidentialité est un facteur important lorsque les technologies de suivi affectent les clients e-commerce.</span><span class="sxs-lookup"><span data-stu-id="46784-106">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="46784-107">En raison des normes de respect de la vie privée telles que le Règlement général sur la protection des données (RGPD) dans l'Union européenne (UE), les directives de confidentialité électroniques doivent être prises en compte pour tout site actif aujourd'hui.</span><span class="sxs-lookup"><span data-stu-id="46784-107">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="46784-108">Étant donné que de nombreux sites de commerce électronique sont accessibles par défaut à l'échelle mondiale, il est important que vous examiniez les normes de conformité de votre site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="46784-108">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="46784-109">Pour en savoir plus sur les principes de base utilisés par Microsoft pour la conformité des cookies, visitez le [Centre de gestion de la confidentialité Microsoft](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="46784-109">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="46784-110">Sur ce site, vous pouvez également obtenir plus d'informations sur les domaines de conformité et de gestion de la confidentialité.</span><span class="sxs-lookup"><span data-stu-id="46784-110">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="46784-111">Le tableau suivant montre la liste de référence actuelle des cookies placés par les sites Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="46784-111">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="46784-112">Nom du cookie</span><span class="sxs-lookup"><span data-stu-id="46784-112">Cookie name</span></span>                               | <span data-ttu-id="46784-113">Utilisation</span><span class="sxs-lookup"><span data-stu-id="46784-113">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="46784-114">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="46784-114">.AspNet.Cookies</span></span>                             | <span data-ttu-id="46784-115">Cookies d'authentification Store Microsoft Azure Active Directory (Azure AD) pour l'authentification unique (SSO).</span><span class="sxs-lookup"><span data-stu-id="46784-115">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="46784-116">Stocke les informations chiffrées de l'utilisateur principal (nom, prénom, e-mail).</span><span class="sxs-lookup"><span data-stu-id="46784-116">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="46784-117">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="46784-117">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="46784-118">ID du panier de magasin utilisé pour obtenir la liste des produits ajoutés à l'instance du panier.</span><span class="sxs-lookup"><span data-stu-id="46784-118">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="46784-119">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="46784-119">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="46784-120">Suivi du consentement de conformité des cookies.</span><span class="sxs-lookup"><span data-stu-id="46784-120">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="46784-121">ai_session</span><span class="sxs-lookup"><span data-stu-id="46784-121">ai_session</span></span>                                  | <span data-ttu-id="46784-122">Détecte le nombre de sessions d'activité de l'utilisateur qui ont inclus certaines pages et fonctionnalités de l'application.</span><span class="sxs-lookup"><span data-stu-id="46784-122">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="46784-123">ai_user</span><span class="sxs-lookup"><span data-stu-id="46784-123">ai_user</span></span>                                     | <span data-ttu-id="46784-124">Détecte le nombre de personnes qui ont utilisé l'application et ses fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="46784-124">Detects how many people used the app and its features.</span></span> <span data-ttu-id="46784-125">Les utilisateurs sont comptés à l'aide d'ID anonymes.</span><span class="sxs-lookup"><span data-stu-id="46784-125">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="46784-126">b2cru</span><span class="sxs-lookup"><span data-stu-id="46784-126">b2cru</span></span>                                       | <span data-ttu-id="46784-127">Stocke l'URL de redirection de manière dynamique.</span><span class="sxs-lookup"><span data-stu-id="46784-127">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="46784-128">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="46784-128">JSESSIONID</span></span>                                  | <span data-ttu-id="46784-129">Utilisé par le connecteur de paiement Adyen pour stocker la session utilisateur.</span><span class="sxs-lookup"><span data-stu-id="46784-129">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="46784-130">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="46784-130">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="46784-131">Authentification</span><span class="sxs-lookup"><span data-stu-id="46784-131">Authentication</span></span>                                               |
| <span data-ttu-id="46784-132">x-ms-cpim-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="46784-132">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="46784-133">Utilisé pour maintenir l'état de la demande.</span><span class="sxs-lookup"><span data-stu-id="46784-133">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="46784-134">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="46784-134">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="46784-135">Jeton de falsification de requête intersites (CRSF) utilisé pour la protection contre CRSF.</span><span class="sxs-lookup"><span data-stu-id="46784-135">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="46784-136">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="46784-136">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="46784-137">Utilisé pour acheminer les demandes vers l'instance de serveur d'authentification de production appropriée.</span><span class="sxs-lookup"><span data-stu-id="46784-137">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="46784-138">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="46784-138">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="46784-139">Utilisé pour acheminer les demandes vers l'instance de serveur d'authentification de production appropriée.</span><span class="sxs-lookup"><span data-stu-id="46784-139">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="46784-140">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="46784-140">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="46784-141">Utilisé pour acheminer les demandes vers l'instance de serveur d'authentification de production appropriée.</span><span class="sxs-lookup"><span data-stu-id="46784-141">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="46784-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="46784-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="46784-143">Utilisé pour maintenir la session SSO.</span><span class="sxs-lookup"><span data-stu-id="46784-143">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="46784-144">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="46784-144">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="46784-145">Utilisé pour le suivi des transactions (le nombre d'onglets ouverts s'authentifiant sur un site B2C), y compris la transaction en cours.</span><span class="sxs-lookup"><span data-stu-id="46784-145">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="46784-146">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="46784-146">Additional resources</span></span>

[<span data-ttu-id="46784-147">Fonctionnalités d'accessibilité</span><span class="sxs-lookup"><span data-stu-id="46784-147">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="46784-148">Vue d'ensemble de la conformité</span><span class="sxs-lookup"><span data-stu-id="46784-148">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="46784-149">Ajouter une page de stratégie de confidentialité</span><span class="sxs-lookup"><span data-stu-id="46784-149">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="46784-150">Remplacer les ID utilisateur associés aux modifications de contenu suivies</span><span class="sxs-lookup"><span data-stu-id="46784-150">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)
