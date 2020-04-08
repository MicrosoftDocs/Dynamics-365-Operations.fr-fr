---
title: Configurer le mode de paiement pour le débit direct ISO20022
description: Cette procédure indique comment paramétrer le mode de paiement client pour le débit direct ISO20022 ou un autre type de paiement en utilisant les états électroniques.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 38afbc3a49d9020540a56e58ce51196b53d6a9e1
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143430"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a><span data-ttu-id="fdd2b-103">Configurer le mode de paiement pour le débit direct ISO20022</span><span class="sxs-lookup"><span data-stu-id="fdd2b-103">Setup method of payment for ISO20022 direct debit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fdd2b-104">Cette procédure indique comment paramétrer le mode de paiement client pour le débit direct ISO20022 ou un autre type de paiement en utilisant les états électroniques.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-104">This procedure shows how to set up the customer method of payment for ISO20022 direct debit or any other payment type using electronic reporting.</span></span> 



<span data-ttu-id="fdd2b-105">Avant d'effectuer cette tâche, vous devez paramétrer les configurations du format d'exportation et les comptes de paiement.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-105">Before you complete this task, you must set up export format configurations and payment accounts.</span></span>



<span data-ttu-id="fdd2b-106">Cette procédure a été créée à l'aide des données fictives de la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-106">This procedure was created using the demo data company DEMF.</span></span>



<span data-ttu-id="fdd2b-107">Il s'agit de la troisième des cinq procédures illustrant le processus de paiement client à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-107">This is the third of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="fdd2b-108">Accédez à Comptabilité client > Paramétrage des paiements > Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-108">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="fdd2b-109">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="fdd2b-110">Par exemple, filtrez sur le champ Mode de paiement. avec une valeur de « ÉLECTRONIQUE ».</span><span class="sxs-lookup"><span data-stu-id="fdd2b-110">For example, filter on the Method of payment field with a value of 'ELECTRONIC'.</span></span>
3. <span data-ttu-id="fdd2b-111">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-111">Click Edit.</span></span>
4. <span data-ttu-id="fdd2b-112">Dans le champ Compte de paiement, indiquez les valeurs DEMF OPER.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-112">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
5. <span data-ttu-id="fdd2b-113">Développez la section Formats de fichier.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-113">Expand the File formats section.</span></span>
6. <span data-ttu-id="fdd2b-114">Sélectionnez Oui dans le champ États électroniques génériques.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-114">Select Yes in the Generic electronic reporting field.</span></span>
7. <span data-ttu-id="fdd2b-115">Entrez ou sélectionnez une valeur dans le champ Exporter la configuration du format.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-115">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="fdd2b-116">Dans la liste, sélectionnez Débit direct ISO20022 (Allemagne).</span><span class="sxs-lookup"><span data-stu-id="fdd2b-116">In the list, select ISO20022 Direct debit (DE).</span></span>  <span data-ttu-id="fdd2b-117">Si cette liste est vide, la configuration du format d'exportation de paiement client n'est pas importée et active.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-117">If the list is empty, the customer payment export format configuration has not been imported and active.</span></span>  
8. <span data-ttu-id="fdd2b-118">Sélectionnez Oui dans le champ Demander un mandat.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-118">Select Yes in the Require mandate field.</span></span>
    * <span data-ttu-id="fdd2b-119">Sélectionnez le paramètre Demander un mandat pour les formats de paiement client, qui nécessitent d'inclure les informations de mandat dans le message de paiement, par exemple le débit direct SEPA.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-119">Select the Require mandate parameter for customer payment formats, which require including mandate information in the payment message, like SEPA direct debit.</span></span>  
9. <span data-ttu-id="fdd2b-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fdd2b-120">Click Save.</span></span>

