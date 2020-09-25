---
title: Normes prises en charge pour la facturation électronique en Europe
description: Cette rubrique décrit le niveau de couverture qui existe pour la facturation électronique pour Europe.
author: mrolecki
manager: AnnBe
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 10274
ms.search.region: Austria, Denmark, Italy, Norway, Spain, France, Belgium, Netherlands
ms.search.industry: ''
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: c86cc90e5f441641bc14d20898e65325d7c7d716
ms.sourcegitcommit: 1ca48d95fbff2555307cc1e5e5e23feea79a8bc1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "3763682"
---
# <a name="supported-standards-for-electronic-invoicing-in-europe"></a><span data-ttu-id="d852f-103">Normes prises en charge pour la facturation électronique en Europe</span><span class="sxs-lookup"><span data-stu-id="d852f-103">Supported standards for electronic invoicing in Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d852f-104">Cette rubrique décrit le niveau de couverture qui existe pour la facturation électronique pour Europe.</span><span class="sxs-lookup"><span data-stu-id="d852f-104">This topic explains the level of coverage that exists for electronic invoicing for Europe.</span></span> 

<span data-ttu-id="d852f-105">L’implémentation et l’adoption de la facturation électronique à l’échelle de l’Union européenne est réglementée [Directive 2010/45/EU](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), ce qui affecte tous les États membres de l’UE.</span><span class="sxs-lookup"><span data-stu-id="d852f-105">Implementation and adoption of European Union-wide electronic invoicing is regulated [Council Directive 2010/45/EU](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), which affects all EU member states.</span></span> <span data-ttu-id="d852f-106">Les sociétés qui souhaitent tirer parti de la facturation électronique doivent envoyer les factures de commande client, les factures financières, les factures de projet, les avoirs de commande client et les avoirs de facture de projet sous forme de fichiers .xml au gouvernement ou à d’autres partenaires commerciaux qui mandatent l’utilisation de la facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="d852f-106">Companies that want to benefit from electronic invoicing must submit sales order invoices, free text invoices, project invoices, sales order credit notes, and project invoice credit notes as .xml files to the government or other trading parties that mandate use of electronic invoicing.</span></span> <span data-ttu-id="d852f-107">Ces fichiers .xml doivent être conformes à certaines normes.</span><span class="sxs-lookup"><span data-stu-id="d852f-107">These .xml files must comply with certain standards.</span></span> <span data-ttu-id="d852f-108">Les exigences spécifiques au pays et leur implémentation peuvent différer entre les États membres de l’UE, mais généralement ils utilisent le langage universel des affaires ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) dans différentes versions avec des personnalisations ainsi que les spécifications [PEPPOL](https://www.peppol.eu) et les points d’accès pour la validation et le transport.</span><span class="sxs-lookup"><span data-stu-id="d852f-108">The country-specific requirements and their implementation may differ across EU member states but commonly they are using Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) in different versions with customizations as well as [PEPPOL](https://www.peppol.eu) specifications and access points for validation and transportation.</span></span> <span data-ttu-id="d852f-109">Le principal l’avantage du langage UBL est que les documents commerciaux peuvent être normalisés à différentes fins.</span><span class="sxs-lookup"><span data-stu-id="d852f-109">The primary advantage of UBL is that business documents can be standardized for different purposes.</span></span> <span data-ttu-id="d852f-110">Comme le langage UBL est une norme internationale flexible qui répond à de nombreuses exigences métier, ces documents commerciaux peuvent être échangés entre les frontières nationales.</span><span class="sxs-lookup"><span data-stu-id="d852f-110">Because UBL is a flexible, international standard that supports many business requirements, these business documents can be exchanged across national borders.</span></span>

## <a name="electronic-invoice-formats-currently-available-in-dynamics-365-finance"></a><span data-ttu-id="d852f-111">Formats de facture électronique actuellement disponibles dans Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="d852f-111">Electronic invoice formats currently available in Dynamics 365 Finance</span></span>

<span data-ttu-id="d852f-112">Les formats de factures électroniques spécifiques au pays suivants sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="d852f-112">The following country-specific formats of electronic invoices are available:</span></span>

-   <span data-ttu-id="d852f-113">OIOUBL v.2.02 pour le Danemark</span><span class="sxs-lookup"><span data-stu-id="d852f-113">OIOUBL v.2.02 for Denmark</span></span>
-   <span data-ttu-id="d852f-114">EHF v.3.0 pour la Norvège</span><span class="sxs-lookup"><span data-stu-id="d852f-114">EHF v.3.0 for Norway</span></span>
-   <span data-ttu-id="d852f-115">PEPPOL BIS v.2 pour l’Autriche, la France, et la Belgique</span><span class="sxs-lookup"><span data-stu-id="d852f-115">PEPPOL BIS v.2 for Austria, France, and Belgium</span></span>
-   <span data-ttu-id="d852f-116">UBL-OHNL 1.9 pour les Pays-Bas</span><span class="sxs-lookup"><span data-stu-id="d852f-116">UBL-OHNL 1.9 for the Netherlands</span></span>
-   <span data-ttu-id="d852f-117">FacturaE v.3.2.1 pour l’Espagne</span><span class="sxs-lookup"><span data-stu-id="d852f-117">FacturaE v.3.2.1 for Spain</span></span>
-   <span data-ttu-id="d852f-118">FatturaPA v.1.2 pour l’Italie</span><span class="sxs-lookup"><span data-stu-id="d852f-118">FatturaPA v.1.2 for Italy</span></span>
-   <span data-ttu-id="d852f-119">xRechnung v.1.2 pour l’Allemagne</span><span class="sxs-lookup"><span data-stu-id="d852f-119">xRechnung v.1.2 for Germany</span></span>
-   <span data-ttu-id="d852f-120">Ouvrir PEPPOL BIS Billing v.3.0 pour l’Union européenne</span><span class="sxs-lookup"><span data-stu-id="d852f-120">Open PEPPOL BIS Billing v.3.0 for European Union</span></span>
-   <span data-ttu-id="d852f-121">Format spécifique estonien version 1.2</span><span class="sxs-lookup"><span data-stu-id="d852f-121">Estonian specific format version 1.2</span></span>
-   <span data-ttu-id="d852f-122">Finvoice 3.0 pour la Finlande</span><span class="sxs-lookup"><span data-stu-id="d852f-122">Finvoice 3.0 for Finland</span></span>

<span data-ttu-id="d852f-123">La facturation électronique est basée sur la [Gestion des états électroniques (ER)](../../dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="d852f-123">Electronic invoicing is based on [Electronic reporting (ER)](../../dev-itpro/analytics/general-electronic-reporting.md).</span></span> <span data-ttu-id="d852f-124">Un modèle de données **Modèle de facture**, un mappage de modèles de factures et plusieurs configurations de format ER spécifiques aux pays/régions ont été créés pour l’Autriche (AT), le Danemark (DK), l’Italie (IT), la Norvège (NO), l’Espagne (ES), la France (FR), la Belgique (BE), les Pays-Bas (NL), l’Allemagne (DE), l’Estonie (EE), la Finlande (FI) et l’Union européenne (UE).</span><span class="sxs-lookup"><span data-stu-id="d852f-124">An **Invoice model** data model, invoice model mapping, and several country/region-specific ER format configurations have been created for Austria (AT), Denmark (DK), Italy (IT), Norway (NO), Spain (ES), France (FR), Belgium (BE), the Netherlands (NL), Germany (DE), Estonia (EE), Finland (FI), and the European Union (EU).</span></span>

-   <span data-ttu-id="d852f-125">Facture client OIOUBL pour AT, DK et NO</span><span class="sxs-lookup"><span data-stu-id="d852f-125">OIOUBL Sales invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="d852f-126">Avoir de vente OIOUBL pour AT, DK et NO</span><span class="sxs-lookup"><span data-stu-id="d852f-126">OIOUBL Sales credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="d852f-127">Facture de projet OIOUBL pour AT, DK et NO</span><span class="sxs-lookup"><span data-stu-id="d852f-127">OIOUBL Project invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="d852f-128">Avoir de projet OIOUBL pour AT, DK et NO</span><span class="sxs-lookup"><span data-stu-id="d852f-128">OIOUBL Project credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="d852f-129">Facture client UBL FR</span><span class="sxs-lookup"><span data-stu-id="d852f-129">UBL Sales Invoice FR</span></span>
-   <span data-ttu-id="d852f-130">Avoir sur vente UBL FR</span><span class="sxs-lookup"><span data-stu-id="d852f-130">UBL Sales Credit Note FR</span></span>
-   <span data-ttu-id="d852f-131">Facture de projet UBL FR</span><span class="sxs-lookup"><span data-stu-id="d852f-131">UBL Project Invoice FR</span></span>
-   <span data-ttu-id="d852f-132">Avoir de projet UBL FR</span><span class="sxs-lookup"><span data-stu-id="d852f-132">UBL Project Credit Note FR</span></span>
-   <span data-ttu-id="d852f-133">Facture client UBL BE</span><span class="sxs-lookup"><span data-stu-id="d852f-133">UBL Sales Invoice BE</span></span>
-   <span data-ttu-id="d852f-134">Avoir sur vente UBL BE</span><span class="sxs-lookup"><span data-stu-id="d852f-134">UBL Sales Credit Note BE</span></span>
-   <span data-ttu-id="d852f-135">Facture de projet UBL BE</span><span class="sxs-lookup"><span data-stu-id="d852f-135">UBL Project Invoice BE</span></span>
-   <span data-ttu-id="d852f-136">Avoir de projet UBL BE</span><span class="sxs-lookup"><span data-stu-id="d852f-136">UBL Project Credit Note BE</span></span>
-   <span data-ttu-id="d852f-137">Facture client UBL NL</span><span class="sxs-lookup"><span data-stu-id="d852f-137">UBL Sales Invoice NL</span></span>
-   <span data-ttu-id="d852f-138">Avoir sur vente UBL NL</span><span class="sxs-lookup"><span data-stu-id="d852f-138">UBL Sales Credit Note NL</span></span>
-   <span data-ttu-id="d852f-139">Facture de projet UBL NL</span><span class="sxs-lookup"><span data-stu-id="d852f-139">UBL Project Invoice NL</span></span>
-   <span data-ttu-id="d852f-140">Avoir de projet UBL NL</span><span class="sxs-lookup"><span data-stu-id="d852f-140">UBL Project Credit Note NL</span></span> 
-   <span data-ttu-id="d852f-141">Facture client (ES)</span><span class="sxs-lookup"><span data-stu-id="d852f-141">Sales invoice (ES)</span></span>
-   <span data-ttu-id="d852f-142">Facture client (IT)</span><span class="sxs-lookup"><span data-stu-id="d852f-142">Sales invoice (IT)</span></span>
-   <span data-ttu-id="d852f-143">Facture de projet (ES)</span><span class="sxs-lookup"><span data-stu-id="d852f-143">Project invoice (ES)</span></span>
-   <span data-ttu-id="d852f-144">Facture de projet (IT)</span><span class="sxs-lookup"><span data-stu-id="d852f-144">Project invoice (IT)</span></span>
-   <span data-ttu-id="d852f-145">Facture client DE</span><span class="sxs-lookup"><span data-stu-id="d852f-145">Sales Invoice DE</span></span>
-   <span data-ttu-id="d852f-146">Facture de projet DE</span><span class="sxs-lookup"><span data-stu-id="d852f-146">Project Invoice DE</span></span>
-   <span data-ttu-id="d852f-147">Facture client Peppol - pour l’UE</span><span class="sxs-lookup"><span data-stu-id="d852f-147">Peppol Sales Invoice - for EU</span></span>
-   <span data-ttu-id="d852f-148">Avoir sur vente Peppol - pour l’UE</span><span class="sxs-lookup"><span data-stu-id="d852f-148">Peppol Sales Credit Note - for EU</span></span>
-   <span data-ttu-id="d852f-149">Facture de projet Peppol - pour l’UE</span><span class="sxs-lookup"><span data-stu-id="d852f-149">Peppol Project Invoice - for EU</span></span>
-   <span data-ttu-id="d852f-150">Avoir sur le projet Peppol - pour l’UE</span><span class="sxs-lookup"><span data-stu-id="d852f-150">Peppol Project Credit Note - for EU</span></span>
-   <span data-ttu-id="d852f-151">Facture client (EE)</span><span class="sxs-lookup"><span data-stu-id="d852f-151">Sales invoice (EE)</span></span>
-   <span data-ttu-id="d852f-152">Facture de projet (EE)</span><span class="sxs-lookup"><span data-stu-id="d852f-152">Project invoice (EE)</span></span>
-   <span data-ttu-id="d852f-153">Facture client (FI)</span><span class="sxs-lookup"><span data-stu-id="d852f-153">Sales invoice (FI)</span></span>
-   <span data-ttu-id="d852f-154">Facture de projet (FI)</span><span class="sxs-lookup"><span data-stu-id="d852f-154">Project invoice (FI)</span></span>

<span data-ttu-id="d852f-155">Les factures électroniques et les avoirs que vous générez contiennent les informations requises, telles que le numéro EAN, la personne à contacter, le numéro de compte de dimension et les informations d’adresse pour le client.</span><span class="sxs-lookup"><span data-stu-id="d852f-155">The electronic invoices and credit notes that you generate include required information, such as a European Article Numbering (EAN) number, contact person, dimension account number, and address information for the customer.</span></span> <span data-ttu-id="d852f-156">Les règles de contrôle sont appliquées lors de la génération des factures pour vous permettre de vérifier que les informations entrées sont correctes.</span><span class="sxs-lookup"><span data-stu-id="d852f-156">Validation rules are applied when invoices are generated so you can verify that the correct information has been entered.</span></span> <span data-ttu-id="d852f-157">L’ensemble des informations requises peut différer d’un pays à l’autre.</span><span class="sxs-lookup"><span data-stu-id="d852f-157">The set of required information may differ from country to country.</span></span> <span data-ttu-id="d852f-158">Comme les exigences ainsi que les pays et formats pris en charge peuvent être modifiés, vous devez toujours aller dans la bibliothèque d’actifs partagés de Microsoft Dynamics Lifecycle Services (LCS) et afficher la liste la plus récente des fichiers disponibles dont le type d’actif est **Configuration GER**.</span><span class="sxs-lookup"><span data-stu-id="d852f-158">Because the requirements, as well as supported countries and formats, is subject to change, you should always go to the Shared asset library on Microsoft Dynamics Lifecycle services (LCS) and view the most up-to-date list of available files that have an asset type of **GER configuration**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d852f-159">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d852f-159">Additional resources</span></span>
<span data-ttu-id="d852f-160">Pour plus de détails sur le paramétrage des factures électroniques, vous pouvez visionner [Guides de tâche](../../fin-and-ops/get-started/help-overview.md#task-guides) dans volet d’aide :</span><span class="sxs-lookup"><span data-stu-id="d852f-160">For more details about how to set up electronic invoices, you can play the following [Task guides](../../fin-and-ops/get-started/help-overview.md#task-guides) in the Help pane:</span></span>

 - <span data-ttu-id="d852f-161">Paramétrer la facturation électronique OIOUBL</span><span class="sxs-lookup"><span data-stu-id="d852f-161">Set up OIOUBL electronic invoicing</span></span>
 - <span data-ttu-id="d852f-162">Importer les configurations de facturation électronique OIOUBL</span><span class="sxs-lookup"><span data-stu-id="d852f-162">Import OIOUBL electronic invoicing configurations</span></span>
 - <span data-ttu-id="d852f-163">Configurer les comptes client pour la facturation électronique OIOUBL</span><span class="sxs-lookup"><span data-stu-id="d852f-163">Set up customer accounts for OIOUBL electronic invoicing</span></span>

> [!NOTE] 
> <span data-ttu-id="d852f-164">Bien que ces guides de tâches ont été créés pour le format de facture électronique spécifique au Danemark, *OIOUBL*, ils s’appliquent à d’autres pays avec des variantes mineures.</span><span class="sxs-lookup"><span data-stu-id="d852f-164">Although these Task guides were created for Danish-specific e-invoice format *OIOUBL*, they are applicable for other supported countries with minor deviations.</span></span>
