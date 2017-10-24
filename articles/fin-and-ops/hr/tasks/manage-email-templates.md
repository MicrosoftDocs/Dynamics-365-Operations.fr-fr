--- 
title: "Gérer les modèles d'e-mails"
description: "Vous pouvez transférer des informations à partir de la base de données de votre organisation vers les signets d'un nouveau document et les utiliser dans des modèles qui vous aident à mieux communiquer avec les candidats"
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1eeaf1675b6653ab2c8c04d05ec1bff3cd0bb18d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="manage-email-templates"></a><span data-ttu-id="bf237-103">Gérer les modèles d'e-mails</span><span class="sxs-lookup"><span data-stu-id="bf237-103">Manage email templates</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bf237-104">Vous pouvez transférer des informations à partir de la base de données de votre organisation vers les signets d'un nouveau document et les utiliser dans des modèles qui vous aident à mieux communiquer avec les candidats</span><span class="sxs-lookup"><span data-stu-id="bf237-104">You can transfer information from your organization’s database to the bookmarks in a new document and use it in templates that help you communicate efficiently with applicants and candidates.</span></span> <span data-ttu-id="bf237-105">Pour ce faire, vous devez créer un modèle contenant du texte standard et certains signets où les données du système doivent être insérées.</span><span class="sxs-lookup"><span data-stu-id="bf237-105">To do this, you create a template that contains standard text and some bookmarks where the system data should be inserted.</span></span> <span data-ttu-id="bf237-106">Par exemple, vous pouvez insérer les coordonnées d'un candidat dans un document Microsoft Word que vous pouvez utiliser lorsque vous communiquez avec ce candidat.</span><span class="sxs-lookup"><span data-stu-id="bf237-106">For example, you can insert address and contact information for an applicant into a Microsoft Word document that you can use when communicating with that applicant.</span></span> <span data-ttu-id="bf237-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="bf237-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="select-which-bookmarks-to-use-in-your-email-templates"></a><span data-ttu-id="bf237-108">Sélectionnez les signets à utiliser dans vos modèles d'e-mail</span><span class="sxs-lookup"><span data-stu-id="bf237-108">Select which bookmarks to use in your email templates</span></span>
1. <span data-ttu-id="bf237-109">Allez dans Signets de candidature.</span><span class="sxs-lookup"><span data-stu-id="bf237-109">Go to Application bookmarks.</span></span>
2. <span data-ttu-id="bf237-110">Dans la liste, recherchez et sélectionnez l'action de correspondance souhaitée.</span><span class="sxs-lookup"><span data-stu-id="bf237-110">In the list, find and select the desired correspondence action.</span></span>
3. <span data-ttu-id="bf237-111">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="bf237-111">Click Edit.</span></span>
4. <span data-ttu-id="bf237-112">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="bf237-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bf237-113">Sélectionnez les champs que vous voulez pouvoir utiliser dans un modèle d'e-mail pour l'action de correspondance sélectionnée, puis déplacez-les dans les champs de signet.</span><span class="sxs-lookup"><span data-stu-id="bf237-113">Select the fields you would like to be able to use in an email template for the selected Correspondence action and move them to the Bookmark fields.</span></span>  
5. <span data-ttu-id="bf237-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bf237-114">Close the page.</span></span>

## <a name="create-an-email-template"></a><span data-ttu-id="bf237-115">Création d'un modèle d'e-mail</span><span class="sxs-lookup"><span data-stu-id="bf237-115">Create an email template</span></span>
1. <span data-ttu-id="bf237-116">Allez dans Ressources humaines > Recrutement > Communication > Modèles d'e-mail de candidature</span><span class="sxs-lookup"><span data-stu-id="bf237-116">Go to Human resources > Recruitment > Communication > Application e-mail templates.</span></span>
2. <span data-ttu-id="bf237-117">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bf237-117">Click New.</span></span>
3. <span data-ttu-id="bf237-118">Sélectionnez Entretien dans le champ Action de correspondance.</span><span class="sxs-lookup"><span data-stu-id="bf237-118">In the Correspondence action field, select 'Interview'.</span></span>
    * <span data-ttu-id="bf237-119">Sélectionnez l'action de correspondance qui contient les signets à utiliser pour ce type de communication par e-mail.</span><span class="sxs-lookup"><span data-stu-id="bf237-119">Select the correspondence action that contains the bookmarks to use for this type of email communication.</span></span>  
4. <span data-ttu-id="bf237-120">Tapez une valeur dans le champ Modèle d'e-mail.</span><span class="sxs-lookup"><span data-stu-id="bf237-120">In the E-mail template field, type a value.</span></span>
5. <span data-ttu-id="bf237-121">Tapez une valeur dans le champ Objet.</span><span class="sxs-lookup"><span data-stu-id="bf237-121">In the Subject field, type a value.</span></span>
6. <span data-ttu-id="bf237-122">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="bf237-122">In the Text field, type a value.</span></span>
7. <span data-ttu-id="bf237-123">Dans la liste, recherchez et sélectionnez le champ de signet souhaité.</span><span class="sxs-lookup"><span data-stu-id="bf237-123">In the list, find and select the desired bookmark field.</span></span>
8. <span data-ttu-id="bf237-124">Continuez à taper votre message e-mail en insérant les champs de signet là où vous en avez besoin.</span><span class="sxs-lookup"><span data-stu-id="bf237-124">Continue typing your email message, inserting the bookmark fields where you need them.</span></span>
    * <span data-ttu-id="bf237-125">Continuez à taper votre message e-mail en insérant les champs de signet là où vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="bf237-125">Continue typing your email message inserting the bookmark fields where desired.</span></span>  
9. <span data-ttu-id="bf237-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bf237-126">Click Save.</span></span>


