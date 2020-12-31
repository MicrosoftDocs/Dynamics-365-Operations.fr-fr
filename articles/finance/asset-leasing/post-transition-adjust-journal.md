---
title: Valider les écritures de journal d’ajustement de transition dans la location d’actifs
description: Cette rubrique décrit la fonctionnalité qui vous permet de faire la transition d’un portefeuille de locations vers les nouvelles normes comptables de location, l’article 842 sur la codification des normes comptables (ASC 842) et la norme internationale en matière de génération des états financiers 16 (IFRS 16).
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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4af7b9dc7a03a6d17ff34ffc726eb87e848dd785
ms.sourcegitcommit: f0f5545a8ff99583e0131f435d91c64bb68a1c38
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2020
ms.locfileid: "4443387"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a><span data-ttu-id="b1ff4-103">Valider les écritures de journal d’ajustement de transition dans la location d’actifs</span><span class="sxs-lookup"><span data-stu-id="b1ff4-103">Post transition adjustment journal entries in Asset leasing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b1ff4-104">Cette rubrique décrit la fonctionnalité qui vous permet de faire la transition d’un portefeuille de location vers les nouvelles normes de comptabilité de location : l’article 842 sur la codification des normes comptables (ASC 842), qui est la norme dans les principes comptables généralement reconnus aux États-Unis (US GAAP), et la norme internationale en matière de génération des états financiers 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="b1ff4-104">This topic describes the functionality that lets you transition a lease portfolio to the new lease accounting standards: Accounting Standards Codification Topic 842 (ASC 842), which is the standard in Generally Accepted Accounting Principles in the US (US GAAP), and International Financial Reporting Standard 16 (IFRS 16).</span></span>

<span data-ttu-id="b1ff4-105">Pour plus d’informations sur la configuration d’un registre pour la transition vers les nouvelles normes, voir [Créer des registres de location](set-up-lease-books.md).</span><span class="sxs-lookup"><span data-stu-id="b1ff4-105">For information about how to set up a book for the transition to the new standards, see [Set up lease books](set-up-lease-books.md).</span></span>

<span data-ttu-id="b1ff4-106">Lorsque vous créez une écriture de journal d’ajustement de transition, une écriture de journal est générée.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-106">When you create a transition adjustment journal entry, a journal entry is generated.</span></span> <span data-ttu-id="b1ff4-107">Cette écriture reflète l’impact sur le bilan de l’enregistrement de location selon les nouvelles normes à cette date.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-107">This entry reflects the balance sheet impact of recording the lease under the new standards on that date.</span></span> <span data-ttu-id="b1ff4-108">Le compte d’actif approprié est débité de la valeur comptable à cette date et le compte de passif est crédité.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-108">The appropriate asset account is debited for the carrying amount on that date, and the liability account is credited.</span></span> <span data-ttu-id="b1ff4-109">La différence est soit débitée, soit créditée aux bénéfices non répartis.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-109">The difference is either debited or credited to retained earnings.</span></span>

<span data-ttu-id="b1ff4-110">Pour enregistrer un ajustement de transition conformément aux nouvelles normes comptables, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-110">To post a transition adjustment in compliance with the new accounting standards, follow these steps.</span></span>

1. <span data-ttu-id="b1ff4-111">Sur la page **Résumé du bail**, sélectionnez le bail, puis sélectionnez **Registres**.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-111">On the **Lease summary** page, select the lease, and then select **Books**.</span></span>
2. <span data-ttu-id="b1ff4-112">Dans le registre, sélectionnez **Calendrier de paiement**.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-112">In the book, select **Payment schedule**.</span></span>
3. <span data-ttu-id="b1ff4-113">Dans la boite de dialogue **Échéancier de paiement**, sélectionnez **Confirmer**.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-113">In the **Payment schedule** dialog box, select **Confirm**.</span></span> <span data-ttu-id="b1ff4-114">Ensuite fermez la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-114">Then close the dialog box.</span></span>
4. <span data-ttu-id="b1ff4-115">Sélectionnez **Ajustement de transition**.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-115">Select **Transition adjustment**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b1ff4-116">Un ajustement de transition ne peut être créé que pour les registres de location affectés à un registre où le champ **Registre de transition** est disponible.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-116">A transition adjustment can be created only for lease books that are assigned to a book where the **Transition book** field is available.</span></span> <span data-ttu-id="b1ff4-117">Si la valeur dans le champ **Début du bail** est postérieure à la date de transition, la valeur dans le champ **Ajustement de transition** ne sera pas mis à jour.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-117">If the value in the **Lease commencement** field is later than the transition date, the value in the **Transition adjustment** field won't be updated.</span></span>

5. <span data-ttu-id="b1ff4-118">Pour afficher l’entrée de journal, sélectionnez **Journaux de location d’actifs**.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-118">To view the journal entry, select **Asset leasing journals**.</span></span>
6. <span data-ttu-id="b1ff4-119">Sélectionnez le nouveau journal, puis sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b1ff4-119">Select the new journal, and then select **Post**.</span></span>
