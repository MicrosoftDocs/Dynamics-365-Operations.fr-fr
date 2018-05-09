---
title: "Configurer une décision conditionnelle dans un workflow"
description: "La procédure suivante permet de configurer les propriétés d'une décision conditionnelle."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3ba840559c13537f53db5cd0eb27a45d0bfb2d82
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="configure-a-conditional-decision-in-a-workflow"></a><span data-ttu-id="5c118-103">Configurer une décision conditionnelle dans un workflow</span><span class="sxs-lookup"><span data-stu-id="5c118-103">Configure a conditional decision in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5c118-104">La procédure suivante permet de configurer les propriétés d'une décision conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="5c118-104">Use the following procedure to configure the properties of a conditional decision.</span></span>

<span data-ttu-id="5c118-105">Une décision conditionnelle est un point où le workflow se divise en deux branches.</span><span class="sxs-lookup"><span data-stu-id="5c118-105">A conditional decision is a point at which a workflow divides into two branches.</span></span> <span data-ttu-id="5c118-106">Pour configurer une décision conditionnelle, dans l'éditeur de workflow, cliquez avec le bouton droit sur la décision conditionnelle, puis cliquez sur **Propriétés** pour ouvrir l'écran **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5c118-106">To configure a conditional decision, in the workflow editor, right-click the conditional decision, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-a-decision"></a><span data-ttu-id="5c118-107">Nommer une décision</span><span class="sxs-lookup"><span data-stu-id="5c118-107">Name a decision</span></span>
<span data-ttu-id="5c118-108">Procédez comme suit pour entrer un nom pour une décision conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="5c118-108">Follow these steps to enter a name for a conditional decision.</span></span>
1.  <span data-ttu-id="5c118-109">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="5c118-109">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="5c118-110">Dans le champ **Nom**, entrez un nom unique pour la décision conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="5c118-110">In the **Name** field, enter a unique name for the conditional decision.</span></span>

## <a name="set-conditions"></a><span data-ttu-id="5c118-111"> Définition des conditions</span><span class="sxs-lookup"><span data-stu-id="5c118-111">Set conditions</span></span>
<span data-ttu-id="5c118-112">Le système détermine la branche utilisée en évaluant si le document soumis répond à des conditions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5c118-112">The system determines which branch is used by evaluating the submitted document to determine whether it meets specific conditions.</span></span>
1.  <span data-ttu-id="5c118-113">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="5c118-113">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="5c118-114">Cliquez sur **Ajouter une condition**.</span><span class="sxs-lookup"><span data-stu-id="5c118-114">Click **Add condition**.</span></span>
3.  <span data-ttu-id="5c118-115">Permet d'entrer une condition.</span><span class="sxs-lookup"><span data-stu-id="5c118-115">Enter a condition.</span></span>
4.  <span data-ttu-id="5c118-116">Entrez des conditions supplémentaires, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5c118-116">Enter additional conditions, if they are required.</span></span>
5.  <span data-ttu-id="5c118-117">Pour vérifier que les conditions que vous avez entrées sont correctement configurées, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5c118-117">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>
    1.  <span data-ttu-id="5c118-118">Cliquez sur **Test** pour ouvrir l'écran **Condition de workflow de test**.</span><span class="sxs-lookup"><span data-stu-id="5c118-118">Click **Test** to open the **Test workflow condition** form.</span></span>
    2.  <span data-ttu-id="5c118-119">Sélectionnez un enregistrement dans la zone **Contrôler la condition** de l'écran.</span><span class="sxs-lookup"><span data-stu-id="5c118-119">Select a record in the **Validate condition** area of the form.</span></span>
    3.  <span data-ttu-id="5c118-120">Cliquez sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="5c118-120">Click **Test**.</span></span> <span data-ttu-id="5c118-121">Le système évalue l'enregistrement pour déterminer s'il répond aux conditions que vous avez spécifiées.</span><span class="sxs-lookup"><span data-stu-id="5c118-121">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4.  <span data-ttu-id="5c118-122">Cliquez sur **OK** ou sur **Annuler** pour revenir à l'écran **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5c118-122">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>






