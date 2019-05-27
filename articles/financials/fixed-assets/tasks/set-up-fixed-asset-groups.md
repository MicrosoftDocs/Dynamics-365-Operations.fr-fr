---
title: Paramétrer les groupes d'immobilisations
description: Cette procédure permet d'indiquer comment créer un groupe d'immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 48784ef4eb12a4a1cae3387e3a45afdf34f2a0fd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546430"
---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="0908d-103">Paramétrer les groupes d'immobilisations</span><span class="sxs-lookup"><span data-stu-id="0908d-103">Set up fixed asset groups</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0908d-104">Cette procédure permet d'indiquer comment créer un groupe d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="0908d-104">This procedure shows how to create a new fixed asset group.</span></span> <span data-ttu-id="0908d-105">Il utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="0908d-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="0908d-106">Accédez à Immobilisations > Paramétrage > Groupes d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="0908d-106">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="0908d-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0908d-107">Click New.</span></span>
3. <span data-ttu-id="0908d-108">Tapez une valeur dans le champ Groupe d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="0908d-108">In the Fixed asset group field, type a value.</span></span>
4. <span data-ttu-id="0908d-109">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="0908d-109">In the Name field, type a value.</span></span>
    * <span data-ttu-id="0908d-110">Les options Numéroter automatiquement les immobilisations et Code souche de numéros du groupe d'immobilisations remplaceront les paramètres des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="0908d-110">Autonumber fixed assets and Number sequence code on the Fixed asset group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="0908d-111">Vous pouvez les modifier ici si les actifs de ce groupe d'immobilisations ont une numérotation différente des autres groupes.</span><span class="sxs-lookup"><span data-stu-id="0908d-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="0908d-112">Cliquez sur Registres.</span><span class="sxs-lookup"><span data-stu-id="0908d-112">Click Books.</span></span>
6. <span data-ttu-id="0908d-113">Dans le champ Registre, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0908d-113">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="0908d-114">Le champ Calculer amortissement est défini sur Oui, le registre d'actifs sera donc inclus dans les propositions d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="0908d-114">The Calculate depreciation field is set to Yes, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="0908d-115">Si le champ Calculer l'amortissement est défini sur Non, l'actif n'est pas automatiquement amorti.</span><span class="sxs-lookup"><span data-stu-id="0908d-115">If Calculate depreciation is set to No, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="0908d-116">Définissez la durée de vie de l'immobilisation en années.</span><span class="sxs-lookup"><span data-stu-id="0908d-116">Set the Service life of the asset, in years.</span></span>
    * <span data-ttu-id="0908d-117">Notez que la valeur du champ Périodes d'amortissement est calculée après la définition de la durée de vie.</span><span class="sxs-lookup"><span data-stu-id="0908d-117">Note that the Depreciation periods field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="0908d-118">Sélectionnez une option dans le champ Convention d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="0908d-118">In the Depreciation convention field, select an option.</span></span>
9. <span data-ttu-id="0908d-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0908d-119">Close the page.</span></span>

