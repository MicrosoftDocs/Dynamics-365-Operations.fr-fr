---
title: Paramétrer des codes déclaration de taxe
description: Les codes déclaration de taxe font référence à un numéro de champ dans la déclaration de taxe.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 830a3465944b32cc17feee60e3cbc5ad0a4dc9d7
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834772"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="282ec-103">Paramétrer des codes déclaration de taxe</span><span class="sxs-lookup"><span data-stu-id="282ec-103">Set up sales tax reporting codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="282ec-104">Les codes déclaration de taxe font référence à un numéro de champ dans la déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="282ec-104">The Sales tax reporting codes refer to a field number on a sales tax report.</span></span> <span data-ttu-id="282ec-105">Ils sont utilisés dans les présentations d'états spécifiques à un pays, l'état des paiements de taxe par code imprime les montants de taxe pour une période de règlement résumée par code déclaration.</span><span class="sxs-lookup"><span data-stu-id="282ec-105">They are used on country specific report layouts and the Sales tax payment by code report to print sales tax amounts for a settlement period summarized per reporting code.</span></span> <span data-ttu-id="282ec-106">Après avoir créé les codes déclaration de taxe, vous pouvez vous y référer dans les organisateurs de paramétrage d'état dans la page du code taxe.</span><span class="sxs-lookup"><span data-stu-id="282ec-106">After you create Sales tax reporting codes, you can refer to them on the Report setup FastTabs in the Sales tax code page.</span></span> 

<span data-ttu-id="282ec-107">La société fictive DEMF sert d'exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="282ec-107">This recording uses the DEMF demo company.</span></span>



1. <span data-ttu-id="282ec-108">Allez dans Taxe > Configuration > Taxe > Codes déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="282ec-108">Go to Tax > Setup > Sales tax > Sales tax reporting codes.</span></span>
2. <span data-ttu-id="282ec-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="282ec-109">Click New.</span></span>
3. <span data-ttu-id="282ec-110">Sélectionnez la présentation d'état à laquelle appartient le code déclaration.</span><span class="sxs-lookup"><span data-stu-id="282ec-110">Select the report layout that the reporting code belongs to.</span></span>
    * <span data-ttu-id="282ec-111">Cette structure est utilisée pour filtrer les codes taxes disponibles pour le code taxe.</span><span class="sxs-lookup"><span data-stu-id="282ec-111">This layout is used to filter the available reporting codes for a Sales tax code.</span></span> <span data-ttu-id="282ec-112">Chaque code taxe appartient à une période de règlement appartenant à une administration fiscale qui utilise une présentation d'état.</span><span class="sxs-lookup"><span data-stu-id="282ec-112">Each Sales tax code belongs to a settlement period which belongs to a Sales tax authority which uses a Report layout.</span></span>  
4. <span data-ttu-id="282ec-113">Entrez un numéro de champ faisant référence à un champ dans une déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="282ec-113">Enter a number that refers to a field on a sales tax report.</span></span>
5. <span data-ttu-id="282ec-114">Dans le champ Texte d'état, entrez une description à afficher dans les états.</span><span class="sxs-lookup"><span data-stu-id="282ec-114">In the Report text field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="282ec-115">Dans le champ Brève description, entrez une description à des fins internes.</span><span class="sxs-lookup"><span data-stu-id="282ec-115">In the Brief description field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="282ec-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="282ec-116">Click Save.</span></span>

