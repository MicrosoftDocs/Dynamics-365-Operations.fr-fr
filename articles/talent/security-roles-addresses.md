---
title: Accès aux adresses privées selon les rôles de sécurité
description: Cette rubrique explique comment résoudre le problème où un client ne peut pas accéder aux adresses privées.
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
ms.openlocfilehash: 58f3322ad64f7de07e17d193ff665bd6536a4070
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897095"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="a37ad-103">Accès aux adresses privées selon les rôles de sécurité</span><span class="sxs-lookup"><span data-stu-id="a37ad-103">Access to private addresses by security role</span></span>

<span data-ttu-id="a37ad-104">**Problème**</span><span class="sxs-lookup"><span data-stu-id="a37ad-104">**Issue**</span></span>

<span data-ttu-id="a37ad-105">Une fois qu'un client duplique un rôle de sécurité et se connecte avec ce nouveau rôle, le client ne peut pas afficher les adresses marquées comme privées.</span><span class="sxs-lookup"><span data-stu-id="a37ad-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="a37ad-106">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="a37ad-106">**Resolution**</span></span>

<span data-ttu-id="a37ad-107">Pour résoudre ce problème, le client doit procéder comme suit pour le rôle de sécurité dupliqué.</span><span class="sxs-lookup"><span data-stu-id="a37ad-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="a37ad-108">Accédez à **Administration d'organisation \> Carnet d'adresses global \> Paramètres du carnet d'adresses global**.</span><span class="sxs-lookup"><span data-stu-id="a37ad-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="a37ad-109">Sous l'onglet **Sécurité de l'emplacement privé**, déplacez le nouveau rôle de sécurité de la liste **Rôles disponibles** vers la liste **Rôles sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="a37ad-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="a37ad-110">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a37ad-110">Select **Save**.</span></span>

![Page des paramètres du carnet d'adresses global](media/GAD-parameters.png)
