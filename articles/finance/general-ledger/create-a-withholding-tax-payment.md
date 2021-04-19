---
title: Créer un paiement de retenue à la source
description: La procédure de la tâche de paiement de retenue à la source permet de régler les soldes de retenue à la source de la Comptabilité fournisseur dans les comptes de retenue à la source et de les compenser dans le compte de retenue à la source pour une période donnée. Cette rubrique répertorie les étapes de configuration d’un paiement de retenue à la source.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 72d80fbb3b2448f4b89fa7d7fa580387e1a3621c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832944"
---
# <a name="create-a-withholding-tax-payment"></a><span data-ttu-id="fb682-104">Créer un paiement de retenue à la source</span><span class="sxs-lookup"><span data-stu-id="fb682-104">Create a withholding tax payment</span></span>

<span data-ttu-id="fb682-105">La procédure de la tâche de paiement de retenue à la source permet de régler les soldes de retenue à la source de la Comptabilité fournisseur dans les comptes de retenue à la source et de les compenser dans le compte de retenue à la source pour une période donnée.</span><span class="sxs-lookup"><span data-stu-id="fb682-105">The Withholding tax payment job procedure settles withholding tax balances from Accounts payable on withholding tax accounts, and offsets them to the withholding tax settlement account for a given period.</span></span> <span data-ttu-id="fb682-106">Cette rubrique répertorie les étapes de configuration d’un paiement de retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="fb682-106">This topic lists the steps for setting up a withholding tax payment.</span></span>

> [!NOTE] 
> <span data-ttu-id="fb682-107">La compensation de la retenue à la source (de la Comptabilité client) n’est pas prise en compte lors du calcul d’un paiement de retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="fb682-107">Withholding tax offset (from accounts receivable) is not taken into account when a withholding tax payment is calculated.</span></span>

1. <span data-ttu-id="fb682-108">Allez dans **Volet de navigation > Modules > Taxe > Déclarations > Retenue à la source > Paiement de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="fb682-108">Go to **Navigation pane > Modules > Tax > Declarations > Withholding tax > Withholding tax payment**.</span></span>
2. <span data-ttu-id="fb682-109">Dans le champ **Période de règlement**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fb682-109">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="fb682-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fb682-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="fb682-111">Entrez une date dans le champ **Date de début**.</span><span class="sxs-lookup"><span data-stu-id="fb682-111">In the **From date** field, enter a date.</span></span>
5. <span data-ttu-id="fb682-112">Entrez une date dans le champ **Date de transaction**.</span><span class="sxs-lookup"><span data-stu-id="fb682-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="fb682-113">Sélectionnez **Mettre à jour** pour imputer le justificatif de paiement de la retenue à la source sur le compte de règlement de la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="fb682-113">Select **Update** to post withholding tax payment voucher to the withholding tax settlement account.</span></span>
7. <span data-ttu-id="fb682-114">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb682-114">Click **OK**.</span></span>

![Paramètres de paiement de la retenue à la source](media/withholding-tax-payment.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]