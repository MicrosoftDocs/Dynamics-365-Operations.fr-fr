---
title: "Normes prises en charge pour la facturation électronique en Europe"
description: "Cette rubrique explique le niveau de couverture existant pour la facturation électronique dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition en Europe."
author: mrolecki
manager: AnnBe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: AX 7.0.1, Operations, Core
ms.custom: 10274
ms.search.region: Austria, Denmark, Italy, Norway, Spain, France, Belgium, Netherlands
ms.search.industry: 
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: d41f4d454bc3a763ca6658babde6c3a6a44be73d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="supported-standards-for-electronic-invoicing-in-europe"></a><span data-ttu-id="caa30-103">Normes prises en charge pour la facturation électronique en Europe</span><span class="sxs-lookup"><span data-stu-id="caa30-103">Supported standards for electronic invoicing in Europe</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="caa30-104">Cette rubrique décrit le niveau de couverture qui existe pour la facturation électronique pour Europe.</span><span class="sxs-lookup"><span data-stu-id="caa30-104">This topic explains the level of coverage that exists for electronic invoicing for Europe.</span></span> 

<span data-ttu-id="caa30-105">L'implémentation et l'adoption de la facturation électronique à l'échelle de l'Union européenne est réglementée [Directive 2010/45/EU](http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), ce qui affecte tous les États membres de l'UE.</span><span class="sxs-lookup"><span data-stu-id="caa30-105">Implementation and adoption of European Union-wide electronic invoicing is regulated [Council Directive 2010/45/EU](http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), which affects all EU member states.</span></span> <span data-ttu-id="caa30-106">Les sociétés qui souhaitent tirer parti de la facturation électronique doivent envoyer les factures de commande client, les factures financières, les factures de projet, les avoirs de commande client et les avoirs de facture de projet sous forme de fichiers .xml au gouvernement ou à d'autres partenaires commerciaux qui mandatent l'utilisation de la facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="caa30-106">Companies that want to benefit from electronic invoicing must submit sales order invoices, free text invoices, project invoices, sales order credit notes, and project invoice credit notes as .xml files to the government or other trading parties that mandate use of electronic invoicing.</span></span> <span data-ttu-id="caa30-107">Ces fichiers .xml doivent être conformes à certaines normes.</span><span class="sxs-lookup"><span data-stu-id="caa30-107">These .xml files must comply with certain standards.</span></span> <span data-ttu-id="caa30-108">Les exigences spécifiques au pays et leur implémentation peuvent différer entre les États membres de l'UE, mais généralement ils utilisent le langage universel des affaires ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) dans différentes versions avec des personnalisations ainsi que les spécifications [PEPPOL](http://www.peppol.eu) et les points d'accès pour la validation et le transport.</span><span class="sxs-lookup"><span data-stu-id="caa30-108">The country-specific requirements and their implementation may differ across EU member states but commonly they are using Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) in different versions with customizations as well as [PEPPOL](http://www.peppol.eu) specifications and access points for validation and transportation.</span></span> <span data-ttu-id="caa30-109">Le principal l'avantage du langage UBL est que les documents commerciaux peuvent être normalisés à différentes fins.</span><span class="sxs-lookup"><span data-stu-id="caa30-109">The primary advantage of UBL is that business documents can be standardized for different purposes.</span></span> <span data-ttu-id="caa30-110">Comme le langage UBL est une norme internationale flexible qui répond à de nombreuses exigences métier, ces documents commerciaux peuvent être échangés entre les frontières nationales.</span><span class="sxs-lookup"><span data-stu-id="caa30-110">Because UBL is a flexible, international standard that supports many business requirements, these business documents can be exchanged across national borders.</span></span>

## <a name="what-electronic-invoice-formats-are-currently-available-in-finance-and-operations"></a><span data-ttu-id="caa30-111">Quels formats de facture électronique sont actuellement disponibles dans Finance and Operations ?</span><span class="sxs-lookup"><span data-stu-id="caa30-111">What electronic invoice formats are currently available in Finance and Operations?</span></span>

<span data-ttu-id="caa30-112">Les formats de factures électroniques spécifiques au pays suivants sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="caa30-112">The following country-specific formats of electronic invoices are available:</span></span>

-   <span data-ttu-id="caa30-113">OIOUBL v.2.02 pour le Danemark</span><span class="sxs-lookup"><span data-stu-id="caa30-113">OIOUBL v.2.02 for Denmark</span></span>
-   <span data-ttu-id="caa30-114">EHF v.2.0.8 pour la Norvège</span><span class="sxs-lookup"><span data-stu-id="caa30-114">EHF v.2.0.8 for Norway</span></span>
-   <span data-ttu-id="caa30-115">PEPPOL BIS v.2 pour l'Autriche, la France, et la Belgique</span><span class="sxs-lookup"><span data-stu-id="caa30-115">PEPPOL BIS v.2 for Austria, France, and Belgium</span></span>
-   <span data-ttu-id="caa30-116">UBL-OHNL 1.9 pour les Pays-Bas</span><span class="sxs-lookup"><span data-stu-id="caa30-116">UBL-OHNL 1.9 for the Netherlands</span></span>
-   <span data-ttu-id="caa30-117">FacturaE v.3.2.1 pour l'Espagne</span><span class="sxs-lookup"><span data-stu-id="caa30-117">FacturaE v.3.2.1 for Spain</span></span>
-   <span data-ttu-id="caa30-118">FatturaPA v.1.2 pour l'Italie</span><span class="sxs-lookup"><span data-stu-id="caa30-118">FatturaPA v.1.2 for Italy</span></span>

<span data-ttu-id="caa30-119">La facturation électronique est basée sur la [gestion des états électroniques](../../dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="caa30-119">Electronic invoicing is based on [electronic reporting](../../dev-itpro/analytics/general-electronic-reporting.md).</span></span> <span data-ttu-id="caa30-120">Il existe un **Modèle de facture client** et plusieurs configurations de format de génération d'états électroniques spécifiques au pays créées pour l'Autriche (AT), le Danemark (DK), l'Italie (IT), la Norvège (NO), l'Espagne (ES), la France (FR), la Belgique (BE) et les Pays-Bas (NL).</span><span class="sxs-lookup"><span data-stu-id="caa30-120">There is a **Customer invoice model** data model and a number of country-specific electronic reporting format configurations created for Austria (AT), Denmark (DK), Italy (IT), Norway (NO), Spain (ES), France (FR), Belgium (BE), and the Netherlands (NL).</span></span>

-   <span data-ttu-id="caa30-121">Facture client OIOUBL pour AT, DK et NO</span><span class="sxs-lookup"><span data-stu-id="caa30-121">OIOUBL Sales invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="caa30-122">Avoir de vente OIOUBL pour AT, DK et NO</span><span class="sxs-lookup"><span data-stu-id="caa30-122">OIOUBL Sales credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="caa30-123">Facture de projet OIOUBL pour AT, DK et NO</span><span class="sxs-lookup"><span data-stu-id="caa30-123">OIOUBL Project invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="caa30-124">Avoir de projet OIOUBL pour AT, DK et NO</span><span class="sxs-lookup"><span data-stu-id="caa30-124">OIOUBL Project credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="caa30-125">Facture client UBL FR</span><span class="sxs-lookup"><span data-stu-id="caa30-125">UBL Sales Invoice FR</span></span>
-   <span data-ttu-id="caa30-126">Avoir sur vente UBL FR</span><span class="sxs-lookup"><span data-stu-id="caa30-126">UBL Sales Credit Note FR</span></span>
-   <span data-ttu-id="caa30-127">Facture de projet UBL FR</span><span class="sxs-lookup"><span data-stu-id="caa30-127">UBL Project Invoice FR</span></span>
-   <span data-ttu-id="caa30-128">Avoir de projet UBL FR</span><span class="sxs-lookup"><span data-stu-id="caa30-128">UBL Project Credit Note FR</span></span>
-   <span data-ttu-id="caa30-129">Facture client UBL BE</span><span class="sxs-lookup"><span data-stu-id="caa30-129">UBL Sales Invoice BE</span></span>
-   <span data-ttu-id="caa30-130">Avoir sur vente UBL BE</span><span class="sxs-lookup"><span data-stu-id="caa30-130">UBL Sales Credit Note BE</span></span>
-   <span data-ttu-id="caa30-131">Facture de projet UBL BE</span><span class="sxs-lookup"><span data-stu-id="caa30-131">UBL Project Invoice BE</span></span>
-   <span data-ttu-id="caa30-132">Avoir de projet UBL BE</span><span class="sxs-lookup"><span data-stu-id="caa30-132">UBL Project Credit Note BE</span></span>
-   <span data-ttu-id="caa30-133">Facture client UBL NL</span><span class="sxs-lookup"><span data-stu-id="caa30-133">UBL Sales Invoice NL</span></span>
-   <span data-ttu-id="caa30-134">Avoir sur vente UBL NL</span><span class="sxs-lookup"><span data-stu-id="caa30-134">UBL Sales Credit Note NL</span></span>
-   <span data-ttu-id="caa30-135">Facture de projet UBL NL</span><span class="sxs-lookup"><span data-stu-id="caa30-135">UBL Project Invoice NL</span></span>
-   <span data-ttu-id="caa30-136">Avoir de projet UBL NL</span><span class="sxs-lookup"><span data-stu-id="caa30-136">UBL Project Credit Note NL</span></span> 
-   <span data-ttu-id="caa30-137">Facture client (ES)</span><span class="sxs-lookup"><span data-stu-id="caa30-137">Sales invoice (ES)</span></span>
-   <span data-ttu-id="caa30-138">Facture client (IT)</span><span class="sxs-lookup"><span data-stu-id="caa30-138">Sales invoice (IT)</span></span>
-   <span data-ttu-id="caa30-139">Facture de projet (ES)</span><span class="sxs-lookup"><span data-stu-id="caa30-139">Project invoice (ES)</span></span>
-   <span data-ttu-id="caa30-140">Facture de projet (IT)</span><span class="sxs-lookup"><span data-stu-id="caa30-140">Project invoice (IT)</span></span>

<span data-ttu-id="caa30-141">Les factures électroniques et les avoirs que vous générez contiennent les informations requises, telles que le numéro EAN, la personne à contacter, le numéro de compte de dimension et les informations d'adresse pour le client.</span><span class="sxs-lookup"><span data-stu-id="caa30-141">The electronic invoices and credit notes that you generate include required information, such as a European Article Numbering (EAN) number, contact person, dimension account number, and address information for the customer.</span></span> <span data-ttu-id="caa30-142">Les règles de contrôle sont appliquées lors de la génération des factures pour vous permettre de vérifier que les informations entrées sont correctes.</span><span class="sxs-lookup"><span data-stu-id="caa30-142">Validation rules are applied when invoices are generated so you can verify that the correct information has been entered.</span></span> <span data-ttu-id="caa30-143">L'ensemble des informations requises peut différer d'un pays à l'autre.</span><span class="sxs-lookup"><span data-stu-id="caa30-143">The set of required information may differ from country to country.</span></span> <span data-ttu-id="caa30-144">Comme les exigences ainsi que les pays et formats pris en charge peuvent être modifiés, vous devez toujours aller dans la bibliothèque d'actifs partagés de Microsoft Dynamics Lifecycle Services (LCS) et afficher la liste la plus récente des fichiers disponibles dont le type d'actif est **Configuration GER**.</span><span class="sxs-lookup"><span data-stu-id="caa30-144">Because the requirements, as well as supported countries and formats, is subject to change, you should always go to the Shared asset library on Microsoft Dynamics Lifecycle services (LCS) and view the most up-to-date list of available files that have an asset type of **GER configuration**.</span></span>

## <a name="additional-information"></a><span data-ttu-id="caa30-145">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="caa30-145">Additional information</span></span>
<span data-ttu-id="caa30-146">Pour plus de détails sur le paramétrage des factures électroniques, vous pouvez visionner [Guides de tâche](../../fin-and-ops/get-started/help-overview.md#task-guides) dans volet d'aide :</span><span class="sxs-lookup"><span data-stu-id="caa30-146">For more details about how to set up electronic invoices, you can play the following [Task guides](../../fin-and-ops/get-started/help-overview.md#task-guides) in the Help pane:</span></span>

 - <span data-ttu-id="caa30-147">Paramétrer la facturation électronique OIOUBL</span><span class="sxs-lookup"><span data-stu-id="caa30-147">Set up OIOUBL electronic invoicing</span></span>
 - <span data-ttu-id="caa30-148">Importer les configurations de facturation électronique OIOUBL</span><span class="sxs-lookup"><span data-stu-id="caa30-148">Import OIOUBL electronic invoicing configurations</span></span>
 - <span data-ttu-id="caa30-149">Configurer les comptes client pour la facturation électronique OIOUBL</span><span class="sxs-lookup"><span data-stu-id="caa30-149">Set up customer accounts for OIOUBL electronic invoicing</span></span>

> [!NOTE] 
> <span data-ttu-id="caa30-150">Bien que ces guides de tâches ont été créés pour le format de facture électronique spécifique au Danemark, *OIOUBL*, ils s'appliquent à d'autres pays avec des variantes mineures.</span><span class="sxs-lookup"><span data-stu-id="caa30-150">Although these Task guides were created for Danish-specific e-invoice format *OIOUBL*, they are applicable for other supported countries with minor deviations.</span></span>

