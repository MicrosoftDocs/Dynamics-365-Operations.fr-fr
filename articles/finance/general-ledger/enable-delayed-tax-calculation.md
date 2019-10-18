---
title: Activer un calcul de taxe différé sur le journal
description: Cette rubrique explique comment utiliser la fonctionnalité **Activer un calcul de taxe différé sur le journal** pour améliorer les performances du calcul de taxe lorsque le volume de lignes de journal est conséquent.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177684"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a><span data-ttu-id="e0a3c-103">Activer un calcul de taxe différé sur le journal</span><span class="sxs-lookup"><span data-stu-id="e0a3c-103">Enable delayed tax calculation on journal</span></span>
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="e0a3c-104">Cette rubrique explique comment utiliser la fonctionnalité **Activer un calcul de taxe différé sur le journal** pour améliorer les performances du calcul de taxe lorsque le volume de lignes de journal est conséquent.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-104">This topic explains how to use the **Enable delayed tax calculation on journal** feature to improve tax calculation performance when the volume of journal lines is huge.</span></span>

<span data-ttu-id="e0a3c-105">Le comportement actuel de calcul de la taxe sur le journal est déclenché en temps réel lorsque l'utilisateur met à jour les champs liés à la taxe, par exemple, le groupe de taxes/groupe de taxes d'article.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-105">Current sales tax calculation behavior on journal is real-time triggered when user updates tax related fields, e.g. sales tax group/item sales tax group.</span></span> <span data-ttu-id="e0a3c-106">Toute mise à jour au niveau de la ligne du journal recalculera le montant de la taxe sur toutes les lignes du journal.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-106">Any update at journal line level will re-calculate tax amount on all journal lines.</span></span> <span data-ttu-id="e0a3c-107">Elle permet à l'utilisateur de voir le montant de la taxe calculée en temps réel, mais pourrait également générer un problème de performance si le volume des lignes du journal est conséquent.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-107">It helps user to see real-time calculated tax amount but it could also bring performance issue if  the volume of journal lines is huge.</span></span>

<span data-ttu-id="e0a3c-108">Cette fonction offre une option de retard du calcul de la taxe pour résoudre le problème de performances.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-108">This feature provides an option to delay tax calculation to solve performance issue.</span></span> <span data-ttu-id="e0a3c-109">Si cette fonction est activée, le montant de la taxe est calculé uniquement lorsque l'utilisateur clique sur la commande « Taxe » ou valide le journal.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-109">If this feature is turned on, tax amount will only be calculated when user clicks "Sales Tax" command or posts the journal.</span></span>

<span data-ttu-id="e0a3c-110">L'utilisateur peut activer/désactiver le paramètre sur trois niveaux :</span><span class="sxs-lookup"><span data-stu-id="e0a3c-110">User can turn on/off the parameter at three levels:</span></span>
- <span data-ttu-id="e0a3c-111">Par entité juridique</span><span class="sxs-lookup"><span data-stu-id="e0a3c-111">By legal entity</span></span>
- <span data-ttu-id="e0a3c-112">Par nom de journal</span><span class="sxs-lookup"><span data-stu-id="e0a3c-112">By journal name</span></span>
- <span data-ttu-id="e0a3c-113">Par en-tête de journal</span><span class="sxs-lookup"><span data-stu-id="e0a3c-113">By journal header</span></span>

<span data-ttu-id="e0a3c-114">Le système considèrera la valeur de paramètre sur l'en-tête de journal comme valeur finale.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-114">System will take the parameter value on journal header as final.</span></span> <span data-ttu-id="e0a3c-115">La valeur du paramètre sur l'en-tête du journal sera par défaut le nom du journal.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-115">Parameter value on journal header will be defaulted from journal name.</span></span> <span data-ttu-id="e0a3c-116">La valeur du paramètre sous le nom de journal passera par défaut au paramètre de comptabilité lorsque le nom du journal est créé.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-116">Parameter value on journal name will be defaulted from general ledger parameter when the journal name is created.</span></span>

<span data-ttu-id="e0a3c-117">Les champs « Montant de taxe réel » et « Montant de taxe calculé » du journal seront masqués si ce paramètre est activé.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-117">"Actual sales tax amount" and "Calculated sales tax amount" fields on journal will be hided if this parameter is turned on.</span></span> <span data-ttu-id="e0a3c-118">L'objectif n'est pas de confondre l'utilisateur, car la valeur de ces deux champs indiquera toujours 0 avant que l'utilisateur ne déclenche le calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-118">The purpose is not to confuse user because the value of these two fields will always show 0 before user trigger the tax calculation.</span></span>

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a><span data-ttu-id="e0a3c-119">Activer le calcul de taxe différé par entité juridique</span><span class="sxs-lookup"><span data-stu-id="e0a3c-119">Enable delayed tax calculation by legal entity</span></span>

1. <span data-ttu-id="e0a3c-120">Accédez à **Comptabilité > Paramétrage de la comptabilité > Paramètres de comptabilité**</span><span class="sxs-lookup"><span data-stu-id="e0a3c-120">Go to **General ledger > Ledger setup > General ledger parameters**</span></span>
2. <span data-ttu-id="e0a3c-121">Cliquez sur l'onglet **Taxe**</span><span class="sxs-lookup"><span data-stu-id="e0a3c-121">Click **Sales tax** tab</span></span>
3. <span data-ttu-id="e0a3c-122">Sous l'organisateur **Général**, cherchez le paramètre **Calcul de taxe différé** et activez/désactivez-le.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-122">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a><span data-ttu-id="e0a3c-123">Activer un calcul de taxe différé par le nom du journal</span><span class="sxs-lookup"><span data-stu-id="e0a3c-123">Enable delayed tax calculation by journal name</span></span>

1. <span data-ttu-id="e0a3c-124">Accédez à **Comptabilité > Paramétrage du journal > Noms des journaux**</span><span class="sxs-lookup"><span data-stu-id="e0a3c-124">Go to **General ledger > Journal setup > Journal names**</span></span>
2. <span data-ttu-id="e0a3c-125">Sous l'organisateur **Général**, cherchez le paramètre **Calcul de taxe différé** et activez/désactivez-le.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-125">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a><span data-ttu-id="e0a3c-126">Activer un calcul de taxe différé par journal</span><span class="sxs-lookup"><span data-stu-id="e0a3c-126">Enable delayed tax calculation by journal</span></span>

1. <span data-ttu-id="e0a3c-127">Accédez à **Comptabilité > Entrées de journal > Journaux des opérations diverses**.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-127">Go to **General ledger > Journal entries > General journals**</span></span>
2. <span data-ttu-id="e0a3c-128">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-128">Click **New**</span></span>
3. <span data-ttu-id="e0a3c-129">Sélectionner un nom de journal</span><span class="sxs-lookup"><span data-stu-id="e0a3c-129">Select a journal name</span></span>
4. <span data-ttu-id="e0a3c-130">Cliquez sur **Paramétrage**</span><span class="sxs-lookup"><span data-stu-id="e0a3c-130">Click **Setup**</span></span>
5. <span data-ttu-id="e0a3c-131">Cherchez le paramètre **Calcul de taxe différé** et activez/désactivez-le.</span><span class="sxs-lookup"><span data-stu-id="e0a3c-131">Find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-header.png)
