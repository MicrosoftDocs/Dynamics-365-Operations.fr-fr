---
title: Conformité des cookies
description: Cette rubrique décrit les considérations relatives à la conformité des cookies et les stratégies par défaut incluses dans Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: 4f54b9b8130a167dbecdb13fccd7039f827f6ed0
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761319"
---
# <a name="cookie-compliance"></a><span data-ttu-id="42c75-103">Conformité des cookies</span><span class="sxs-lookup"><span data-stu-id="42c75-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="42c75-104">Cette rubrique décrit les considérations relatives à la conformité des cookies et les stratégies par défaut incluses dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="42c75-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="42c75-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="42c75-105">Overview</span></span>

<span data-ttu-id="42c75-106">La confidentialité est un facteur important lorsque les technologies de suivi affectent les clients e-commerce.</span><span class="sxs-lookup"><span data-stu-id="42c75-106">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="42c75-107">En raison des normes de respect de la vie privée telles que le Règlement général sur la protection des données (RGPD) dans l’Union européenne (UE), les directives de confidentialité électroniques doivent être prises en compte pour tout site actif aujourd’hui.</span><span class="sxs-lookup"><span data-stu-id="42c75-107">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="42c75-108">Étant donné que de nombreux sites de commerce électronique sont accessibles par défaut à l’échelle mondiale, il est important que vous examiniez les normes de conformité de votre site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="42c75-108">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="42c75-109">Pour en savoir plus sur les principes de base utilisés par Microsoft pour la conformité des cookies, visitez le [Centre de gestion de la confidentialité Microsoft](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="42c75-109">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="42c75-110">Sur ce site, vous pouvez également obtenir plus d’informations sur les domaines de conformité et de gestion de la confidentialité.</span><span class="sxs-lookup"><span data-stu-id="42c75-110">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="42c75-111">Le tableau suivant montre la liste de référence actuelle des cookies placés par les sites Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="42c75-111">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="42c75-112">Nom du cookie</span><span class="sxs-lookup"><span data-stu-id="42c75-112">Cookie name</span></span>                               | <span data-ttu-id="42c75-113">Utilisation</span><span class="sxs-lookup"><span data-stu-id="42c75-113">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="42c75-114">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="42c75-114">.AspNet.Cookies</span></span>                             | <span data-ttu-id="42c75-115">Cookies d’authentification Store Microsoft Azure Active Directory (Azure AD) pour l’authentification unique (SSO).</span><span class="sxs-lookup"><span data-stu-id="42c75-115">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="42c75-116">Stocke les informations chiffrées de l’utilisateur principal (nom, prénom, e-mail).</span><span class="sxs-lookup"><span data-stu-id="42c75-116">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="42c75-117">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="42c75-117">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="42c75-118">ID du panier de magasin utilisé pour obtenir la liste des produits ajoutés à l’instance du panier.</span><span class="sxs-lookup"><span data-stu-id="42c75-118">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="42c75-119">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="42c75-119">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="42c75-120">Suivi du consentement de conformité des cookies.</span><span class="sxs-lookup"><span data-stu-id="42c75-120">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="42c75-121">ai_session</span><span class="sxs-lookup"><span data-stu-id="42c75-121">ai_session</span></span>                                  | <span data-ttu-id="42c75-122">Détecte le nombre de sessions d’activité de l’utilisateur qui ont inclus certaines pages et fonctionnalités de l’application.</span><span class="sxs-lookup"><span data-stu-id="42c75-122">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="42c75-123">ai_user</span><span class="sxs-lookup"><span data-stu-id="42c75-123">ai_user</span></span>                                     | <span data-ttu-id="42c75-124">Détecte le nombre de personnes qui ont utilisé l’application et ses fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="42c75-124">Detects how many people used the app and its features.</span></span> <span data-ttu-id="42c75-125">Les utilisateurs sont comptés à l’aide d’ID anonymes.</span><span class="sxs-lookup"><span data-stu-id="42c75-125">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="42c75-126">b2cru</span><span class="sxs-lookup"><span data-stu-id="42c75-126">b2cru</span></span>                                       | <span data-ttu-id="42c75-127">Stocke l’URL de redirection de manière dynamique.</span><span class="sxs-lookup"><span data-stu-id="42c75-127">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="42c75-128">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="42c75-128">JSESSIONID</span></span>                                  | <span data-ttu-id="42c75-129">Utilisé par le connecteur de paiement Adyen pour stocker la session utilisateur.</span><span class="sxs-lookup"><span data-stu-id="42c75-129">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="42c75-130">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="42c75-130">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="42c75-131">Authentification</span><span class="sxs-lookup"><span data-stu-id="42c75-131">Authentication</span></span>                                               |
| <span data-ttu-id="42c75-132">x-ms-cpim-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="42c75-132">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="42c75-133">Utilisé pour maintenir l’état de la demande.</span><span class="sxs-lookup"><span data-stu-id="42c75-133">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="42c75-134">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="42c75-134">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="42c75-135">Jeton de falsification de requête intersites (CRSF) utilisé pour la protection contre CRSF.</span><span class="sxs-lookup"><span data-stu-id="42c75-135">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="42c75-136">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="42c75-136">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="42c75-137">Utilisé pour acheminer les demandes vers l’instance de serveur d’authentification de production appropriée.</span><span class="sxs-lookup"><span data-stu-id="42c75-137">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="42c75-138">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="42c75-138">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="42c75-139">Utilisé pour acheminer les demandes vers l’instance de serveur d’authentification de production appropriée.</span><span class="sxs-lookup"><span data-stu-id="42c75-139">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="42c75-140">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="42c75-140">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="42c75-141">Utilisé pour acheminer les demandes vers l’instance de serveur d’authentification de production appropriée.</span><span class="sxs-lookup"><span data-stu-id="42c75-141">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="42c75-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="42c75-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="42c75-143">Utilisé pour maintenir la session SSO.</span><span class="sxs-lookup"><span data-stu-id="42c75-143">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="42c75-144">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="42c75-144">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="42c75-145">Utilisé pour le suivi des transactions (le nombre d’onglets ouverts s’authentifiant sur un site B2C), y compris la transaction en cours.</span><span class="sxs-lookup"><span data-stu-id="42c75-145">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a><span data-ttu-id="42c75-146">Consentement aux cookies de l’utilisateur du site sur un site d’e-commerce</span><span class="sxs-lookup"><span data-stu-id="42c75-146">Site user cookie consent on an e-Commerce site</span></span> 

<span data-ttu-id="42c75-147">Si une fonctionnalité ou un module de site d’e-commerce utilise un cookie non essentiel, le consentement de l’utilisateur du site doit être obtenu avant que le cookie ne soit suivi.</span><span class="sxs-lookup"><span data-stu-id="42c75-147">If an e-Commerce site feature or module uses a non-essential cookie, a site user's consent must be obtained before the cookie is tracked.</span></span> <span data-ttu-id="42c75-148">Pour permettre aux utilisateurs du site de donner leur consentement aux cookies sur le site d’e-commerce, un auteur de site doit ajouter et configurer un module de consentement aux cookies dans le module d’en-tête de la page pour s’assurer que le consentement est demandé et reçu.</span><span class="sxs-lookup"><span data-stu-id="42c75-148">To allow site users to provide cookie consent on the e-Commerce site, a site author must add and configure a cookie consent module in the page's header module to ensure that the consent is prompted for and received.</span></span> <span data-ttu-id="42c75-149">Le consentement de l’utilisateur du site doit être donné avant qu’une fonctionnalité ou un module utilisant un cookie non essentiel puisse être affiché sur une page du site.</span><span class="sxs-lookup"><span data-stu-id="42c75-149">Site user consent must be given before a feature or module using a non-essential cookie can be rendered on a site page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="42c75-150">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="42c75-150">Additional resources</span></span>

[<span data-ttu-id="42c75-151">Fonctionnalités d’accessibilité</span><span class="sxs-lookup"><span data-stu-id="42c75-151">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="42c75-152">Vue d’ensemble de la conformité</span><span class="sxs-lookup"><span data-stu-id="42c75-152">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="42c75-153">Ajouter une page de stratégie de confidentialité</span><span class="sxs-lookup"><span data-stu-id="42c75-153">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="42c75-154">Remplacer les ID utilisateur associés aux modifications de contenu suivies</span><span class="sxs-lookup"><span data-stu-id="42c75-154">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)

[<span data-ttu-id="42c75-155">Module de consentement aux cookies</span><span class="sxs-lookup"><span data-stu-id="42c75-155">Cookie consent module</span></span>](cookie-consent-module.md) 
 
[<span data-ttu-id="42c75-156">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="42c75-156">Header module</span></span>](author-header-module.md)
