---
title: "Paramétrer une fonctionnalité de connexion étendue pour Cloud POS et MPOS"
description: "Cette rubrique couvre les options de configuration de la connexion étendue pour Cloud POS et Retail Modern POS (MPOS)."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: b47fb70ef0f05b9e10d7899b9a6da107f8764660
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="set-up-extended-logon-functionality-for-cloud-pos-and-mpos"></a><span data-ttu-id="d187a-103">Paramétrer une fonctionnalité de connexion étendue pour Cloud POS et MPOS</span><span class="sxs-lookup"><span data-stu-id="d187a-103">Set up extended logon functionality for Cloud POS and MPOS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d187a-104">Cette rubrique couvre les options de configuration de la connexion étendue pour Cloud POS et Retail Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="d187a-104">This topic covers your options for setting up extended logon for Cloud POS and Retail Modern POS (MPOS).</span></span>

## <a name="setting-up-extended-logon"></a><span data-ttu-id="d187a-105">Paramétrage d'une connexion étendue</span><span class="sxs-lookup"><span data-stu-id="d187a-105">Setting up extended logon</span></span>

<span data-ttu-id="d187a-106">Vous trouverez le paramétrage des masques de code-barres dans **Vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **Profils PDV** &gt; **Profils de fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="d187a-106">You can find the setup for bar code masks at **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profiles** &gt; **Functionality profiles**.</span></span> <span data-ttu-id="d187a-107">L'organisateur **Fonctions** inclut les options suivantes relatives à la connexion étendue.</span><span class="sxs-lookup"><span data-stu-id="d187a-107">The **Functions** FastTab includes the following options that are related to extended logon.</span></span>

### <a name="staff-bar-code-logon"></a><span data-ttu-id="d187a-108">Connexion du personnel par code-barres</span><span class="sxs-lookup"><span data-stu-id="d187a-108">Staff bar code logon</span></span>

<span data-ttu-id="d187a-109">Lorsque l'option **Connexion du personnel par code-barres** est activée, les collaborateurs qui ont une connexion étendue affectée à leurs informations d'identification de point de vente (PDV) peuvent se connecter à l'aide d'un code-barres.</span><span class="sxs-lookup"><span data-stu-id="d187a-109">When the **Staff bar code logon** option is enabled, workers who have an extended logon assigned to their point of sale (POS) credentials can log on by using a bar code.</span></span>

### <a name="staff-bar-code-logon-requires-password"></a><span data-ttu-id="d187a-110">La connexion du personnel par code-barres nécessite un mot de passe</span><span class="sxs-lookup"><span data-stu-id="d187a-110">Staff bar code logon requires password</span></span>

<span data-ttu-id="d187a-111">Lorsque l'option **La connexion du personnel par code-barres nécessite un mot de passe** est activée, la connexion du personnel par code-barres sélectionne uniquement le collaborateur qui est affecté à la connexion étendue présentée.</span><span class="sxs-lookup"><span data-stu-id="d187a-111">When the **Staff bar code logon requires password** option is enabled, the staff bar code logon selects only the worker who is assigned to the extended logon that is presented.</span></span> <span data-ttu-id="d187a-112">Les collaborateurs doivent toujours entrer leur mot de passe lorsque cette option est activée.</span><span class="sxs-lookup"><span data-stu-id="d187a-112">Workers must still enter their password when this option is enabled.</span></span>

### <a name="staff-card-logon"></a><span data-ttu-id="d187a-113">Connexion du personnel par carte</span><span class="sxs-lookup"><span data-stu-id="d187a-113">Staff card logon</span></span>

<span data-ttu-id="d187a-114">Lorsque l'option **Connexion du personnel par carte** est activée, les collaborateurs qui ont une connexion étendue affectée à leurs informations d'identification de PDV peuvent se connecter à l'aide d'une bande magnétique.</span><span class="sxs-lookup"><span data-stu-id="d187a-114">When the **Staff card logon** option is enabled, workers who have an extended logon assigned to their POS credentials can log on by using a magnetic stripe.</span></span>

### <a name="staff-card-logon-requires-password"></a><span data-ttu-id="d187a-115">La connexion du personnel par carte nécessite un mot de passe</span><span class="sxs-lookup"><span data-stu-id="d187a-115">Staff card logon requires password</span></span>

<span data-ttu-id="d187a-116">Lorsque l'option **La connexion du personnel par carte nécessite un mot de passe** est activée, la connexion du personnel par carte sélectionne uniquement le collaborateur qui est affecté à la connexion étendue présentée.</span><span class="sxs-lookup"><span data-stu-id="d187a-116">When the **Staff card logon requires password** option is enabled, the staff card logon selects only the worker who is assigned to the extended logon that is presented.</span></span> <span data-ttu-id="d187a-117">Les collaborateurs doivent toujours entrer leur mot de passe lorsque cette option est activée.</span><span class="sxs-lookup"><span data-stu-id="d187a-117">Workers must still enter their password when this option is enabled.</span></span>

## <a name="assigning-an-extended-logon"></a><span data-ttu-id="d187a-118">Affectation d'une connexion étendue</span><span class="sxs-lookup"><span data-stu-id="d187a-118">Assigning an extended logon</span></span>

<span data-ttu-id="d187a-119">Par défaut, seuls les responsables peuvent affecter une connexion étendue aux collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="d187a-119">By default, only managers can assign extended logon to workers.</span></span> <span data-ttu-id="d187a-120">Pour affecter une connexion étendue, accédez à **Connexion étendue** dans le PDV.</span><span class="sxs-lookup"><span data-stu-id="d187a-120">To assign extended logon, go to **Extended log on** in POS.</span></span> <span data-ttu-id="d187a-121">Recherchez ensuite un collaborateur en entrant son ID d'opérateur dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="d187a-121">Then search for a worker by entering his or her operator ID in the search field.</span></span> <span data-ttu-id="d187a-122">Sélectionnez le collaborateur, puis cliquez sur **Affecter**.</span><span class="sxs-lookup"><span data-stu-id="d187a-122">Select the worker, and then click **Assign**.</span></span> <span data-ttu-id="d187a-123">Sur la page suivante, faites glisser ou scannez la connexion étendue à affecter au collaborateur.</span><span class="sxs-lookup"><span data-stu-id="d187a-123">On the next page, swipe or scan the extended logon to assign to the worker.</span></span> <span data-ttu-id="d187a-124">Si cette opération permet une lecture correcte, le bouton **OK** devient disponible.</span><span class="sxs-lookup"><span data-stu-id="d187a-124">If the swipe or scan is successfully read, the **OK** button becomes available.</span></span> <span data-ttu-id="d187a-125">Cliquez sur **OK** pour enregistrer la connexion étendue pour ce collaborateur.</span><span class="sxs-lookup"><span data-stu-id="d187a-125">Click **OK** to save the extended logon for that worker.</span></span>

## <a name="deleting-an-extended-logon"></a><span data-ttu-id="d187a-126">Suppression d'une connexion étendue</span><span class="sxs-lookup"><span data-stu-id="d187a-126">Deleting an extended logon</span></span>

<span data-ttu-id="d187a-127">Pour supprimer la connexion étendue affectée à un collaborateur, recherchez le collaborateur à l'aide de l'opération **Connexion étendue**.</span><span class="sxs-lookup"><span data-stu-id="d187a-127">To delete the extended logon that is assigned to a worker, search for the worker by using the **Extended log on** operation.</span></span> <span data-ttu-id="d187a-128">Sélectionnez le collaborateur, puis cliquez sur **Annuler l'affectation**.</span><span class="sxs-lookup"><span data-stu-id="d187a-128">Select the worker, and then click **Unassign**.</span></span> <span data-ttu-id="d187a-129">Toutes les informations d'identification de la connexion étendue associées à ce collaborateur sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="d187a-129">All extended logon credentials that are associated with that worker are removed.</span></span>

## <a name="extending-extended-logon"></a><span data-ttu-id="d187a-130">Extension de connexion étendue</span><span class="sxs-lookup"><span data-stu-id="d187a-130">Extending extended logon</span></span>

<span data-ttu-id="d187a-131">Le service de connexion peut être étendu pour prendre en charge les périphériques de connexion étendue supplémentaires, tels que des scanneurs de paume.</span><span class="sxs-lookup"><span data-stu-id="d187a-131">The logon service can be extended to support additional extended logon devices, such as palm scanners.</span></span> <span data-ttu-id="d187a-132">Pour plus d'informations, voir la documentation sur l'extensibilité de PDV.</span><span class="sxs-lookup"><span data-stu-id="d187a-132">For more information, see the POS extensibility documentation.</span></span>

## <a name="using-extended-logon"></a><span data-ttu-id="d187a-133">Utilisation d'une connexion étendue</span><span class="sxs-lookup"><span data-stu-id="d187a-133">Using extended logon</span></span>

<span data-ttu-id="d187a-134">Lorsque la connexion étendue est configurée, et qu'un collaborateur a été affecté à un code-barres ou une bande magnétique, celui-ci doit juste faire glisser ou scanner sa carte lorsque la page de connexion de PDV s'affiche.</span><span class="sxs-lookup"><span data-stu-id="d187a-134">When extended logon is configured, and a worker has been assigned a bar code or magnetic stripe, the worker just has to swipe or scan his or her card while the POS logon page is displayed.</span></span> <span data-ttu-id="d187a-135">Si un mot de passe est également requis pour pouvoir continuer la connexion, le collaborateur est invité à entrer son mot de passe.</span><span class="sxs-lookup"><span data-stu-id="d187a-135">If a password is also required before logon can proceed, the worker is prompted to enter his or her password.</span></span>




