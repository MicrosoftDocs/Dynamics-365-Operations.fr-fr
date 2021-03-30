---
title: Gérer la validation d’un compte IBAN (Numéro de compte bancaire international)
description: Cette rubrique explique comment gérer la validation d’un compte IBAN (Numéro de compte bancaire international).
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: f3e7376827a42034e68cb0ee492b82f7274930ea
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253985"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a><span data-ttu-id="8284b-103">Gérer la validation d’un compte IBAN (Numéro de compte bancaire international)</span><span class="sxs-lookup"><span data-stu-id="8284b-103">Manage International Bank Account Number (IBAN) account validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8284b-104">La validation d’un IBAN (Numéro de compte bancaire international) augmente le niveau de validation lorsque vous ajoutez un IBAN à un compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="8284b-104">International Bank Account Number (IBAN) validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="8284b-105">Les informations sur la structure IBAN sont enregistrées dans Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="8284b-105">Information about the structure of the IBAN is stored in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="8284b-106">Ces informations sont chargées automatiquement lorsque vous utilisez pour la première fois l’IBAN sur les comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="8284b-106">That information is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="8284b-107">Elles contiennent la longueur de l’IBAN, les positions de départ du numéro de compte bancaire et du numéro d’acheminement, et la longueur du numéro de compte bancaire et du numéro d’acheminement.</span><span class="sxs-lookup"><span data-stu-id="8284b-107">It contains the length of the IBAN, the starting positions of the bank account number and the routing number, and the length of the bank account number and routing number.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="8284b-108">Paramétrer les structures IBAN</span><span class="sxs-lookup"><span data-stu-id="8284b-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="8284b-109">Accédez à **Gestion de la trésorerie et de la banque \> Paramétrage \> Structures IBAN**.</span><span class="sxs-lookup"><span data-stu-id="8284b-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="8284b-110">Notez que les structures IBAN pour chaque pays ou région ont été paramétrées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="8284b-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="8284b-111">Si vous souhaitez personnaliser les structures pour un pays ou une région spécifique, vous pouvez les modifier.</span><span class="sxs-lookup"><span data-stu-id="8284b-111">If you want to customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="8284b-112">Les définitions de structure feront partie de chaque nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="8284b-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="8284b-113">Vous pouvez utiliser le menu **Réinitialiser les structures** pour charger les dernières définitions après chaque mise à jour.</span><span class="sxs-lookup"><span data-stu-id="8284b-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="8284b-114">Valider la structure IBAN d’un compte bancaire</span><span class="sxs-lookup"><span data-stu-id="8284b-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="8284b-115">Accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**.</span><span class="sxs-lookup"><span data-stu-id="8284b-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="8284b-116">Créez un compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="8284b-116">Create a bank account.</span></span>
3. <span data-ttu-id="8284b-117">Dans l’organisateur **Informations supplémentaires**, entrez un IBAN.</span><span class="sxs-lookup"><span data-stu-id="8284b-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="8284b-118">Si la longueur de l’IBAN ne correspond pas à la longueur définie pour chaque pays ou région, vous recevrez un message d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="8284b-118">If the length of the IBAN doesn't match the length that is defined for each country or region, you will receive a warning message.</span></span> <span data-ttu-id="8284b-119">Vous ne pouvez pas continuer si la longueur de l’IBAN ne correspond pas à celle spécifiée dans la structure IBAN.</span><span class="sxs-lookup"><span data-stu-id="8284b-119">You can't continue if the length of the IBAN doesn't match the length specified in the IBAN structure.</span></span>

    <span data-ttu-id="8284b-120">La validation vérifie également que le numéro de compte bancaire correspond à la partie de l’IBAN qui représente le numéro de compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="8284b-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="8284b-121">Si le numéro de compte bancaire ne correspond pas, vous recevrez un message d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="8284b-121">If the bank account number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="8284b-122">Ce message n’est qu’un avertissement.</span><span class="sxs-lookup"><span data-stu-id="8284b-122">This message is only a warning.</span></span> <span data-ttu-id="8284b-123">Vous pouvez continuer même si le numéro de compte bancaire ne correspond pas.</span><span class="sxs-lookup"><span data-stu-id="8284b-123">You can continue even if the bank account number doesn't match.</span></span>

    <span data-ttu-id="8284b-124">La validation vérifie également que le numéro d’acheminement correspond à la partie de l’IBAN qui représente le numéro d’acheminement.</span><span class="sxs-lookup"><span data-stu-id="8284b-124">The validation also verifies that the bank routing number matches the part of the IBAN that represents the bank routing number.</span></span> <span data-ttu-id="8284b-125">Le numéro d’acheminement contient un numéro bancaire et souvent une agence bancaire supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="8284b-125">The routing number includes a bank number and often an additional bank branch.</span></span> <span data-ttu-id="8284b-126">Si le numéro d’acheminement bancaire ne correspond pas, vous recevrez un message d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="8284b-126">If the bank routing number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="8284b-127">Ce message n’est qu’un avertissement.</span><span class="sxs-lookup"><span data-stu-id="8284b-127">This message is only a warning.</span></span> <span data-ttu-id="8284b-128">Vous pouvez continuer même si le numéro d’acheminement bancaire ne correspond pas.</span><span class="sxs-lookup"><span data-stu-id="8284b-128">You can continue even if the bank routing number doesn't match.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]