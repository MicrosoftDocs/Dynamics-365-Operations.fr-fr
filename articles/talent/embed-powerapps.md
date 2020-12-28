---
title: Intégrer les applications Power Apps dans Dynamics 365 Human Resources
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
ms.openlocfilehash: 8275a8a7c68fa13d6b9880c4c411deaa2dcbb998
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461121"
---
# <a name="embed-power-apps-apps-in-dynamics-365-human-resources"></a><span data-ttu-id="cbb91-103">Intégrer les applications Power Apps dans Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="cbb91-103">Embed Power Apps apps in Dynamics 365 Human Resources</span></span>

<span data-ttu-id="cbb91-104">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="cbb91-104">**Issue**</span></span>

<span data-ttu-id="cbb91-105">L'élément de menu **Power Apps** a disparu du module **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="cbb91-105">The **Power Apps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="cbb91-106">**Cause**</span><span class="sxs-lookup"><span data-stu-id="cbb91-106">**Cause**</span></span>

<span data-ttu-id="cbb91-107">La conception de l'interface utilisateur (IU) a été modifiée, et Microsoft Power Apps est désormais inclus dans le modèle de personnalisation standard.</span><span class="sxs-lookup"><span data-stu-id="cbb91-107">The user interface (UI) design has been changed, and Microsoft Power Apps is now included in the standard personalization model.</span></span>

<span data-ttu-id="cbb91-108">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="cbb91-108">**Resolution**</span></span>

<span data-ttu-id="cbb91-109">La manière dont les applications Power Apps sont incorporées a été modifiée.</span><span class="sxs-lookup"><span data-stu-id="cbb91-109">The way that Power Apps are embedded has been changed.</span></span> <span data-ttu-id="cbb91-110">Les applications Power Apps sont maintenant ajoutées via le modèle de personnalisation.</span><span class="sxs-lookup"><span data-stu-id="cbb91-110">Power Apps are now added through the personalization model.</span></span> <span data-ttu-id="cbb91-111">Vous pouvez ajouter des applications Power Apps à presque toutes les pages de Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="cbb91-111">You can add Power Apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="cbb91-112">Pour plus d'informations sur l'incorporation d'applications Power Apps dans Talent, voir [Incorporer des applications Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="cbb91-112">For information about how to embed Power Apps in Talent, see [Embed Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="cbb91-113">Tout client Power Apps ayant incorporé des applications avant la modification doit avoir été mis à niveau vers le nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="cbb91-113">Any Power Apps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="cbb91-114">Le bouton **Power Apps** est dans le coin supérieur droit de presque chaque page de Talent.</span><span class="sxs-lookup"><span data-stu-id="cbb91-114">The **Power Apps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="cbb91-115">Vous pouvez utiliser ce bouton pour insérer des applications.</span><span class="sxs-lookup"><span data-stu-id="cbb91-115">You can use this button to insert apps.</span></span>

<span data-ttu-id="cbb91-116">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="cbb91-116">Here is an example.</span></span>

1. <span data-ttu-id="cbb91-117">Accédez à **Gestion du personnel \> Liens \> Collaborateurs \> Employés**.</span><span class="sxs-lookup"><span data-stu-id="cbb91-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="cbb91-118">Sélectionnez le bouton **Power Apps**, puis sélectionnez **Ajouter une application depuis Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="cbb91-118">Select the **Power Apps** button, and then select **Add an app from Power Apps**.</span></span>

    ![Bouton Power Apps](media/png.png)

3. <span data-ttu-id="cbb91-120">Remplissez les champs de la boîte de dialogue **Ajouter une application depuis Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="cbb91-120">Complete the fields in the **Add an app from Power Apps** dialog box.</span></span>

    ![Ajouter une application depuis une boîte de dialogue Power Apps](media/insert-powerapp.png)

<span data-ttu-id="cbb91-122">Sinon, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cbb91-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="cbb91-123">Dans le volet Actions de la page, sous l'onglet **Options**, dans le groupe **Personnaliser**, sélectionnez **Personnaliser cette page**.</span><span class="sxs-lookup"><span data-stu-id="cbb91-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this page**.</span></span>

    ![Personnaliser le groupe sous l'onglet Options](media/options.png)

    <span data-ttu-id="cbb91-125">La barre d'outils de personnalisation s'affiche.</span><span class="sxs-lookup"><span data-stu-id="cbb91-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="cbb91-126">Dans la barre d'outils, sélectionnez **Ajouter une application depuis Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="cbb91-126">On the toolbar, select **Add an app from Power Apps**.</span></span>

    ![Ajouter une application depuis Power Apps à l'aide de la barre d'outils de personnalisation](media/powerapp-bar.png)
