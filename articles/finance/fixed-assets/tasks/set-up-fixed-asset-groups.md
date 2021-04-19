---
title: Paramétrer les groupes d’immobilisations
description: Cette rubrique explique comment créer un groupe d’immobilisations.
author: saraschi2
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c1b97193f09cfbb943522ca7af6bace9a14d9cf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819552"
---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="1fb55-103">Paramétrer les groupes d’immobilisations</span><span class="sxs-lookup"><span data-stu-id="1fb55-103">Set up fixed asset groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1fb55-104">Cette rubrique explique comment créer un groupe d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="1fb55-104">This topic explains how to create a new fixed asset group.</span></span> <span data-ttu-id="1fb55-105">Il utilise le rôle de comptable et les données de démonstration de l’entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="1fb55-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="1fb55-106">Dans le volet de navigation, accédez à **Modules > Immobilisations > Paramétrage > Groupes d’immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="1fb55-106">In the navigation pane, go to **Modules > Fixed assets > Setup > Fixed asset groups**.</span></span>
2. <span data-ttu-id="1fb55-107">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1fb55-107">Select **New**.</span></span>
3. <span data-ttu-id="1fb55-108">Tapez une valeur dans le champ **Groupe d’immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="1fb55-108">In the **Fixed asset group** field, type a value.</span></span>
4. <span data-ttu-id="1fb55-109">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="1fb55-109">In the **Name** field, type a value.</span></span> <span data-ttu-id="1fb55-110">Les options Numéroter automatiquement les immobilisations et Code souche de numéros du groupe **d’immobilisations** remplaceront les paramètres des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="1fb55-110">Autonumber fixed assets and Number sequence code on the **Fixed asset** group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="1fb55-111">Vous pouvez les modifier ici si les actifs de ce groupe d’immobilisations ont une numérotation différente des autres groupes.</span><span class="sxs-lookup"><span data-stu-id="1fb55-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="1fb55-112">Sélectionnez **Registres**.</span><span class="sxs-lookup"><span data-stu-id="1fb55-112">Select **Books**.</span></span>
6. <span data-ttu-id="1fb55-113">Dans le champ **Registre**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1fb55-113">In the **Book** field, enter or select a value.</span></span> <span data-ttu-id="1fb55-114">Le champ **Calculer amortissement** est défini sur **Oui**, le registre d’actifs sera donc inclus dans les propositions d’amortissement.</span><span class="sxs-lookup"><span data-stu-id="1fb55-114">The **Calculate depreciation** field is set to **Yes**, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="1fb55-115">Si le champ **Calculer l’amortissement** est défini sur **Non**, l’actif n’est pas automatiquement amorti.</span><span class="sxs-lookup"><span data-stu-id="1fb55-115">If **Calculate depreciation** is set to **No**, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="1fb55-116">Définissez la durée de vie de l’immobilisation en années.</span><span class="sxs-lookup"><span data-stu-id="1fb55-116">Set the Service life of the asset, in years.</span></span> <span data-ttu-id="1fb55-117">Notez que la valeur du champ **Périodes d’amortissement** est calculée après la définition de la durée de vie.</span><span class="sxs-lookup"><span data-stu-id="1fb55-117">Note that the **Depreciation periods** field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="1fb55-118">Sélectionnez une option dans le champ **Convention d’amortissement**.</span><span class="sxs-lookup"><span data-stu-id="1fb55-118">In the **Depreciation convention** field, select an option.</span></span>
9. <span data-ttu-id="1fb55-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1fb55-119">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]