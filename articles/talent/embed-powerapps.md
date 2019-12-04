---
title: Incorporer les applications Power Apps dans Dynamics 365 - Core HR
description: Cette rubrique explique comment résoudre le problème où l'option de menu Microsoft Power Apps a disparu du module Administration du système.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6d1b7f1dd71e6bcbf10c4d91fe33e9494b041a2c
ms.sourcegitcommit: ae0efac749ab34d423fac44d00a597801c143fbb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/22/2019
ms.locfileid: "2830207"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a><span data-ttu-id="a83cc-103">Incorporer les applications Power Apps dans Dynamics 365 - Core HR</span><span class="sxs-lookup"><span data-stu-id="a83cc-103">Embed Power Apps apps in Dynamics 365 - Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a83cc-104">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="a83cc-104">**Issue**</span></span>

<span data-ttu-id="a83cc-105">L'élément de menu **Power Apps** a disparu du module **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="a83cc-105">The **Power Apps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="a83cc-106">**Cause**</span><span class="sxs-lookup"><span data-stu-id="a83cc-106">**Cause**</span></span>

<span data-ttu-id="a83cc-107">La conception de l'interface utilisateur (IU) a été modifiée, et Microsoft Power Apps est désormais inclus dans le modèle de personnalisation standard.</span><span class="sxs-lookup"><span data-stu-id="a83cc-107">The user interface (UI) design has been changed, and Microsoft Power Apps is now included in the standard personalization model.</span></span>

<span data-ttu-id="a83cc-108">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="a83cc-108">**Resolution**</span></span>

<span data-ttu-id="a83cc-109">La manière dont les applications Power Apps sont incorporées a été modifiée.</span><span class="sxs-lookup"><span data-stu-id="a83cc-109">The way that Power Apps are embedded has been changed.</span></span> <span data-ttu-id="a83cc-110">Les applications Power Apps sont maintenant ajoutées via le modèle de personnalisation.</span><span class="sxs-lookup"><span data-stu-id="a83cc-110">Power Apps are now added through the personalization model.</span></span> <span data-ttu-id="a83cc-111">Vous pouvez ajouter des applications Power Apps à presque toutes les pages de Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="a83cc-111">You can add Power Apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="a83cc-112">Pour plus d'informations sur l'incorporation d'applications Power Apps dans Talent, voir [Incorporer des applications Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="a83cc-112">For information about how to embed Power Apps in Talent, see [Embed Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="a83cc-113">Tout client Power Apps ayant incorporé des applications avant la modification doit avoir été mis à niveau vers le nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="a83cc-113">Any Power Apps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="a83cc-114">Le bouton **Power Apps** est dans le coin supérieur droit de presque chaque page de Talent.</span><span class="sxs-lookup"><span data-stu-id="a83cc-114">The **Power Apps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="a83cc-115">Vous pouvez utiliser ce bouton pour insérer une application Power Apps.</span><span class="sxs-lookup"><span data-stu-id="a83cc-115">You can use this button to insert Power Apps.</span></span>

<span data-ttu-id="a83cc-116">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="a83cc-116">Here is an example.</span></span>

1. <span data-ttu-id="a83cc-117">Accédez à **Gestion du personnel \> Liens \> Collaborateurs \> Employés**.</span><span class="sxs-lookup"><span data-stu-id="a83cc-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="a83cc-118">Sélectionnez le bouton **Power Apps**, puis sélectionnez **Insérer un PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a83cc-118">Select the **Power Apps** button, and then select **Insert a PowerApp**.</span></span>

    ![Bouton Power Apps](media/png.png)

3. <span data-ttu-id="a83cc-120">Renseignez les champs de la boîte de dialogue **Insérer un PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a83cc-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Boîte de dialogue Insérer un PowerApp](media/insert-powerapp.png)

<span data-ttu-id="a83cc-122">Sinon, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a83cc-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="a83cc-123">Sur le volet Action de la page, sous l'onglet **Options**, dans le groupe **Personnaliser**, sélectionnez **Personnaliser cet écran**.</span><span class="sxs-lookup"><span data-stu-id="a83cc-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Personnaliser le groupe sous l'onglet Options](media/options.png)

    <span data-ttu-id="a83cc-125">La barre d'outils de personnalisation s'affiche.</span><span class="sxs-lookup"><span data-stu-id="a83cc-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="a83cc-126">Sur la barre d'outils, sélectionnez **Insérer \> PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a83cc-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Insérer une application Power Apps à l'aide de la barre d'outils de personnalisation](media/powerapp-bar.png)
