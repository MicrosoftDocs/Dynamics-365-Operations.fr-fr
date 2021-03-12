---
title: Gérer les modèles d’e-mails
description: Cette rubrique explique comment gérer les modèles d’e-mail.
author: andreabichsel
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMApplicationWordBookmark, HRMApplicationEmailTemplate
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b9bd15e73535f1d07b664ed659f9f15b3b0b7594
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797461"
---
# <a name="manage-email-templates"></a><span data-ttu-id="844c6-103">Gérer les modèles d’e-mails</span><span class="sxs-lookup"><span data-stu-id="844c6-103">Manage email templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="844c6-104">Vous pouvez transférer des informations à partir de la base de données de votre organisation vers les signets d’un nouveau document et les utiliser dans des modèles qui vous aident à mieux communiquer avec les candidats.</span><span class="sxs-lookup"><span data-stu-id="844c6-104">You can transfer information from your organization's database to the bookmarks in a new document and use it in templates that help you communicate efficiently with applicants and candidates.</span></span> <span data-ttu-id="844c6-105">Pour ce faire, vous devez créer un modèle contenant du texte standard et certains signets où les données du système doivent être insérées.</span><span class="sxs-lookup"><span data-stu-id="844c6-105">To do this, you create a template that contains standard text and some bookmarks where the system data should be inserted.</span></span> <span data-ttu-id="844c6-106">Par exemple, vous pouvez insérer les coordonnées d’un candidat dans un document Microsoft Word que vous pouvez utiliser lorsque vous communiquez avec ce candidat.</span><span class="sxs-lookup"><span data-stu-id="844c6-106">For example, you can insert address and contact information for an applicant into a Microsoft Word document that you can use when communicating with that applicant.</span></span> <span data-ttu-id="844c6-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="844c6-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="select-which-bookmarks-to-use-in-your-email-templates"></a><span data-ttu-id="844c6-108">Sélectionnez les signets à utiliser dans vos modèles d’e-mail</span><span class="sxs-lookup"><span data-stu-id="844c6-108">Select which bookmarks to use in your email templates</span></span>
1. <span data-ttu-id="844c6-109">Dans le volet de navigation, accédez à **Modules > Ressources humaines > Recrutement > Communication > Signets de candidature**.</span><span class="sxs-lookup"><span data-stu-id="844c6-109">In the navigation pane, go to **Modules > Human Resources > Recruitment > Communication > Application bookmarks**.</span></span>
2. <span data-ttu-id="844c6-110">Dans la liste, recherchez et sélectionnez l’action de correspondance souhaitée.</span><span class="sxs-lookup"><span data-stu-id="844c6-110">In the list, find and select the desired correspondence action.</span></span>
3. <span data-ttu-id="844c6-111">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="844c6-111">Select **Edit**.</span></span>
4. <span data-ttu-id="844c6-112">Sélectionnez les champs que vous voulez pouvoir utiliser dans un modèle d’e-mail pour l’action de correspondance sélectionnée, puis déplacez-les dans les champs de signet.</span><span class="sxs-lookup"><span data-stu-id="844c6-112">Select the fields you would like to be able to use in an email template for the selected Correspondence action and move them to the Bookmark fields.</span></span>  
5. <span data-ttu-id="844c6-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="844c6-113">Close the page.</span></span>

## <a name="create-an-email-template"></a><span data-ttu-id="844c6-114">Créer un modèle d’e-mail</span><span class="sxs-lookup"><span data-stu-id="844c6-114">Create an email template</span></span>
1. <span data-ttu-id="844c6-115">Dans le volet de navigation, accédez à **Modules > Ressources humaines > Recrutement > Communication > Modèles d’e-mail de candidature**.</span><span class="sxs-lookup"><span data-stu-id="844c6-115">In the navigation pane, go to **Modules > Human resources > Recruitment > Communication > Application e-mail templates**.</span></span>
2. <span data-ttu-id="844c6-116">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="844c6-116">Select **New**.</span></span>
3. <span data-ttu-id="844c6-117">Dans le champ **Entretien**, sélectionnez **Entretien**.</span><span class="sxs-lookup"><span data-stu-id="844c6-117">In the **Correspondence action** field, select **Interview**.</span></span> <span data-ttu-id="844c6-118">Sélectionnez l’action de correspondance qui contient les signets à utiliser pour ce type de communication par e-mail.</span><span class="sxs-lookup"><span data-stu-id="844c6-118">Select the correspondence action that contains the bookmarks to use for this type of email communication.</span></span>  
4. <span data-ttu-id="844c6-119">Dans le champ **Modèle d’e-mail**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="844c6-119">In the **E-mail template** field, type a value.</span></span>
5. <span data-ttu-id="844c6-120">Tapez une valeur dans le champ **Objet**.</span><span class="sxs-lookup"><span data-stu-id="844c6-120">In the **Subject** field, type a value.</span></span>
6. <span data-ttu-id="844c6-121">Tapez une valeur dans le champ **Texte**.</span><span class="sxs-lookup"><span data-stu-id="844c6-121">In the **Text** field, type a value.</span></span>
7. <span data-ttu-id="844c6-122">Dans la liste, recherchez et sélectionnez le champ de signet souhaité.</span><span class="sxs-lookup"><span data-stu-id="844c6-122">In the list, find and select the desired bookmark field.</span></span>
8. <span data-ttu-id="844c6-123">Continuez à taper votre message e-mail en insérant les champs de signet là où vous en avez besoin.</span><span class="sxs-lookup"><span data-stu-id="844c6-123">Continue typing your email message, inserting the bookmark fields where you need them.</span></span>
9. <span data-ttu-id="844c6-124">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="844c6-124">Select **Save**.</span></span>

