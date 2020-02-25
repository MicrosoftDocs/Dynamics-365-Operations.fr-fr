---
title: Tâches périodiques de gestion des crédits
description: Cette rubrique décrit les tâches périodiques qui sont une partie nécessaire du processus de gestion des limites de crédit pour les clients.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: df3b0b239fe542eab80fa92057248328d3f5188f
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015223"
---
# <a name="periodic-credit-management-tasks"></a><span data-ttu-id="d0a2f-103">Tâches périodiques de gestion des crédits</span><span class="sxs-lookup"><span data-stu-id="d0a2f-103">Periodic credit management tasks</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="d0a2f-104">Cette rubrique décrit les tâches périodiques qui sont une partie nécessaire du processus de gestion des limites de crédit pour les clients.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-104">This topic describes the periodic tasks that are a necessary part of the process of managing credit limits for customers.</span></span>

## <a name="update-risk-scores"></a><span data-ttu-id="d0a2f-105">Mettre à jour les scores de risque</span><span class="sxs-lookup"><span data-stu-id="d0a2f-105">Update risk scores</span></span>

<span data-ttu-id="d0a2f-106">À mesure que les entreprises évoluent et que les circonstances changent, les risques de crédit pour un client donné peuvent également changer.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-106">As businesses evolve and circumstances change, the credit risks for a given customer can also change.</span></span> <span data-ttu-id="d0a2f-107">Pour aider à maintenir des limites de crédit appropriées pour vos clients, vous devez revoir périodiquement les critères de chaque score de risque et mettre à jour les scores de chaque client.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-107">To help maintain appropriate credit limits for your customers, you must periodically review the criteria for each risk score and update the scores for each customer.</span></span> <span data-ttu-id="d0a2f-108">Vous pouvez mettre à jour les scores suivants en utilisant la page **Mettre à jour les scores de risque** (**Crédit et relances \> Tâches périodiques \> Gestion de crédit \> Mettre à jour les scores de risque**).</span><span class="sxs-lookup"><span data-stu-id="d0a2f-108">You can update the following scores by using the **Update risk scores** page (**Credit and collections \> Periodic tasks \> Credit management \> Update risk scores**).</span></span> <span data-ttu-id="d0a2f-109">Tous les calculs définis par l'utilisateur sont également traités.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-109">All user-defined calculations are also processed.</span></span>

- <span data-ttu-id="d0a2f-110">**Jours de paiement moyens** - Ce score est le nombre moyen de jours qu'un client prend pour payer ses factures.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-110">**Average payment days** – This score is the average number of days that a customer takes to pay invoices.</span></span>
- <span data-ttu-id="d0a2f-111">**Client depuis** - Ce score est le nombre d'années qu'un client a été client de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-111">**Customer since** – This score is the number of years that a customer has been a customer of your organization.</span></span>
- <span data-ttu-id="d0a2f-112">**En affaires depuis** - Ce score est le nombre d'années d'activité d'un client.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-112">**In business since** – This score is the number of years that a customer has been in business.</span></span> <span data-ttu-id="d0a2f-113">Il utilise la valeur du champ **Début d'activité** sur la page **Clients**.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-113">It uses the value of the **Business start** field on the **Customers** page.</span></span>
- <span data-ttu-id="d0a2f-114">**Ventes quotidiennes restantes** - Ce score est basé sur le bilan de la comptabilité client, le chiffre d'affaires et le nombre de jours pour la période précédente de 12 mois.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-114">**Days sales outstanding** – This score is based on the accounts receivable balance, sales revenue, and number of days for the previous 12-month period.</span></span>
- <span data-ttu-id="d0a2f-115">**Solde moyen** - Ce score est basé sur le bilan de la comptabilité client pour la période précédente de 12 mois.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-115">**Average balance** – This score is based on the accounts receivable balance for the previous 12-month period.</span></span>
- <span data-ttu-id="d0a2f-116">**Groupe de gestion des crédits**, **Statut du compte** et **Pays** - Ces scores utilisent les informations du client.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-116">**Credit management group**, **Account status**, and **Country** – These scores use information from the customer.</span></span>

## <a name="update-customer-balance-statistics"></a><span data-ttu-id="d0a2f-117">Mettre à jour les statistiques de solde client</span><span class="sxs-lookup"><span data-stu-id="d0a2f-117">Update customer balance statistics</span></span>

<span data-ttu-id="d0a2f-118">Vous pouvez exécuter le processus **Mettre à jour les statistiques de solde client** pour mettre à jour le calcul des statistiques de solde indiquées sur la page **Demande de statistiques de solde**.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-118">You can run the **Update customer balance statistics** process to update the calculation of balance statistics that is shown on the **Balance statistics inquiry** page.</span></span> <span data-ttu-id="d0a2f-119">Ces informations sont utilisées pour calculer les scores de risque et les valeurs qui sont affichées dans les récapitulatifs des statistiques de crédit de la page **Client**.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-119">This information is used to calculate risk scores and the values that are shown in the credit statistics FactBoxes on the **Customer** page.</span></span>

<span data-ttu-id="d0a2f-120">Lorsque vous exécutez le processus, il met à jour les statistiques de solde client pour un seul client.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-120">When you run the process, it updates customer balance statistics for a single customer.</span></span> <span data-ttu-id="d0a2f-121">Pour configurer un traitement par lots pour exécuter le processus pour plusieurs clients, vous pouvez utiliser la page **Calculer les statistiques de solde** (**Gestion de crédit \> Tâches périodiques \> Calculer les statistiques de solde**).</span><span class="sxs-lookup"><span data-stu-id="d0a2f-121">To set up a batch job to run the process for multiple customers, you can use the **Calculate balance statistics** page (**Credit management \> Periodic tasks \> Calculate balance statistics**).</span></span>
