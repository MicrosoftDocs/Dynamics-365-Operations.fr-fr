---
title: "Paramétrer les alertes de fraude"
description: "Cette rubrique décrit le paramétrage des règles pour alerter les représentants du service client en cas d'informations potentiellement frauduleuses lorsque des commandes sont traitées. Vous pouvez définir des codes spécifiques pour mettre en attente automatiquement ou manuellement des commandes suspectes."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 09d80015298c3d0219b6ffb290dc456990536a62
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-fraud-alerts"></a><span data-ttu-id="3d606-104">Paramétrer les alertes de fraude</span><span class="sxs-lookup"><span data-stu-id="3d606-104">Set up fraud alerts</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="3d606-105">Cette rubrique décrit le paramétrage des règles pour alerter les représentants du service client en cas d'informations potentiellement frauduleuses lorsque des commandes sont traitées.</span><span class="sxs-lookup"><span data-stu-id="3d606-105">This topic explains how to set up rules to alert customer service representatives of potentially fraudulent information when orders are processed.</span></span> <span data-ttu-id="3d606-106">Vous pouvez définir des codes spécifiques pour mettre en attente automatiquement ou manuellement des commandes suspectes.</span><span class="sxs-lookup"><span data-stu-id="3d606-106">You can define specific codes to use to automatically or manually put suspicious orders on hold.</span></span> 

<span data-ttu-id="3d606-107">Avant de paramétrer et d'utiliser des règles de contrôle de fraude, vous devez activer le contrôle de fraude et définir les valeurs de base du contrôle de fraude dans les paramètres du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="3d606-107">Before you set up and use fraud checking rules, you must enable fraud checking and define the basic fraud checking values in the call center parameters.</span></span> <span data-ttu-id="3d606-108">Il existe deux types de règles de fraude :</span><span class="sxs-lookup"><span data-stu-id="3d606-108">There are two types of fraud rules:</span></span>

-   <span data-ttu-id="3d606-109">Les **règles statiques** utilisent une valeur spécifique, telle qu'un numéro de téléphone qui a été mis sur la liste noire.</span><span class="sxs-lookup"><span data-stu-id="3d606-109">**Static rules** use a specific value, such as a phone number that has been blacklisted.</span></span>
-   <span data-ttu-id="3d606-110">Les **règles dynamiques** peuvent comporter des variables et des conditions.</span><span class="sxs-lookup"><span data-stu-id="3d606-110">**Dynamic rules** can be composed from variables and conditions.</span></span>

<span data-ttu-id="3d606-111">Avant de créer une règle dynamique, vous devez créer les variables et les conditions qui définissent ce à quoi la règle s'applique et quand elle doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="3d606-111">Before you create a dynamic rule, you must create the variables and conditions that define who the rule applies to and when the rule should be applied.</span></span> <span data-ttu-id="3d606-112">Par exemple, vous pouvez créer une règle qui détermine qu'à chaque fois que le client 1202 passe une commande d'un montant de 1 000,00 ou plus, sa commande sera mise en attente jusqu'à ce que le paiement du client puisse être vérifié.</span><span class="sxs-lookup"><span data-stu-id="3d606-112">For example, you want to create a rule to require that any sales order that customer 1202 places that is worth 1,000.00 or more be put on hold until the customer payment can be verified.</span></span> <span data-ttu-id="3d606-113">Dans ce cas, les variables sont le client 1202 et un total de commande de 1 000,00.</span><span class="sxs-lookup"><span data-stu-id="3d606-113">In this case, the variables are customer 1202 and an order total of 1,000.00.</span></span> <span data-ttu-id="3d606-114">La condition spécifie que si le client 1202 passe une commande, et que le montant total de la commande est égal ou supérieur à 1 000.00, la commande client doit être mise en attente jusqu'à ce que le paiement client puisse être vérifié.</span><span class="sxs-lookup"><span data-stu-id="3d606-114">The condition specifies that if customer 1202 places an order, and the total amount of the order is equal to or more than 1,000.00, the sales order must be put on hold until the customer payment can be verified.</span></span>




