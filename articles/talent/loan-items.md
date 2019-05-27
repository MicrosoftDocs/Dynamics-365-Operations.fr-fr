---
title: Gérer des articles qui prêtés aux employés
description: Les articles empruntés sont des enregistrements qui permettent aux responsables de suivre les articles physiques que votre société prête aux employés.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmLoanItem, HcmLoanType, HcmPersonLoan
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 3581
ms.assetid: b14bdddb-f10e-4619-9f91-8c88439da862
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 5942016374eb2c681e65b2d6151824924f290dc2
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517973"
---
# <a name="manage-items-that-are-lent-to-workers"></a><span data-ttu-id="dd930-103">Gérer des articles qui prêtés aux employés</span><span class="sxs-lookup"><span data-stu-id="dd930-103">Manage items that are lent to workers</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dd930-104">Les articles empruntés sont des enregistrements qui permettent aux responsables de suivre les articles physiques que votre société prête aux employés.</span><span class="sxs-lookup"><span data-stu-id="dd930-104">Loan items are records that help managers track the physical items that your company lends to its workers.</span></span> 

<span data-ttu-id="dd930-105">Voici quelques exemples d'articles qu'une société peut prêter aux employés :</span><span class="sxs-lookup"><span data-stu-id="dd930-105">The following points list examples of items that a company might lend to workers:</span></span>
-   <span data-ttu-id="dd930-106">téléphones portables ;</span><span class="sxs-lookup"><span data-stu-id="dd930-106">Mobile telephones</span></span>
-   <span data-ttu-id="dd930-107">véhicules ;</span><span class="sxs-lookup"><span data-stu-id="dd930-107">Automobiles</span></span>
-   <span data-ttu-id="dd930-108">équipement informatique ;</span><span class="sxs-lookup"><span data-stu-id="dd930-108">Computer equipment</span></span>

<span data-ttu-id="dd930-109">Chaque article physique doit avoir un article de prêt correspondant.</span><span class="sxs-lookup"><span data-stu-id="dd930-109">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="dd930-110">Chaque enregistrement d'article emprunté doit décrire la nature de l'emprunt, le responsable de l'emprunt et le nombre de jours d'emprunt de l'article.</span><span class="sxs-lookup"><span data-stu-id="dd930-110">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can loaned to a worker.</span></span> <span data-ttu-id="dd930-111">Vous pouvez créer plusieurs articles empruntés, tels que des clés, des cartes d'accès ou des uniformes, simultanément.</span><span class="sxs-lookup"><span data-stu-id="dd930-111">You can create multiple loan items, for items such as keys, access cards or uniforms, at the same time.</span></span> 

<span data-ttu-id="dd930-112">Lors de l'emprunt d'un article, entrez la date d'emprunt de l'article et la date de retour prévue.</span><span class="sxs-lookup"><span data-stu-id="dd930-112">When loaning an item, enter the date that the item was loaned, and the planned return date.</span></span> <span data-ttu-id="dd930-113">Au retour de l'article, entrez la date de retour réelle.</span><span class="sxs-lookup"><span data-stu-id="dd930-113">When the item is returned, enter the actual return date.</span></span>

<span data-ttu-id="dd930-114">Les employés peuvent consulter les enregistrements des articles qui ont été empruntés à l'aide de l'espace de travail Libre service employé.</span><span class="sxs-lookup"><span data-stu-id="dd930-114">Employees can view the records of the items that have been loaned to them using the Employee self-service workspace.</span></span> <span data-ttu-id="dd930-115">Ils peuvent également modifier les enregistrements existants ou indiquer de nouveaux articles empruntés, s'ils ont reçu des articles physiques supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="dd930-115">They can also edit the existing records or enter new loan items, if they've received additional physical items.</span></span>  <span data-ttu-id="dd930-116">Un workflow peut être paramétré pour acheminer les modifications apportées aux nouveaux articles empruntés ou à ceux existants via un processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="dd930-116">Workflow can be set up to route changes to new or existing loan items through an approval process.</span></span> 

<span data-ttu-id="dd930-117">Les responsables peuvent afficher les articles empruntés pour leurs états directs.</span><span class="sxs-lookup"><span data-stu-id="dd930-117">Managers can view loaned items for their direct reports.</span></span> <span data-ttu-id="dd930-118">Ils peuvent également avoir l'autorisation d'ajouter de nouveaux articles empruntés au nom de leurs employés.</span><span class="sxs-lookup"><span data-stu-id="dd930-118">They can also be granted permission to add new loan items on behalf of their employees.</span></span>

 <a name="account-for-lost-or-misplaced-loan-items"></a><span data-ttu-id="dd930-119">Compte pour les articles empruntés perdus ou égarés</span><span class="sxs-lookup"><span data-stu-id="dd930-119">Account for lost or misplaced loan items</span></span>
-----------------------------------------

<span data-ttu-id="dd930-120">Si un article est endommagé ou égaré, entrez un enregistrement de retour fictif.</span><span class="sxs-lookup"><span data-stu-id="dd930-120">If an item becomes damaged or misplaced, enter a fictitious return record.</span></span> <span data-ttu-id="dd930-121">Ensuite, supprimez l'article ou conservez-le dans la vue d'ensemble et modifiez la description pour indiquer que l'article n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="dd930-121">Then either delete the item or keep it in the overview and change the description to indicate that the item is not available.</span></span>


<a name="additional-resources"></a><span data-ttu-id="dd930-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="dd930-122">Additional resources</span></span>
--------

[<span data-ttu-id="dd930-123">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="dd930-123">Human resources</span></span>](index.md)



