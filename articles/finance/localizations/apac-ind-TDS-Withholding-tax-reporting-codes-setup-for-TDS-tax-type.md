---
title: Paramétrer les codes déclaration de retenue à la source pour le type de taxe TDS
description: Les codes déclaration de retenue à la source sont utilisés pour générer les déclarations des formulaires 26Q et 27Q pour l'impôt retenu à la source (TDS). Cette rubrique explique comment configurer les étapes des codes de déclaration de retenue à la source afin de pouvoir configurer les codes de déclaration TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1f9325d182f89b98e8b943ae047c55e7e1aeb02f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023248"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a><span data-ttu-id="35e00-104">Paramétrer les codes déclaration de retenue à la source pour le type de taxe TDS</span><span class="sxs-lookup"><span data-stu-id="35e00-104">Set up withholding tax reporting codes for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="35e00-105">Les codes déclaration de retenue à la source sont utilisés pour générer les déclarations des formulaires 26Q et 27Q pour l'impôt retenu à la source (TDS).</span><span class="sxs-lookup"><span data-stu-id="35e00-105">Withholding tax reporting codes are used to generate Form 26Q and Form 27Q statements for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="35e00-106">Cette rubrique explique comment configurer les étapes des codes de déclaration de retenue à la source afin de pouvoir configurer les codes de déclaration TDS.</span><span class="sxs-lookup"><span data-stu-id="35e00-106">This topic explains how to set up withholding tax reporting codes steps so that you can set up TDS reporting codes.</span></span>

1. <span data-ttu-id="35e00-107">Accédez à **Taxe \> Configuration \> Retenue à la source \> Codes déclaration de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="35e00-107">Go to **Tax \> Setup \> Withholding tax \> Withholding tax reporting codes**.</span></span>

    <span data-ttu-id="35e00-108">[![Page des codes déclaration de retenue à la source](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)</span><span class="sxs-lookup"><span data-stu-id="35e00-108">[![Withholding tax reporting codes page](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)</span></span>

2. <span data-ttu-id="35e00-109">Dans le champ **Type de taxe**, sélectionnez **TDS** pour définir des codes déclaration de retenue à la source pour le type de taxe TDS.</span><span class="sxs-lookup"><span data-stu-id="35e00-109">In the **Tax type** field, select **TDS** to define withholding tax reporting codes for the TDS tax type.</span></span>
3. <span data-ttu-id="35e00-110">Dans le champ **Composant de retenue à la source**, sélectionnez le composant TDS pour lequel vous définissez le code de déclaration de retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="35e00-110">In the **Withholding tax component** field, select the TDS component to that you're defining the withholding tax reporting code for.</span></span> <span data-ttu-id="35e00-111">Le champ **Groupe de composants de retenue à la source** affiche le groupe de composants TDS qui a été défini pour le composant TDS que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="35e00-111">The **Withholding tax component group** field shows the TDS component group that was defined for the TDS component that you're defining.</span></span>

    <span data-ttu-id="35e00-112">Le champ **Code de section** dans le raccourci **Général** affiche le code de section associé au groupe de composants TDS.</span><span class="sxs-lookup"><span data-stu-id="35e00-112">The **Section code** field on the **General** FastTab shows the section code that is attached to the TDS component group.</span></span>

4. <span data-ttu-id="35e00-113">Sur le raccourci **Général**, dans le champ **Code de déclaration**, sélectionnez le code de déclaration TDS :</span><span class="sxs-lookup"><span data-stu-id="35e00-113">On the **General** FastTab, in the **Reporting code** field, select the TDS reporting code:</span></span>

    - <span data-ttu-id="35e00-114">TDS</span><span class="sxs-lookup"><span data-stu-id="35e00-114">TDS</span></span>
    - <span data-ttu-id="35e00-115">TCS</span><span class="sxs-lookup"><span data-stu-id="35e00-115">TCS</span></span>
    - <span data-ttu-id="35e00-116">Surcharge</span><span class="sxs-lookup"><span data-stu-id="35e00-116">Surcharge</span></span>
    - <span data-ttu-id="35e00-117">PE\_Cess</span><span class="sxs-lookup"><span data-stu-id="35e00-117">PE\_Cess</span></span>
    - <span data-ttu-id="35e00-118">SHE\_Cess</span><span class="sxs-lookup"><span data-stu-id="35e00-118">SHE\_Cess</span></span>

5. <span data-ttu-id="35e00-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="35e00-119">Close the page.</span></span>
