---
title: "Déclaration d'échanges de biens"
description: "Cet article fournit des informations sur la génération d'états de déclaration d'échanges de biens pour le commerce de marchandises et, dans certains cas, pour les services entre les pays/régions de l'Union européenne (UE). Il fournit une vue d'ensemble du processus de déclaration, et décrit les paramètres et les conditions préalables requises."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Intrastat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 28581
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7c713f3a1cb5aa4758a72a7cc42c73c57b602219
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="intrastat"></a><span data-ttu-id="8d794-104">Déclaration d'échanges de biens</span><span class="sxs-lookup"><span data-stu-id="8d794-104">Intrastat</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="8d794-105">Cet article fournit des informations sur la génération d'états de déclaration d'échanges de biens pour le commerce de marchandises et, dans certains cas, pour les services entre les pays/régions de l'Union européenne (UE).</span><span class="sxs-lookup"><span data-stu-id="8d794-105">This article provides information about Intrastat reporting for the trade of goods and, in some cases, services among countries/regions of the European Union (EU).</span></span> <span data-ttu-id="8d794-106">Il fournit une vue d'ensemble du processus de déclaration, et décrit les paramètres et les conditions préalables requises.</span><span class="sxs-lookup"><span data-stu-id="8d794-106">It provides an overview of the reporting process, and describes the required settings and prerequisites.</span></span>

<span data-ttu-id="8d794-107">Intrastat est le système de collecte d'informations et de génération de statistiques sur le commerce de marchandises entre les pays/régions de l'Union européenne (UE).</span><span class="sxs-lookup"><span data-stu-id="8d794-107">Intrastat is the system for collecting information and generating statistics about the trade of goods among countries/regions of the European Union (EU).</span></span> <span data-ttu-id="8d794-108">Une génération d'états Intrastat est requise chaque fois qu'un produit franchit la frontière d'un autre pays/région de l'Union Européenne.</span><span class="sxs-lookup"><span data-stu-id="8d794-108">Intrastat reporting is required whenever a product crosses the border of another EU country/region.</span></span> <span data-ttu-id="8d794-109">Dans plusieurs pays/régions, la génération d'états Intrastat s'applique également aux services.</span><span class="sxs-lookup"><span data-stu-id="8d794-109">In several countries/regions, Intrastat reporting also applies to services.</span></span> <span data-ttu-id="8d794-110">Les éléments obligatoires et facultatifs peuvent être collectés dans la génération d'états Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8d794-110">Mandatory and optional elements can be collected in Intrastat reporting.</span></span> <span data-ttu-id="8d794-111">Les éléments suivants sont obligatoires : le numéro de taxe sur la valeur ajoutée (TVA) de la partie responsable de fournir les informations, la période de référence, le flux (arrivée ou expédition), le code marchandise à huit chiffres, l'état membre partenaire (état membre de provenance à l'arrivée et état membre de destination à l'expédition), la valeur des marchandises, la quantité des marchandises (masse nette et unité supplémentaire) et la nature de la transaction.</span><span class="sxs-lookup"><span data-stu-id="8d794-111">The following elements are mandatory: the value-added tax (VAT) number of the party that is responsible for providing information, the reference period, the flow (arrival or dispatch), the eight-digit commodity code, the partner member state (member state of consignment on arrivals and member state of destination on dispatches), the value of the goods, the quantity of the goods (net mass and supplementary unit), and the nature of the transaction.</span></span> <span data-ttu-id="8d794-112">Les pays/régions peuvent également recueillir des éléments facultatifs sous diverses conditions.</span><span class="sxs-lookup"><span data-stu-id="8d794-112">Countries/regions can also collect optional elements under various conditions.</span></span> <span data-ttu-id="8d794-113">Certains éléments facultatifs sont le pays/la région d'origine, les conditions de livraison, le mode de transport, un code marchandise plus détaillé que CN8, la région d'origine à l'expédition et la région de destination à l'arrivée, la procédure statistique, la valeur statistique, une description des marchandises, et le port/aéroport de chargement/déchargement.</span><span class="sxs-lookup"><span data-stu-id="8d794-113">Some optional elements are the country/region of origin, the delivery terms, the mode of transport, a more detailed commodity code than CN8, the region of origin on dispatches and the region of destination on arrivals, the statistical procedure, the statistical value, a description of the goods, and the port/airport of loading/unloading.</span></span>

## <a name="overview-of-the-intrastat-reporting-process"></a><span data-ttu-id="8d794-114">Vue d'ensemble du processus de génération d'états Intrastat</span><span class="sxs-lookup"><span data-stu-id="8d794-114">Overview of the Intrastat reporting process</span></span>
<span data-ttu-id="8d794-115">Les sections suivantes décrivent le flux global d'informations utilisé pour la génération d'états Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8d794-115">The following sections describe the overall flow of information that is used for Intrastat reporting.</span></span>

### <a name="1-enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a><span data-ttu-id="8d794-116">1. Entrez une transaction qui franchit la frontière d'un autre pays de l'Union Européenne.</span><span class="sxs-lookup"><span data-stu-id="8d794-116">1. Enter a transaction that crosses the border of another EU country/region</span></span>

<span data-ttu-id="8d794-117">Une facture client, une facture financière, une facture d'achat, une facture de projet, un bon de livraison du client, un accusé de réception de marchandises de fournisseur ou un ordre de transfert est transféré au journal Intrastat uniquement si le type de pays/région de destination (à l'expédition) ou la consignation (à l'arrivée) est **EU**.</span><span class="sxs-lookup"><span data-stu-id="8d794-117">A customer invoice, free text invoice, purchase invoice, project invoice, customer packing slip, vendor product receipt, or transfer order is transferred to the Intrastat journal only if the country/region type of the destination (on dispatches) or consignment (on arrivals) is **EU**.</span></span> <span data-ttu-id="8d794-118">Cette fonctionnalité a été étendue pour Microsoft Dynamics 365 for Operations (1611) et permet de spécifier des adresses de chargement pour une transaction intracommunautaire.</span><span class="sxs-lookup"><span data-stu-id="8d794-118">This feature was extended for Microsoft Dynamics 365 for Operations (1611) and allows you to specify lading addresses for an intra-community transaction.</span></span> <span data-ttu-id="8d794-119">Si une adresse de chargement diffère de l'adresse commerciale d'un fournisseur (ou de l'adresse commerciale d'un client pour l'ordre de retour), la déclaration d'échanges de biens utilisera ces informations.</span><span class="sxs-lookup"><span data-stu-id="8d794-119">If a lading address differs with a vendor business address (or customer business address for return order) the Intrastat reporting will operate with this information.</span></span> <span data-ttu-id="8d794-120">Lorsque vous créez une commande client, une facture financière, une commande fournisseur, une facture fournisseur, une facture de projet ou un ordre de transfert, certains champs liés au commerce extérieur ont des valeurs par défaut dans l'en-tête de document ou sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="8d794-120">When you create a sales order, free text invoice, purchase order, vendor invoice, project invoice, or transfer order, some fields that are related to foreign trade have default values in the document header or on the line.</span></span> <span data-ttu-id="8d794-121">Le code transaction par défaut provient du champ correspondant de la page **Paramètres de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="8d794-121">The default transaction code is taken from the corresponding field on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="8d794-122">Le code marchandise par défaut, le pays/la région d'origine, et l'état/la province d'origine proviennent de l'article.</span><span class="sxs-lookup"><span data-stu-id="8d794-122">The default commodity code, country/region of origin, and state/province of origin are taken from the item.</span></span> <span data-ttu-id="8d794-123">Vous pouvez modifier les valeurs par défaut et vous pouvez également remplir d'autres informations liées au commerce extérieur : la procédure statistique, le mode de transport, et le port.</span><span class="sxs-lookup"><span data-stu-id="8d794-123">You can change the default values and can also fill in other foreign trade–related information: the statistics procedure, transport method, and port.</span></span>

### <a name="2-use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a><span data-ttu-id="8d794-124">2. Le journal de déclaration d'échanges de biens vous permet de générer des informations sur le commerce entre pays/régions de l'Union européenne.</span><span class="sxs-lookup"><span data-stu-id="8d794-124">2. Use the Intrastat journal to generate information about trade among EU countries/regions</span></span>

<span data-ttu-id="8d794-125">À des fins statistiques, vous générez des informations sur le commerce entre les pays/régions de l'Union européenne tous les mois.</span><span class="sxs-lookup"><span data-stu-id="8d794-125">For statistical purposes, you generate information about trade among EU countries/regions every month.</span></span> <span data-ttu-id="8d794-126">Vous pouvez transférer des transactions d'une facture financière, d'une facture client, d'un bon de livraison du client, d'une facture fournisseur, d'un bon de livraison fournisseur, d'une facture de projet, ou d'un ordre de transfert, en fonction des critères de transfert paramétrées sur la page **Paramètres de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="8d794-126">You can transfer transactions from a free text invoice, customer invoice, customer packing slip, vendor invoice, vendor packing slip, project invoice, or transfer order, according to the transfer criteria that are set up on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="8d794-127">Sinon, vous pouvez saisir les transactions manuellement.</span><span class="sxs-lookup"><span data-stu-id="8d794-127">Alternatively, you can enter transactions manually.</span></span> <span data-ttu-id="8d794-128">Vous pouvez manuellement mettre à jour les transactions transférées dans le journal Intrastat, si des mises à jour sont requises.</span><span class="sxs-lookup"><span data-stu-id="8d794-128">You can manually update transferred transactions in the Intrastat journal, if any updates are required.</span></span> <span data-ttu-id="8d794-129">Sous des conditions spécifiques qui sont paramétrées sur la page **Compression de la déclaration d'échanges de biens**, vous pouvez compresser les transactions dans le journal Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8d794-129">Under specific conditions that are set up on the **Compression of Intrastat** page, you can compress the transactions in the Intrastat journal.</span></span> <span data-ttu-id="8d794-130">Certains pays/régions vous permettent d'appliquer un seuil de transaction faible.</span><span class="sxs-lookup"><span data-stu-id="8d794-130">Some countries/regions let you apply a small transaction threshold.</span></span> <span data-ttu-id="8d794-131">Vous pouvez ensuite générer un état pour les transactions qui sont en dessous de ce seuil sous le code marchandise spécifié.</span><span class="sxs-lookup"><span data-stu-id="8d794-131">You can then report transactions that are below that threshold under the specified commodity code.</span></span> <span data-ttu-id="8d794-132">Vous pouvez mettre à jour le code marchandise à jour dans les lignes correspondantes du journal Intrastat, en fonction du paramètre **Limite inférieure** de la page **Paramètres de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="8d794-132">You can update the commodity code on the corresponding Intrastat journal lines, based on the **Minimum limit** setting on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="8d794-133">Vous pouvez également compresser ces transactions, en fonction du paramètre **Compression de la déclaration d'échanges de biens**.</span><span class="sxs-lookup"><span data-stu-id="8d794-133">You can also compress those transactions, based on the **Compression of Intrastat** setting.</span></span> <span data-ttu-id="8d794-134">Vous pouvez valider l'exhaustivité des transactions dans le journal Intrastat, en fonction du paramètre **Vérifier le paramétrage** de la page **Paramètres de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="8d794-134">You can validate the completeness of the transactions in the Intrastat journal, based on the **Check setup** setting on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="8d794-135">Les données dans les champs correspondants peuvent être validées pour leur exhaustivité : pays/région, état ou province, poids, code marchandise, code transaction, unité supplémentaire, port, origine, conditions de livraison, mode de transport, et numéro identifiant TVA.</span><span class="sxs-lookup"><span data-stu-id="8d794-135">The data in corresponding fields might be validated for completeness: country/region, state or province, weight, commodity code, transaction code, additional unit, port, origin, terms of delivery, transport method, and tax exempt number.</span></span> <span data-ttu-id="8d794-136">Les transactions qui ne sont pas terminées sont marquées comme non valides.</span><span class="sxs-lookup"><span data-stu-id="8d794-136">Transactions that aren't completed will be marked as not valid.</span></span>

### <a name="3-use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a><span data-ttu-id="8d794-137">3. Le journal de déclaration d'échanges de biens vous permet de générer des états sur les informations relatives au commerce entre pays/régions de l'Union européenne.</span><span class="sxs-lookup"><span data-stu-id="8d794-137">3. Use the Intrastat journal to report information about trade among EU countries/regions</span></span>

<span data-ttu-id="8d794-138">À des fins statistiques, vous générez des états sur les informations relative au commerce entre les pays/régions de l'Union européenne tous les mois.</span><span class="sxs-lookup"><span data-stu-id="8d794-138">For statistical purposes, you report information about trade among EU countries/regions every month.</span></span> <span data-ttu-id="8d794-139">Vous pouvez imprimer l'état Intrastat, en fonction des paramètres **Mise en correspondance des formats d'état** de la page **Paramètres de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="8d794-139">You can print the Intrastat report, based on the **Report format mapping** settings on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="8d794-140">Vous pouvez également générer un fichier électronique, en fonction des paramètres **Mise en correspondance des formats de fichier** de la page **Paramètres de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="8d794-140">You can also generate an electronic file, based on the **File format mapping** settings on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="8d794-141">Pour plus d'informations sur la déclaration d'échanges de biens, consultez les enregistrements de tâche de la déclaration d'échanges de biens :</span><span class="sxs-lookup"><span data-stu-id="8d794-141">For more information about Intrastat reporting, including required prerequisites, see the Intrastat reporting task recordings:</span></span>

-   <span data-ttu-id="8d794-142">Générer un fichier de déclaration d'échanges de biens de l'UE,</span><span class="sxs-lookup"><span data-stu-id="8d794-142">Generate an EU Intrastat declaration,</span></span>
-   <span data-ttu-id="8d794-143">Transférer des transactions dans la déclaration d'échanges de biens,</span><span class="sxs-lookup"><span data-stu-id="8d794-143">Transfer transactions to the Intrastat,</span></span>
-   <span data-ttu-id="8d794-144">Définition d'une adresse de chargement pour une transaction intracommunautaire.</span><span class="sxs-lookup"><span data-stu-id="8d794-144">Specifying lading address for an intra-community transaction.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d794-145">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="8d794-145">Prerequisites</span></span>
<span data-ttu-id="8d794-146">Le tableau suivant répertorie les conditions préalables à la déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="8d794-146">The following table lists the prerequisites for Intrastat reporting.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d794-147">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="8d794-147">Prerequisite</span></span></th>
<th><span data-ttu-id="8d794-148">Description</span><span class="sxs-lookup"><span data-stu-id="8d794-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8d794-149">Configuration de l'adresse</span><span class="sxs-lookup"><span data-stu-id="8d794-149">Address setup</span></span></td>
<td><span data-ttu-id="8d794-150">Paramétrez les codes ISO (Organisation internationale de normalisation) des pays/régions.</span><span class="sxs-lookup"><span data-stu-id="8d794-150">Set up International Organization for Standardization (ISO) codes for countries/regions.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d794-151">Entité juridique</span><span class="sxs-lookup"><span data-stu-id="8d794-151">Legal entity</span></span></td>
<td><span data-ttu-id="8d794-152">Paramétrez les numéros identifiant TVA pour l'importation/exportation, l'extension du numéro d'agence pour l'importation/exportation, puis le code Intrastat affecté à l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="8d794-152">Set up tax exempt numbers for import/export, the branch number extension for import/export, and the Intrastat code that is assigned to the legal entity.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8d794-153">Hiérarchie de catégories de produit (hiérarchie de vente, hiérarchie d'approvisionnement)</span><span class="sxs-lookup"><span data-stu-id="8d794-153">Product category hierarchy (sales hierarchy, procurement hierarchy)</span></span></td>
<td><span data-ttu-id="8d794-154">Affectez les codes marchandise Intrastat aux nœuds de catégorie sous l'onglet <strong>Codes marchandise</strong> de la page <strong>Hiérarchie de catégories</strong>.</span><span class="sxs-lookup"><span data-stu-id="8d794-154">Assign the Intrastat commodity codes to the category nodes on the <strong>Commodity codes</strong> tab of the <strong>Category hierarchy</strong> page.</span></span> <span data-ttu-id="8d794-155">Lorsque vous affectez un code marchandise à un nœud de catégorie parente, ce code peut s'applique à tous les nœuds de catégorie enfant.</span><span class="sxs-lookup"><span data-stu-id="8d794-155">When you assign a commodity code to a parent category node, that code is applicable to all child category nodes.</span></span> <span data-ttu-id="8d794-156">Les codes marchandise sélectionnés seront disponibles dans la vue <strong>Sélectionné</strong> lorsque vous sélectionnez un code marchandise dans les détails des produits lancés, et sur les lignes de commande client, de commande fournisseur et d'ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="8d794-156">The selected commodity codes will be available in the <strong>Selected</strong> view when you select a commodity code in the released product details, and on sales order, purchase order, and transfer order lines.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d794-157">Détails des produits lancés</span><span class="sxs-lookup"><span data-stu-id="8d794-157">Released product details</span></span></td>
<td><span data-ttu-id="8d794-158">Paramétrez les données suivantes sur le commerce extérieur pour les produits lancés :</span><span class="sxs-lookup"><span data-stu-id="8d794-158">Set up the following foreign trade data for released products:</span></span>
<ul>
<li><span data-ttu-id="8d794-159"><strong>Code marchandise</strong> – Effectuez votre sélection soit dans la liste des marchandises sélectionnées qui est extraite des catégories de produit affectées, soit dans la liste complète des codes marchandise Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8d794-159"><strong>Commodity code</strong> – Select from either the list of selected commodities that is retrieved from assigned product categories or the full list of Intrastat commodity codes.</span></span></li>
<li><span data-ttu-id="8d794-160"><strong>Pourcentage des frais statistiques</strong></span><span class="sxs-lookup"><span data-stu-id="8d794-160"><strong>Statistical charges percentage</strong></span></span></li>
<li><span data-ttu-id="8d794-161"><strong>Pays/région d'origine</strong> – Sélectionnez le pays/la région par défaut où les marchandises ont été entièrement obtenues ou produites.</span><span class="sxs-lookup"><span data-stu-id="8d794-161"><strong>Country/region of origin</strong> – Select the default country/region where the goods were completely obtained or produced.</span></span></li>
<li><span data-ttu-id="8d794-162"><strong>État/Province d'origine/de destination</strong> – Sélectionnez l'état/la province par défaut de destination à l'arrivée et l'état/la province d'origine à l'expédition.</span><span class="sxs-lookup"><span data-stu-id="8d794-162"><strong>State/province of origin/destination</strong> – Select the default state/province of destination for arrivals and the state/province of origin for dispatches.</span></span></li>
<li><span data-ttu-id="8d794-163"><strong>Poids net en kg</strong></span><span class="sxs-lookup"><span data-stu-id="8d794-163"><strong>Net weight in kg</strong></span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8d794-164">Clients</span><span class="sxs-lookup"><span data-stu-id="8d794-164">Customers</span></span></td>
<td><span data-ttu-id="8d794-165">Paramétrez l'adresse de livraison du client dans le pays/la région de l'Union européenne.</span><span class="sxs-lookup"><span data-stu-id="8d794-165">Set up the customer delivery address in the EU country/region.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d794-166">Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="8d794-166">Vendors</span></span></td>
<td><span data-ttu-id="8d794-167">Paramétrez l'adresse de livraison du fournisseur dans le pays/la région de l'Union européenne.</span><span class="sxs-lookup"><span data-stu-id="8d794-167">Set up the vendor address in the EU country/region.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8d794-168">Frais divers</span><span class="sxs-lookup"><span data-stu-id="8d794-168">Miscellaneous charges</span></span></td>
<td><span data-ttu-id="8d794-169">Paramétrez un code frais divers à inclure avec le montant de la facture, le montant statistique, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="8d794-169">Set up the miscellaneous charges code to include in the invoice amount, the statistical amount, or both.</span></span> <span data-ttu-id="8d794-170">Sur la page <strong>Codes frais</strong> , sous l'onglet <strong>Commerce extérieur</strong>, activez <strong>Valeur de la facture de la déclaration d'échanges de biens</strong> afin d'inclure le montant des frais à la valeur de la facture, et activez <strong>Valeur statistique de la déclaration d'échanges de biens</strong> afin d'inclure le montant des frais à la valeur statistique.</span><span class="sxs-lookup"><span data-stu-id="8d794-170">On the <strong>Charges codes</strong> page, on the <strong>Foreign trade</strong> tab, enable <strong>Intrastat invoice value</strong> to include the charges amount in the invoice value, and enable <strong>Intrastat statistical value</strong> to include the charges amount in the statistical value.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d794-171">États électroniques</span><span class="sxs-lookup"><span data-stu-id="8d794-171">Electronic reporting</span></span></td>
<td><span data-ttu-id="8d794-172">Paramétrez les configurations électroniques de génération d'états pour exporter les données Intrastat dans un fichier électronique au format requis par les autorités appropriées, et pour obtenir un aperçu des données Intrastat dans un format convivial et lisible (par exemple, dans Microsoft Excel).</span><span class="sxs-lookup"><span data-stu-id="8d794-172">Set up electronic reporting configurations to export Intrastat data in an electronic file that has the format that is requested by the relevant authorities, and to preview Intrastat data in a user-friendly, readable format (for example, in Microsoft Excel).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d794-173">Entreposage</span><span class="sxs-lookup"><span data-stu-id="8d794-173">Warehousing</span></span></td>
<td><span data-ttu-id="8d794-174">Associer les comptes fournisseur aux codes entrepôt pour remplir le numéro identifiant TVA lors du transfert de l'ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="8d794-174">Associate vendor accounts with warehouse codes for filling tax exempt number when transferring Transfer order.</span></span></td>
</tr>
</tbody>
</table>

## <a name="setup"></a><span data-ttu-id="8d794-175">Configuration</span><span class="sxs-lookup"><span data-stu-id="8d794-175">Setup</span></span>
<span data-ttu-id="8d794-176">Les sections suivantes décrivent les paramètres requis pour la génération d'états Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8d794-176">The following sections describe the settings that are required for Intrastat reporting.</span></span>

### <a name="set-up-all-required-intrastat-related-lists"></a><span data-ttu-id="8d794-177">Paramétrer toutes les listes requises associées à Intrastat</span><span class="sxs-lookup"><span data-stu-id="8d794-177">Set up all required Intrastat-related lists</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d794-178">Liste</span><span class="sxs-lookup"><span data-stu-id="8d794-178">List</span></span></th>
<th><span data-ttu-id="8d794-179">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8d794-179">Additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8d794-180">Codes marchandise</span><span class="sxs-lookup"><span data-stu-id="8d794-180">Commodity codes</span></span></td>
<td><span data-ttu-id="8d794-181">Paramétrez une hiérarchie de catégories de type <strong>Code marchandise</strong>, et entrez tous les codes marchandise selon la liste combinée de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="8d794-181">Set up a category hierarchy of type <strong>Commodity code</strong>, and enter all commodity codes according to the combined nomenclature list.</span></span> <span data-ttu-id="8d794-182">Pour chaque marchandise, vous paramétrez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="8d794-182">For each commodity, you set up the following information:</span></span>
<ul>
<li><span data-ttu-id="8d794-183">Le nom de la marchandise et le code marchandise</span><span class="sxs-lookup"><span data-stu-id="8d794-183">The name of the commodity and the commodity code</span></span></li>
<li><span data-ttu-id="8d794-184">Le nom convivial et/ou le nom traduit</span><span class="sxs-lookup"><span data-stu-id="8d794-184">The friendly name and/or translated name</span></span></li>
<li><span data-ttu-id="8d794-185">Paramètres pour signaler des unités supplémentaires dans l'onglet <strong>Commerce extérieur</strong>. Vous pouvez sélectionner l'unité supplémentaire dans la liste des unités.</span><span class="sxs-lookup"><span data-stu-id="8d794-185">Settings for reporting additional (supplementary) units on the <strong>Foreign trade</strong> tab. You can select the additional unit in the unit list.</span></span> <span data-ttu-id="8d794-186">Vous pouvez également spécifier si le poids des marchandises doit être déclaré en sus de l'unité supplémentaire sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8d794-186">You can also specify whether the weight of commodities must be reported in addition to the selected additional unit.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d794-187">Codes transaction</span><span class="sxs-lookup"><span data-stu-id="8d794-187">Transaction codes</span></span></td>
<td><span data-ttu-id="8d794-188">Paramétrez la nature de la transaction en fonction des exigences de votre pays/région.</span><span class="sxs-lookup"><span data-stu-id="8d794-188">Set up the nature of the transaction according to your country's/region's requirements.</span></span> <span data-ttu-id="8d794-189">Pour chaque code transaction que vous paramétrez, vous devez définir les règles de calcul des montants de facture et les montants statistiques pour les ordres de transfert et les ventes/commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="8d794-189">For each transaction code that you set up, you must set up the rules for calculating invoice amounts and statistical amounts for transfer orders and sales/purchase orders.</span></span>
<ul>
<li><span data-ttu-id="8d794-190">Pour les ordres de transfert, vous paramétrez une des règles suivantes pour le calcul des montants de facture et des montants statistiques :</span><span class="sxs-lookup"><span data-stu-id="8d794-190">For transfer orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:</span></span>
<ul>
<li><span data-ttu-id="8d794-191"><strong>Vide</strong> – Le montant est 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="8d794-191"><strong>Empty</strong> – The amount will be 0 (zero).</span></span></li>
<li><span data-ttu-id="8d794-192"><strong>Montant du coût financier</strong> – Le montant est égal au coût financier.</span><span class="sxs-lookup"><span data-stu-id="8d794-192"><strong>Financial cost amount</strong> – The amount will be equal to the financial cost.</span></span></li>
<li><span data-ttu-id="8d794-193"><strong>Coût total</strong> – Le montant est égal au coût total de la transaction.</span><span class="sxs-lookup"><span data-stu-id="8d794-193"><strong>Total cost</strong> – The amount will be equal to the total cost of the transaction.</span></span></li>
<li><span data-ttu-id="8d794-194"><strong>Manuel</strong> – Le montant est égal au montant qui est spécifié manuellement sur la ligne d'ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="8d794-194"><strong>Manual</strong> – The amount will be equal to the amount that is manually specified on the transfer order line.</span></span></li>
</ul></li>
<li><span data-ttu-id="8d794-195">Pour les commandes client et les commandes fournisseur, vous paramétrez une des règles suivantes pour le calcul des montants de facture et des montants statistiques :</span><span class="sxs-lookup"><span data-stu-id="8d794-195">For sales orders and purchase orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:</span></span>
<ul>
<li><span data-ttu-id="8d794-196"><strong>Vide</strong> – Le montant est 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="8d794-196"><strong>Empty</strong> – The amount will be 0 (zero).</span></span></li>
<li><span data-ttu-id="8d794-197"><strong>Montant de la facture</strong> – Le montant est égal au montant facturé pour la marchandise.</span><span class="sxs-lookup"><span data-stu-id="8d794-197"><strong>Invoice amount</strong> – The amount will be equal to the amount that is invoiced for the commodity.</span></span></li>
<li><span data-ttu-id="8d794-198"><strong>Montant de base</strong> – Le montant est égal au montant qui serait facturé avant que toute remise soit appliquée.</span><span class="sxs-lookup"><span data-stu-id="8d794-198"><strong>Base amount</strong> – The amount will be equal to the amount that would be invoiced before any discount is applied.</span></span></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8d794-199">Modes de transport</span><span class="sxs-lookup"><span data-stu-id="8d794-199">Transport methods</span></span></td>
<td><span data-ttu-id="8d794-200">Paramétrez le mode de transport en fonction des exigences de votre pays/région.</span><span class="sxs-lookup"><span data-stu-id="8d794-200">Set up the transport mode according to your country's/region's requirements.</span></span> <span data-ttu-id="8d794-201">Pour chaque mode de livraison, vous pouvez paramétrer une méthode de transport par défaut sous l'onglet <strong>Commerce extérieur</strong>.</span><span class="sxs-lookup"><span data-stu-id="8d794-201">For each delivery mode, you can set up a default transport method on the <strong>Foreign trade</strong> tab.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d794-202">Ports</span><span class="sxs-lookup"><span data-stu-id="8d794-202">Ports</span></span></td>
<td><span data-ttu-id="8d794-203">Paramétrez le port/aéroport de chargement/déchargement si ces informations sont recueillies par votre pays/région.</span><span class="sxs-lookup"><span data-stu-id="8d794-203">Set up the port/airport of loading/unloading if this information is collected by your country/region.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8d794-204">Procédures statistiques</span><span class="sxs-lookup"><span data-stu-id="8d794-204">Statistics procedures</span></span></td>
<td><span data-ttu-id="8d794-205">Paramétrez la procédure statistique si ces informations sont recueillies par votre pays/région.</span><span class="sxs-lookup"><span data-stu-id="8d794-205">Set up the statistical procedure if this information is collected by your country/region.</span></span></td>
</tr>
</tbody>
</table>

### <a name="set-up-rules-for-compressing-intrastat-transactions"></a><span data-ttu-id="8d794-206">Paramétrage de règles pour la compression des transactions Intrastat</span><span class="sxs-lookup"><span data-stu-id="8d794-206">Set up rules for compressing Intrastat transactions</span></span>

<span data-ttu-id="8d794-207">Sur la page **Compression de la déclaration d'échanges de biens**, vous pouvez sélectionner les champs à utiliser pour la compression.</span><span class="sxs-lookup"><span data-stu-id="8d794-207">On the **Compression of Intrastat** page, you can select the fields to use for compression.</span></span> <span data-ttu-id="8d794-208">Toutes les transactions ayant la même combinaison de valeurs pour les champs sélectionnés dans le journal Intrastat seront compressées en une seule transaction lors de l'exécution de la fonction Compresser dans le journal Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8d794-208">All transactions that have the same combination of values for the selected fields in the Intrastat journal will be compressed into a single transaction when you run the Compress function in the Intrastat journal.</span></span>

### <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="8d794-209">Définir les paramètres de commerce extérieur</span><span class="sxs-lookup"><span data-stu-id="8d794-209">Set up foreign trade parameters</span></span>

<span data-ttu-id="8d794-210">La page **Paramètres de commerce extérieur** permet de définir les paramètres du tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="8d794-210">Use the **Foreign trade parameters** page to set up the parameters in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d794-211">Tabulation</span><span class="sxs-lookup"><span data-stu-id="8d794-211">Tab</span></span></th>
<th><span data-ttu-id="8d794-212">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8d794-212">Parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8d794-213">Général</span><span class="sxs-lookup"><span data-stu-id="8d794-213">General</span></span></td>
<td><ul>
<li><span data-ttu-id="8d794-214"><strong>Général</strong> – Spécifiez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="8d794-214"><strong>General</strong> – Specify the following information:</span></span>
<ul>
<li><span data-ttu-id="8d794-215">Les codes transaction par défaut pour les commandes client, les commandes fournisseur, les avoirs et les ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="8d794-215">The default transaction codes for sales orders, purchase orders, credit notes, and transfer orders.</span></span> <span data-ttu-id="8d794-216">Le code transaction paramétré pour les avoirs est également utilisé comme code pour le retour des marchandises physiques et pour les écarts des retours physiques par rapport aux avoirs de correction.</span><span class="sxs-lookup"><span data-stu-id="8d794-216">The transaction code that is set up for credit notes is also used as the code for physical goods return and is used for deviating physical returns versus correction credit notes.</span></span></li>
<li><span data-ttu-id="8d794-217">L'employé responsable de la préparation des états Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8d794-217">The employee who is responsible for preparing Intrastat reports.</span></span></li>
</ul></li>
<li><span data-ttu-id="8d794-218"><strong>Limite inférieure</strong> – Permet de spécifier les paramètres de mise à jour des transactions qui sont en dessous du seuil :</span><span class="sxs-lookup"><span data-stu-id="8d794-218"><strong>Minimum limit</strong> – Specify the settings for updating transactions that are below the threshold:</span></span>
<ul>
<li><span data-ttu-id="8d794-219">Le montant et le poids de seuil</span><span class="sxs-lookup"><span data-stu-id="8d794-219">The threshold amount and weight</span></span></li>
<li><span data-ttu-id="8d794-220">Le code marchandise à appliquer aux transactions qui sont sous le seuil</span><span class="sxs-lookup"><span data-stu-id="8d794-220">The commodity code to apply to transactions that are under the threshold</span></span></li>
</ul></li>
<li><span data-ttu-id="8d794-221"><strong>Transfert</strong> – Permet de spécifier les critères pour transférer les transactions vers le journal Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8d794-221"><strong>Transfer</strong> – Specify the criteria for transferring transactions to the Intrastat journal.</span></span> <span data-ttu-id="8d794-222">Vous pouvez spécifier que les transactions sont transférées uniquement lorsque les articles correspondent à l'un des les critères suivants ou à tous :</span><span class="sxs-lookup"><span data-stu-id="8d794-222">You can specify that transactions are transferred only when the items meet one or all of the following criteria:</span></span>
<ul>
<li><span data-ttu-id="8d794-223">Les articles ne sont pas des articles de service.</span><span class="sxs-lookup"><span data-stu-id="8d794-223">The items aren't service items.</span></span></li>
<li><span data-ttu-id="8d794-224">L'article est doté d'un code marchandise.</span><span class="sxs-lookup"><span data-stu-id="8d794-224">The items have a commodity code.</span></span></li>
<li><span data-ttu-id="8d794-225">Les articles ont un poids.</span><span class="sxs-lookup"><span data-stu-id="8d794-225">The items have a weight.</span></span></li>
<li><span data-ttu-id="8d794-226">Les articles ont des unités supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="8d794-226">The items have additional units.</span></span></li>
</ul></li>
<li><span data-ttu-id="8d794-227"><strong>Vérifier le paramétrage</strong> – Permet de spécifier les règles de validation de l'exhaustivité des données Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8d794-227"><strong>Check setup</strong> – Specify the rules for validating the completeness of Intrastat data.</span></span> <span data-ttu-id="8d794-228">Vous pouvez sélectionner les données qui sont validées.</span><span class="sxs-lookup"><span data-stu-id="8d794-228">You can select which data is validated.</span></span></li>
<li><span data-ttu-id="8d794-229"><strong>Règles d'arrondi</strong> – Permet de spécifier les paramètres suivants pour les arrondis et les poids dans la génération d'états Intrastat :</span><span class="sxs-lookup"><span data-stu-id="8d794-229"><strong>Rounding rules</strong> – Specify the following settings for rounding amounts and weights in Intrastat reporting:</span></span>
<ul>
<li><span data-ttu-id="8d794-230">La règle d'arrondi (précision)</span><span class="sxs-lookup"><span data-stu-id="8d794-230">The rounding rule (precision)</span></span></li>
<li><span data-ttu-id="8d794-231">La méthode d'arrondi : au chiffre supérieur, au chiffre inférieur ou normale</span><span class="sxs-lookup"><span data-stu-id="8d794-231">The rounding method: up, down, or normal</span></span></li>
<li><span data-ttu-id="8d794-232">Le nombre de décimales pour les montants et les poids</span><span class="sxs-lookup"><span data-stu-id="8d794-232">The number of decimal places for amounts and weights</span></span></li>
<li><span data-ttu-id="8d794-233">Instructions pour l'arrondi des poids inférieurs à 1 kilogramme (kg) : jusqu'à 1 kg, normale, ou aucun arrondi</span><span class="sxs-lookup"><span data-stu-id="8d794-233">Instructions for rounding weights that are less than 1 kilogram (kg): up to 1 kg, normal, or no rounding</span></span></li>
</ul></li>
<li><span data-ttu-id="8d794-234"><strong>États électroniques</strong> – Permet de spécifier les références aux configurations de génération d'états électroniques, afin que vous puissiez générer un fichier électronique et un état.</span><span class="sxs-lookup"><span data-stu-id="8d794-234"><strong>Electronic reporting</strong> – Specify references to electronic reporting configurations, so that you can generate an electronic file and report.</span></span></li>
<li><span data-ttu-id="8d794-235"><strong>Hiérarchie des nomenclatures douanières</strong> – Permet de spécifier la hiérarchie de catégories du type de <strong>Code marchandise</strong> qui représente le code marchandise Intrastat CN8.</span><span class="sxs-lookup"><span data-stu-id="8d794-235"><strong>Commodity code hierarchy</strong> – Specify the category hierarchy of the <strong>Commodity code</strong> type that represents Intrastat commodity code CN8.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d794-236">Coordonnées des agents</span><span class="sxs-lookup"><span data-stu-id="8d794-236">Agent contact information</span></span></td>
<td><span data-ttu-id="8d794-237">Spécifiez le nom, l'adresse, le numéro identifiant TVA, le numéro de téléphone, et le numéro de télécopie de l'agent.</span><span class="sxs-lookup"><span data-stu-id="8d794-237">Specify the agent's name, address, tax exempt number, telephone number, and fax number.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8d794-238">Propriétés de pays/régions</span><span class="sxs-lookup"><span data-stu-id="8d794-238">Country/region properties</span></span></td>
<td><span data-ttu-id="8d794-239">Définissez le pays/la région de l'entité juridique actuelle sur <strong>Local</strong>.</span><span class="sxs-lookup"><span data-stu-id="8d794-239">Set the country/region of the current legal entity to <strong>Domestic</strong>.</span></span> <span data-ttu-id="8d794-240">Définissez les pays/régions de l'UE qui participent au commerce intracommunautaire avec l'entité juridique actuelle sur <strong>UE</strong>.</span><span class="sxs-lookup"><span data-stu-id="8d794-240">Set the country/region of EU countries/regions that participate in EU trade with the current legal entity to <strong>EU</strong>.</span></span> <span data-ttu-id="8d794-241">Pour chaque pays/région, identifiez également le code pays/région pour le commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="8d794-241">For each country/region, you also identify country/region code for foreign trade purposes.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8d794-242">Souche de numéros</span><span class="sxs-lookup"><span data-stu-id="8d794-242">Number sequence</span></span></td>
<td><span data-ttu-id="8d794-243">Spécifiez la souche de numéros pour le journal Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8d794-243">Specify the number sequence for the Intrastat journal.</span></span></td>
</tr>
</tbody>
</table>

 




