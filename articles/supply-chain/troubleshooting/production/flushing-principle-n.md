---
title: Les paramètres de principe d'effacement sur les lignes de nomenclature ne sont pas respectés
description: Les paramètres de principe d'effacement sur les lignes de nomenclature (BOM) ne sont pas respectés
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 84a84728016119a2a02f59f6903171afbceb48e7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026509"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a><span data-ttu-id="85885-103">Les paramètres de principe d'effacement sur les lignes de nomenclature ne sont pas respectés</span><span class="sxs-lookup"><span data-stu-id="85885-103">Flushing principle settings on BOM lines aren't respected</span></span>

<span data-ttu-id="85885-104">Numéro de la base de connaissances : 4612725</span><span class="sxs-lookup"><span data-stu-id="85885-104">KB number: 4612725</span></span>

## <a name="symptoms"></a><span data-ttu-id="85885-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="85885-105">Symptoms</span></span>

<span data-ttu-id="85885-106">Ce problème se produit lorsque le champ **Consommation de nomenclature automatique** dans l'onglet **Mise à jour automatique** de la page **Paramètres de contrôle de production** est définie sur *Principe d'effacement*.</span><span class="sxs-lookup"><span data-stu-id="85885-106">This issue occurs when the **Automatic BOM consumption** field on the **Automatic update** tab of the **Production control parameters** page is set to *Flushing principle*.</span></span> <span data-ttu-id="85885-107">Ce paramètre indique que toutes les lignes de nomenclature (BOM) doivent être automatiquement consommées lors de la réception d'une commande d'achat.</span><span class="sxs-lookup"><span data-stu-id="85885-107">This setting indicates that all bill of materials (BOM) lines should automatically be consumed when a purchase order is received.</span></span> <span data-ttu-id="85885-108">Si le champ **Principe d'effacement** sur les lignes de nomenclature est explicitement défini sur *Manuel*, vous pouvez vous attendre à ce que les lignes de nomenclature ne soient pas automatiquement consommées.</span><span class="sxs-lookup"><span data-stu-id="85885-108">If the **Flushing principle** field on BOM lines is explicitly set to *Manual*, you might expect that the BOM lines won't automatically be consumed.</span></span> <span data-ttu-id="85885-109">Toutefois, lorsque ce problème se produit, les lignes de nomenclature où le champ **Principe d'effacement** est défini sur *Manuel* sont automatiquement consommés de toute façon.</span><span class="sxs-lookup"><span data-stu-id="85885-109">However, when this issue occurs, BOM lines where the **Flushing principle** field is set to *Manual* are automatically consumed anyway.</span></span>

## <a name="resolution"></a><span data-ttu-id="85885-110">Résolution</span><span class="sxs-lookup"><span data-stu-id="85885-110">Resolution</span></span>

<span data-ttu-id="85885-111">Si vous rencontrez ce problème, vos paramètres de contrôle de production peuvent être configurés pour remplacer le paramètre **Principe d'effacement** sur les lignes de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="85885-111">If you're experiencing this issue, your production control parameters might be set up to override the **Flushing principle** setting on BOM lines.</span></span> <span data-ttu-id="85885-112">Sur la page **Paramètres de contrôle de production**, dans l'onglet **Mise à jour automatique**, vérifiez la valeur du champ **Consommation de nomenclature automatique**.</span><span class="sxs-lookup"><span data-stu-id="85885-112">On the **Production control parameters** page, on the **Automatic update** tab, check the value of the **Automatic BOM consumption** field.</span></span> <span data-ttu-id="85885-113">S'il est paramétré sur *Toujours*, le système ignorera le **Principe d'effacement** sur toutes les lignes de nomenclature et effacera toujours les lignes.</span><span class="sxs-lookup"><span data-stu-id="85885-113">If it's set to *Always*, the system will disregard the **Flushing principle** setting on all BOM lines and will always flush the lines.</span></span> <span data-ttu-id="85885-114">Pour que le système respecte le paramètre **Principe d'effacement** sur les lignes de nomenclature, modifiez la valeur du champ **Consommation de nomenclature automatique** sur *Principe d'effacement*.</span><span class="sxs-lookup"><span data-stu-id="85885-114">To make the system respect the **Flushing principle** setting on BOM lines, change the value of the **Automatic BOM consumption** field to *Flushing principle*.</span></span>
