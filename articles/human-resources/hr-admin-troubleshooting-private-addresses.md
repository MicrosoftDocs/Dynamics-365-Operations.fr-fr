---
title: Accéder aux adresses privées selon les rôles de sécurité
description: Cet article explique comment résoudre le problème où un client ne peut pas accéder aux adresses privées.
author: andreabichsel
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8daee1b645836e96a4bf3057cb317d5409d4583a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803919"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="58155-103">Accès aux adresses privées selon les rôles de sécurité</span><span class="sxs-lookup"><span data-stu-id="58155-103">Access to private addresses by security role</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="58155-104">**Problème**</span><span class="sxs-lookup"><span data-stu-id="58155-104">**Issue**</span></span>

<span data-ttu-id="58155-105">Une fois qu’un client duplique un rôle de sécurité et se connecte avec ce nouveau rôle, le client ne peut pas afficher les adresses marquées comme privées.</span><span class="sxs-lookup"><span data-stu-id="58155-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="58155-106">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="58155-106">**Resolution**</span></span>

<span data-ttu-id="58155-107">Pour résoudre ce problème, le client doit procéder comme suit pour le rôle de sécurité dupliqué.</span><span class="sxs-lookup"><span data-stu-id="58155-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="58155-108">Accédez à **Administration d’organisation \> Carnet d’adresses global \> Paramètres du carnet d’adresses global**.</span><span class="sxs-lookup"><span data-stu-id="58155-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="58155-109">Sous l’onglet **Sécurité de l’emplacement privé**, déplacez le nouveau rôle de sécurité de la liste **Rôles disponibles** vers la liste **Rôles sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="58155-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="58155-110">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="58155-110">Select **Save**.</span></span>

![Page des paramètres du carnet d’adresses global](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]