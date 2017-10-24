--- 
title: "Paramétrer le mode de paiement pour les virements ISO20022"
description: "Cette procédure indique comment paramétrer le mode de paiement fournisseur pour le virement ISO20022 ou un autre type de paiement en utilisant les états électroniques pour générer un fichier."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bed51f8749dfa0264ad39f51f9ceb295ac46fe93
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a><span data-ttu-id="5a595-103">Paramétrer le mode de paiement pour les virements ISO20022</span><span class="sxs-lookup"><span data-stu-id="5a595-103">Set up method of payment for ISO20022 credit transfer</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5a595-104">Cette procédure indique comment paramétrer le mode de paiement fournisseur pour le virement ISO20022 ou un autre type de paiement en utilisant les états électroniques pour générer un fichier.</span><span class="sxs-lookup"><span data-stu-id="5a595-104">This procedure shows how to set up the vendor method of payment for ISO20022 credit transfer or any other payment type using electronic reporting to generate a file.</span></span> 

<span data-ttu-id="5a595-105">Avant d'effectuer cette tâche, vous devez exporter les configurations de format et paramétrer les comptes de paiement.</span><span class="sxs-lookup"><span data-stu-id="5a595-105">Before you complete this task, you must export format configurations and set up payment accounts.</span></span>

<span data-ttu-id="5a595-106">Cette tâche a été créé à l'aide des données fictives de la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="5a595-106">This task was created using the DEMF demo data company.</span></span>

<span data-ttu-id="5a595-107">Il s'agit de la troisième des cinq procédures illustrant le processus de paiement fournisseur à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="5a595-107">This is the third procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="5a595-108">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="5a595-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="5a595-109">Accédez à Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="5a595-109">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="5a595-110">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="5a595-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="5a595-111">Par exemple, filtrez sur le champ Mode de paiement. avec une valeur de « SEPA CT ».</span><span class="sxs-lookup"><span data-stu-id="5a595-111">For example, filter on the Method of payment field with a value of 'SEPA CT'.</span></span>
3. <span data-ttu-id="5a595-112">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="5a595-112">Click Edit.</span></span>
4. <span data-ttu-id="5a595-113">Sélectionnez Total dans le champ Période.</span><span class="sxs-lookup"><span data-stu-id="5a595-113">In the Period field, select 'Total'.</span></span>
5. <span data-ttu-id="5a595-114">Sélectionnez « Paiement électronique » dans le champ Type de paiement.</span><span class="sxs-lookup"><span data-stu-id="5a595-114">In the Payment type field, select 'Electronic payment'.</span></span>
6. <span data-ttu-id="5a595-115">Développez la section Formats de fichier.</span><span class="sxs-lookup"><span data-stu-id="5a595-115">Expand the File formats section.</span></span>
7. <span data-ttu-id="5a595-116">Sélectionnez Oui dans le champ États électroniques génériques.</span><span class="sxs-lookup"><span data-stu-id="5a595-116">Select Yes in the Generic electronic reporting field.</span></span>
8. <span data-ttu-id="5a595-117">Entrez ou sélectionnez une valeur dans le champ Exporter la configuration du format.</span><span class="sxs-lookup"><span data-stu-id="5a595-117">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="5a595-118">Dans la liste, sélectionnez la valeur du virement ISO20022 (DE).</span><span class="sxs-lookup"><span data-stu-id="5a595-118">In the list, select the value ISO20022 Credit transfer (DE).</span></span> <span data-ttu-id="5a595-119">Si cette liste est vide, la configuration du format d'exportation de paiement fournisseur n'est pas importée et active.</span><span class="sxs-lookup"><span data-stu-id="5a595-119">If the list is empty, the vendor payment export format configuration is not imported and active.</span></span>  
9. <span data-ttu-id="5a595-120">Sélectionnez Banque dans le champ Type de compte.</span><span class="sxs-lookup"><span data-stu-id="5a595-120">In the Account type field, select 'Bank'.</span></span>
10. <span data-ttu-id="5a595-121">Dans le champ Compte de paiement, indiquez les valeurs DEMF OPER.</span><span class="sxs-lookup"><span data-stu-id="5a595-121">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
11. <span data-ttu-id="5a595-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="5a595-122">Click Save.</span></span>


