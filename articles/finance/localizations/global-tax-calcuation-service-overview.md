---
title: Calcul de la taxe (version préliminaire)
description: Cette rubrique explique la portée et les fonctionnalités générales de la fonctionnalité de calcul des taxes.
author: wangchen
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9daa6e001200d03a2639974fb6de618d77ddf09d
ms.sourcegitcommit: cb282e8d2306ab71adf80a84346a6863d2d019e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6184099"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="1b1e8-103">Calcul de la taxe (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="1b1e8-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="1b1e8-104">Le calcul des taxes est un service multi-locataire hyper évolutif qui permet au moteur Global Tax Engine d’automatiser et de simplifier le processus de détermination et de calcul des taxes.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="1b1e8-105">Le moteur de taxe est entièrement configurable.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="1b1e8-106">Les éléments qui peuvent être configurés incluent, mais sans s’y limiter, le modèle de données taxables, le code taxe, la matrice d’applicabilité de la taxe et la formule de calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="1b1e8-107">Le moteur de taxe fonctionne sur la plateforme des services essentiels Microsoft Azure, et offre une technologie moderne et une évolutivité exponentielle.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="1b1e8-108">Le calcul des taxes s’intègre à Dynamics 365 Finance et Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="1b1e8-109">À terme, il s’intégrera également avec Dynamics 365 Project Operations, Dynamics 365 Commerce et d’autres applications propriétaires et tierces.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b1e8-110">Lorsque vous activez le service de calcul des taxes, certaines opérations sur les données associées peuvent être effectuées dans un centre de données autre que le centre de données qui gère vos données de service.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-110">When you enable the Tax Calculation service, some operations on related data might be performed in a data center other than the data center that maintains your service data.</span></span> <span data-ttu-id="1b1e8-111">Consultez les [Conditions générales d’utilisation](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) avant d’activer le service de calcul des taxes.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-111">Review the [Terms and Conditions](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) before you enable the Tax Calculation service.</span></span> <span data-ttu-id="1b1e8-112">La protection de votre vie privée est importante pour nous.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-112">Your privacy is important to us.</span></span> <span data-ttu-id="1b1e8-113">Pour en savoir plus, lisez notre [Déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=521839).</span><span class="sxs-lookup"><span data-stu-id="1b1e8-113">To learn more, read our [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839).</span></span>

<span data-ttu-id="1b1e8-114">Le calcul des taxes est un moteur de taxe à base de microservices qui offre une évolutivité exponentielle.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-114">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="1b1e8-115">Il peut vous aider à exécuter les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="1b1e8-115">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="1b1e8-116">Configurer le calcul des taxes via Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="1b1e8-116">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="1b1e8-117">RCS est une version améliorée du concepteur de rapports électroniques (ER) et est disponible en tant que service autonome.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-117">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="1b1e8-118">Configurer la matrice de taxe pour déterminer automatiquement les codes et les taux de taxe.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-118">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="1b1e8-119">Configurer la matrice de taxe pour déterminer automatiquement le numéro d’immatriculation fiscale.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-119">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="1b1e8-120">Configurer le concepteur de calcul de taxe pour définir des formules et des conditions.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-120">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="1b1e8-121">Partager la solution de détermination et de calcul des taxes entre les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-121">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="1b1e8-122">Pour utiliser le service de calcul des taxes, installez le complément de service de calcul des taxes à partir de votre projet dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="1b1e8-122">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="1b1e8-123">Terminez ensuite la configuration dans RCS et activez le service de calcul des taxes dans Finance and Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-123">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="1b1e8-124">Pour plus d’informations, voir [Prise en main du service de taxe](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="1b1e8-124">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="1b1e8-125">Disponibilité</span><span class="sxs-lookup"><span data-stu-id="1b1e8-125">Availability</span></span>

<span data-ttu-id="1b1e8-126">Le calcul des taxes est disponible uniquement dans les environnements bac à sable et pour certains clients, via un programme de version préliminaire publique.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-126">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="1b1e8-127">À terme, il deviendra généralement disponible pour tous les clients et dans les environnements de production.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-127">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="1b1e8-128">De nouvelles fonctionnalités seront publiées régulièrement. Assurez-vous donc de consulter régulièrement la documentation la plus à jour pour en savoir plus sur la couverture et l’étendue des fonctionnalités prises en charge.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-128">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="1b1e8-129">Le calcul des taxes est déployé dans les zones géographiques Azure suivantes.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-129">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="1b1e8-130">Il sera également déployé dans davantage de zones géographiques Azure, en fonction des besoins des clients :</span><span class="sxs-lookup"><span data-stu-id="1b1e8-130">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="1b1e8-131">Etats-Unis</span><span class="sxs-lookup"><span data-stu-id="1b1e8-131">United States</span></span>
- <span data-ttu-id="1b1e8-132">Europe</span><span class="sxs-lookup"><span data-stu-id="1b1e8-132">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="1b1e8-133">Le calcul des taxes ne prend pas en charge les déploiements sur site de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-133">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="1b1e8-134">Il ne prend pas non plus en charge les versions antérieures, telles que Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-134">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="1b1e8-135">Principales fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="1b1e8-135">Feature highlights</span></span>

- <span data-ttu-id="1b1e8-136">Une matrice de taxe configurable pour déterminer et calculer automatiquement les taxes</span><span class="sxs-lookup"><span data-stu-id="1b1e8-136">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="1b1e8-137">Prise en charge de plusieurs numéros d’immatriculation de taxe</span><span class="sxs-lookup"><span data-stu-id="1b1e8-137">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="1b1e8-138">Prise en charge des ordres de transfert pour la détermination et le calcul des taxes</span><span class="sxs-lookup"><span data-stu-id="1b1e8-138">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="1b1e8-139">Prise en charge des ordres de transfert pour la détermination de plusieurs numéros d’immatriculation de taxe</span><span class="sxs-lookup"><span data-stu-id="1b1e8-139">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="1b1e8-140">Transactions prises en charge</span><span class="sxs-lookup"><span data-stu-id="1b1e8-140">Supported transactions</span></span>

<span data-ttu-id="1b1e8-141">Le calcul des taxes peut être activé par entité juridique et par transaction.</span><span class="sxs-lookup"><span data-stu-id="1b1e8-141">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="1b1e8-142">Les transactions suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="1b1e8-142">The following transactions are supported:</span></span>

- <span data-ttu-id="1b1e8-143">Processus de vente</span><span class="sxs-lookup"><span data-stu-id="1b1e8-143">Sales process</span></span>

    - <span data-ttu-id="1b1e8-144">Devis de vente</span><span class="sxs-lookup"><span data-stu-id="1b1e8-144">Sales quotation</span></span>
    - <span data-ttu-id="1b1e8-145">Commandes client</span><span class="sxs-lookup"><span data-stu-id="1b1e8-145">Sales order</span></span>
    - <span data-ttu-id="1b1e8-146">Confirmation</span><span class="sxs-lookup"><span data-stu-id="1b1e8-146">Confirmation</span></span>
    - <span data-ttu-id="1b1e8-147">Prélèvements</span><span class="sxs-lookup"><span data-stu-id="1b1e8-147">Picking list</span></span>
    - <span data-ttu-id="1b1e8-148">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="1b1e8-148">Packing slip</span></span>
    - <span data-ttu-id="1b1e8-149">Facture client</span><span class="sxs-lookup"><span data-stu-id="1b1e8-149">Sales invoice</span></span>
    - <span data-ttu-id="1b1e8-150">Avoir</span><span class="sxs-lookup"><span data-stu-id="1b1e8-150">Credit note</span></span>
    - <span data-ttu-id="1b1e8-151">Ordre de retour</span><span class="sxs-lookup"><span data-stu-id="1b1e8-151">Return order</span></span>
    - <span data-ttu-id="1b1e8-152">Frais divers d’en-tête</span><span class="sxs-lookup"><span data-stu-id="1b1e8-152">Header miscellaneous charge</span></span>
    - <span data-ttu-id="1b1e8-153">Frais divers de ligne</span><span class="sxs-lookup"><span data-stu-id="1b1e8-153">Line miscellaneous charge</span></span>

- <span data-ttu-id="1b1e8-154">Processus d’achat</span><span class="sxs-lookup"><span data-stu-id="1b1e8-154">Purchase process</span></span>

    - <span data-ttu-id="1b1e8-155">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="1b1e8-155">Purchase order</span></span>
    - <span data-ttu-id="1b1e8-156">Confirmation</span><span class="sxs-lookup"><span data-stu-id="1b1e8-156">Confirmation</span></span>
    - <span data-ttu-id="1b1e8-157">Préparation de réception</span><span class="sxs-lookup"><span data-stu-id="1b1e8-157">Receipts list</span></span>
    - <span data-ttu-id="1b1e8-158">Accusé de réception des produits</span><span class="sxs-lookup"><span data-stu-id="1b1e8-158">Product receipt</span></span>
    - <span data-ttu-id="1b1e8-159">Facture d’achat</span><span class="sxs-lookup"><span data-stu-id="1b1e8-159">Purchase invoice</span></span>
    - <span data-ttu-id="1b1e8-160">Frais divers d’en-tête</span><span class="sxs-lookup"><span data-stu-id="1b1e8-160">Header miscellaneous charge</span></span>
    - <span data-ttu-id="1b1e8-161">Frais divers de ligne</span><span class="sxs-lookup"><span data-stu-id="1b1e8-161">Line miscellaneous charge</span></span>
    - <span data-ttu-id="1b1e8-162">Avoir</span><span class="sxs-lookup"><span data-stu-id="1b1e8-162">Credit note</span></span>
    - <span data-ttu-id="1b1e8-163">Ordre de retour</span><span class="sxs-lookup"><span data-stu-id="1b1e8-163">Return order</span></span>
    - <span data-ttu-id="1b1e8-164">Demande d’achat</span><span class="sxs-lookup"><span data-stu-id="1b1e8-164">Purchase requisition</span></span>
    - <span data-ttu-id="1b1e8-165">Frais divers de ligne de demande d’achat</span><span class="sxs-lookup"><span data-stu-id="1b1e8-165">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="1b1e8-166">Appel d’offre</span><span class="sxs-lookup"><span data-stu-id="1b1e8-166">Request for quotation</span></span>
    - <span data-ttu-id="1b1e8-167">Frais divers d’en-tête d’appel d’offre</span><span class="sxs-lookup"><span data-stu-id="1b1e8-167">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="1b1e8-168">Frais divers de ligne d’appel d’offre</span><span class="sxs-lookup"><span data-stu-id="1b1e8-168">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="1b1e8-169">Processus d’inventaire</span><span class="sxs-lookup"><span data-stu-id="1b1e8-169">Inventory process</span></span>

    - <span data-ttu-id="1b1e8-170">Ordre de transfert – Expédition</span><span class="sxs-lookup"><span data-stu-id="1b1e8-170">Transfer order – ship</span></span>
    - <span data-ttu-id="1b1e8-171">Ordre de transfert – Réception</span><span class="sxs-lookup"><span data-stu-id="1b1e8-171">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="1b1e8-172">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="1b1e8-172">Related resources</span></span>

[<span data-ttu-id="1b1e8-173">Prise en main du service de taxe</span><span class="sxs-lookup"><span data-stu-id="1b1e8-173">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="1b1e8-174">Plusieurs numéros d’immatriculation de TVA</span><span class="sxs-lookup"><span data-stu-id="1b1e8-174">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="1b1e8-175">Prise en charge de la fonction de taxe pour les ordres de transfert</span><span class="sxs-lookup"><span data-stu-id="1b1e8-175">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="1b1e8-176">Comment créer une extension dans le service de taxe</span><span class="sxs-lookup"><span data-stu-id="1b1e8-176">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)
