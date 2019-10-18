---
title: Paramétrer des codes déclaration de taxe
description: Les codes déclaration de taxe font référence à un numéro de champ dans la déclaration de taxe.
author: twheeloc
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4751256858da417ec9bb1b7d9ccd16fb6bef1cac
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185932"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="6ac60-103">Paramétrer des codes déclaration de taxe</span><span class="sxs-lookup"><span data-stu-id="6ac60-103">Set up sales tax reporting codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6ac60-104">Les codes déclaration de taxe font référence à un numéro de champ dans la déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="6ac60-104">The Sales tax reporting codes refer to a field number on a sales tax report.</span></span> <span data-ttu-id="6ac60-105">Ils sont utilisés dans les présentations d'états spécifiques à un pays, l'état des paiements de taxe par code imprime les montants de taxe pour une période de règlement résumée par code déclaration.</span><span class="sxs-lookup"><span data-stu-id="6ac60-105">They are used on country specific report layouts and the Sales tax payment by code report to print sales tax amounts for a settlement period summarized per reporting code.</span></span> <span data-ttu-id="6ac60-106">Après avoir créé les codes déclaration de taxe, vous pouvez vous y référer dans les organisateurs de paramétrage d'état dans la page du code taxe.</span><span class="sxs-lookup"><span data-stu-id="6ac60-106">After you create Sales tax reporting codes, you can refer to them on the Report setup FastTabs in the Sales tax code page.</span></span> 

<span data-ttu-id="6ac60-107">La société fictive DEMF sert d'exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="6ac60-107">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="6ac60-108">Dans le **Volet de navigation**, accédez à **Taxes > Paramétrage > Taxe > Codes déclaration de taxe**.</span><span class="sxs-lookup"><span data-stu-id="6ac60-108">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="6ac60-109">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6ac60-109">Click **New**.</span></span>
3. <span data-ttu-id="6ac60-110">Sélectionnez la présentation d'état à laquelle appartient le code déclaration.</span><span class="sxs-lookup"><span data-stu-id="6ac60-110">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="6ac60-111">Cette structure est utilisée pour filtrer les codes taxes disponibles pour le code taxe.</span><span class="sxs-lookup"><span data-stu-id="6ac60-111">This layout is used to filter the available reporting codes for a Sales tax code.</span></span> <span data-ttu-id="6ac60-112">Chaque code taxe appartient à une période de règlement appartenant à une administration fiscale qui utilise une présentation d'état.</span><span class="sxs-lookup"><span data-stu-id="6ac60-112">Each Sales tax code belongs to a settlement period which belongs to a Sales tax authority which uses a Report layout.</span></span>  
4. <span data-ttu-id="6ac60-113">Dans le champ **Code de déclaration**, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="6ac60-113">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="6ac60-114">Dans le champ **Texte d'état**, entrez une description à afficher dans les états.</span><span class="sxs-lookup"><span data-stu-id="6ac60-114">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="6ac60-115">Dans le champ **Brève description**, entrez une description à des fins internes.</span><span class="sxs-lookup"><span data-stu-id="6ac60-115">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="6ac60-116">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6ac60-116">Click **Save**.</span></span>

