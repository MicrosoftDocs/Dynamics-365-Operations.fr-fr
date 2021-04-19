---
title: Modification des conventions d’amortissement pour plusieurs immobilisations
description: Cette tâche permet de mettre à jour la convention d’amortissement pour un groupe d’immobilisations spécifié.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a71b24b0c2ea072aeff8c994cfdac10bc57b64c6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823978"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a><span data-ttu-id="b3d2f-103">Modification des conventions d’amortissement pour plusieurs immobilisations</span><span class="sxs-lookup"><span data-stu-id="b3d2f-103">Change depreciation conventions for multiple fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b3d2f-104">Cette tâche permet de mettre à jour la convention d’amortissement pour un groupe d’immobilisations spécifié.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-104">This task updates the depreciation convention for a specified fixed asset group.</span></span> <span data-ttu-id="b3d2f-105">La société fictive USMF sert d’exemple dans ce guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-105">This task guide uses the USMF demo company.</span></span>

1. <span data-ttu-id="b3d2f-106">Accédez à Immobilisations > Tâches périodiques > Mise à jour collective.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-106">Go to Fixed assets > Periodic tasks > Mass update</span></span>
2. <span data-ttu-id="b3d2f-107">Dans le champ Registre des amortissements, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-107">In the Depreciation book field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b3d2f-108">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="b3d2f-109">Entrez une date dans le champ Début de la mise en service.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-109">In the Placed in service start field, enter a date.</span></span>
5. <span data-ttu-id="b3d2f-110">Entrez une date dans le champ Fin de la mise en service.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-110">In the Placed in service end field, enter a date.</span></span>
    * <span data-ttu-id="b3d2f-111">Seuls les actifs qui font partie du registre des amortissements sélectionné et qui ont été mis en service entre ces dates sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-111">Only assets that are a part of the select depreciation book and that have been placed in service between these dates will be updated.</span></span>  
6. <span data-ttu-id="b3d2f-112">Sélectionnez une option dans le champ Convention d’amortissement actuelle.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-112">In the Current depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="b3d2f-113">Seuls les actifs ayant une convention d’amortissement sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-113">Only assets that have the current depreciation convention will be updated.</span></span>  
7. <span data-ttu-id="b3d2f-114">Sélectionnez une option dans le champ Nouvelle convention d’amortissement.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-114">In the New depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="b3d2f-115">Vérifiez que l’état s’imprime sur la destination sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-115">Verify the report will print to the desired destination.</span></span>  
8. <span data-ttu-id="b3d2f-116">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="b3d2f-117">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-117">Click Filter.</span></span>
10. <span data-ttu-id="b3d2f-118">Sélectionnez le groupe Immobilisations dans la liste.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-118">In the list, select the Fixed asset group.</span></span>
11. <span data-ttu-id="b3d2f-119">Dans le champ Critères, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-119">In the Criteria field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="b3d2f-120">Sélectionnez le groupe d’immobilisations souhaité.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-120">Select the desired Fixed asset group.</span></span>
13. <span data-ttu-id="b3d2f-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-121">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="b3d2f-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-122">Click OK.</span></span>
15. <span data-ttu-id="b3d2f-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-123">Click OK.</span></span>
    *  <span data-ttu-id="b3d2f-124">Les résultats du processus sont affichés dans l’état Mise à jour collective.</span><span class="sxs-lookup"><span data-stu-id="b3d2f-124">Results of the process are shown on the Mass update report.</span></span>     



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]