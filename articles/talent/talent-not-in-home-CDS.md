---
title: Talent ne figure pas dans les applications Microsoft Dynamics 365 (Common Data Service 1.0)
description: Cette rubrique explique comment procéder si le client ne voit pas l'application Microsoft Dynamics 365 Talent parmi les applications Microsoft Dynamics 365.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 956af80a8ab2f454d9f523d3c74dda754ef0f793
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009374"
---
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a><span data-ttu-id="cdf9e-103">Talent ne figure pas dans les applications Microsoft Dynamics 365 (Common Data Service 1.0)</span><span class="sxs-lookup"><span data-stu-id="cdf9e-103">Talent doesn't appear among the Microsoft Dynamics 365 apps (Common Data Service 1.0)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cdf9e-104">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="cdf9e-104">**Issue**</span></span>

<span data-ttu-id="cdf9e-105">Le client ne voit pas à l'application Microsoft Dynamics 365 Talent parmi les applications Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cdf9e-105">The customer doesn't see the Microsoft Dynamics 365 Talent app among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="cdf9e-106">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="cdf9e-106">**Resolution**</span></span>

<span data-ttu-id="cdf9e-107">L'utilisateur doit être ajouté au rôle Créateur d'environnement pour l'environnement dans Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="cdf9e-107">The user must be added to the Environment Maker role for the environment in Microsoft PowerApps.</span></span>

1. <span data-ttu-id="cdf9e-108">L'utilisateur administrateur disposant d'une licence PowerApps Plan 2 doit ouvrir le [Portail d'administration PowerApps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="cdf9e-108">The admin user who has a PowerApps Plan 2 license must open the [PowerApps Admin portal](https://preview.admin.powerapps.com/).</span></span>
2. <span data-ttu-id="cdf9e-109">Sélectionnez **Environnements**, puis sélectionnez l'environnement approprié pour Talent.</span><span class="sxs-lookup"><span data-stu-id="cdf9e-109">Select **Environments**, and select the correct environment for Talent.</span></span>
3. <span data-ttu-id="cdf9e-110">Sous l'onglet **Sécurité**, sous l'onglet **Rôles d'environnement**, sélectionnez **Créateur d'environnement**.</span><span class="sxs-lookup"><span data-stu-id="cdf9e-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Onglet Rôles d'environnement](media/environment-roles.png)

4. <span data-ttu-id="cdf9e-112">Sous l'onglet **Utilisateurs**, ajoutez l'utilisateur ou votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cdf9e-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Onglet Utilisateurs](media/environment-maker.png)

5. <span data-ttu-id="cdf9e-114">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="cdf9e-114">Select **Save**.</span></span>
6. <span data-ttu-id="cdf9e-115">L'utilisateur doit à présent se connecter à [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="cdf9e-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>
7. <span data-ttu-id="cdf9e-116">Sélectionnez **synchroniser** pour mettre à jour les applications de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cdf9e-116">Select **Sync** to update the user apps.</span></span>

    ![Bouton Synchroniser](media/get-more.png)

    <span data-ttu-id="cdf9e-118">Une fois la synchronisation terminée, Talent apparaît sur la page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="cdf9e-118">After synchronization is completed, Talent will appear on the home page.</span></span>
