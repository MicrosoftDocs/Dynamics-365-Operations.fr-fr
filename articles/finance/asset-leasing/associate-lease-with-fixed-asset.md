---
title: Associer des immobilisations à des baux
description: La rubrique explique comment associer une immobilisation existante à un nouveau bail.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5c4f14d38b3cfc2c4d09cfeb5854204701250757
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260851"
---
# <a name="associate-fixed-assets-with-leases"></a><span data-ttu-id="6c627-103">Associer des immobilisations à des baux</span><span class="sxs-lookup"><span data-stu-id="6c627-103">Associate fixed assets with leases</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6c627-104">La rubrique explique comment associer une immobilisation existante à un nouveau bail.</span><span class="sxs-lookup"><span data-stu-id="6c627-104">The topic explains how to associate an existing fixed asset with a new lease.</span></span> <span data-ttu-id="6c627-105">Lorsque vous associez une immobilisation à un bail, la valeur du droit d’utilisation de l’actif lors de la comptabilisation initiale sera le coût d’acquisition de l’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="6c627-105">When you associate a fixed asset with a lease, the right-of-use (ROU) asset value at initial recognition will be the acquisition cost of the fixed asset.</span></span>

<span data-ttu-id="6c627-106">Avant de pouvoir associer une immobilisation à un bail, vous devez créer un enregistrement pour l’immobilisation dans Immobilisations.</span><span class="sxs-lookup"><span data-stu-id="6c627-106">Before you can associate a fixed asset with a lease, you must create a record for the fixed asset in Fixed assets.</span></span> <span data-ttu-id="6c627-107">Puis, sur la page **Récapitulatif du bail**, vous devez créer un bail et lier l’actif à ce bail.</span><span class="sxs-lookup"><span data-stu-id="6c627-107">Then, on the **Lease summary** page, you must create a lease and link the asset to that lease.</span></span>

1. <span data-ttu-id="6c627-108">Ajouter un bail en suivant les étapes dans [Ajouter ou copier des baux](add-lease.md).</span><span class="sxs-lookup"><span data-stu-id="6c627-108">Add a lease by following the steps in [Add or copy leases](add-lease.md).</span></span> <span data-ttu-id="6c627-109">Sur la page **Ajouter un bail**, dans le champ **Numéro d’immobilisation**, sélectionnez l’actif qui n’a pas encore été acquis.</span><span class="sxs-lookup"><span data-stu-id="6c627-109">On the **Add lease** page, in the **Fixed asset number** field, select the asset that hasn't yet been acquired.</span></span>
2. <span data-ttu-id="6c627-110">Sélectionnez **Registres** et confirmez le programme de paiement.</span><span class="sxs-lookup"><span data-stu-id="6c627-110">Select **Books**, and confirm the payment schedule.</span></span>
3. <span data-ttu-id="6c627-111">Sélectionnez **Comptabilisation initiale**.</span><span class="sxs-lookup"><span data-stu-id="6c627-111">Select **Initial recognition**.</span></span>
4. <span data-ttu-id="6c627-112">Sélectionnez **Journal de location d’actifs**.</span><span class="sxs-lookup"><span data-stu-id="6c627-112">Select **Asset leasing journal**.</span></span>

    <span data-ttu-id="6c627-113">L’entrée de journal de comptabilisation initiale pour le bail débite l’immobilisation pour le montant généralement débité sur le compte de droit d’utilisation de l’actif.</span><span class="sxs-lookup"><span data-stu-id="6c627-113">The initial recognition journal entry for the lease debits the fixed asset for the amount that is usually debited to the ROU asset account.</span></span>

    <span data-ttu-id="6c627-114">Vous pouvez maintenant afficher le type de transaction et le registre pour l’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="6c627-114">You can now view the transaction type and book for the fixed asset.</span></span>

5. <span data-ttu-id="6c627-115">Sélectionnez **Détails du journal**.</span><span class="sxs-lookup"><span data-stu-id="6c627-115">Select **Journal details**.</span></span>
6. <span data-ttu-id="6c627-116">Sélectionnez **Lignes** pour afficher les lignes individuelles de l’entrée de journal.</span><span class="sxs-lookup"><span data-stu-id="6c627-116">Select **Lines** to view the individual lines for the journal entry.</span></span>
7. <span data-ttu-id="6c627-117">Sélectionnez la ligne de journal qui contient l’actif, puis sélectionnez l’onglet **Immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="6c627-117">Select the journal line that contains the asset, and then select the **Fixed Assets** tab.</span></span>

    <span data-ttu-id="6c627-118">L’onglet **Immobilisations** affiche le type de transaction et le registre.</span><span class="sxs-lookup"><span data-stu-id="6c627-118">The **Fixed assets** tab shows the transaction type and the book.</span></span> <span data-ttu-id="6c627-119">Par défaut, le champ **Type de transaction** est défini sur **Acquisition**, et le champ **Registre** est défini sur le registre actuel de l’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="6c627-119">By default, the **Transaction type** field is set to **Acquisition**, and the **Book** field is set to the current book for the fixed asset.</span></span>

<span data-ttu-id="6c627-120">Une fois que vous avez validé l’entrée de journal de comptabilisation initiale, la transaction apparaît comme une transaction d’acquisition pour l’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="6c627-120">After you post the initial recognition journal entry, the transaction appears as an acquisition transaction for the fixed asset.</span></span> <span data-ttu-id="6c627-121">Pour afficher la table des transactions, accédez à **Immobilisations \>Immobilisations \> Immobilisations**, sélectionnez l’actif approprié, puis sélectionnez **Évaluations**.</span><span class="sxs-lookup"><span data-stu-id="6c627-121">To view the transaction table, go to **Fixed assets \> Fixed assets \> Fixed assets**, select the appropriate asset, and then select **Valuations**.</span></span> <span data-ttu-id="6c627-122">Vous devez voir que l’entrée de journal de comptabilisation initiale a créé une transaction d’acquisition pour l’immobilisation spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6c627-122">You should see that the initial recognition journal entry has created an acquisition transaction for the specified fixed asset.</span></span>

<span data-ttu-id="6c627-123">L’immobilisation peut désormais être amortie à l’aide de la fonctionnalité d’amortissement standard dans Immobilisations.</span><span class="sxs-lookup"><span data-stu-id="6c627-123">The fixed asset can now be depreciated by using the standard depreciation functionality in Fixed assets.</span></span> <span data-ttu-id="6c627-124">Pour plus d’informations sur l’amortissement, voir [Méthodes et conventions d’amortissement](../fixed-assets/depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="6c627-124">For more information about depreciation, see [Depreciation methods and conventions](../fixed-assets/depreciation-methods-conventions.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6c627-125">Si vous associez une immobilisation à un bail, les boutons **Amortissement des actifs** et **Dépréciation du bail** sont désactivés dans la location d’actifs.</span><span class="sxs-lookup"><span data-stu-id="6c627-125">If you associate a fixed asset with a lease, the **Asset depreciation** and **Lease impairment** buttons are disabled in Asset leasing.</span></span> <span data-ttu-id="6c627-126">Vous pouvez afficher les transactions d’amortissement des immobilisations et de dépréciation de location à partir des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="6c627-126">You can view asset depreciation and lease impairment transactions from Fixed assets.</span></span> <span data-ttu-id="6c627-127">Le bouton **Transactions d’actif**, qui ouvre un formulaire de demande est également désactivé.</span><span class="sxs-lookup"><span data-stu-id="6c627-127">The **Asset transactions** button, which opens an inquiry form is also disabled.</span></span> <span data-ttu-id="6c627-128">Vous pouvez également ouvrir le formulaire de demande **Transactions d’actif** dans Immobilisations.</span><span class="sxs-lookup"><span data-stu-id="6c627-128">You can also open the **Asset transactions** inquiry form in Fixed assets.</span></span>  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]