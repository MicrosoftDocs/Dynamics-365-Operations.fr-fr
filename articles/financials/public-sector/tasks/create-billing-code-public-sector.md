--- 
title: "Créer un code de facturation pour le secteur public"
description: "Les champs personnalisés du code facturation permettent de rassembler les valeurs des champs de code facturation lors de la création de factures financières."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: da9b072e9eeb1c581e900882648daa8b87d3bf1d
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-billing-code-for-the-public-sector"></a><span data-ttu-id="32518-103">Créer un code de facturation pour le secteur public</span><span class="sxs-lookup"><span data-stu-id="32518-103">Create a billing code for the public sector</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="32518-104">Les champs personnalisés du code facturation permettent de rassembler les valeurs des champs de code facturation lors de la création de factures financières.</span><span class="sxs-lookup"><span data-stu-id="32518-104">Billing code custom fields allow you to collect values for billing code fields when free text invoices are created.</span></span> <span data-ttu-id="32518-105">Une fois que vous avez affecté le champ personnalisé aux codes facturation,les utilisateurs peuvent accéder au champ lorsque le code facturation est sélectionné au niveau d'une ligne de facture financière.</span><span class="sxs-lookup"><span data-stu-id="32518-105">After you assign the custom field to billing codes, users can access the field when the billing code is selected on a free text invoice line.</span></span> <span data-ttu-id="32518-106">Cette procédure a été créée à l'aide des données de la société fictive PSUS dans la partition du secteur public.</span><span class="sxs-lookup"><span data-stu-id="32518-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="32518-107">Accédez à Comptabilité client > Configuration > Champs personnalisés du code facturation.</span><span class="sxs-lookup"><span data-stu-id="32518-107">Go to Accounts receivable > Setup > Billing code custom fields.</span></span>
2. <span data-ttu-id="32518-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="32518-108">Click New.</span></span>
3. <span data-ttu-id="32518-109">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="32518-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="32518-110">Sélectionnez une option dans le champ Type.</span><span class="sxs-lookup"><span data-stu-id="32518-110">In the Type field, select an option.</span></span>
    * <span data-ttu-id="32518-111">Lorsque vous sélectionnez une option, les champs de la section Description changent pour refléter les paramètres disponibles pour cette option.</span><span class="sxs-lookup"><span data-stu-id="32518-111">When you select an option, the fields in the Description section will change to the settings available for that option.</span></span>  
    * <span data-ttu-id="32518-112">Dans la section Détails, entrez la valeur par défaut pour ce champ personnalisé et toutes autres valeurs nécessaires.</span><span class="sxs-lookup"><span data-stu-id="32518-112">In the Details section, enter the default value for this custom field and any other values that are needed.</span></span>  
5. <span data-ttu-id="32518-113">Ouvrez la section Description.</span><span class="sxs-lookup"><span data-stu-id="32518-113">Open the Description section.</span></span>
6. <span data-ttu-id="32518-114">Facultatif : dans le champ Description de l'utilisation, décrivez comment le champ personnalisé doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="32518-114">Optional: In the Usage description field, describe how the custom field should be used.</span></span> <span data-ttu-id="32518-115">Ces informations sont à usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="32518-115">This information is for internal purposes only.</span></span> <span data-ttu-id="32518-116">Elle ne sont pas visibles pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="32518-116">It is not visible to the user.</span></span>
7. <span data-ttu-id="32518-117">Ouvrez la section Références du code facturation.</span><span class="sxs-lookup"><span data-stu-id="32518-117">Open the Billing code references section.</span></span> <span data-ttu-id="32518-118">Lorsque vous affectez ce champ personnalisé à un code facturation, le code facturation est indiqué ici.</span><span class="sxs-lookup"><span data-stu-id="32518-118">When you assign this custom field to a billing code, the billing code will be listed here.</span></span>
8. <span data-ttu-id="32518-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="32518-119">Click Save.</span></span>


