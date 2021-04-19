---
title: Configurer des décisions conditionnelles dans un workflow
description: La procédure suivante permet de configurer les propriétés d’une décision conditionnelle.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed53eeb26e1b4b1df1647739ce1d115c7dd169f8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747929"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a><span data-ttu-id="e8d6b-103">Configurer des décisions conditionnelles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="e8d6b-103">Configure conditional decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e8d6b-104">La procédure suivante permet de configurer les propriétés d’une décision conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-104">Use the following procedure to configure the properties of a conditional decision.</span></span>

<span data-ttu-id="e8d6b-105">Une décision conditionnelle est un point où le workflow se divise en deux branches.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-105">A conditional decision is a point at which a workflow divides into two branches.</span></span> <span data-ttu-id="e8d6b-106">Pour configurer une décision conditionnelle, dans l’éditeur de workflow, cliquez avec le bouton droit sur la décision conditionnelle, puis cliquez sur **Propriétés** pour ouvrir l’écran **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-106">To configure a conditional decision, in the workflow editor, right-click the conditional decision, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-a-decision"></a><span data-ttu-id="e8d6b-107">Nommer une décision</span><span class="sxs-lookup"><span data-stu-id="e8d6b-107">Name a decision</span></span>

<span data-ttu-id="e8d6b-108">Procédez comme suit pour entrer un nom pour une décision conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-108">Follow these steps to enter a name for a conditional decision.</span></span>

1. <span data-ttu-id="e8d6b-109">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="e8d6b-110">Dans le champ **Nom**, entrez un nom unique pour la décision conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-110">In the **Name** field, enter a unique name for the conditional decision.</span></span>

## <a name="set-conditions"></a><span data-ttu-id="e8d6b-111">Définition des conditions</span><span class="sxs-lookup"><span data-stu-id="e8d6b-111">Set conditions</span></span>

<span data-ttu-id="e8d6b-112">Le système détermine la branche utilisée en évaluant si le document soumis répond à des conditions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-112">The system determines which branch is used by evaluating the submitted document to determine whether it meets specific conditions.</span></span>

1. <span data-ttu-id="e8d6b-113">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="e8d6b-114">Cliquez sur **Ajouter une condition**.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-114">Click **Add condition**.</span></span>
3. <span data-ttu-id="e8d6b-115">Permet d’entrer une condition.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-115">Enter a condition.</span></span>
4. <span data-ttu-id="e8d6b-116">Entrez des conditions supplémentaires, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-116">Enter additional conditions, if they are required.</span></span>
5. <span data-ttu-id="e8d6b-117">Pour vérifier que les conditions que vous avez entrées sont correctement configurées, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e8d6b-117">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="e8d6b-118">Cliquez sur **Test** pour ouvrir l’écran **Condition de workflow de test**.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-118">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="e8d6b-119">Sélectionnez un enregistrement dans la zone **Contrôler la condition** de l’écran.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-119">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="e8d6b-120">Cliquez sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-120">Click **Test**.</span></span> <span data-ttu-id="e8d6b-121">Le système évalue l’enregistrement pour déterminer s’il répond aux conditions que vous avez spécifiées.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-121">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="e8d6b-122">Cliquez sur **OK** ou sur **Annuler** pour revenir à l’écran **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e8d6b-122">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]