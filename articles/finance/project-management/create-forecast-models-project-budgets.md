---
title: Création de modèles de prévision pour les budgets de projet
description: Cette rubrique décrit comment créer un modèle de prévision pour les budgets restants.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321777"
---
# <a name="create-forecast-models-for-project-budgets"></a><span data-ttu-id="e8ce0-103">Création de modèles de prévision pour les budgets de projet</span><span class="sxs-lookup"><span data-stu-id="e8ce0-103">Create forecast models for project budgets</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e8ce0-104">Cette rubrique décrit comment créer un modèle de prévision pour les budgets restants.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-104">This topic describes how to create a forecast model for remaining budgets.</span></span> <span data-ttu-id="e8ce0-105">Un projet soumis au contrôle budgétaire fait appel à deux types de budgets : le budget d'origine et le budget restant.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-105">A project that is subject to budget control uses two types of budgets: original and remaining.</span></span> <span data-ttu-id="e8ce0-106">Lorsque vous créez un budget de projet, vous devez spécifier les modèles de prévision du budget d'origine et du budget restant créés dans la page **Modèles de prévision**.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-106">When you create a project budget, you must specify the original and remaining budget forecast models that were created in the **Forecast models** page.</span></span> <span data-ttu-id="e8ce0-107">Les budgets de projet basés sur les modèles spécifiés sont créés lorsque vous approuvez le budget de projet.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-107">Project budgets based on the specified models are created when you commit the project budget.</span></span>

> [!NOTE]
> <span data-ttu-id="e8ce0-108">Un modèle de prévision utilisé pour le contrôle budgétaire ne peut pas disposer d'un sous-modèle et ne peut pas être utilisé en tant que sous-modèle.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-108">A forecast model that is used for budget control can’t have a submodel or be used as a submodel.</span></span>

1. <span data-ttu-id="e8ce0-109">Sélectionnez **Gestion de projet et comptabilité** > **Configuration** > **Prévisions**  > **Modèles de prévision**.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-109">Select **Project management and accounting** > **Setup** > **Forecasts**  > **Forecast models**.</span></span>
2. <span data-ttu-id="e8ce0-110">Sélectionnez **Nouveau** pour créer un modèle de prévision, puis entrez un ID modèle, ainsi qu'un nom pour le nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-110">Select **New** to create a new forecast model, and then enter a model ID number and name for the new model.</span></span> 
3. <span data-ttu-id="e8ce0-111">Définissez l'option **Arrêté** sur **Oui** pour empêcher toute modification des lignes de prévision du modèle de prévision.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-111">Set the **Stopped** option to **Yes** to prevent any changes to the forecast lines for the forecast model.</span></span> 
4. <span data-ttu-id="e8ce0-112">Si les lignes de prévision auxquelles le modèle est associé doivent générer des prévisions de flux de trésorerie dans la comptabilité, définissez **Inclure les budgets dans les prévisions de flux de trésorerie** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-112">If the forecast lines that the model is associated with should generate cash flow forecasts in the general ledger, set **Include in Cash flow forecasts** to **Yes.**</span></span> 
5. <span data-ttu-id="e8ce0-113">Pour utiliser la date du projet comme date de facture, définissez **Date prévisionnelle de facturation** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-113">To use the project date as the invoice date, set **Forecast Invoice date** to **Yes**.</span></span> 
6. <span data-ttu-id="e8ce0-114">Dans le champ **Type de budget**, sélectionnez l'un des types de modèles suivants :</span><span class="sxs-lookup"><span data-stu-id="e8ce0-114">In the **Budget type** field, select one of the following model types:</span></span>

   - <span data-ttu-id="e8ce0-115">**Budget d'origine** : Utilisez ce type de modèle pour les montants de budget d'origine engagés lors de la création et de l'approbation du budget initial.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-115">**Original budget**: Use the original budget amounts that are committed when the initial budget is created and approved.</span></span>
   - <span data-ttu-id="e8ce0-116">**Budget restant** : Utilisez ce type de modèle pour les montants de budget restant au cours du cycle de vie du projet.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-116">**Remaining budget**: Use the remaining budget amounts during the life of the project.</span></span> <span data-ttu-id="e8ce0-117">Les soldes de ce modèle de prévision sont réduits par les transactions réelles et augmentés ou diminués par les révisions de budget.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-117">The balances in this forecast model are reduced by actual transactions and increased or decreased by budget revisions.</span></span>
   - <span data-ttu-id="e8ce0-118">**Report de budget** : Utilisez ce type de modèle pour les montants de report de budget pour le projet.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-118">**Carry-forward**: Use the carry-forward budget amounts for the project.</span></span> <span data-ttu-id="e8ce0-119">Le report est un processus facultatif qui peut être exécuté pour transférer les montants de budget inutilisés d'un exercice à un autre.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-119">Carry-forward is an optional process that can be run to transfer unused budget amounts from one fiscal year to another.</span></span>

7. <span data-ttu-id="e8ce0-120">Définissez les options suivantes selon vos besoins :</span><span class="sxs-lookup"><span data-stu-id="e8ce0-120">Set the following options as required:</span></span>

   - <span data-ttu-id="e8ce0-121">Activez **Date prévisionnelle de facturation** pour utiliser la date du projet comme date de facture.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-121">Enable **Forecast invoice date** to use the project date as the invoice date.</span></span>
   - <span data-ttu-id="e8ce0-122">Activez **Prévision avec WIP** pour effectuer des prévisions en fonction des travaux en cours (WIP), puis sélectionnez le type de WIP.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-122">Enable **Forecast with WIP** to forecast based on work in progress (WIP), and then select the type of WIP.</span></span> 
   - <span data-ttu-id="e8ce0-123">Vous pouvez conserver la valeur par défaut **Type de budget** sur la valeur **Aucun**, ou entrez un nouveau type.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-123">You can keep the default **Budget type** as **None** or enter a new type.</span></span> <span data-ttu-id="e8ce0-124">Le type de budget ne peut pas être modifié après avoir modifié un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-124">The budget type can't be changed after you change a record.</span></span>     
    > [!NOTE]
    > <span data-ttu-id="e8ce0-125">Si vous modifiez le type de budget par défaut, toutes les autres options ne seront plus disponibles pour les mises à jour et vous ne pourrez pas réutiliser ce modèle de prévision.</span><span class="sxs-lookup"><span data-stu-id="e8ce0-125">If you change the default budget type, all other options will become unavailable for updates, and you can't reuse this forecast model.</span></span> 
   


 

