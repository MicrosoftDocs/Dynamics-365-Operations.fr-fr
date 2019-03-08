---
title: Incorporer les applications PowerApps dans Core HR
description: Cette rubrique explique comment résoudre le problème où l'option de menu PowerApps a disparu du module Administration du système.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 197b553f0b202ee29ad42274e2c0e03446ec782c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304397"
---
# <a name="embed-powerapps-apps-in-core-hr"></a><span data-ttu-id="a1b9d-103">Incorporer les applications PowerApps dans Core HR</span><span class="sxs-lookup"><span data-stu-id="a1b9d-103">Embed PowerApps apps in Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a1b9d-104">**Problème**</span><span class="sxs-lookup"><span data-stu-id="a1b9d-104">**Issue**</span></span>

<span data-ttu-id="a1b9d-105">L'élément de menu **PowerApps** a disparu du module **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-105">The **PowerApps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="a1b9d-106">**Cause**</span><span class="sxs-lookup"><span data-stu-id="a1b9d-106">**Cause**</span></span>

<span data-ttu-id="a1b9d-107">La conception de l'interface utilisateur (IU) a été modifiée, et Microsoft PowerApps est désormais inclus dans le modèle de personnalisation standard.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-107">The user interface (UI) design has been changed, and Microsoft PowerApps is now included in the standard personalization model.</span></span>

<span data-ttu-id="a1b9d-108">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="a1b9d-108">**Resolution**</span></span>

<span data-ttu-id="a1b9d-109">La manière dont les applications PowerApps sont incorporées a été modifiée.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-109">The way that PowerApps apps are embedded has been changed.</span></span> <span data-ttu-id="a1b9d-110">Les applications PowerApps sont maintenant ajoutées via le modèle de personnalisation.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-110">PowerApps apps are now added through the personalization model.</span></span> <span data-ttu-id="a1b9d-111">Vous pouvez ajouter des applications PowerApps à presque toutes les pages de Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-111">You can add PowerApps apps to almost all pages in Microsoft Dynamics 365 for Talent.</span></span>

<span data-ttu-id="a1b9d-112">Pour plus d'informations sur l'incorporation d'applications PowerApps dans Talent, voir [Incorporer des applications PowerApps](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="a1b9d-112">For information about how to embed PowerApps apps in Talent, see [Embed PowerApps apps](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="a1b9d-113">Tout client PowerApps ayant incorporé des applications avant la modification doit avoir été mis à niveau vers le nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-113">Any PowerApps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="a1b9d-114">Le bouton **PowerApps** est dans le coin supérieur droit de presque chaque page de Talent.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-114">The **PowerApps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="a1b9d-115">Vous pouvez utiliser ce bouton pour insérer une application PowerApps.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-115">You can use this button to insert a PowerApps app.</span></span>

<span data-ttu-id="a1b9d-116">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="a1b9d-116">Here is an example.</span></span>

1. <span data-ttu-id="a1b9d-117">Accédez à **Gestion du personnel \> Liens \> Collaborateurs \> Employés**.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="a1b9d-118">Sélectionnez le bouton **PowerApps**, puis sélectionnez **Insérer un PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-118">Select the **PowerApps** button, and then select **Insert a PowerApp**.</span></span>

    ![Bouton PowerApps](media/png.png)

3. <span data-ttu-id="a1b9d-120">Renseignez les champs de la boîte de dialogue **Insérer un PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Boîte de dialogue Insérer un PowerApp](media/insert-powerapp.png)

<span data-ttu-id="a1b9d-122">Sinon, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a1b9d-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="a1b9d-123">Sur le volet Action de la page, sous l'onglet **Options**, dans le groupe **Personnaliser**, sélectionnez **Personnaliser cet écran**.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Personnaliser le groupe sous l'onglet Options](media/options.png)

    <span data-ttu-id="a1b9d-125">La barre d'outils de personnalisation s'affiche.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="a1b9d-126">Sur la barre d'outils, sélectionnez **Insérer \> PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="a1b9d-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Insérez une application PowerApps à l'aide de la barre d'outils de personnalisation](media/powerapp-bar.png)
