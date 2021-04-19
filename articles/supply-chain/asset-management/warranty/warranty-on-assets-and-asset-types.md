---
title: Garanties sur les actifs et les types d’actifs
description: Cette rubrique explique comment paramétrer les garanties sur les actifs et les types d’actifs dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f05f5af76aeb037d606d38a368a49d011f0d2bd6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825564"
---
# <a name="warranties-on-assets-and-asset-types"></a><span data-ttu-id="65c19-103">Garanties sur les actifs et les types d’actifs</span><span class="sxs-lookup"><span data-stu-id="65c19-103">Warranties on assets and asset types</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="65c19-104">Cette rubrique explique comment paramétrer les garanties sur les actifs et les types d’actifs dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="65c19-104">This topic explains how to set up warranties on assets and asset types in Asset Management.</span></span>

## <a name="set-up-a-warranty-on-an-asset-type"></a><span data-ttu-id="65c19-105">Configurer une garantie sur un type d’actif</span><span class="sxs-lookup"><span data-stu-id="65c19-105">Set up a warranty on an asset type</span></span>

1. <span data-ttu-id="65c19-106">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Types d’actif** \> **Types d’actif**.</span><span class="sxs-lookup"><span data-stu-id="65c19-106">Select **Asset management** \> **Setup** \> **Asset types** \> **Asset types**.</span></span>
2. <span data-ttu-id="65c19-107">Dans le volet gauche, sélectionnez le type d’actif à joindre à un contrat de garantie fournisseur, puis sélectionnez **Valeurs par défaut du type d’actif**.</span><span class="sxs-lookup"><span data-stu-id="65c19-107">In the left pane, select the asset type to attach a vendor warranty agreement to, and then select **Asset type defaults**.</span></span>
3. <span data-ttu-id="65c19-108">Sur l’organisateur **Général**, dans le champ **Garantie fournisseur**, sélectionnez le contrat.</span><span class="sxs-lookup"><span data-stu-id="65c19-108">On the **General** FastTab, in the **Vendor warranty** field, select the agreement.</span></span>

## <a name="set-up-a-warranty-on-an-asset"></a><span data-ttu-id="65c19-109">Configurer une garantie sur un actif</span><span class="sxs-lookup"><span data-stu-id="65c19-109">Set up a warranty on an asset</span></span>

1. <span data-ttu-id="65c19-110">Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les actifs**.</span><span class="sxs-lookup"><span data-stu-id="65c19-110">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="65c19-111">Sélectionnez l’actif, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="65c19-111">Select the asset, and then select **Edit**.</span></span>
3. <span data-ttu-id="65c19-112">Sur l’organisateur **Fournisseur**, dans la section **Garantie fournisseur**, dans le champ **Garantie**, sélectionnez le contrat de garantie.</span><span class="sxs-lookup"><span data-stu-id="65c19-112">On the **Vendor** FastTab, in the **Vendor warranty** section, in the **Warranty** field, select the warranty agreement.</span></span>
4. <span data-ttu-id="65c19-113">Dans les champs **Début de garantie** et **Fin de garantie**, sélectionnez les dates de début et de fin.</span><span class="sxs-lookup"><span data-stu-id="65c19-113">In the **Warranty start** and **Warranty end** fields, select the start and end dates.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="65c19-114">Si une date est sélectionnée dans le champ **Début de garantie** sur un ordre de travail, l’assurance devient valide pour l’ordre de travail à cette date.</span><span class="sxs-lookup"><span data-stu-id="65c19-114">If a date is selected in the **Warranty start** field on a work order, the warranty becomes valid for the work order on that date.</span></span> <span data-ttu-id="65c19-115">Lorsque vous créez un ordre de travail, le champ **Début de garantie** est automatiquement défini à la date de création.</span><span class="sxs-lookup"><span data-stu-id="65c19-115">When you create a work order, the **Warranty start** field is automatically set to the date of creation.</span></span> <span data-ttu-id="65c19-116">Toutefois, vous pouvez modifier la date afin qu’elle corresponde, par exemple, à la date de début d’un contrat de garantie.</span><span class="sxs-lookup"><span data-stu-id="65c19-116">However, you can change the date so that it corresponds to, for example, the start date of a warranty agreement.</span></span>
    >
    > ![Page Ordre de travail](media/02-warranty.png)

> [!NOTE]
> <span data-ttu-id="65c19-118">Lorsque vous créez un ordre de travail pour un actif couvert par une garantie fournisseur, si l’ordre de travail a une date de début prévue pendant la période de garantie, vous recevez une notification concernant le contrat de garantie.</span><span class="sxs-lookup"><span data-stu-id="65c19-118">When you create a work order for an asset that is covered by a vendor warranty, if the work order has an expected start date during the warranty period, you receive a notification about the warranty agreement.</span></span> <span data-ttu-id="65c19-119">Vous pouvez ensuite annuler l’ordre de travail, si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="65c19-119">You can then cancel the work order, as you require.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]