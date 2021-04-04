---
title: Configurer et gérer la journalisation de la base de données
description: Vous pouvez suivre les modifications apportées aux tables et aux champs dans Dynamics 365 Human Resources avec la journalisation de la base de données.
author: andreabichsel
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8057ebd0bc061c6bf78d8674c45e0885ffce681c
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467647"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="d3c11-103">Configurer et gérer la journalisation de la base de données</span><span class="sxs-lookup"><span data-stu-id="d3c11-103">Configure and manage database logging</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d3c11-104">Vous pouvez suivre les modifications apportées aux tables et aux champs dans Dynamics 365 Human Resources avec la journalisation de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d3c11-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="d3c11-105">Cette rubrique décrit comment :</span><span class="sxs-lookup"><span data-stu-id="d3c11-105">This topic describes how to:</span></span>

- <span data-ttu-id="d3c11-106">Gérer la sécurité et les performances pour la journalisation de la base de données</span><span class="sxs-lookup"><span data-stu-id="d3c11-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="d3c11-107">Paramétrer la connexion de la base de données</span><span class="sxs-lookup"><span data-stu-id="d3c11-107">Set up database logging</span></span>
- <span data-ttu-id="d3c11-108">Nettoyer les journaux de base de données</span><span class="sxs-lookup"><span data-stu-id="d3c11-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="d3c11-109">Présenter la journalisation de la base de données</span><span class="sxs-lookup"><span data-stu-id="d3c11-109">Overview of database logging</span></span>

<span data-ttu-id="d3c11-110">La journalisation de la base de données effectue le suivi des modifications apportées aux tables et aux champs dans Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d3c11-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="d3c11-111">Ces modifications incluent l’insertion, la mise à jour ou la suppression.</span><span class="sxs-lookup"><span data-stu-id="d3c11-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="d3c11-112">La journalisation de la base de données stocke un enregistrement des modifications apportées aux tables ou aux champs dans la table de journal de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d3c11-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="d3c11-113">Les utilisations commerciales de la journalisation de la base de données comprennent :</span><span class="sxs-lookup"><span data-stu-id="d3c11-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="d3c11-114">Création d’un enregistrement d’audit des modifications apportées à des tables spécifiques contenant des informations sensibles.</span><span class="sxs-lookup"><span data-stu-id="d3c11-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="d3c11-115">Suivi des transactions uniques.</span><span class="sxs-lookup"><span data-stu-id="d3c11-115">Tracking single transactions.</span></span> <span data-ttu-id="d3c11-116">La journalisation de la base de données n’est pas destinée au suivi des transactions automatisées qui s’exécutent dans des travaux par lots.</span><span class="sxs-lookup"><span data-stu-id="d3c11-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="d3c11-117">Sécurité pour la journalisation de la base de données</span><span class="sxs-lookup"><span data-stu-id="d3c11-117">Security for database logging</span></span>

<span data-ttu-id="d3c11-118">Les journaux de base de données peuvent contenir des données confidentielles.</span><span class="sxs-lookup"><span data-stu-id="d3c11-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="d3c11-119">Limitez l’accès pour inclure uniquement les rôles de sécurité qui ont besoin d’accéder aux données du journal.</span><span class="sxs-lookup"><span data-stu-id="d3c11-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="d3c11-120">Journalisation et performances de la base de données</span><span class="sxs-lookup"><span data-stu-id="d3c11-120">Database logging and performance</span></span>

<span data-ttu-id="d3c11-121">Bien que précieuse d’un point de vue commercial, la journalisation de la base de données peut être coûteuse en termes d’utilisation et de gestion des ressources.</span><span class="sxs-lookup"><span data-stu-id="d3c11-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="d3c11-122">Les implications de performance de la journalisation de la base de données comprennent :</span><span class="sxs-lookup"><span data-stu-id="d3c11-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="d3c11-123">La table des journaux de la base de données peut croître rapidement et entraîner une augmentation de la taille de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d3c11-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="d3c11-124">La croissance dépend de la quantité de données enregistrées que vous décidez de conserver.</span><span class="sxs-lookup"><span data-stu-id="d3c11-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="d3c11-125">Par défaut, la table des journaux de la base de données ne conserve que 30 jours de données de journal.</span><span class="sxs-lookup"><span data-stu-id="d3c11-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="d3c11-126">La journalisation de la base de données peut nuire aux processus automatisés de longue durée, tels que les importations de données de longue durée.</span><span class="sxs-lookup"><span data-stu-id="d3c11-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="d3c11-127">Utilisation optimale</span><span class="sxs-lookup"><span data-stu-id="d3c11-127">Best practices</span></span>

<span data-ttu-id="d3c11-128">Pour améliorer les performances, limitez les entrées de journal en sélectionnant des champs spécifiques à enregistrer au lieu de tables entières.</span><span class="sxs-lookup"><span data-stu-id="d3c11-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="d3c11-129">Pour aider à maintenir les performances globales, la journalisation de la base de données est limitée à 20 tables.</span><span class="sxs-lookup"><span data-stu-id="d3c11-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="d3c11-130">Seules les mises à jour peuvent être enregistrées pour des champs individuels.</span><span class="sxs-lookup"><span data-stu-id="d3c11-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="d3c11-131">Paramétrer la connexion de la base de données</span><span class="sxs-lookup"><span data-stu-id="d3c11-131">Set up database logging</span></span>

<span data-ttu-id="d3c11-132">Vous pouvez utiliser l’assistant **Consignation des modifications de base de données** pour configurer la journalisation de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d3c11-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="d3c11-133">L’assistant offre un moyen flexible de configurer la journalisation des tables ou des champs.</span><span class="sxs-lookup"><span data-stu-id="d3c11-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="d3c11-134">Accédez à **Administration système> liens> Base de données> Configuration du journal de base de données**.</span><span class="sxs-lookup"><span data-stu-id="d3c11-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="d3c11-135">Sélectionnez **Nouveau** pour démarrer l’assistant **Consignation des modifications de base de données**.</span><span class="sxs-lookup"><span data-stu-id="d3c11-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="d3c11-136">Suivez les instructions de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="d3c11-136">Complete the wizard.</span></span>

## <a name="clean-up-database-logs"></a><span data-ttu-id="d3c11-137">Nettoyer les journaux de base de données</span><span class="sxs-lookup"><span data-stu-id="d3c11-137">Clean up database logs</span></span>

<span data-ttu-id="d3c11-138">Vous pouvez supprimer tout ou partie des journaux de la base de données à l’aide des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3c11-138">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="d3c11-139">Sélectionnez tous les journaux pour une table particulière.</span><span class="sxs-lookup"><span data-stu-id="d3c11-139">Select all logs for a particular table.</span></span>
- <span data-ttu-id="d3c11-140">Sélectionnez des types spécifiques de journal de base de données.</span><span class="sxs-lookup"><span data-stu-id="d3c11-140">Select specific types of database log.</span></span>
- <span data-ttu-id="d3c11-141">Sélectionnez une date et une heure de création d’un journal.</span><span class="sxs-lookup"><span data-stu-id="d3c11-141">Select a date and time that a log was created.</span></span>

<span data-ttu-id="d3c11-142">Pour paramétrer le nettoyage des journaux de base de données, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d3c11-142">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="d3c11-143">Accédez à **Administration système> liens> Base de données> Journal de base de données**.</span><span class="sxs-lookup"><span data-stu-id="d3c11-143">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="d3c11-144">Sélectionnez **Nettoyer le journal**.</span><span class="sxs-lookup"><span data-stu-id="d3c11-144">Select **Clean up log**.</span></span>

2. <span data-ttu-id="d3c11-145">Choisissez une méthode de sélection des journaux à supprimer en entrant l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3c11-145">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="d3c11-146">ID table</span><span class="sxs-lookup"><span data-stu-id="d3c11-146">Table ID</span></span>
   - <span data-ttu-id="d3c11-147">Type de journal</span><span class="sxs-lookup"><span data-stu-id="d3c11-147">Type of log</span></span>
   - <span data-ttu-id="d3c11-148">Date et heure de création</span><span class="sxs-lookup"><span data-stu-id="d3c11-148">Created date and time</span></span>

3. <span data-ttu-id="d3c11-149">Utilisez l’onglet **Nettoyage des journaux de base de données** pour déterminer quand exécuter la tâche de nettoyage des journaux.</span><span class="sxs-lookup"><span data-stu-id="d3c11-149">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="d3c11-150">Par défaut, les journaux de base de données sont disponibles pendant 30 jours.</span><span class="sxs-lookup"><span data-stu-id="d3c11-150">By default, database logs are available for 30 days.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]