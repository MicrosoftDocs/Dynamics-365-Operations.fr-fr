---
title: "Gérer la validation d'un compte IBAN (Numéro de compte bancaire international)"
description: "Cette rubrique explique comment gérer la validation d'un compte IBAN (Numéro de compte bancaire international)."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e091aab70a98e0f4b96c41c1ee48926947539105
ms.contentlocale: fr-fr
ms.lasthandoff: 08/31/2018

---

# <a name="manage-international-bank-account-number-iban-account-validation"></a><span data-ttu-id="58af7-103">Gérer la validation d'un compte IBAN (Numéro de compte bancaire international)</span><span class="sxs-lookup"><span data-stu-id="58af7-103">Manage International Bank Account Number (IBAN) account validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58af7-104">La validation d'un compte IBAN (Numéro de compte bancaire international) augmente le niveau de validation lorsque vous ajoutez un IBAN à un compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="58af7-104">International Bank Account Number (IBAN) account validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="58af7-105">La structure de l'IBAN est enregistrée dans Microsoft Dynamics 365 for Finance and Operations, et est automatiquement chargée lorsque vous utilisez pour la première fois l'IBAN dans des comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="58af7-105">The structure of the IBAN is stored in Microsoft Dynamics 365 for Finance and Operation, and is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="58af7-106">Le numéro de compte bancaire fait partie de la structure définie pour un numéro IBAN.</span><span class="sxs-lookup"><span data-stu-id="58af7-106">The bank account number is part of the structure defined for an IBAN number.</span></span> <span data-ttu-id="58af7-107">Selon cette structure, si la position et la longueur du numéro de compte dans l'IBAN ne correspondent pas à la position définie dans la structure pour chaque pays ou région, vous recevrez des messages d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="58af7-107">Based on that structure, if the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you will receive warning messages.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="58af7-108">Paramétrer les structures IBAN</span><span class="sxs-lookup"><span data-stu-id="58af7-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="58af7-109">Accédez à **Gestion de la trésorerie et de la banque \> Paramétrage \> Structures IBAN**.</span><span class="sxs-lookup"><span data-stu-id="58af7-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="58af7-110">Notez que les structures IBAN pour chaque pays ou région ont été paramétrées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="58af7-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="58af7-111">Si vous devez personnaliser les structures pour un pays ou une région spécifique, vous pouvez les modifier.</span><span class="sxs-lookup"><span data-stu-id="58af7-111">If you must customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="58af7-112">Les définitions de structure feront partie de chaque nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="58af7-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="58af7-113">Vous pouvez utiliser le menu **Réinitialiser les structures** pour charger les dernières définitions après chaque mise à jour.</span><span class="sxs-lookup"><span data-stu-id="58af7-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="58af7-114">Valider la structure IBAN d'un compte bancaire</span><span class="sxs-lookup"><span data-stu-id="58af7-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="58af7-115">Accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**.</span><span class="sxs-lookup"><span data-stu-id="58af7-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="58af7-116">Créez un compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="58af7-116">Create a bank account.</span></span>
3. <span data-ttu-id="58af7-117">Dans l'organisateur **Informations supplémentaires**, entrez un IBAN.</span><span class="sxs-lookup"><span data-stu-id="58af7-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="58af7-118">Si la position et la longueur du numéro de compte dans l'IBAN ne correspondent pas à la position définie dans la structure pour chaque pays ou région, vous recevez un message.</span><span class="sxs-lookup"><span data-stu-id="58af7-118">If the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you receive a message.</span></span> <span data-ttu-id="58af7-119">Vous ne pouvez pas continuer si la longueur de l'IBAN ne correspond pas à celle de la structure IBAN.</span><span class="sxs-lookup"><span data-stu-id="58af7-119">You can't continue if the length of the IBAN doesn't match the length in the IBAN structure.</span></span>

    <span data-ttu-id="58af7-120">La validation vérifie également que le numéro de compte bancaire correspond à la partie de l'IBAN qui représente le numéro de compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="58af7-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="58af7-121">Si le numéro de compte bancaire ne correspond pas, vous recevez un message d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="58af7-121">If the bank account number doesn't match, you receive a warning message.</span></span> <span data-ttu-id="58af7-122">Ce message n'est qu'un avertissement.</span><span class="sxs-lookup"><span data-stu-id="58af7-122">This message is only a warning.</span></span> <span data-ttu-id="58af7-123">Vous pouvez continuer même si le numéro de compte bancaire ne correspond pas.</span><span class="sxs-lookup"><span data-stu-id="58af7-123">You can continue even if the bank account number doesn't match.</span></span>

