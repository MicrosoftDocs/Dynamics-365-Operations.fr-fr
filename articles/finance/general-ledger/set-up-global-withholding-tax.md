---
title: Paramétrer la retenue à la source globale
description: Cette rubrique répertorie les étapes de paramétrage de la retenue à la source globale pour les ventes et les achats.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
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
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7ee577651694f0553447d6e9d0851402a586f363
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060735"
---
# <a name="set-up-global-withholding-tax"></a><span data-ttu-id="454f1-103">Paramétrer la retenue à la source globale</span><span class="sxs-lookup"><span data-stu-id="454f1-103">Set up global withholding tax</span></span>

<span data-ttu-id="454f1-104">Cette rubrique répertorie les étapes de paramétrage de la retenue à la source globale pour les ventes et les achats.</span><span class="sxs-lookup"><span data-stu-id="454f1-104">This topic lists the steps for setting up global withholding tax for sales and purchases.</span></span> 

1. <span data-ttu-id="454f1-105">Paramétrez les administrations de retenue à la source sur la page **Administrations fiscales**.</span><span class="sxs-lookup"><span data-stu-id="454f1-105">Set up withholding tax authorities on the **Withholding tax authorities** page.</span></span>

2. <span data-ttu-id="454f1-106">Paramétrez les périodes de règlement de retenue à la source sur la page **Périodes de règlement de la retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="454f1-106">Set up withholding settlement periods on the **Withholding tax settlement periods** page.</span></span>

3. <span data-ttu-id="454f1-107">Paramétrez des groupes de validation dans la comptabilité pour les retenues à la source sur la page **Retenue à la source > groupe de validation dans la comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="454f1-107">Set up withholding ledger posting group on the **Withholding tax > ledger posting group** page.</span></span>

   > [!Note] 
   >
   > <span data-ttu-id="454f1-108">Le compte **Retenue à la source** sera attribué avec un compte principal et un **Type de validation** « Retenue à la source ».</span><span class="sxs-lookup"><span data-stu-id="454f1-108">**Withholding tax** account will be assigned with a main account with **Posting type** of Withholding tax.</span></span> <span data-ttu-id="454f1-109">Le compte **Compensation de la retenue à la source** sera également attribué avec un compte principal et un **Type de validation** « Compensation de la retenue à la source ».</span><span class="sxs-lookup"><span data-stu-id="454f1-109">**Withholding tax offset** account will also be assigned with a main account with **Posting type** "Withholding tax offset".</span></span> <span data-ttu-id="454f1-110">Allez dans **Comptabilité > Plan comptable > Comptes > Comptes principaux**, définissez le **Type de validation** dans le sous-formulaire **Contrôle de validation** pour les comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="454f1-110">Go to **General ledger > Chart of accounts > Accounts > Main accounts**, set up the **Posting type** in the **Posting validation** sub-form for the main accounts.</span></span>

4. <span data-ttu-id="454f1-111">Paramétrez les codes de retenue à la source sur la page **Codes de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="454f1-111">Set up withholding tax codes on the **Withholding tax codes** page.</span></span>

5. <span data-ttu-id="454f1-112">Paramétrez les groupes de retenue à la source sur la page **Groupes de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="454f1-112">Set up withholding tax groups on the **Withholding tax groups** page.</span></span>

6. <span data-ttu-id="454f1-113">Configurez les types de produits des retenues à la source sur la page **Produits des retenues à la source** **types**.</span><span class="sxs-lookup"><span data-stu-id="454f1-113">Set up withholding tax revenue types on the **Withholding tax revenue** **types** page.</span></span>

7. <span data-ttu-id="454f1-114">Paramétrez les groupes de retenue à la source sur la page **Groupes de retenues à la source d'articles** pour un article ou un service.</span><span class="sxs-lookup"><span data-stu-id="454f1-114">Set up withholding tax groups on the **Item withholding tax groups** page for an item or service.</span></span>

8. <span data-ttu-id="454f1-115">Paramétrez **Montant de facture minimal** sur la page **Paramètres de comptabilité > Retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="454f1-115">Set up **Minimum invoice amount** on the **General ledger parameters > Withholding tax** page.</span></span>
