---
title: Paramétrer des codes déclaration de taxe
description: Les codes déclaration de taxe font référence à un numéro de champ répertorié dans la déclaration de taxe.
author: twheeloc
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e040bac6ef9e950e8d7f97e3c136636acf1fe43
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813529"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="c2ac2-103">Paramétrer des codes déclaration de taxe</span><span class="sxs-lookup"><span data-stu-id="c2ac2-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c2ac2-104">Les codes déclaration de taxe font référence à un numéro de champ répertorié dans la déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-104">The Sales tax reporting codes refer to a field number that's listed on a sales tax report.</span></span> <span data-ttu-id="c2ac2-105">Ils sont utilisés sur des présentations de rapport spécifiques à un pays.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-105">They are used on country-specific report layouts.</span></span> <span data-ttu-id="c2ac2-106">Ils sont également utilisés sur l’état de déclaration de taxe par code.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-106">They're also used on the Sales tax payment by code report.</span></span> <span data-ttu-id="c2ac2-107">Ce rapport affiche les montants de la taxe pour une période de décompte récapitulée pour chaque code de déclaration.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-107">That report shows sales tax amounts for a settlement period summarized for each reporting code.</span></span> <span data-ttu-id="c2ac2-108">Après avoir créé les codes déclaration de taxe, vous pouvez vous y référer dans les organisateurs de paramétrage d’état sur la page **code taxe**.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-108">After you create Sales tax reporting codes, you can refer to those codes on the Report setup FastTabs, which you can access from the **Sales tax code** page.</span></span> 

<span data-ttu-id="c2ac2-109">La société fictive DEMF sert d’exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-109">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="c2ac2-110">Dans le **Volet de navigation**, accédez à **Taxes > Paramétrage > Taxe > Codes déclaration de taxe**.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-110">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="c2ac2-111">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-111">Click **New**.</span></span>
3. <span data-ttu-id="c2ac2-112">Sélectionnez la présentation d’état à laquelle appartient le code déclaration.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-112">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="c2ac2-113">Cette structure est utilisée pour filtrer les codes taxes disponibles pour le code taxe.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-113">This layout is used to filter the available reporting codes for a sales tax code.</span></span> <span data-ttu-id="c2ac2-114">Chaque code taxe appartient à une période de règlement appartenant à une administration fiscale qui utilise une présentation d’état.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-114">Each sales tax code belongs to a settlement period, which belongs to a Sales tax authority, which uses a report layout.</span></span>  
4. <span data-ttu-id="c2ac2-115">Dans le champ **Code de déclaration**, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-115">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="c2ac2-116">Dans le champ **Texte d’état**, entrez une description à afficher dans les états.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-116">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="c2ac2-117">Dans le champ **Brève description**, entrez une description à des fins internes.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-117">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="c2ac2-118">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c2ac2-118">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]