---
title: Paramètres d’approvisionnement pour le coût au débarquement
description: Cette rubrique décrit comment configurer les paramètres d’approvisionnement appropriés lorsque vous utilisez le module de coût au débarquement.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ccda3bd769a646e2390711883b8e40bec50e4d6a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020981"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a><span data-ttu-id="9814d-103">Paramètres d’approvisionnement pour le coût au débarquement</span><span class="sxs-lookup"><span data-stu-id="9814d-103">Procurement and sourcing parameters for Landed cost</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9814d-104">La page **Paramètres d’approvisionnement** a quelques paramètres qui sont particulièrement pertinents lorsque vous utilisez le module **coût au débarquement**.</span><span class="sxs-lookup"><span data-stu-id="9814d-104">The **Procurement and sourcing parameters** page has a few settings that are especially relevant when you use the **Landed cost** module.</span></span> <span data-ttu-id="9814d-105">Utilisez la boîte de dialogue **Mettre à jour les lignes de commande** qui s’ouvre à partir de la page **Paramètres d’approvisionnement** pour spécifier si les lignes de commande fournisseur doivent être automatiquement mises à jour lorsque des modifications sont apportées à l’en-tête de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9814d-105">Use the **Update order lines** dialog box that is opened from the **Procurement and sourcing parameters** page to specify whether purchase order lines should automatically be updated when changes are made on the purchase order header.</span></span>

<span data-ttu-id="9814d-106">Pour terminer ce paramétrage, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9814d-106">To complete this setup, follow these steps.</span></span>

1. <span data-ttu-id="9814d-107">Accédez à **Approvisionnements \> Paramétrage \> Paramètres d’approvisionnements**.</span><span class="sxs-lookup"><span data-stu-id="9814d-107">Go to **Procurement and sourcing \> Setup \> Procurement and sourcing parameters**.</span></span>
1. <span data-ttu-id="9814d-108">Sur l’onglet **Général**, sélectionnez le lien **Mettre à jour les lignes de commande**.</span><span class="sxs-lookup"><span data-stu-id="9814d-108">On the **General** tab, select the **Update order lines** link.</span></span>
1. <span data-ttu-id="9814d-109">La boîte de dialogue **Mettre à jour les lignes de commande** répertorie les champs de l’en-tête de commande qui peuvent également appliquer des mises à jour automatiques aux champs associés sur les lignes de commande.</span><span class="sxs-lookup"><span data-stu-id="9814d-109">The **Update order lines** dialog box lists the fields on the order header that can also apply automatic updates to related fields on the order lines.</span></span> <span data-ttu-id="9814d-110">Définissez chaque champ de la liste sur l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9814d-110">Set each field in the list to one of the following values:</span></span>

    - <span data-ttu-id="9814d-111">**Toujours** – Les lignes de commande doivent être mises à jour automatiquement lorsque l’en-tête de la commande est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="9814d-111">**Always** – The order lines should automatically be updated when the order header is updated.</span></span>
    - <span data-ttu-id="9814d-112">**Jamais** – Les lignes de commande ne doivent jamais être mises à jour lorsque l’en-tête de la commande est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="9814d-112">**Never** – The order lines should never be updated when the order header is updated.</span></span>
    - <span data-ttu-id="9814d-113">**Inviter** – L’utilisateur sera invité à choisir si les lignes de commande doivent être mises à jour.</span><span class="sxs-lookup"><span data-stu-id="9814d-113">**Prompt** – The user will be prompted to select whether the order lines should be updated.</span></span>
