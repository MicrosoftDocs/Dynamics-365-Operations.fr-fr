---
title: Entrer des combinaisons de compte et de dimensions (contrôle d'accès segmenté)
description: Cet article décrit comment entrer des combinaisons de comptes et de dimensions ou de comptes généraux. L'expérience de saisie est souvent appelée « contrôle d'accès segmenté ».
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14071
ms.assetid: e6fce826-c403-4d91-a78b-e9a58c44ac03
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9addb2897bac68115a38f0239764ab65af2378c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "315657"
---
# <a name="enter-account-and-dimension-combinations-segmented-entry-control"></a><span data-ttu-id="936f3-104">Entrer des combinaisons de compte et de dimensions (contrôle d'accès segmenté)</span><span class="sxs-lookup"><span data-stu-id="936f3-104">Enter account and dimension combinations (segmented entry control)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="936f3-105">Cet article décrit comment entrer des combinaisons de comptes et de dimensions ou de comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="936f3-105">This article describes how to enter account and dimension combinations or ledger accounts.</span></span> <span data-ttu-id="936f3-106">L'expérience de saisie est souvent appelée « contrôle d'accès segmenté ».</span><span class="sxs-lookup"><span data-stu-id="936f3-106">The entry experience is often referred to as segmented entry control.</span></span>

<span data-ttu-id="936f3-107">Les utilisateurs entrent des combinaisons de compte et de dimension dans diverses pages, telles que des pages de journaux généraux, de budgétisation et de définitions de validation.</span><span class="sxs-lookup"><span data-stu-id="936f3-107">Users enter account and dimension combinations on various pages, such as pages for general journals, budgeting, and posting definitions.</span></span> <span data-ttu-id="936f3-108">Les combinaisons de compte et de dimensions valables dépendent des structures de compte affectées à la comptabilité et aux règles avancées affectées aux structures de compte.</span><span class="sxs-lookup"><span data-stu-id="936f3-108">The valid account and dimension combinations depend on the account structures that are assigned to the ledger and the advanced rules that are assigned to the account structures.</span></span> <span data-ttu-id="936f3-109">Lorsque les utilisateurs entrent une combinaison, ils peuvent taper les valeurs manuellement ou tirer profit d'une riche expérience de recherche.</span><span class="sxs-lookup"><span data-stu-id="936f3-109">When users enter a combination, they can either manually type the values or take advantage of a rich, lookup experience.</span></span> <span data-ttu-id="936f3-110">Lorsque vous activez le champ, vous pouvez commencer à entrer votre saisie pour rechercher la valeur et la description.</span><span class="sxs-lookup"><span data-stu-id="936f3-110">When you enter the field, you can start to type and it will search the value and the description.</span></span> <span data-ttu-id="936f3-111">Par exemple, si vous tapez 180, le système recherche une valeur commençant par cette combinaison de chiffres.</span><span class="sxs-lookup"><span data-stu-id="936f3-111">For example, if you type 180 it will search any value that begins with that number combination.</span></span> <span data-ttu-id="936f3-112">Vous pouvez également taper Disponibilités pour rechercher une valeur dont la description commence par Disponibilités.</span><span class="sxs-lookup"><span data-stu-id="936f3-112">Or you may type Cash and it will search any value that has a description that begins with Cash.</span></span> <span data-ttu-id="936f3-113">Vous pouvez également utiliser un caractère générique, tel que \*Disponibilités ou \*180 pour déterminer si la valeur ou la description contient les critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="936f3-113">You can also use a wildcard, such as \*Cash or \*180 to search if the value or description contain the search criteria.</span></span> 

<span data-ttu-id="936f3-114">Le tableau suivant décrit les raccourcis clavier qui peuvent être utilisés lorsque la recherche est clôturée.</span><span class="sxs-lookup"><span data-stu-id="936f3-114">The following table describes the keyboard shortcuts that can be used when the lookup is closed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="936f3-115">Raccourci clavier</span><span class="sxs-lookup"><span data-stu-id="936f3-115">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="936f3-116">Action</span><span class="sxs-lookup"><span data-stu-id="936f3-116">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="936f3-117">Alt + Flèche Bas</span><span class="sxs-lookup"><span data-stu-id="936f3-117">Alt+Down Arrow</span></span></td>
<td><span data-ttu-id="936f3-118">Ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="936f3-118">Open the lookup.</span></span> <span data-ttu-id="936f3-119">Si vous appuyez sur la Alt+flèche Bas une deuxième fois, la vue se déplace sur les segments dans le menu volant.</span><span class="sxs-lookup"><span data-stu-id="936f3-119">If you press Alt+Down Arrow a second time, the focus moves to the segments in the flyout.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="936f3-120">Entrée et Shift+Entrée</span><span class="sxs-lookup"><span data-stu-id="936f3-120">Enter and Shift+Enter</span></span></li>
<li><span data-ttu-id="936f3-121">Séparateur Plan de comptes</span><span class="sxs-lookup"><span data-stu-id="936f3-121">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="936f3-122">Flèche droite et flèche gauche</span><span class="sxs-lookup"><span data-stu-id="936f3-122">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="936f3-123">Permet de passer au segment suivant ou précédent.</span><span class="sxs-lookup"><span data-stu-id="936f3-123">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="936f3-124">Tabulation</span><span class="sxs-lookup"><span data-stu-id="936f3-124">Tab</span></span></td>
<td><span data-ttu-id="936f3-125">Permet de passer au champ suivant dans la grille.</span><span class="sxs-lookup"><span data-stu-id="936f3-125">Move to the next field in the grid.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="936f3-126">Le tableau suivant décrit les raccourcis clavier qui peuvent être utilisés lorsque la recherche est en cours.</span><span class="sxs-lookup"><span data-stu-id="936f3-126">The following table describes the keyboard shortcuts that can be used when the lookup is open.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="936f3-127">Raccourci clavier</span><span class="sxs-lookup"><span data-stu-id="936f3-127">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="936f3-128">Action</span><span class="sxs-lookup"><span data-stu-id="936f3-128">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="936f3-129">Échap</span><span class="sxs-lookup"><span data-stu-id="936f3-129">Esc</span></span></td>
<td><span data-ttu-id="936f3-130">Fermez la recherche.</span><span class="sxs-lookup"><span data-stu-id="936f3-130">Close the lookup.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="936f3-131">Flèche Haut ou Flèche Bas</span><span class="sxs-lookup"><span data-stu-id="936f3-131">Up Arrow and Down Arrow</span></span></li>
<li><span data-ttu-id="936f3-132">Page précédente et page suivante</span><span class="sxs-lookup"><span data-stu-id="936f3-132">Page Up and Page Down</span></span></li>
<li><span data-ttu-id="936f3-133">Début et fin</span><span class="sxs-lookup"><span data-stu-id="936f3-133">Home and End</span></span></li>
</ul></td>
<td><span data-ttu-id="936f3-134">Accéder à la valeur précédente ou suivante dans les listes, au groupe de valeurs précédent ou suivant, ou au premier ou dernier élément dans la recherche.</span><span class="sxs-lookup"><span data-stu-id="936f3-134">Move to the previous or next value in the lists, to the previous or next group of values, or to the first or last element in the lookup.</span></span></td>
</tr>
<tr class="odd">
<td><ul>
<li><span data-ttu-id="936f3-135">Séparateur Plan de comptes</span><span class="sxs-lookup"><span data-stu-id="936f3-135">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="936f3-136">Flèche droite et flèche gauche</span><span class="sxs-lookup"><span data-stu-id="936f3-136">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="936f3-137">Permet de passer au segment suivant ou précédent.</span><span class="sxs-lookup"><span data-stu-id="936f3-137">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="936f3-138">Onglet</span><span class="sxs-lookup"><span data-stu-id="936f3-138">Tab</span></span></td>
<td><span data-ttu-id="936f3-139">Permet de passer au champ suivant dans la grille.</span><span class="sxs-lookup"><span data-stu-id="936f3-139">Move to the next field in the grid.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="936f3-140">Alt+W</span><span class="sxs-lookup"><span data-stu-id="936f3-140">Alt+W</span></span></td>
<td><span data-ttu-id="936f3-141">Permet de basculer entre <strong>Afficher tout</strong> et <strong>Afficher valide</strong>.</span><span class="sxs-lookup"><span data-stu-id="936f3-141">Switch between <strong>Show all</strong> and <strong>Show valid</strong>.</span></span></td>
</tr>
</tbody>
</table>





