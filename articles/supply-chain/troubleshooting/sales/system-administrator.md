---
title: Les administrateurs système ne peuvent pas effacer les suspensions de commande car ils ne sont pas autorisés
description: Les administrateurs système ne peuvent pas effacer les suspensions de commande car ils ne sont pas autorisés.
author: SmithaNataraj
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: acabd6409d9b2860535335bc648bcc34304e0cb0
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026524"
---
# <a name="system-administrators-cant-clear-order-holds-because-they-arent-authorized"></a><span data-ttu-id="1d606-103">Les administrateurs système ne peuvent pas effacer les suspensions de commande car ils ne sont pas autorisés</span><span class="sxs-lookup"><span data-stu-id="1d606-103">System administrators can't clear order holds because they aren't authorized</span></span>

<span data-ttu-id="1d606-104">Numéro de la base de connaissances : 4614642</span><span class="sxs-lookup"><span data-stu-id="1d606-104">KB number: 4614642</span></span>

## <a name="symptoms"></a><span data-ttu-id="1d606-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="1d606-105">Symptoms</span></span>

<span data-ttu-id="1d606-106">Les administrateurs système ne peuvent pas effacer les suspensions de commande client à moins d'avoir le rôle spécifique qui est attribué dans le code de blocage de commande.</span><span class="sxs-lookup"><span data-stu-id="1d606-106">System administrators can't clear sales order holds unless they have the specific role that is assigned in the order hold code.</span></span>

## <a name="resolution"></a><span data-ttu-id="1d606-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="1d606-107">Resolution</span></span>

<span data-ttu-id="1d606-108">L'accès à certaines opérations, telles que la compensation des blocages de commande client, est régi par la mise en place d'une politique commerciale.</span><span class="sxs-lookup"><span data-stu-id="1d606-108">Access to some operations, such as clearing sales order holds, is driven by the setup of a business policy.</span></span> <span data-ttu-id="1d606-109">Les administrateurs système ne sont généralement pas autorisés à effectuer des opérations de ce type.</span><span class="sxs-lookup"><span data-stu-id="1d606-109">System administrators aren't typically allowed to perform operations of this type.</span></span> 

<span data-ttu-id="1d606-110">Le plus souvent, l'accès pour effectuer une tâche spécifique est régi par des stratégies d'entreprise, et seules des personnes spécifiques d'une organisation sont autorisées à effectuer cette tâche.</span><span class="sxs-lookup"><span data-stu-id="1d606-110">More often, access to perform a specific task is governed by business policies, and only specific persons in an organization are approved to perform that task.</span></span> <span data-ttu-id="1d606-111">Les exemples incluent les approbations qui résultent des approbations de workflow et des tâches spécifiques qui résultent d'une configuration de workflow.</span><span class="sxs-lookup"><span data-stu-id="1d606-111">Examples include approvals that are the result of workflow approvals and specific tasks that are the result of a workflow configuration.</span></span>

<span data-ttu-id="1d606-112">Bien qu'aucun flux de travail ne soit associé aux réservations de commande, le principe est similaire.</span><span class="sxs-lookup"><span data-stu-id="1d606-112">Although no workflow is associated with order holds, the principle is similar.</span></span> <span data-ttu-id="1d606-113">Un rôle pertinent désigne le groupe spécifique de personnes dans une organisation qui ont le droit de dégager des commandes.</span><span class="sxs-lookup"><span data-stu-id="1d606-113">A relevant role designates the specific group of people in an organization who have the right to clear order holds.</span></span> <span data-ttu-id="1d606-114">Ce droit ne doit pas nécessairement être accordé à tous les administrateurs, car cette approche enfreint la politique commerciale définie.</span><span class="sxs-lookup"><span data-stu-id="1d606-114">This right should not necessarily be granted to all administrators, because that approach violates the defined business policy.</span></span>
