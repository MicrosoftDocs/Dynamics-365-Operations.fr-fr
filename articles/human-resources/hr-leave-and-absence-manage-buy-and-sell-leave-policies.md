---
title: Gérer les politiques d'achat et de vente de congés
description: Vous pouvez permettre aux employés d'acheter et de vendre des congés dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
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
ms.openlocfilehash: 859445f2b6e980b5960e512e69129f6a8fc6df2b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429011"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="067c5-103">Gérer les politiques d'achat et de vente de congés</span><span class="sxs-lookup"><span data-stu-id="067c5-103">Manage buy and sell leave policies</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="067c5-104">Vous pouvez permettre aux employés d'acheter des congés en créant une stratégie d'achat de congés.</span><span class="sxs-lookup"><span data-stu-id="067c5-104">You can enable employees to buy leave by creating a buy leave policy.</span></span>  

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="067c5-105">Permettre aux employés d'acheter et de vendre des congés</span><span class="sxs-lookup"><span data-stu-id="067c5-105">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="067c5-106">Dans la page **Paramètres de congé et d'absence**, sélectionnez **Oui** pour **Autoriser les employés à acheter des congés**.</span><span class="sxs-lookup"><span data-stu-id="067c5-106">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave**.</span></span> 

## <a name="create-a-buy-leave-policy"></a><span data-ttu-id="067c5-107">Créer une stratégie d'achat de congé</span><span class="sxs-lookup"><span data-stu-id="067c5-107">Create a buy leave policy</span></span>

1. <span data-ttu-id="067c5-108">Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="067c5-108">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="067c5-109">Sélectionnez **Stratégie d'achat et de vente de congés**.</span><span class="sxs-lookup"><span data-stu-id="067c5-109">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="067c5-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="067c5-110">Select **New**.</span></span>

4. <span data-ttu-id="067c5-111">Entrez un **Nom** et une **Description** pour la stratégie sous **Stratégie d'achat et de vente de congés**.</span><span class="sxs-lookup"><span data-stu-id="067c5-111">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="067c5-112">Sélectionnez un **Type de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="067c5-112">Select a **Policy type**.</span></span> 

   <span data-ttu-id="067c5-113">Les types de stratégie disponibles sont **Quantité** et **Heures par semaine**.</span><span class="sxs-lookup"><span data-stu-id="067c5-113">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="067c5-114">Sélectionnez **Quantité** pour entrer une **Quantité fixe** pour les quantités maximales que les employés peuvent acheter et vendre.</span><span class="sxs-lookup"><span data-stu-id="067c5-114">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="067c5-115">Si vous sélectionnez **Heures par semaine**, le temps de travail défini dans les horaires de travail attribués à l'employé sera utilisé pour déterminer la quantité maximale de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="067c5-115">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="067c5-116">Sélectionnez une **Date de début** et une **Date de fin** pour la stratégie.</span><span class="sxs-lookup"><span data-stu-id="067c5-116">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="067c5-117">Les demandes d'achat ou de vente de congés ne pourront être soumises que pendant cette période.</span><span class="sxs-lookup"><span data-stu-id="067c5-117">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="067c5-118">Sous **Stratégie d'achat**, sélectionnez **Équivalence temps plein** (ETP) pour calculer la quantité maximale au prorata de l'ETP défini pour le poste du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="067c5-118">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="067c5-119">Si le type de stratégie est **Quantité**, entrez une **Quantité maximale fixe**.</span><span class="sxs-lookup"><span data-stu-id="067c5-119">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

8. <span data-ttu-id="067c5-120">Sélectionnez **Ajouter** pour ajouter les types de congés à acheter par les collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="067c5-120">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="067c5-121">Vous pouvez ajouter plusieurs types de congés à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="067c5-121">You can add multiple leave types to the policy.</span></span> 

9. <span data-ttu-id="067c5-122">Entrer les **Mois de service** pour le type de congé afin d'autoriser différents mois de service pour déterminer la quantité maximale qu'un collaborateur peut acheter.</span><span class="sxs-lookup"><span data-stu-id="067c5-122">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

10. <span data-ttu-id="067c5-123">Entrez la **Quantité maximale** pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="067c5-123">Enter the **Maximum amount** for the leave type.</span></span> 

11. <span data-ttu-id="067c5-124">Entrez le **Taux** auquel le collaborateur achètera le congé.</span><span class="sxs-lookup"><span data-stu-id="067c5-124">Enter the **Rate** at which the employee will buy the leave.</span></span> 

12. <span data-ttu-id="067c5-125">Entrez éventuellement le **Code de rémunération** à utiliser pour acheter des congés.</span><span class="sxs-lookup"><span data-stu-id="067c5-125">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

13. <span data-ttu-id="067c5-126">Définissez éventuellement s'il faut utiliser l'ETP pour déterminer la quantité maximale pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="067c5-126">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="067c5-127">Ajouter la stratégie d'achat et de vente de congés à un plan de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="067c5-127">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="067c5-128">Dans la page **Congé et absence**, sélectionnez un plan de congé et d'absence.</span><span class="sxs-lookup"><span data-stu-id="067c5-128">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="067c5-129">Sous **Règles**, sélectionnez **Stratégie d'achat et de vente de congés**.</span><span class="sxs-lookup"><span data-stu-id="067c5-129">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="067c5-130">Voir également :</span><span class="sxs-lookup"><span data-stu-id="067c5-130">See also</span></span>

[<span data-ttu-id="067c5-131">Vue d'ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="067c5-131">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="067c5-132">Configurer les types de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="067c5-132">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="067c5-133">Régulariser les plans de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="067c5-133">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="067c5-134">Achat et vente de congés</span><span class="sxs-lookup"><span data-stu-id="067c5-134">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

