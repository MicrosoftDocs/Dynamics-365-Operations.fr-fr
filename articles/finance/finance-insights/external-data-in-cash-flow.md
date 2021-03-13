---
title: Utiliser des données externes dans les prévisions de flux de trésorerie (version préliminaire)
description: Cette rubrique décrit les étapes de configuration que vous devez effectuer pour que des données externes puissent être saisies ou importées dans les prévisions de flux de trésorerie.
author: rcarlson
manager: AnnBe
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ae0eba6d397725cf425d9781a597d904e1958d44
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009390"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a><span data-ttu-id="5ee49-103">Utiliser des données externes dans les prévisions de flux de trésorerie (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="5ee49-103">Use external data in cash flow forecasts (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="5ee49-104">Les données externes peuvent être saisies ou importées dans les prévisions de trésorerie.</span><span class="sxs-lookup"><span data-stu-id="5ee49-104">External data can be entered or imported into cash flow forecasts.</span></span> <span data-ttu-id="5ee49-105">Cette rubrique décrit les étapes de configuration spécifiques à l’utilisation de données externes et permettant d’inclure les données externes dans une prévision de flux de trésorerie.</span><span class="sxs-lookup"><span data-stu-id="5ee49-105">This topic describes the setup steps that are specific to the use of external data and that enable the external data to be included in a cash flow forecast.</span></span>

## <a name="external-data-setup"></a><span data-ttu-id="5ee49-106">Configuration des données externes</span><span class="sxs-lookup"><span data-stu-id="5ee49-106">External data setup</span></span>

<span data-ttu-id="5ee49-107">Utilisez l’onglet **Source externe** sur la page **Configuration des prévisions de trésorerie** (**Gestion de la trésorerie et de la banque \> Prévisions de trésorerie**) pour saisir des paramètres prenant en charge l’utilisation de données externes dans les prévisions de flux de trésorerie.</span><span class="sxs-lookup"><span data-stu-id="5ee49-107">Use the **External source** tab on the **Cash flow forecast setup** page (**Cash and bank management \> Cash flow forecasting**) to enter settings that support the use of external data in cash flow forecasts.</span></span>

<span data-ttu-id="5ee49-108">Pour plus d’informations sur la configuration des compteurs, voir [Prévisions de flux de trésorerie](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).</span><span class="sxs-lookup"><span data-stu-id="5ee49-108">For more information about the setup, see [Cash flow forecasting](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).</span></span>

<span data-ttu-id="5ee49-109">Pour saisir des données externes pour les prévisions de flux de trésorerie, vous pouvez utiliser l’expérience Ouvrir dans Excel pour saisir et modifier des données externes.</span><span class="sxs-lookup"><span data-stu-id="5ee49-109">To enter external data for cash flow forecasts, you can use the Open in Excel experience for entering and modifying external data.</span></span> <span data-ttu-id="5ee49-110">Sélectionnez le bouton **Données externes** puis soit **Ajouter des données externes** soit **Modifier les données externes existantes**.</span><span class="sxs-lookup"><span data-stu-id="5ee49-110">Select the **External data** button, and then select either **Add External Data** or **Edit existing external data**.</span></span> <span data-ttu-id="5ee49-111">Quand le fichier Microsoft Excel est ouvert, vous pouvez saisir des informations dans les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="5ee49-111">When the Microsoft Excel file is opened, you can enter information in the following fields:</span></span>

- <span data-ttu-id="5ee49-112">**ID entrée**</span><span class="sxs-lookup"><span data-stu-id="5ee49-112">**Entry ID**</span></span>
- <span data-ttu-id="5ee49-113">**Description** (facultative)</span><span class="sxs-lookup"><span data-stu-id="5ee49-113">**Description** (optional)</span></span>
- <span data-ttu-id="5ee49-114">**Nom de la source externe** – Sélectionnez l’une des valeurs de la liste que vous avez définie lors de la configuration de Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="5ee49-114">**External Source name** – Select one of the values in the list that you defined when you set up Finance Insights.</span></span>
- <span data-ttu-id="5ee49-115">**Entité juridique**</span><span class="sxs-lookup"><span data-stu-id="5ee49-115">**Legal Entity**</span></span>
- <span data-ttu-id="5ee49-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="5ee49-116">**Date**</span></span>
- <span data-ttu-id="5ee49-117">**Montant dans la devise de transaction**</span><span class="sxs-lookup"><span data-stu-id="5ee49-117">**Amount in transaction currency**</span></span>
- <span data-ttu-id="5ee49-118">**Code devise**</span><span class="sxs-lookup"><span data-stu-id="5ee49-118">**Currency Code**</span></span>
- <span data-ttu-id="5ee49-119">**Dimension par défaut** (facultatif)</span><span class="sxs-lookup"><span data-stu-id="5ee49-119">**Default Dimension** (optional)</span></span>
- <span data-ttu-id="5ee49-120">**Numéro de référence** (facultatif)</span><span class="sxs-lookup"><span data-stu-id="5ee49-120">**Document number** (optional)</span></span>
- <span data-ttu-id="5ee49-121">**Numéro de compte** (facultatif)</span><span class="sxs-lookup"><span data-stu-id="5ee49-121">**Account number** (optional)</span></span>
- <span data-ttu-id="5ee49-122">**Nom du compte** (facultatif)</span><span class="sxs-lookup"><span data-stu-id="5ee49-122">**Account name** (optional)</span></span>

## <a name="importing-external-data-by-using-the-data-management-framework"></a><span data-ttu-id="5ee49-123">Importation de données externes à l’aide de la structure de gestion des données</span><span class="sxs-lookup"><span data-stu-id="5ee49-123">Importing external data by using the Data Management framework</span></span>

<span data-ttu-id="5ee49-124">Vous pouvez importer des données externes pour les prévisions de flux de trésorerie en utilisant l’espace de travail **Gestion de données** et l’entité nommée **Entrée source externe des prévisions de trésorerie**.</span><span class="sxs-lookup"><span data-stu-id="5ee49-124">You can import external data for cash flow forecasts by using the **Data Management** workspace and the entity that is named **Cash flow forecast external source entry**.</span></span>

<span data-ttu-id="5ee49-125">En outre, si vous devez déplacer des données de configuration d’un environnement à un autre, la zone d’entités suivantes est disponible pour les tables de configuration requises :</span><span class="sxs-lookup"><span data-stu-id="5ee49-125">Additionally, if you must move setup data from one environment to another, the following entities area available for the setup tables that are required:</span></span>

- <span data-ttu-id="5ee49-126">Paramétrage de la source externe des prévisions de flux de trésorerie</span><span class="sxs-lookup"><span data-stu-id="5ee49-126">Cash flow forecast external source setup</span></span>
- <span data-ttu-id="5ee49-127">Paramétrage de l’entité juridique de la source externe des prévisions de flux de trésorerie</span><span class="sxs-lookup"><span data-stu-id="5ee49-127">Cash flow forecast external source legal entity setup</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="5ee49-128">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="5ee49-128">Privacy notice</span></span>
<span data-ttu-id="5ee49-129">Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.</span><span class="sxs-lookup"><span data-stu-id="5ee49-129">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
