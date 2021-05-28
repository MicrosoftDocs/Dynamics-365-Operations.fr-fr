---
title: Configurer un environnement de développement d’e-commerce pour déboguer sur une machine virtuelle Retail Server Niveau 1
description: Cette rubrique explique comment configurer un environnement de développement d’e-commerce pour déboguer sur une machine virtuelle (VM) Retail Server Niveau 1.
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
ms.openlocfilehash: 38a616c418c3b32490c9adaf69a69af0d47d3478
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019444"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a><span data-ttu-id="a3fbc-103">Configurer un environnement de développement d’e-commerce pour déboguer sur une machine virtuelle Retail Server Niveau 1</span><span class="sxs-lookup"><span data-stu-id="a3fbc-103">Set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a3fbc-104">Cette rubrique explique comment configurer un environnement de développement d’e-commerce pour déboguer sur une machine virtuelle (VM) Retail Server Niveau 1.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-104">This topic explains how to set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine (VM).</span></span>

## <a name="description"></a><span data-ttu-id="a3fbc-105">Description</span><span class="sxs-lookup"><span data-stu-id="a3fbc-105">Description</span></span>

<span data-ttu-id="a3fbc-106">Les environnements Microsoft Dynamics 365 Commerce de niveau 1 sont généralement déployés pour Commerce Runtime (CRT) et le développement de l’extension de point de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="a3fbc-106">Microsoft Dynamics 365 Commerce Tier 1 environments are typically deployed for Commerce runtime (CRT) and point of sale (POS) extension development.</span></span> <span data-ttu-id="a3fbc-107">Ce sont des environnements autonomes.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-107">They are standalone environments.</span></span> <span data-ttu-id="a3fbc-108">En raison de la nature logiciel en tant que service (SaaS) de l’architecture, ils n’incluent pas de composants e-commerce.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-108">Because of the software as a service (SaaS) nature of the architecture, they don't include e-commerce components.</span></span>

<span data-ttu-id="a3fbc-109">Dans certains scénarios, vous souhaiterez peut-être tester les appels aux extensions dans un environnement de niveau 1, afin de pouvoir déboguer des extensions à partir de composants e-commerce.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-109">In some scenarios, you might want to test calls to extensions in a Tier 1 environment, so that you can debug extensions from e-commerce components.</span></span> <span data-ttu-id="a3fbc-110">Pour des instructions générales, voir [Déboguer dans un environnement de développement Commerce de niveau 1](../e-commerce-extensibility/debug-tier-1.md).</span><span class="sxs-lookup"><span data-stu-id="a3fbc-110">For general instructions, see [Debug against a Tier 1 Commerce development environment](../e-commerce-extensibility/debug-tier-1.md).</span></span>

<span data-ttu-id="a3fbc-111">Lorsque vous déboguez dans un environnement de niveau 1, étant donné que le site appelle maintenant un autre serveur Retail Server, les appels entre serveurs peuvent provoquer diverses erreurs liées à la stratégie de sécurité du contenu.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-111">When you debug against a Tier 1 environment, because the site is now calling a different Retail Server, cross-server calls might cause various errors that are related to the content security policy.</span></span>

<span data-ttu-id="a3fbc-112">L’illustration suivante montre un exemple d’erreur qui peut se produire lorsqu’une variante est sélectionnée sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-112">The following illustration shows an example of an error that might occur when a variant is selected on a product details page.</span></span>

![Erreur lorsqu’une variante est sélectionnée sur une page de détails du produit](media/unhandled-rejection-error.jpg)

<span data-ttu-id="a3fbc-114">L’illustration suivante montre un exemple d’erreur similaire dans les outils de débogage d’un navigateur (outils de développement F12).</span><span class="sxs-lookup"><span data-stu-id="a3fbc-114">The following illustration shows an example of a similar error in a browser's debugger tools (F12 Developer Tools).</span></span> <span data-ttu-id="a3fbc-115">Le message d’erreur mentionne la violation de la directive de stratégie de sécurité du contenu.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-115">The error message mentions violation of the content security policy directive.</span></span>

![Erreur des outils de débogage](media/debugger-tools-error.JPG)

## <a name="resolution"></a><span data-ttu-id="a3fbc-117">Résolution</span><span class="sxs-lookup"><span data-stu-id="a3fbc-117">Resolution</span></span>

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a><span data-ttu-id="a3fbc-118">Désactiver la stratégie de sécurité du contenu pour le site dans le générateur de site Commerce</span><span class="sxs-lookup"><span data-stu-id="a3fbc-118">Disable the content security policy for the site in Commerce site builder</span></span>

1. <span data-ttu-id="a3fbc-119">Sélectionnez le site sur lequel vous travaillez.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-119">Select the site that you're working on.</span></span>
1. <span data-ttu-id="a3fbc-120">Sélectionnez **Paramètres**, puis **Extensions**.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-120">Select **Settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="a3fbc-121">Sur l’onglet **Stratégie de sécurité du contenu**, sélectionnez **Désactiver la stratégie de sécurité du contenu**.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-121">On the **Content security policy** tab, select **Disable content security policy**.</span></span>
1. <span data-ttu-id="a3fbc-122">Sélectionnez **Enregistrer et publier**.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-122">Select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="a3fbc-123">La connexion B2C ne fonctionnera pas dans un environnement de développement local.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-123">Business-to-consumer (B2C) sign-in won't work in a local development environment.</span></span> <span data-ttu-id="a3fbc-124">Cependant, vous pouvez utiliser des caisses invité ou créer des simulations de page pour simuler la connexion d’un utilisateur si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a3fbc-124">However, you can use guest checkouts or build page mocks to simulate a user sign-in as required.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a3fbc-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a3fbc-125">Additional resources</span></span>

[<span data-ttu-id="a3fbc-126">Démarrer avec le développement d’extensibilité en ligne de l’e-commerce</span><span class="sxs-lookup"><span data-stu-id="a3fbc-126">Get started with e-commerce online extensibility development</span></span>](../e-commerce-extensibility/sdk-getting-started.md)

[<span data-ttu-id="a3fbc-127">Gérer la stratégie de sécurité du contenu (CSP) sur le site d’e-commerce</span><span class="sxs-lookup"><span data-stu-id="a3fbc-127">Manage content security policy (CSP) on e-commerce site</span></span>](../manage-csp.md)
