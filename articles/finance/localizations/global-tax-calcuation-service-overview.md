---
title: Calcul de la taxe (version préliminaire)
description: Cette rubrique explique la portée et les fonctionnalités générales de la fonctionnalité de calcul des taxes.
author: wangchen
ms.date: 04/12/2021
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
ms.openlocfilehash: 3df952e0632807e55f176e63dc2047be5e622ec2
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892347"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="1941c-103">Calcul de la taxe (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="1941c-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="1941c-104">Le calcul des taxes est un service multi-locataire hyper évolutif qui permet au moteur Global Tax Engine d’automatiser et de simplifier le processus de détermination et de calcul des taxes.</span><span class="sxs-lookup"><span data-stu-id="1941c-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="1941c-105">Le moteur de taxe est entièrement configurable.</span><span class="sxs-lookup"><span data-stu-id="1941c-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="1941c-106">Les éléments qui peuvent être configurés incluent, mais sans s’y limiter, le modèle de données taxables, le code taxe, la matrice d’applicabilité de la taxe et la formule de calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="1941c-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="1941c-107">Le moteur de taxe fonctionne sur la plateforme des services essentiels Microsoft Azure, et offre une technologie moderne et une évolutivité exponentielle.</span><span class="sxs-lookup"><span data-stu-id="1941c-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="1941c-108">Le calcul des taxes s’intègre à Dynamics 365 Finance et Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1941c-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="1941c-109">À terme, il s’intégrera également avec Dynamics 365 Project Operations, Dynamics 365 Commerce et d’autres applications propriétaires et tierces.</span><span class="sxs-lookup"><span data-stu-id="1941c-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="1941c-110">Le calcul des taxes est un moteur de taxe à base de microservices qui offre une évolutivité exponentielle.</span><span class="sxs-lookup"><span data-stu-id="1941c-110">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="1941c-111">Il peut vous aider à exécuter les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="1941c-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="1941c-112">Configurer le calcul des taxes via Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="1941c-112">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="1941c-113">RCS est une version améliorée du concepteur de rapports électroniques (ER) et est disponible en tant que service autonome.</span><span class="sxs-lookup"><span data-stu-id="1941c-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="1941c-114">Configurer la matrice de taxe pour déterminer automatiquement les codes et les taux de taxe.</span><span class="sxs-lookup"><span data-stu-id="1941c-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="1941c-115">Configurer la matrice de taxe pour déterminer automatiquement le numéro d’immatriculation fiscale.</span><span class="sxs-lookup"><span data-stu-id="1941c-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="1941c-116">Configurer le concepteur de calcul de taxe pour définir des formules et des conditions.</span><span class="sxs-lookup"><span data-stu-id="1941c-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="1941c-117">Partager la solution de détermination et de calcul des taxes entre les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="1941c-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="1941c-118">Pour utiliser le service de calcul des taxes, installez le complément de service de calcul des taxes à partir de votre projet dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="1941c-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="1941c-119">Terminez ensuite la configuration dans RCS et activez le service de calcul des taxes dans Finance and Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1941c-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="1941c-120">Pour plus d’informations, voir [Prise en main du service de taxe](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="1941c-120">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="1941c-121">Disponibilité</span><span class="sxs-lookup"><span data-stu-id="1941c-121">Availability</span></span>

<span data-ttu-id="1941c-122">Le calcul des taxes est disponible uniquement dans les environnements bac à sable et pour certains clients, via un programme de version préliminaire publique.</span><span class="sxs-lookup"><span data-stu-id="1941c-122">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="1941c-123">À terme, il deviendra généralement disponible pour tous les clients et dans les environnements de production.</span><span class="sxs-lookup"><span data-stu-id="1941c-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="1941c-124">De nouvelles fonctionnalités seront publiées régulièrement. Assurez-vous donc de consulter régulièrement la documentation la plus à jour pour en savoir plus sur la couverture et l’étendue des fonctionnalités prises en charge.</span><span class="sxs-lookup"><span data-stu-id="1941c-124">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="1941c-125">Le calcul des taxes est déployé dans les zones géographiques Azure suivantes.</span><span class="sxs-lookup"><span data-stu-id="1941c-125">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="1941c-126">Il sera également déployé dans davantage de zones géographiques Azure, en fonction des besoins des clients :</span><span class="sxs-lookup"><span data-stu-id="1941c-126">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="1941c-127">Etats-Unis</span><span class="sxs-lookup"><span data-stu-id="1941c-127">United States</span></span>
- <span data-ttu-id="1941c-128">Europe</span><span class="sxs-lookup"><span data-stu-id="1941c-128">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="1941c-129">Le calcul des taxes ne prend pas en charge les déploiements sur site de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1941c-129">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="1941c-130">Il ne prend pas non plus en charge les versions antérieures, telles que Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="1941c-130">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="1941c-131">Principales fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="1941c-131">Feature highlights</span></span>

- <span data-ttu-id="1941c-132">Une matrice de taxe configurable pour déterminer et calculer automatiquement les taxes</span><span class="sxs-lookup"><span data-stu-id="1941c-132">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="1941c-133">Prise en charge de plusieurs numéros d’immatriculation de taxe</span><span class="sxs-lookup"><span data-stu-id="1941c-133">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="1941c-134">Prise en charge des ordres de transfert pour la détermination et le calcul des taxes</span><span class="sxs-lookup"><span data-stu-id="1941c-134">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="1941c-135">Prise en charge des ordres de transfert pour la détermination de plusieurs numéros d’immatriculation de taxe</span><span class="sxs-lookup"><span data-stu-id="1941c-135">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="1941c-136">Transactions prises en charge</span><span class="sxs-lookup"><span data-stu-id="1941c-136">Supported transactions</span></span>

<span data-ttu-id="1941c-137">Le calcul des taxes peut être activé par entité juridique et par transaction.</span><span class="sxs-lookup"><span data-stu-id="1941c-137">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="1941c-138">Les transactions suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="1941c-138">The following transactions are supported:</span></span>

- <span data-ttu-id="1941c-139">Processus de vente</span><span class="sxs-lookup"><span data-stu-id="1941c-139">Sales process</span></span>

    - <span data-ttu-id="1941c-140">Devis de vente</span><span class="sxs-lookup"><span data-stu-id="1941c-140">Sales quotation</span></span>
    - <span data-ttu-id="1941c-141">Commandes client</span><span class="sxs-lookup"><span data-stu-id="1941c-141">Sales order</span></span>
    - <span data-ttu-id="1941c-142">Confirmation</span><span class="sxs-lookup"><span data-stu-id="1941c-142">Confirmation</span></span>
    - <span data-ttu-id="1941c-143">Prélèvements</span><span class="sxs-lookup"><span data-stu-id="1941c-143">Picking list</span></span>
    - <span data-ttu-id="1941c-144">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="1941c-144">Packing slip</span></span>
    - <span data-ttu-id="1941c-145">Facture client</span><span class="sxs-lookup"><span data-stu-id="1941c-145">Sales invoice</span></span>
    - <span data-ttu-id="1941c-146">Avoir</span><span class="sxs-lookup"><span data-stu-id="1941c-146">Credit note</span></span>
    - <span data-ttu-id="1941c-147">Ordre de retour</span><span class="sxs-lookup"><span data-stu-id="1941c-147">Return order</span></span>
    - <span data-ttu-id="1941c-148">Frais divers d’en-tête</span><span class="sxs-lookup"><span data-stu-id="1941c-148">Header miscellaneous charge</span></span>
    - <span data-ttu-id="1941c-149">Frais divers de ligne</span><span class="sxs-lookup"><span data-stu-id="1941c-149">Line miscellaneous charge</span></span>

- <span data-ttu-id="1941c-150">Processus d’achat</span><span class="sxs-lookup"><span data-stu-id="1941c-150">Purchase process</span></span>

    - <span data-ttu-id="1941c-151">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="1941c-151">Purchase order</span></span>
    - <span data-ttu-id="1941c-152">Confirmation</span><span class="sxs-lookup"><span data-stu-id="1941c-152">Confirmation</span></span>
    - <span data-ttu-id="1941c-153">Préparation de réception</span><span class="sxs-lookup"><span data-stu-id="1941c-153">Receipts list</span></span>
    - <span data-ttu-id="1941c-154">Accusé de réception des produits</span><span class="sxs-lookup"><span data-stu-id="1941c-154">Product receipt</span></span>
    - <span data-ttu-id="1941c-155">Facture d’achat</span><span class="sxs-lookup"><span data-stu-id="1941c-155">Purchase invoice</span></span>
    - <span data-ttu-id="1941c-156">Frais divers d’en-tête</span><span class="sxs-lookup"><span data-stu-id="1941c-156">Header miscellaneous charge</span></span>
    - <span data-ttu-id="1941c-157">Frais divers de ligne</span><span class="sxs-lookup"><span data-stu-id="1941c-157">Line miscellaneous charge</span></span>
    - <span data-ttu-id="1941c-158">Avoir</span><span class="sxs-lookup"><span data-stu-id="1941c-158">Credit note</span></span>
    - <span data-ttu-id="1941c-159">Ordre de retour</span><span class="sxs-lookup"><span data-stu-id="1941c-159">Return order</span></span>
    - <span data-ttu-id="1941c-160">Demande d’achat</span><span class="sxs-lookup"><span data-stu-id="1941c-160">Purchase requisition</span></span>
    - <span data-ttu-id="1941c-161">Frais divers de ligne de demande d’achat</span><span class="sxs-lookup"><span data-stu-id="1941c-161">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="1941c-162">Appel d’offre</span><span class="sxs-lookup"><span data-stu-id="1941c-162">Request for quotation</span></span>
    - <span data-ttu-id="1941c-163">Frais divers d’en-tête d’appel d’offre</span><span class="sxs-lookup"><span data-stu-id="1941c-163">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="1941c-164">Frais divers de ligne d’appel d’offre</span><span class="sxs-lookup"><span data-stu-id="1941c-164">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="1941c-165">Processus d’inventaire</span><span class="sxs-lookup"><span data-stu-id="1941c-165">Inventory process</span></span>

    - <span data-ttu-id="1941c-166">Ordre de transfert – Expédition</span><span class="sxs-lookup"><span data-stu-id="1941c-166">Transfer order – ship</span></span>
    - <span data-ttu-id="1941c-167">Ordre de transfert – Réception</span><span class="sxs-lookup"><span data-stu-id="1941c-167">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="1941c-168">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="1941c-168">Related resources</span></span>

[<span data-ttu-id="1941c-169">Prise en main du service de taxe</span><span class="sxs-lookup"><span data-stu-id="1941c-169">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="1941c-170">Plusieurs numéros d’immatriculation de TVA</span><span class="sxs-lookup"><span data-stu-id="1941c-170">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="1941c-171">Prise en charge de la fonction de taxe pour les ordres de transfert</span><span class="sxs-lookup"><span data-stu-id="1941c-171">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="1941c-172">Comment créer une extension dans le service de taxe</span><span class="sxs-lookup"><span data-stu-id="1941c-172">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)