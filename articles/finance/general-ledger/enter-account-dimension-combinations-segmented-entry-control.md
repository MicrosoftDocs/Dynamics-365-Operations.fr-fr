---
title: Entrer des combinaisons de compte et de dimensions (contrôle d’accès segmenté)
description: Cet article décrit comment entrer des combinaisons de comptes et de dimensions ou de comptes généraux. L’expérience de saisie est souvent appelée « contrôle d’accès segmenté ».
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure
audience: Application User
ms.reviewer: roschlom
ms.custom: 14071
ms.assetid: e6fce826-c403-4d91-a78b-e9a58c44ac03
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1e35f5fb4400f849e9a139e1a96b18e8b9df384
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968777"
---
# <a name="enter-account-and-dimension-combinations-segmented-entry-control"></a><span data-ttu-id="0f433-104">Entrer des combinaisons de compte et de dimensions (contrôle d’accès segmenté)</span><span class="sxs-lookup"><span data-stu-id="0f433-104">Enter account and dimension combinations (segmented entry control)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0f433-105">Cet article décrit comment entrer des combinaisons de comptes et de dimensions ou de comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="0f433-105">This article describes how to enter account and dimension combinations or ledger accounts.</span></span> <span data-ttu-id="0f433-106">L’expérience de saisie est souvent appelée « contrôle d’accès segmenté ».</span><span class="sxs-lookup"><span data-stu-id="0f433-106">The entry experience is often referred to as segmented entry control.</span></span>

<span data-ttu-id="0f433-107">Les utilisateurs entrent des combinaisons de compte et de dimension dans diverses pages, telles que des pages de journaux généraux, de budgétisation et de définitions de validation.</span><span class="sxs-lookup"><span data-stu-id="0f433-107">Users enter account and dimension combinations on various pages, such as pages for general journals, budgeting, and posting definitions.</span></span> <span data-ttu-id="0f433-108">Les combinaisons de compte et de dimensions valables dépendent des structures de compte affectées à la comptabilité et aux règles avancées affectées aux structures de compte.</span><span class="sxs-lookup"><span data-stu-id="0f433-108">The valid account and dimension combinations depend on the account structures that are assigned to the ledger and the advanced rules that are assigned to the account structures.</span></span> <span data-ttu-id="0f433-109">Lorsque les utilisateurs entrent une combinaison, ils peuvent taper les valeurs manuellement ou tirer profit d’une riche expérience de recherche.</span><span class="sxs-lookup"><span data-stu-id="0f433-109">When users enter a combination, they can either manually type the values or take advantage of a rich, lookup experience.</span></span> <span data-ttu-id="0f433-110">Lorsque vous activez le champ, vous pouvez commencer à entrer votre saisie pour rechercher la valeur et la description.</span><span class="sxs-lookup"><span data-stu-id="0f433-110">When you enter the field, you can start to type and it will search the value and the description.</span></span> <span data-ttu-id="0f433-111">Par exemple, si vous tapez 180, le système recherche une valeur commençant par cette combinaison de chiffres.</span><span class="sxs-lookup"><span data-stu-id="0f433-111">For example, if you type 180 it will search any value that begins with that number combination.</span></span> <span data-ttu-id="0f433-112">Vous pouvez également taper Disponibilités pour rechercher une valeur dont la description commence par Disponibilités.</span><span class="sxs-lookup"><span data-stu-id="0f433-112">Or you may type Cash and it will search any value that has a description that begins with Cash.</span></span> <span data-ttu-id="0f433-113">Vous pouvez également utiliser un caractère générique, tel que \*Disponibilités ou \*180 pour déterminer si la valeur ou la description contient les critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="0f433-113">You can also use a wildcard, such as \*Cash or \*180 to search if the value or description contain the search criteria.</span></span> 

<span data-ttu-id="0f433-114">Le tableau suivant décrit les raccourcis clavier qui peuvent être utilisés lorsque la recherche est clôturée.</span><span class="sxs-lookup"><span data-stu-id="0f433-114">The following table describes the keyboard shortcuts that can be used when the lookup is closed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f433-115">Raccourci clavier</span><span class="sxs-lookup"><span data-stu-id="0f433-115">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="0f433-116">Action</span><span class="sxs-lookup"><span data-stu-id="0f433-116">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0f433-117">Alt + Flèche Bas</span><span class="sxs-lookup"><span data-stu-id="0f433-117">Alt+Down Arrow</span></span></td>
<td><span data-ttu-id="0f433-118">Ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="0f433-118">Open the lookup.</span></span> <span data-ttu-id="0f433-119">Si vous appuyez sur la Alt+flèche Bas une deuxième fois, la vue se déplace sur les segments dans le menu volant.</span><span class="sxs-lookup"><span data-stu-id="0f433-119">If you press Alt+Down Arrow a second time, the focus moves to the segments in the flyout.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="0f433-120">Entrée et Shift+Entrée</span><span class="sxs-lookup"><span data-stu-id="0f433-120">Enter and Shift+Enter</span></span></li>
<li><span data-ttu-id="0f433-121">Séparateur Plan de comptes</span><span class="sxs-lookup"><span data-stu-id="0f433-121">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="0f433-122">Flèche droite et flèche gauche</span><span class="sxs-lookup"><span data-stu-id="0f433-122">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="0f433-123">Permet de passer au segment suivant ou précédent.</span><span class="sxs-lookup"><span data-stu-id="0f433-123">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0f433-124">Tabulation</span><span class="sxs-lookup"><span data-stu-id="0f433-124">Tab</span></span></td>
<td><span data-ttu-id="0f433-125">Permet de passer au champ suivant dans la grille.</span><span class="sxs-lookup"><span data-stu-id="0f433-125">Move to the next field in the grid.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0f433-126">Le tableau suivant décrit les raccourcis clavier qui peuvent être utilisés lorsque la recherche est en cours.</span><span class="sxs-lookup"><span data-stu-id="0f433-126">The following table describes the keyboard shortcuts that can be used when the lookup is open.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f433-127">Raccourci clavier</span><span class="sxs-lookup"><span data-stu-id="0f433-127">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="0f433-128">Action</span><span class="sxs-lookup"><span data-stu-id="0f433-128">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0f433-129">Échap</span><span class="sxs-lookup"><span data-stu-id="0f433-129">Esc</span></span></td>
<td><span data-ttu-id="0f433-130">Fermez la recherche.</span><span class="sxs-lookup"><span data-stu-id="0f433-130">Close the lookup.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="0f433-131">Flèche Haut ou Flèche Bas</span><span class="sxs-lookup"><span data-stu-id="0f433-131">Up Arrow and Down Arrow</span></span></li>
<li><span data-ttu-id="0f433-132">Page précédente et page suivante</span><span class="sxs-lookup"><span data-stu-id="0f433-132">Page Up and Page Down</span></span></li>
<li><span data-ttu-id="0f433-133">Début et fin</span><span class="sxs-lookup"><span data-stu-id="0f433-133">Home and End</span></span></li>
</ul></td>
<td><span data-ttu-id="0f433-134">Accéder à la valeur précédente ou suivante dans les listes, au groupe de valeurs précédent ou suivant, ou au premier ou dernier élément dans la recherche.</span><span class="sxs-lookup"><span data-stu-id="0f433-134">Move to the previous or next value in the lists, to the previous or next group of values, or to the first or last element in the lookup.</span></span></td>
</tr>
<tr class="odd">
<td><ul>
<li><span data-ttu-id="0f433-135">Séparateur Plan de comptes</span><span class="sxs-lookup"><span data-stu-id="0f433-135">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="0f433-136">Flèche droite et flèche gauche</span><span class="sxs-lookup"><span data-stu-id="0f433-136">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="0f433-137">Permet de passer au segment suivant ou précédent.</span><span class="sxs-lookup"><span data-stu-id="0f433-137">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0f433-138">Onglet</span><span class="sxs-lookup"><span data-stu-id="0f433-138">Tab</span></span></td>
<td><span data-ttu-id="0f433-139">Permet de passer au champ suivant dans la grille.</span><span class="sxs-lookup"><span data-stu-id="0f433-139">Move to the next field in the grid.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0f433-140">Alt+W</span><span class="sxs-lookup"><span data-stu-id="0f433-140">Alt+W</span></span></td>
<td><span data-ttu-id="0f433-141">Permet de basculer entre <strong>Afficher tout</strong> et <strong>Afficher valide</strong>.</span><span class="sxs-lookup"><span data-stu-id="0f433-141">Switch between <strong>Show all</strong> and <strong>Show valid</strong>.</span></span></td>
</tr>
</tbody>
</table>





