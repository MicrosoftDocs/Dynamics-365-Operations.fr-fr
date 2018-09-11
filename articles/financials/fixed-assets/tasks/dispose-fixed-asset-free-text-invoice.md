--- 
title: "Céder des immobilisations à l'aide d'une facture financière"
description: "Cette procédure indique comment acquérir une immobilisation à l'aide de la proposition d'acquisition du journal des immobilisations."
author: saraschi2
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: bf449be5f9b79c1e6bf7d9a5dd6d7cdede20eea9
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="dispose-of-a-fixed-asset-using-a-free-text-invoice"></a><span data-ttu-id="9864c-103">Céder des immobilisations à l'aide d'une facture financière</span><span class="sxs-lookup"><span data-stu-id="9864c-103">Dispose of a fixed asset using a free text invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9864c-104">Cette procédure indique comment acquérir une immobilisation à l'aide de la proposition d'acquisition du journal des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="9864c-104">This procedure shows how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="9864c-105">Elle utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="9864c-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="9864c-106">Accédez à Immobilisations > Entrées de journal > Journal des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="9864c-106">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="9864c-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9864c-107">Click New.</span></span>
3. <span data-ttu-id="9864c-108">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="9864c-108">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="9864c-109">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="9864c-109">Click Lines.</span></span>
5. <span data-ttu-id="9864c-110">Cliquez sur Propositions.</span><span class="sxs-lookup"><span data-stu-id="9864c-110">Click Proposals.</span></span>
6. <span data-ttu-id="9864c-111">Cliquez sur Proposition d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="9864c-111">Click Acquisition proposal.</span></span>
7. <span data-ttu-id="9864c-112">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="9864c-112">Click Filter.</span></span>
8. <span data-ttu-id="9864c-113">Cliquez sur Réinitialiser pour effacer les valeurs précédentes.</span><span class="sxs-lookup"><span data-stu-id="9864c-113">Click Reset to clear out previous values.</span></span>
9. <span data-ttu-id="9864c-114">Sélectionnez la ligne Numéro d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="9864c-114">Select the Fixed asset number row.</span></span>
10. <span data-ttu-id="9864c-115">Dans le champ Critères, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9864c-115">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="9864c-116">Définissez les critères restants pour les immobilisations à acquérir avec cette proposition.</span><span class="sxs-lookup"><span data-stu-id="9864c-116">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
11. <span data-ttu-id="9864c-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9864c-117">Click OK.</span></span>
12. <span data-ttu-id="9864c-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9864c-118">Click OK.</span></span>
    * <span data-ttu-id="9864c-119">Vérifiez les lignes de transaction créées.</span><span class="sxs-lookup"><span data-stu-id="9864c-119">Verify the transaction lines created.</span></span>  
    * <span data-ttu-id="9864c-120">Seules les immobilisations dont la date et le prix d'acquisition sont définis sur le registre sont incluses dans la proposition d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="9864c-120">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
13. <span data-ttu-id="9864c-121">Cliquez sur l'onglet Registres.</span><span class="sxs-lookup"><span data-stu-id="9864c-121">Click the Books tab.</span></span>
14. <span data-ttu-id="9864c-122">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="9864c-122">Click Post.</span></span>


