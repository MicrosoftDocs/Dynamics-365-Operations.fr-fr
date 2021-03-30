---
title: Proposer des acquisitions d’immobilisations
description: Cette rubrique décrit comment acquérir une immobilisation à l’aide de la proposition d’acquisition du journal des immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 07/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 426a5e42c1fc26958ab37eddd915334f8b0e19cc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205026"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="7fdaa-103">Proposer des acquisitions d’immobilisations</span><span class="sxs-lookup"><span data-stu-id="7fdaa-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7fdaa-104">Cette rubrique décrit comment acquérir une immobilisation à l’aide de la proposition d’acquisition du journal des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="7fdaa-105">Elle utilise le rôle de comptable et les données de démonstration de l’entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="7fdaa-106">Pour acquérir une immobilisation via un journal de proposition d’immobilisation, vous devez d’abord créer l’enregistrement d’immobilisation, puis définir le prix d’acquisition dans le registre des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

1. <span data-ttu-id="7fdaa-107">Dans le volet de navigation, accédez à **Modules > Immobilisations > Entrées de journal > Journal des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="7fdaa-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-108">Select **New**.</span></span>
3. <span data-ttu-id="7fdaa-109">Dans le champ **Nom**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-109">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="7fdaa-110">Dans le volet Actions, sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-110">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="7fdaa-111">Sélectionnez **Propositions**.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-111">Select **Proposals**.</span></span>
6. <span data-ttu-id="7fdaa-112">Sélectionnez **Proposition d’acquisition**.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-112">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="7fdaa-113">Sélectionnez **Filtrer**.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-113">Select **Filter**.</span></span> <span data-ttu-id="7fdaa-114">Sélectionnez **Réinitialiser** pour effacer les valeurs précédentes.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-114">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="7fdaa-115">Sélectionnez la ligne **Numéro d’immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-115">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="7fdaa-116">Dans le champ **Critères**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-116">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="7fdaa-117">Définissez les critères restants pour les immobilisations à acquérir avec cette proposition.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-117">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="7fdaa-118">Sélectionnez **OK** deux fois pour quitter le volet.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-118">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="7fdaa-119">Vérifiez les lignes de transaction créées.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-119">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="7fdaa-120">Seules les immobilisations dont la date et le prix d’acquisition sont définis sur le registre sont incluses dans la proposition d’acquisition.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-120">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="7fdaa-121">Dans la page, sélectionnez l’onglet **Registres**.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-121">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="7fdaa-122">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="7fdaa-122">Select **Post**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]