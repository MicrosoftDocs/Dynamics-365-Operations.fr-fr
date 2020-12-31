---
title: Imprimer l’état de déclaration de taxe par code
description: Cette rubrique fournit des informations sur les paramètres et les actions nécessaires pour imprimer l’état de déclaration de taxe par code dans la devise du code comptable ou fiscal.
author: anasyash
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 7033999f7258e9ddd1d01620f9ad416e94ef3111
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443182"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a><span data-ttu-id="5b025-103">Imprimer l’état de déclaration de taxe par code</span><span class="sxs-lookup"><span data-stu-id="5b025-103">Print the Sales tax payment by code report</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b025-104">Pour imprimer l’état **Déclaration de taxe par code**, accédez à **Taxe** \> **Recherches et états** \> **Déclarations de taxe** \> **Déclaration de taxe par code**.</span><span class="sxs-lookup"><span data-stu-id="5b025-104">To print the **Sales tax payment by code** report, go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span> <span data-ttu-id="5b025-105">Par défaut, les montants prédéfinis sont générés dans la devise comptable de l’entité juridique pour tous les codes de déclaration configurés sur la page **Codes déclaration de taxe**.</span><span class="sxs-lookup"><span data-stu-id="5b025-105">By default, report amounts are generated in the accounting currency of the legal entity for all reporting codes that are set up on the **Sales tax reporting codes** page.</span></span>

<span data-ttu-id="5b025-106">Vous pouvez également générer ce rapport afin qu’il affiche les montants de paiement de la taxe de vente dans les devises des codes de taxe de vente pour tous les codes de déclaration affectés aux codes de taxe de vente sur la page **Codes taxe**.</span><span class="sxs-lookup"><span data-stu-id="5b025-106">You can also generate this report so that it shows the sales tax payment amounts in the currencies of sales tax codes for all reporting codes that are assigned to sales tax codes on the **Sales tax codes** page.</span></span>

## <a name="turn-on-the-feature"></a><span data-ttu-id="5b025-107">Activer la fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="5b025-107">Turn on the feature</span></span>

<span data-ttu-id="5b025-108">Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonction suivante : **Générer l’état Déclaration de taxe par code dans la devise du code taxe**.</span><span class="sxs-lookup"><span data-stu-id="5b025-108">In the **Feature management** workspace, turn on the following feature: **Generate the Sales tax payment by code report in the sales tax code currency**.</span></span>

## <a name="run-the-report"></a><span data-ttu-id="5b025-109">Exécuter le rapport</span><span class="sxs-lookup"><span data-stu-id="5b025-109">Run the report</span></span>

1. <span data-ttu-id="5b025-110">Accédez à **Taxe** \> **Recherches et états** \> **États de taxe** \> **Paiement de taxe par code**.</span><span class="sxs-lookup"><span data-stu-id="5b025-110">Go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span>
2. <span data-ttu-id="5b025-111">Dans le champ **Devise du rapport**, sélectionnez l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="5b025-111">In the **Report currency** field, select one of the following values:</span></span>

    - <span data-ttu-id="5b025-112">**Devise comptable** - Imprimez les montants du rapport dans la devise comptable.</span><span class="sxs-lookup"><span data-stu-id="5b025-112">**Accounting currency** – Print the report amounts in the accounting currency.</span></span>
    - <span data-ttu-id="5b025-113">**Devise du code taxe** - Imprimer les montants du rapport dans les devises des codes taxe.</span><span class="sxs-lookup"><span data-stu-id="5b025-113">**Sales tax code currency** – Print the report amounts in the currencies of sales tax codes.</span></span>

    ![Boîte de dialogue Déclaration de taxe par code](media/Sales-tax-payment-by-code.png)

<span data-ttu-id="5b025-115">L’illustration suivante présente un exemple de l’état généré.</span><span class="sxs-lookup"><span data-stu-id="5b025-115">The following illustration shows an example of the report that is generated.</span></span> <span data-ttu-id="5b025-116">Le rapport montre que le code de déclaration de taxe **101** a la devise **EUR** si le champ **Devise de la taxe** est défini sur **EUR** pour le code taxe auquel le code de déclaration est affecté.</span><span class="sxs-lookup"><span data-stu-id="5b025-116">The report shows that reporting code **101** has the **EUR** currency if the **Sales tax currency** field is set to **EUR** for the sales tax code that the reporting code is assigned to.</span></span>

![Exemple de l’état de déclaration de taxe par code](media/Sales-tax-payment-by-code-2.png)
