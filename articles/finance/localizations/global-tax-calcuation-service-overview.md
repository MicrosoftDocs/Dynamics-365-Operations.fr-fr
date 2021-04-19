---
title: Service de calcul des taxes (Version préliminaire)
description: Cette rubrique explique la portée et les fonctionnalités générales du service de calcul des taxes.
author: wangchen
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 518d3fda7b97e55d23beea6a1ba0e50b44a7aa0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818222"
---
# <a name="tax-calculation-service-preview"></a><span data-ttu-id="e23be-103">Service de calcul des taxes (Version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="e23be-103">Tax calculation service (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="e23be-104">Le service de calcul des taxes est un service multi-locataire hyper évolutif qui permet au moteur Global Tax Engine d’automatiser et de simplifier le processus de détermination et de calcul des taxes.</span><span class="sxs-lookup"><span data-stu-id="e23be-104">The tax calculation service is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="e23be-105">Le moteur de taxe est entièrement configurable.</span><span class="sxs-lookup"><span data-stu-id="e23be-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="e23be-106">Les éléments qui peuvent être configurés incluent, mais sans s’y limiter, le modèle de données taxables, le code taxe, la matrice d’applicabilité de la taxe et la formule de calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="e23be-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="e23be-107">Le moteur de taxe fonctionne sur la plateforme des services essentiels Microsoft Azure, et offre une technologie moderne et une évolutivité exponentielle.</span><span class="sxs-lookup"><span data-stu-id="e23be-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="e23be-108">Le service de calcul des taxes s’intègre à Dynamics 365 Finance et Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e23be-108">The tax calculation service integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="e23be-109">À terme, il s’intégrera également avec Dynamics 365 Project Operations, Dynamics 365 Commerce et d’autres applications propriétaires et tierces.</span><span class="sxs-lookup"><span data-stu-id="e23be-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="e23be-110">Le service de calcul des taxes est un moteur de taxe Microsoft qui offre une évolutivité exponentielle.</span><span class="sxs-lookup"><span data-stu-id="e23be-110">The tax calculation service is a Microsoft-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="e23be-111">Il peut vous aider à exécuter les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="e23be-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="e23be-112">Configurer le service de calcul des taxes via Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="e23be-112">Configure the tax calculation service through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="e23be-113">RCS est une version améliorée du concepteur de rapports électroniques (ER) et est disponible en tant que service autonome.</span><span class="sxs-lookup"><span data-stu-id="e23be-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="e23be-114">Configurer la matrice de taxe pour déterminer automatiquement les codes et les taux de taxe.</span><span class="sxs-lookup"><span data-stu-id="e23be-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="e23be-115">Configurer la matrice de taxe pour déterminer automatiquement le numéro d’immatriculation fiscale.</span><span class="sxs-lookup"><span data-stu-id="e23be-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="e23be-116">Configurer le concepteur de calcul de taxe pour définir des formules et des conditions.</span><span class="sxs-lookup"><span data-stu-id="e23be-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="e23be-117">Partager la solution de détermination et de calcul des taxes entre les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="e23be-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="e23be-118">Pour utiliser le service de calcul des taxes, installez le complément de service de calcul des taxes à partir de votre projet dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e23be-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="e23be-119">Terminez ensuite la configuration dans RCS et activez le service de calcul des taxes dans Finance and Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e23be-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="e23be-120">Pour plus d’informations, voir [Prise en main du service de taxe](https://go.microsoft.com/fwlink/?linkid=2138482).</span><span class="sxs-lookup"><span data-stu-id="e23be-120">For more information, see [Get started with tax service](https://go.microsoft.com/fwlink/?linkid=2138482).</span></span>

## <a name="availability"></a><span data-ttu-id="e23be-121">Disponibilité</span><span class="sxs-lookup"><span data-stu-id="e23be-121">Availability</span></span>

<span data-ttu-id="e23be-122">Le service de calcul des taxes est disponible uniquement dans les environnements bac à sable et pour certains clients, via un programme de version préliminaire publique.</span><span class="sxs-lookup"><span data-stu-id="e23be-122">The tax calculation service is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="e23be-123">À terme, il deviendra généralement disponible pour tous les clients et dans les environnements de production.</span><span class="sxs-lookup"><span data-stu-id="e23be-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="e23be-124">De nouvelles fonctionnalités continueront d’être fournies dans le service de calcul des taxes.</span><span class="sxs-lookup"><span data-stu-id="e23be-124">New features will continue to be delivered in the tax calculation service.</span></span> <span data-ttu-id="e23be-125">Par conséquent, assurez-vous de consulter régulièrement la documentation la plus à jour pour en savoir plus sur la couverture et l’étendue des fonctionnalités prises en charge.</span><span class="sxs-lookup"><span data-stu-id="e23be-125">Therefore, be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="e23be-126">Le service de calcul des taxes est déployé dans les zones géographiques Azure suivantes.</span><span class="sxs-lookup"><span data-stu-id="e23be-126">The tax calculation service is deployed in the following Azure geographies.</span></span> <span data-ttu-id="e23be-127">Il sera également déployé dans davantage de zones géographiques Azure, en fonction des besoins des clients :</span><span class="sxs-lookup"><span data-stu-id="e23be-127">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="e23be-128">Etats-Unis</span><span class="sxs-lookup"><span data-stu-id="e23be-128">United States</span></span>
- <span data-ttu-id="e23be-129">Europe</span><span class="sxs-lookup"><span data-stu-id="e23be-129">Europe</span></span>
- <span data-ttu-id="e23be-130">France</span><span class="sxs-lookup"><span data-stu-id="e23be-130">France</span></span>
- <span data-ttu-id="e23be-131">Royaume-Uni</span><span class="sxs-lookup"><span data-stu-id="e23be-131">United Kingdom</span></span>

> [!NOTE]
> <span data-ttu-id="e23be-132">Le service de calcul des taxes ne prend pas en charge les déploiements sur site de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e23be-132">The tax calculation service doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="e23be-133">Il ne prend pas non plus en charge les versions antérieures, telles que Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="e23be-133">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="e23be-134">Principales fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="e23be-134">Feature highlights</span></span>

- <span data-ttu-id="e23be-135">Une matrice de taxe configurable pour déterminer et calculer automatiquement les taxes</span><span class="sxs-lookup"><span data-stu-id="e23be-135">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="e23be-136">Prise en charge de plusieurs numéros d’immatriculation de taxe sur la valeur ajoutée (TVA)</span><span class="sxs-lookup"><span data-stu-id="e23be-136">Support for multiple value-added tax (VAT) registration numbers</span></span>
- <span data-ttu-id="e23be-137">Prise en charge des ordres de transfert pour la détermination et le calcul des taxes</span><span class="sxs-lookup"><span data-stu-id="e23be-137">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="e23be-138">Prise en charge des ordres de transfert pour la détermination de plusieurs numéros d’immatriculation de TVA</span><span class="sxs-lookup"><span data-stu-id="e23be-138">Transfer order support for determination of multiple VAT registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="e23be-139">Transactions prises en charge</span><span class="sxs-lookup"><span data-stu-id="e23be-139">Supported transactions</span></span>

<span data-ttu-id="e23be-140">Le service de calcul des taxes peut être activé par entité juridique et par transaction.</span><span class="sxs-lookup"><span data-stu-id="e23be-140">The tax calculation service can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="e23be-141">Les transactions suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="e23be-141">The following transactions are supported:</span></span>

- <span data-ttu-id="e23be-142">Processus de vente</span><span class="sxs-lookup"><span data-stu-id="e23be-142">Sales process</span></span>

    - <span data-ttu-id="e23be-143">Devis de vente</span><span class="sxs-lookup"><span data-stu-id="e23be-143">Sales quotation</span></span>
    - <span data-ttu-id="e23be-144">Commandes client</span><span class="sxs-lookup"><span data-stu-id="e23be-144">Sales order</span></span>
    - <span data-ttu-id="e23be-145">Confirmation</span><span class="sxs-lookup"><span data-stu-id="e23be-145">Confirmation</span></span>
    - <span data-ttu-id="e23be-146">Prélèvements</span><span class="sxs-lookup"><span data-stu-id="e23be-146">Picking list</span></span>
    - <span data-ttu-id="e23be-147">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="e23be-147">Packing slip</span></span>
    - <span data-ttu-id="e23be-148">Facture client</span><span class="sxs-lookup"><span data-stu-id="e23be-148">Sales invoice</span></span>
    - <span data-ttu-id="e23be-149">Avoir</span><span class="sxs-lookup"><span data-stu-id="e23be-149">Credit note</span></span>
    - <span data-ttu-id="e23be-150">Ordre de retour</span><span class="sxs-lookup"><span data-stu-id="e23be-150">Return order</span></span>
    - <span data-ttu-id="e23be-151">Frais divers d’en-tête</span><span class="sxs-lookup"><span data-stu-id="e23be-151">Header miscellaneous charge</span></span>
    - <span data-ttu-id="e23be-152">Frais divers de ligne</span><span class="sxs-lookup"><span data-stu-id="e23be-152">Line miscellaneous charge</span></span>

- <span data-ttu-id="e23be-153">Processus d’achat</span><span class="sxs-lookup"><span data-stu-id="e23be-153">Purchase process</span></span>

    - <span data-ttu-id="e23be-154">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="e23be-154">Purchase order</span></span>
    - <span data-ttu-id="e23be-155">Confirmation</span><span class="sxs-lookup"><span data-stu-id="e23be-155">Confirmation</span></span>
    - <span data-ttu-id="e23be-156">Préparation de réception</span><span class="sxs-lookup"><span data-stu-id="e23be-156">Receipts list</span></span>
    - <span data-ttu-id="e23be-157">Accusé de réception des produits</span><span class="sxs-lookup"><span data-stu-id="e23be-157">Product receipt</span></span>
    - <span data-ttu-id="e23be-158">Facture d’achat</span><span class="sxs-lookup"><span data-stu-id="e23be-158">Purchase invoice</span></span>
    - <span data-ttu-id="e23be-159">Frais divers d’en-tête</span><span class="sxs-lookup"><span data-stu-id="e23be-159">Header miscellaneous charge</span></span>
    - <span data-ttu-id="e23be-160">Frais divers de ligne</span><span class="sxs-lookup"><span data-stu-id="e23be-160">Line miscellaneous charge</span></span>
    - <span data-ttu-id="e23be-161">Avoir</span><span class="sxs-lookup"><span data-stu-id="e23be-161">Credit note</span></span>
    - <span data-ttu-id="e23be-162">Ordre de retour</span><span class="sxs-lookup"><span data-stu-id="e23be-162">Return order</span></span>
    - <span data-ttu-id="e23be-163">Demande d’achat</span><span class="sxs-lookup"><span data-stu-id="e23be-163">Purchase requisition</span></span>
    - <span data-ttu-id="e23be-164">Frais divers de ligne de demande d’achat</span><span class="sxs-lookup"><span data-stu-id="e23be-164">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="e23be-165">Appel d’offre</span><span class="sxs-lookup"><span data-stu-id="e23be-165">Request for quotation</span></span>
    - <span data-ttu-id="e23be-166">Frais divers d’en-tête d’appel d’offre</span><span class="sxs-lookup"><span data-stu-id="e23be-166">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="e23be-167">Frais divers de ligne d’appel d’offre</span><span class="sxs-lookup"><span data-stu-id="e23be-167">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="e23be-168">Processus d’inventaire</span><span class="sxs-lookup"><span data-stu-id="e23be-168">Inventory process</span></span>

    - <span data-ttu-id="e23be-169">Ordre de transfert – Expédition</span><span class="sxs-lookup"><span data-stu-id="e23be-169">Transfer order – ship</span></span>
    - <span data-ttu-id="e23be-170">Ordre de transfert – Réception</span><span class="sxs-lookup"><span data-stu-id="e23be-170">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="e23be-171">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="e23be-171">Related resources</span></span>

[<span data-ttu-id="e23be-172">Prise en main du service de taxe</span><span class="sxs-lookup"><span data-stu-id="e23be-172">Get started with tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138482)

[<span data-ttu-id="e23be-173">Plusieurs numéros d’immatriculation de TVA</span><span class="sxs-lookup"><span data-stu-id="e23be-173">Multiple VAT registration number</span></span>](https://go.microsoft.com/fwlink/?linkid=2153387)

[<span data-ttu-id="e23be-174">Prise en charge de la fonction de taxe pour les ordres de transfert</span><span class="sxs-lookup"><span data-stu-id="e23be-174">Tax feature support for transfer order</span></span>](https://go.microsoft.com/fwlink/?linkid=2153388)

[<span data-ttu-id="e23be-175">Comment créer une extension dans le service de taxe</span><span class="sxs-lookup"><span data-stu-id="e23be-175">How to build extension in tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138483)
