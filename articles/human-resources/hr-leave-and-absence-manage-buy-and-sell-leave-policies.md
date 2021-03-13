---
title: Gérer les politiques d’achat et de vente de congés
description: Vous pouvez permettre aux employés d’acheter et de vendre des congés dans Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 89563204cf1423ddce47d7bacace8f14edf87005
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115994"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="ea260-103">Gérer les stratégies d’achat et de vente de congés</span><span class="sxs-lookup"><span data-stu-id="ea260-103">Manage buy and sell leave policies</span></span>

<span data-ttu-id="ea260-104">Vous pouvez permettre aux employés de vendre et d’acheter des congés en créant une stratégie de vente et d’achat de congés.</span><span class="sxs-lookup"><span data-stu-id="ea260-104">You can enable employees to buy and sell leave by creating a buy and sell leave policy.</span></span> <span data-ttu-id="ea260-105">Vous pouvez configurer ces stratégies pour utiliser le workflow pour les approbations, définir des montants et des taux maximums et des tarifs pour l’achat et la vente.</span><span class="sxs-lookup"><span data-stu-id="ea260-105">You can configure these policies to use workflow for approvals, set maximum amounts and rates, and set rates for buying and selling.</span></span> 

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="ea260-106">Permettre aux employés d’acheter et de vendre des congés</span><span class="sxs-lookup"><span data-stu-id="ea260-106">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="ea260-107">Dans la page **Paramètres de congé et d’absence**, sélectionnez **Oui** pour **Autoriser les employés à acheter des congés** et **Autoriser les employés à vendre des congés**.</span><span class="sxs-lookup"><span data-stu-id="ea260-107">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span>

## <a name="create-a-buy-and-sell-leave-policy"></a><span data-ttu-id="ea260-108">Créer une stratégie d’achat et de vente de congés</span><span class="sxs-lookup"><span data-stu-id="ea260-108">Create a buy and sell leave policy</span></span>

1. <span data-ttu-id="ea260-109">Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="ea260-109">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="ea260-110">Sélectionnez **Stratégie d’achat et de vente de congés**.</span><span class="sxs-lookup"><span data-stu-id="ea260-110">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="ea260-111">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ea260-111">Select **New**.</span></span>

4. <span data-ttu-id="ea260-112">Entrez un **Nom** et une **Description** pour la stratégie sous **Stratégie d’achat et de vente de congés**.</span><span class="sxs-lookup"><span data-stu-id="ea260-112">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="ea260-113">Sélectionnez un **Type de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="ea260-113">Select a **Policy type**.</span></span> 

   <span data-ttu-id="ea260-114">Les types de stratégie disponibles sont **Quantité** et **Heures par semaine**.</span><span class="sxs-lookup"><span data-stu-id="ea260-114">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="ea260-115">Sélectionnez **Quantité** pour entrer une **Quantité fixe** pour les quantités maximales que les employés peuvent acheter et vendre.</span><span class="sxs-lookup"><span data-stu-id="ea260-115">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="ea260-116">Si vous sélectionnez **Heures par semaine**, le temps de travail défini dans les horaires de travail attribués à l’employé sera utilisé pour déterminer la quantité maximale de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="ea260-116">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="ea260-117">Sélectionnez une **Date de début** et une **Date de fin** pour la stratégie.</span><span class="sxs-lookup"><span data-stu-id="ea260-117">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="ea260-118">Les demandes d’achat ou de vente de congés ne pourront être soumises que pendant cette période.</span><span class="sxs-lookup"><span data-stu-id="ea260-118">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="ea260-119">Sélectionnez un **ID de workflow** pour la stratégie.</span><span class="sxs-lookup"><span data-stu-id="ea260-119">Select a **Workflow ID** for the policy.</span></span> <span data-ttu-id="ea260-120">Toutes les demandes d’achat et de vente utiliseront ce workflow pour examen et approbation.</span><span class="sxs-lookup"><span data-stu-id="ea260-120">Any buy and sell requests will use this workflow for review and approval.</span></span> 

8. <span data-ttu-id="ea260-121">Sous **Stratégie d’achat**, sélectionnez **Équivalence temps plein** (ETP) pour calculer la quantité maximale au prorata de l’ETP défini pour le poste du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ea260-121">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="ea260-122">Si le type de stratégie est **Quantité**, entrez une **Quantité maximale fixe**.</span><span class="sxs-lookup"><span data-stu-id="ea260-122">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

9. <span data-ttu-id="ea260-123">Sélectionnez **Ajouter** pour ajouter les types de congés à acheter par les collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="ea260-123">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="ea260-124">Vous pouvez ajouter plusieurs types de congés à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="ea260-124">You can add multiple leave types to the policy.</span></span> 

10. <span data-ttu-id="ea260-125">Entrer les **Mois de service** pour le type de congé afin d’autoriser différents mois de service pour déterminer la quantité maximale qu’un collaborateur peut acheter.</span><span class="sxs-lookup"><span data-stu-id="ea260-125">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

11. <span data-ttu-id="ea260-126">Entrez la **Quantité maximale** pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="ea260-126">Enter the **Maximum amount** for the leave type.</span></span> 

12. <span data-ttu-id="ea260-127">Entrez le **Taux** auquel le collaborateur achètera le congé.</span><span class="sxs-lookup"><span data-stu-id="ea260-127">Enter the **Rate** at which the employee will buy the leave.</span></span> 

13. <span data-ttu-id="ea260-128">Entrez éventuellement le **Code de rémunération** à utiliser pour acheter des congés.</span><span class="sxs-lookup"><span data-stu-id="ea260-128">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

14. <span data-ttu-id="ea260-129">Définissez éventuellement s’il faut utiliser l’ETP pour déterminer la quantité maximale pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="ea260-129">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

15. <span data-ttu-id="ea260-130">Pour créer une stratégie de vente, suivez les étapes 8 à 14 sous **Stratégie de vente**.</span><span class="sxs-lookup"><span data-stu-id="ea260-130">To create a sell policy, follow steps 8 through 14 under **Sell policy**.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="ea260-131">Ajouter la stratégie d’achat et de vente de congés à un plan de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="ea260-131">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="ea260-132">Dans la page **Congé et absence**, sélectionnez un plan de congé et d’absence.</span><span class="sxs-lookup"><span data-stu-id="ea260-132">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="ea260-133">Sous **Règles**, sélectionnez **Stratégie d’achat et de vente de congés**.</span><span class="sxs-lookup"><span data-stu-id="ea260-133">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea260-134">Voir également :</span><span class="sxs-lookup"><span data-stu-id="ea260-134">See also</span></span>

[<span data-ttu-id="ea260-135">Vue d’ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="ea260-135">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="ea260-136">Configurer les types de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="ea260-136">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="ea260-137">Régulariser les plans de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="ea260-137">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="ea260-138">Achat et vente de congés</span><span class="sxs-lookup"><span data-stu-id="ea260-138">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

