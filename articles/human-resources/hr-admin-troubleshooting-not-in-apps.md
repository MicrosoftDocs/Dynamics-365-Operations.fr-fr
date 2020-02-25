---
title: Human Resources n'apparaît pas dans les applications Microsoft Dynamics 365
description: Cet article explique comment procéder si le client ne voit pas l'application Microsoft Dynamics 365 Human Resources parmi les applications Microsoft Dynamics 365.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d39e6ef4168f08f20b92979a296ed088744ad0da
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009088"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a><span data-ttu-id="1fcda-103">Human Resources n'apparaît pas dans les applications Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1fcda-103">Human Resources doesn't appear in Microsoft Dynamics 365 apps</span></span>

<span data-ttu-id="1fcda-104">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="1fcda-104">**Issue**</span></span>

<span data-ttu-id="1fcda-105">Le client ne voit pas Dynamics 365 Human Resources parmi les applications Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1fcda-105">The customer doesn't see Dynamics 365 Human Resources among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="1fcda-106">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="1fcda-106">**Resolution**</span></span>

<span data-ttu-id="1fcda-107">L'utilisateur doit être ajouté au rôle Créateur d'environnement pour l'environnement dans Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="1fcda-107">The user must be added to the Environment Maker role for the environment in Microsoft Power Apps.</span></span>

1. <span data-ttu-id="1fcda-108">L'utilisateur administrateur disposant d'une licence Power Apps Plan 2 doit ouvrir le [Portail d'administration Power Apps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="1fcda-108">The admin user who has a Power Apps Plan 2 license must open the [Power Apps Admin portal](https://preview.admin.powerapps.com/).</span></span>

2. <span data-ttu-id="1fcda-109">Sélectionnez **Environnements**, puis sélectionnez l'environnement approprié pour Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1fcda-109">Select **Environments**, and select the correct environment for Human Resources.</span></span>

3. <span data-ttu-id="1fcda-110">Sous l'onglet **Sécurité**, sous l'onglet **Rôles d'environnement**, sélectionnez **Créateur d'environnement**.</span><span class="sxs-lookup"><span data-stu-id="1fcda-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Onglet Rôles d'environnement](media/environment-roles.png)

4. <span data-ttu-id="1fcda-112">Sous l'onglet **Utilisateurs**, ajoutez l'utilisateur ou votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1fcda-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Onglet Utilisateurs](media/environment-maker.png)

5. <span data-ttu-id="1fcda-114">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1fcda-114">Select **Save**.</span></span>

6. <span data-ttu-id="1fcda-115">L'utilisateur doit à présent se connecter à [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="1fcda-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>

7. <span data-ttu-id="1fcda-116">Sélectionnez **synchroniser** pour mettre à jour les applications de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1fcda-116">Select **Sync** to update the user apps.</span></span>

    ![Bouton Synchroniser](media/get-more.png)

    <span data-ttu-id="1fcda-118">Une fois la synchronisation terminée, Human Resources apparaît sur la page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="1fcda-118">After synchronization is completed, Human Resources will appear on the home page.</span></span>
