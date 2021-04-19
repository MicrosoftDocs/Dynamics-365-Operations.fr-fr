---
title: Proposer des acquisitions d’immobilisations
description: Cette rubrique décrit comment acquérir une immobilisation à l’aide de la proposition d’acquisition du journal des immobilisations.
author: saraschi2
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d529cd53b41827a78b282afd4d2c69d2f2db555e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817162"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="ca0b8-103">Proposer des acquisitions d’immobilisations</span><span class="sxs-lookup"><span data-stu-id="ca0b8-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ca0b8-104">Cette rubrique décrit comment acquérir une immobilisation à l’aide de la proposition d’acquisition du journal des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="ca0b8-105">Elle utilise le rôle de comptable et les données de démonstration de l’entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="ca0b8-106">Pour acquérir une immobilisation via un journal de proposition d’immobilisation, vous devez d’abord créer l’enregistrement d’immobilisation, puis définir le prix d’acquisition dans le registre des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

## <a name="create-an-asset-acquisition-proposal"></a><span data-ttu-id="ca0b8-107">Créer une proposition d’acquisition d’actif</span><span class="sxs-lookup"><span data-stu-id="ca0b8-107">Create an asset acquisition proposal</span></span>

<span data-ttu-id="ca0b8-108">Procédez comme suit pour créer une proposition d’acquisition d’actif.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-108">Complete the following steps to create an asset acquisition proposal.</span></span> 

1. <span data-ttu-id="ca0b8-109">Dans le volet de navigation, accédez à **Modules > Immobilisations > Entrées de journal > Journal des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-109">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="ca0b8-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-110">Select **New**.</span></span>
3. <span data-ttu-id="ca0b8-111">Dans le champ **Nom**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="ca0b8-112">Dans le volet Actions, sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-112">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="ca0b8-113">Sélectionnez **Propositions**.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-113">Select **Proposals**.</span></span>
6. <span data-ttu-id="ca0b8-114">Sélectionnez **Proposition d’acquisition**.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-114">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="ca0b8-115">Sélectionnez **Filtrer**.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-115">Select **Filter**.</span></span> <span data-ttu-id="ca0b8-116">Sélectionnez **Réinitialiser** pour effacer les valeurs précédentes.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-116">Select **Reset** to clear previous values.</span></span>
8. <span data-ttu-id="ca0b8-117">Sélectionnez la ligne **Numéro d’immobilisation**.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-117">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="ca0b8-118">Dans le champ **Critères**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-118">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="ca0b8-119">Définissez les critères restants pour les immobilisations à acquérir avec cette proposition.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-119">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="ca0b8-120">Sélectionnez **OK** deux fois pour quitter le volet.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-120">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="ca0b8-121">Vérifiez que les lignes de transaction sont bien créées.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-121">Verify that the transaction lines are created.</span></span>  
- <span data-ttu-id="ca0b8-122">Seules les immobilisations dont la date et le prix d’acquisition sont définis sur le registre sont incluses dans la proposition d’acquisition.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-122">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="ca0b8-123">Dans la page, sélectionnez l’onglet **Registres**.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-123">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="ca0b8-124">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-124">Select **Post**.</span></span>

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a><span data-ttu-id="ca0b8-125">Inclure les dimensions financières par défaut dans une proposition d’acquisition</span><span class="sxs-lookup"><span data-stu-id="ca0b8-125">Include default financial dimensions in an acquisition proposal</span></span>

<span data-ttu-id="ca0b8-126">La transaction d’acquisition peut être créée à l’aide de compléments Excel, en accédant à **Immobilisations > Entrées de journal > Journal des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-126">The acquisition transaction can be created using Excel add-ins, by going to **Fixed assets > Journal entries > Fixed asset journal**.</span></span> <span data-ttu-id="ca0b8-127">Créez un nouveau journal et passez à la section **Lignes** sur la page et sélectionnez l’icône Excel, puis sélectionnez une ligne du Journal des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-127">Create a new journal and move to the **Lines** section on the page and select the Excel icon, and then select a Fixed asset journal line.</span></span> <span data-ttu-id="ca0b8-128">Le système créera et ouvrira un modèle Excel représentant les lignes du journal.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-128">The system will create and open an Excel template representing journal lines.</span></span> <span data-ttu-id="ca0b8-129">Vous pouvez ajouter des données pour les lignes de journal que vous ajoutez dans le modèle, puis publier ces informations dans le système.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-129">You can add data for the journal lines you're adding into the template, and then publish that information back into the system.</span></span> 

<span data-ttu-id="ca0b8-130">Si des dimensions par défaut ont été configurées pour le registre d’actifs sélectionné et les immobilisations correspondantes qui ont été saisies dans le modèle Excel, les dimensions financières par défaut seront appelées à partir des données principales du registre d’actifs lorsque le journal sera publié par Excel vers le système.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-130">If default dimensions have been set up for the selected asset book and the corresponding fixed assets that were entered in the Excel template, the default financial dimensions will be called from the asset book master data when the journal is published from the Excel to the system.</span></span> <span data-ttu-id="ca0b8-131">Pour inclure automatiquement des dimensions financières dans un registre d’actifs lors de la publication du journal des immobilisations à partir du complément Excel, les dimensions par défaut doivent être configurées à l’avance.</span><span class="sxs-lookup"><span data-stu-id="ca0b8-131">To include financial dimensions on an asset book automatically while publishing the fixed asset journal from the Excel add-in, the default dimensions must be set up in advance.</span></span>  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
