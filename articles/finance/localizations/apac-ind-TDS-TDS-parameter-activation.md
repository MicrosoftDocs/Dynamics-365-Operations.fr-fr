---
title: Définir des paramètres TDS
description: Cette rubrique explique comment définir des paramètres pour activer la fonctionnalité de taxe déduite à la source (TDS) dans des transactions spécifiées. Il s'agit d'une étape nécessaire pour utiliser la fonction Taxe déduite à la Source (TDS).
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
ms.openlocfilehash: dda276b7d634317aae26728f7d9f51af9ccfb896
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023236"
---
# <a name="set-the-tds-parameters"></a><span data-ttu-id="c4a32-104">Définir des paramètres TDS</span><span class="sxs-lookup"><span data-stu-id="c4a32-104">Set the TDS parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4a32-105">Cette rubrique explique comment définir des paramètres pour activer la fonctionnalité de taxe déduite à la source (TDS) dans des transactions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="c4a32-105">This topic explains how to set parameters to activate Tax Deducted at Source (TDS) functionality in specified transactions.</span></span> <span data-ttu-id="c4a32-106">Il s'agit d'une étape nécessaire pour utiliser la fonction Taxe déduite à la Source (TDS).</span><span class="sxs-lookup"><span data-stu-id="c4a32-106">This is a necessary step to use the Tax Deducted at Source TDS feature.</span></span>

1. <span data-ttu-id="c4a32-107">Accédez à **Comptabilité \> Paramétrage de la comptabilité \> Paramètres de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="c4a32-107">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="c4a32-108">Dans l'onglet **Impôts directs**, dans la section **Impôt déduit à la source**, définissez l'option **Activer TDS** sur **Oui** pour activer la fonctionnalité TDS, ainsi que les pages et les champs qui y sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="c4a32-108">On the **Direct taxes** tab, in the **Tax Deducted at Source** section, set the **Activate TDS** option to **Yes** to activate the TDS functionality, and the pages and fields that are used for it.</span></span>
3. <span data-ttu-id="c4a32-109">Définit l'option **Facturer** sur **Oui** pour activer les champs utilisés pour calculer et déduire TDS au niveau de la facture.</span><span class="sxs-lookup"><span data-stu-id="c4a32-109">Set the **Invoice** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the invoice level.</span></span>
4. <span data-ttu-id="c4a32-110">Définissez l'option **Paiement** sur **Oui** pour activer les champs utilisés pour calculer et déduire TDS au niveau de la facture.</span><span class="sxs-lookup"><span data-stu-id="c4a32-110">Set the **Payment** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the payment level.</span></span>

    <span data-ttu-id="c4a32-111">[![Onglet Taxes directes](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span><span class="sxs-lookup"><span data-stu-id="c4a32-111">[![Direct taxes tab](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span></span>

5. <span data-ttu-id="c4a32-112">Dans l'onglet **Souches de numéros**, recherchez la ligne où le champ **Référence** est défini sur **Paiement de la retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="c4a32-112">On the **Number sequences** tab, find the row where the **Reference** field is set to **Withholding tax payment**.</span></span> <span data-ttu-id="c4a32-113">Dans le champ **Code souche de N°** pour la ligne, sélectionnez le code souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="c4a32-113">In the **Number sequence code** field for the row, select the number sequence code.</span></span> <span data-ttu-id="c4a32-114">Le code de souche de numéros est utilisé pour générer des numéros de pièce justificative pour le processus de règlement TDS périodique.</span><span class="sxs-lookup"><span data-stu-id="c4a32-114">The number sequence code is used to generate voucher numbers for the periodic TDS settlement process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c4a32-115">Pour exécuter le processus de règlement TDS périodique, accédez à **Impôt \> Déclarations \> Retenue à la source \> Paiement de la retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="c4a32-115">To run the periodic TDS settlement process, go to **Tax \> Declarations \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="c4a32-116">[![Onglet Souches de numéros](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span><span class="sxs-lookup"><span data-stu-id="c4a32-116">[![Number sequences tab](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span></span>

6. <span data-ttu-id="c4a32-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c4a32-117">Close the page.</span></span>
