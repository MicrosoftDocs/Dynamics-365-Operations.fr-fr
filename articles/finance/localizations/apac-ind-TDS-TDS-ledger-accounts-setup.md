---
title: Paramétrer les comptes généraux TDS
description: Cette rubrique explique comment configurer des comptes généraux pour la fonction Taxe déduite à la source (TDS).
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
ms.openlocfilehash: 93d4cb54488ec0eeee40ca56f3e46f30012f54f5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023237"
---
# <a name="set-up-tds-ledger-accounts"></a><span data-ttu-id="76a1f-103">Paramétrer les comptes généraux TDS</span><span class="sxs-lookup"><span data-stu-id="76a1f-103">Set up TDS ledger accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="76a1f-104">Cette rubrique explique comment configurer des comptes généraux pour la fonction Taxe déduite à la source (TDS).</span><span class="sxs-lookup"><span data-stu-id="76a1f-104">This topic explains how to set up ledger accounts for the Tax Deducted at Source (TDS) feature.</span></span> <span data-ttu-id="76a1f-105">Utilisez la page **Plan comptable** pour configurer les comptes généraux pour TDS.</span><span class="sxs-lookup"><span data-stu-id="76a1f-105">You use the **Chart of accounts** page to set up ledger accounts for TDS.</span></span>

1. <span data-ttu-id="76a1f-106">Accédez à **Comptabilité \> Plan de comptes \> Comptes \> Comptes principaux**.</span><span class="sxs-lookup"><span data-stu-id="76a1f-106">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**.</span></span>
2. <span data-ttu-id="76a1f-107">Dans l'onglet **Aperçu**, sélectionnez **Alt+N** pour créer un compte général TDS et saisissez les détails requis.</span><span class="sxs-lookup"><span data-stu-id="76a1f-107">On the **Overview** tab, select **Alt+N** to create a TDS ledger account, and enter the required details.</span></span>
3. <span data-ttu-id="76a1f-108">Dans l'onglet **Paramétrer**, dans le champ **Type de validation**, sélectionnez **Retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="76a1f-108">On the **Setup** tab, in the **Posting type** field, select **Withholding tax**.</span></span>     

    > [!NOTE]
    > <span data-ttu-id="76a1f-109">Les comptes généraux dont le type de validation est **Retenue à la source** ne peuvent être définis que comme des comptes clients utilisés pour comptabiliser le montant des comptes clients TDS pour un code TVA TDS.</span><span class="sxs-lookup"><span data-stu-id="76a1f-109">Ledger accounts that have a posting type of **Withholding tax** can be defined only as receivable accounts that are used to post the TDS receivable amount for a TDS tax code.</span></span>

4. <span data-ttu-id="76a1f-110">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="76a1f-110">Close the page.</span></span>
