---
title: Proposer des acquisitions d'immobilisations
description: Cette rubrique décrit comment acquérir une immobilisation à l'aide de la proposition d'acquisition du journal des immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b35b13dc266fd5bccde437526400832d394b9aa
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177696"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="3ba45-103">Proposer des acquisitions d'immobilisations</span><span class="sxs-lookup"><span data-stu-id="3ba45-103">Propose fixed asset acquisitions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3ba45-104">Cette rubrique décrit comment acquérir une immobilisation à l'aide de la proposition d'acquisition du journal des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="3ba45-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="3ba45-105">Elle utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="3ba45-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="3ba45-106">Dans le volet de navigation, accédez à **Modules > Immobilisations > Entrées de journal > Journal des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="3ba45-106">In the Navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="3ba45-107">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="3ba45-107">Select **New**.</span></span>
3. <span data-ttu-id="3ba45-108">Dans le champ **Nom**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3ba45-108">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="3ba45-109">Dans le volet Actions, sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="3ba45-109">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="3ba45-110">Sélectionnez **Propositions**.</span><span class="sxs-lookup"><span data-stu-id="3ba45-110">Select **Proposals**.</span></span>
6. <span data-ttu-id="3ba45-111">Sélectionnez **Proposition d'acquisition**.</span><span class="sxs-lookup"><span data-stu-id="3ba45-111">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="3ba45-112">Sélectionnez **Filtrer**.</span><span class="sxs-lookup"><span data-stu-id="3ba45-112">Select **Filter**.</span></span> <span data-ttu-id="3ba45-113">Sélectionnez **Réinitialiser** pour effacer les valeurs précédentes.</span><span class="sxs-lookup"><span data-stu-id="3ba45-113">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="3ba45-114">Sélectionnez la ligne **Numéro d'immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="3ba45-114">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="3ba45-115">Dans le champ **Critères**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3ba45-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="3ba45-116">Définissez les critères restants pour les immobilisations à acquérir avec cette proposition.</span><span class="sxs-lookup"><span data-stu-id="3ba45-116">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="3ba45-117">Sélectionnez **OK** deux fois pour quitter le volet.</span><span class="sxs-lookup"><span data-stu-id="3ba45-117">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="3ba45-118">Vérifiez les lignes de transaction créées.</span><span class="sxs-lookup"><span data-stu-id="3ba45-118">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="3ba45-119">Seules les immobilisations dont la date et le prix d'acquisition sont définis sur le registre sont incluses dans la proposition d'acquisition.</span><span class="sxs-lookup"><span data-stu-id="3ba45-119">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="3ba45-120">Dans la page, sélectionnez l'onglet **Registres**.</span><span class="sxs-lookup"><span data-stu-id="3ba45-120">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="3ba45-121">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="3ba45-121">Select **Post**.</span></span>

