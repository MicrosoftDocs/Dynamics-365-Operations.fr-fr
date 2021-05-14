---
title: Les champs de poids sur les lignes de charge ne correspondent pas à ceux situés sur la charge
description: Les champs de poids sur les lignes de charge ne correspondent pas à ceux situés sur la charge
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924349"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a><span data-ttu-id="60849-103">Les champs de poids sur les lignes de charge ne correspondent pas à ceux situés sur la charge</span><span class="sxs-lookup"><span data-stu-id="60849-103">The weight fields on load lines don't match the weight fields on the load</span></span>

<span data-ttu-id="60849-104">Codes d'erreur : WHSLoadWeightOnLinesDoNotMatchLoadWarning</span><span class="sxs-lookup"><span data-stu-id="60849-104">Error codes: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span></span>

## <a name="symptoms"></a><span data-ttu-id="60849-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="60849-105">Symptoms</span></span>

<span data-ttu-id="60849-106">Le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="60849-106">The system shows the following error message:</span></span>

> <span data-ttu-id="60849-107">Les champs de poids sur les lignes de charge ne correspondent pas à ceux situés sur la charge %1.</span><span class="sxs-lookup"><span data-stu-id="60849-107">The weight fields on load lines do not match the weight fields on load %1.</span></span> <span data-ttu-id="60849-108">Exécutez le contrôle de la cohérence du poids de la charge de l’entrepôt pour recalculer les champs de poids.</span><span class="sxs-lookup"><span data-stu-id="60849-108">Run the Warehouse load weight consistency check to recalculate the weight fields.</span></span>

## <a name="cause"></a><span data-ttu-id="60849-109">Cause</span><span class="sxs-lookup"><span data-stu-id="60849-109">Cause</span></span>

<span data-ttu-id="60849-110">Les champs **Poids net** et **Tare** sont définis sur *0* (zéro) sur la ligne de charge.</span><span class="sxs-lookup"><span data-stu-id="60849-110">The **Net weight** and **Tara weight** fields are set to *0* (zero) on the load line.</span></span> <span data-ttu-id="60849-111">Cependant, les champs de poids ne sont pas définis sur *0* pour les mesures de poids sur le produit.</span><span class="sxs-lookup"><span data-stu-id="60849-111">However, the weight fields aren't set to *0* for the weight measurements on the product.</span></span> <span data-ttu-id="60849-112">Lorsque les champs de poids ne sont pas définis sur la ligne de charge, toute correction de la quantité sur la ligne de charge peut entraîner un calcul de poids incorrect sur la charge.</span><span class="sxs-lookup"><span data-stu-id="60849-112">When weight fields aren't set on the load line, any corrections of the quantity on the load line might cause incorrect weight calculation on the load.</span></span> <span data-ttu-id="60849-113">Ce problème peut se produire si les poids du produit ont été modifiés depuis la création de la ligne de charge.</span><span class="sxs-lookup"><span data-stu-id="60849-113">This issue might occur if the weights on the product have been changed since the load line was created.</span></span>

## <a name="resolution"></a><span data-ttu-id="60849-114">Résolution</span><span class="sxs-lookup"><span data-stu-id="60849-114">Resolution</span></span>

<span data-ttu-id="60849-115">Par défaut, lorsqu'une ligne de charge est créée, les champs de poids du produit y sont saisis.</span><span class="sxs-lookup"><span data-stu-id="60849-115">By default, when a load line is created, the weight fields from the product are entered on it.</span></span> <span data-ttu-id="60849-116">Si le poids est nul, vous pouvez le recalculer en utilisant la fonctionnalité *Vérification de la cohérence du poids de la charge de l’entrepôt*.</span><span class="sxs-lookup"><span data-stu-id="60849-116">If the weight is zero, you can recalculate it by using the *Warehouse load weight consistency check* functionality.</span></span>

1. <span data-ttu-id="60849-117">Accédez à **Administration système \> Tâches périodiques \> Base de données \> Contrôle de cohérence**.</span><span class="sxs-lookup"><span data-stu-id="60849-117">Go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="60849-118">Dans la boîte de dialogue **Contrôle de cohérence**, définissez le champ **Module** sur *Gestion des entrepôts*.</span><span class="sxs-lookup"><span data-stu-id="60849-118">In the **Consistency check** dialog box, set the **Module** field to *Warehouse management*.</span></span>
1. <span data-ttu-id="60849-119">Définissez le champ **Vérifier/réparer** sur *Corriger les erreurs*.</span><span class="sxs-lookup"><span data-stu-id="60849-119">Set the **Check/Fix** field to *Fix error*.</span></span>
1. <span data-ttu-id="60849-120">Dans la liste des cases à cocher, cochez la case **Vérification de la cohérence du poids de la charge de l’entrepôt** et assurez-vous que seule la ligne correspondant à cette case est mise en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="60849-120">In the checkbox list, select the **Warehouse load weight consistency check** checkbox, and make sure that only the row for this checkbox is highlighted.</span></span>
1. <span data-ttu-id="60849-121">En haut de la liste des cases à cocher, sélectionnez le bouton points de suspension (**...**), puis sélectionnez **Boîte de dialogue** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="60849-121">At the top of the checkbox list, select the ellipsis button (**...**), and then select **Dialog** on the menu.</span></span>
1. <span data-ttu-id="60849-122">Dans la boîte de dialogue **Vérification de la cohérence du poids de la charge de l’entrepôt**, définissez les champs suivants pour spécifier les critères pour lesquels la vérification de cohérence doit s'exécuter :</span><span class="sxs-lookup"><span data-stu-id="60849-122">In the **Warehouse load weight consistency check** dialog box, set the following fields to specify the criteria that the consistency check should run for:</span></span>

    - <span data-ttu-id="60849-123">**ID de chargement :** Spécifiez un ID de chargement.</span><span class="sxs-lookup"><span data-stu-id="60849-123">**Load ID:** Specify a load ID.</span></span> <span data-ttu-id="60849-124">Laissez ce champ vide pour vérifier tous les ID de chargement.</span><span class="sxs-lookup"><span data-stu-id="60849-124">Leave this blank to check all load IDs.</span></span>
    - <span data-ttu-id="60849-125">**Numéro d'article :** Spécifiez un numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="60849-125">**Item number:** Specify an item number.</span></span> <span data-ttu-id="60849-126">Laissez ce champ vide pour vérifier tous les articles.</span><span class="sxs-lookup"><span data-stu-id="60849-126">Leave this blank to check all items.</span></span>
    - <span data-ttu-id="60849-127">**Toujours recalculer le poids sur les charges :** Définissez cette option sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="60849-127">**Always recalculate weight on loads:** Set this option to *Yes*.</span></span>
    - <span data-ttu-id="60849-128">**Autoriser l'écrasement du poids sur les lignes de charge :** Définissez cette option sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="60849-128">**Allow overwrite of weight on load lines:** Set this option to *Yes*.</span></span>

1. <span data-ttu-id="60849-129">Cliquez sur **OK** pour fermer la boite de dialogue **Vérification de la cohérence du poids de la charge de l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="60849-129">Select **OK** to close the **Warehouse load weight consistency check** dialog box.</span></span>
1. <span data-ttu-id="60849-130">Sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Exécuter** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="60849-130">Select the ellipsis button, and then select **Execute** on the menu.</span></span>

<span data-ttu-id="60849-131">Le poids est recalculé en fonction des critères que vous avez spécifiés.</span><span class="sxs-lookup"><span data-stu-id="60849-131">The weight is recalculated based on the criteria that you specified.</span></span> <span data-ttu-id="60849-132">Cliquez sur le lien **Détails du message** pour afficher le résultat du contrôle de cohérence.</span><span class="sxs-lookup"><span data-stu-id="60849-132">Select the **Message details** link to view the result of the consistency check.</span></span>
