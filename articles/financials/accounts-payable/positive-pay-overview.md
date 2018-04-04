---
title: Vue d'ensemble des paiements positifs
description: "Cet article fournit des informations sur le paiement positif qui est utilisé pour générer une liste électronique de chèques devant être présentés à la banque."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 13a7a842e7b4522b508a34fdf86bb3bf58a0845f
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="positive-pay-overview"></a><span data-ttu-id="e0f83-103">Vue d'ensemble des paiements positifs</span><span class="sxs-lookup"><span data-stu-id="e0f83-103">Positive pay overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e0f83-104">Cet article fournit des informations sur le paiement positif qui est utilisé pour générer une liste électronique de chèques devant être présentés à la banque.</span><span class="sxs-lookup"><span data-stu-id="e0f83-104">This article provides information about positive pay, which is used to generate an electronic list of checks that can be presented to a bank.</span></span> 

<span data-ttu-id="e0f83-105">Vous pouvez utiliser le paiement positif pour générer la liste électronique des chèques devant être présentés à la banque.</span><span class="sxs-lookup"><span data-stu-id="e0f83-105">Positive pay is used to generate an electronic list of checks that can be presented to a bank.</span></span> <span data-ttu-id="e0f83-106">Des fichiers de paiement positifs peuvent aider les banques à empêcher les fraudes par chèque.</span><span class="sxs-lookup"><span data-stu-id="e0f83-106">Positive pay files can help banks prevent check fraud.</span></span> <span data-ttu-id="e0f83-107">Paramétrez le paiement positif pour générer une liste électronique de chèques chaque fois que des chèques sont imprimés.</span><span class="sxs-lookup"><span data-stu-id="e0f83-107">You set up positive pay to generate an electronic list of checks every time that checks are printed.</span></span> <span data-ttu-id="e0f83-108">Puis, lorsqu'un chèque est présenté à la banque, la banque le compare avec la liste des chèques que vous avez précédemment envoyés.</span><span class="sxs-lookup"><span data-stu-id="e0f83-108">Then, when a check is presented to the bank, the bank compares the check with the list of checks that you previously submitted.</span></span> <span data-ttu-id="e0f83-109">Si le chèque correspond à un chèque de la liste, la banque le compense.</span><span class="sxs-lookup"><span data-stu-id="e0f83-109">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="e0f83-110">Si le chèque ne correspond pas à un chèque dans la liste, la banque le conserve pour examen.</span><span class="sxs-lookup"><span data-stu-id="e0f83-110">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

<span data-ttu-id="e0f83-111">Le salaire positif est également appelé SafePay.</span><span class="sxs-lookup"><span data-stu-id="e0f83-111">Positive pay is also known as SafePay.</span></span> 

<span data-ttu-id="e0f83-112">Les fichiers de paiement positif peuvent contenir des informations confidentielles sur les bénéficiaires et les montants des chèques.</span><span class="sxs-lookup"><span data-stu-id="e0f83-112">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="e0f83-113">Veillez donc à utiliser les mesures de sécurité appropriées depuis la génération des fichiers jusqu'à leur réception par la banque.</span><span class="sxs-lookup"><span data-stu-id="e0f83-113">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="e0f83-114">Les fichiers de paiement positif sont téléchargés en fonction des instructions de téléchargement pour le navigateur Web.</span><span class="sxs-lookup"><span data-stu-id="e0f83-114">Positive pay files are downloaded according to the download instructions for the web browser.</span></span> 

<span data-ttu-id="e0f83-115">Les fichiers de paiement positifs sont créés à l'aide d'entités de données.</span><span class="sxs-lookup"><span data-stu-id="e0f83-115">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="e0f83-116">Avant de générer un fichier de paiement positif, vous devez définir les formats de transformation pour le XML qui traduit les données en un format que la banque peut consommer.</span><span class="sxs-lookup"><span data-stu-id="e0f83-116">Before you generate a positive pay file, you must set up the transformation formats for the XML that translates the data into a format that the bank can consume.</span></span> 

<span data-ttu-id="e0f83-117">Pour chaque compte bancaire pour lequel vous souhaitez générer des informations de paiement positif, vous devez affecter le format de paiement positif.</span><span class="sxs-lookup"><span data-stu-id="e0f83-117">For each bank account that you want to generate positive pay information for, you must assign the positive pay format.</span></span> <span data-ttu-id="e0f83-118">Après avoir généré les paiements, vous pouvez générer un fichier de paiement positif pour une entité juridique unique et un compte bancaire unique.</span><span class="sxs-lookup"><span data-stu-id="e0f83-118">After you generate payments, you can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="e0f83-119">Sinon, vous pouvez générer des fichiers de paiement positif pour plusieurs entités juridiques et comptes bancaires en même temps.</span><span class="sxs-lookup"><span data-stu-id="e0f83-119">Alternatively, you can generate positive pay files for multiple legal entities and bank accounts at the same time.</span></span> 

<span data-ttu-id="e0f83-120">Lorsque les chèques répertoriés dans un fichier de paiement positif ont été payés, vous recevez un numéro de confirmation de la banque.</span><span class="sxs-lookup"><span data-stu-id="e0f83-120">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="e0f83-121">Vous pouvez ensuite confirmer le fichier de paiement positif dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e0f83-121">You can then confirm the positive pay file in Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="e0f83-122">Si vous devez modifier un fichier de paiement positif, vous pouvez le rappeler.</span><span class="sxs-lookup"><span data-stu-id="e0f83-122">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="e0f83-123">Puis, pour chaque chèque présent dans un fichier de paiement positif, le champ qui indique si le chèque a été inclus dans un fichier de paiement positif est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="e0f83-123">Then, for each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span>

<span data-ttu-id="e0f83-124">Pour plus d'informations, voir [Paramétrer et générer des fichiers de paiement positif](set-up-generate-positive-pay-files.md).</span><span class="sxs-lookup"><span data-stu-id="e0f83-124">For more information, see [Set up and generate positive pay files](set-up-generate-positive-pay-files.md).</span></span>




