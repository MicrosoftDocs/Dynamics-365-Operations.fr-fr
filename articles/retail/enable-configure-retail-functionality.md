---
title: "Initialiser les données de départ dans un nouvel environnement de vente au détail"
description: "Cet article décrit les données créées dans le cadre du processus d'initialisation de Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7636cd112e551caa86ebfbe3b74d7bd94c0f6b0d
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a><span data-ttu-id="848b6-103">Initialiser les données de départ dans un nouvel environnement de vente au détail</span><span class="sxs-lookup"><span data-stu-id="848b6-103">Initialize seed data in a new Retail environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="848b6-104">Cet article décrit les données créées dans le cadre du processus d'initialisation de Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="848b6-104">This article describes the data that's created as part of the initialization process for Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="848b6-105">Une fois la solution Retail déployée via les Microsoft Dynamics Lifecycle Services (LCS), vous devez initialiser la configuration de vente au détail pour créer les données de configuration de base.</span><span class="sxs-lookup"><span data-stu-id="848b6-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span> <span data-ttu-id="848b6-106">**Important :** avant d'initialiser la configuration de vente au détail, vérifiez que vous avez spécifié une langue et une adresse postale pour chaque entité juridique dans laquelle vous paramètrez des magasins de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="848b6-106">**Important:** Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="848b6-107">Cette étape doit être exécutée pour chaque entité juridique que vous utilisez pour la vente au détail.</span><span class="sxs-lookup"><span data-stu-id="848b6-107">This step must be completed for each legal entity that you use for retail.</span></span> <span data-ttu-id="848b6-108">Pour initialiser la configuration de vente au détail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="848b6-108">To initialize the retail configuration, follow these steps.</span></span>

1.  <span data-ttu-id="848b6-109">Démarrez le client Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="848b6-109">Start the Dynamics 365 for Retail client.</span></span>
2.  <span data-ttu-id="848b6-110">Cliquez sur **Vente au détail** &gt; **Configuration du siège** &gt; **Paramètres** &gt; **Paramètres des ventes au détail**.</span><span class="sxs-lookup"><span data-stu-id="848b6-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3.  <span data-ttu-id="848b6-111">Cliquez sur **Initialiser**.</span><span class="sxs-lookup"><span data-stu-id="848b6-111">Click **Initialize**.</span></span>

<span data-ttu-id="848b6-112">L'initialisation crée les données de configuration par défaut suivantes :</span><span class="sxs-lookup"><span data-stu-id="848b6-112">Initialization creates the following default configuration data:</span></span>

-   <span data-ttu-id="848b6-113">Tâches et sous-tâches de Retail Planification</span><span class="sxs-lookup"><span data-stu-id="848b6-113">Retail scheduler jobs and subjobs</span></span>
-   <span data-ttu-id="848b6-114">Schéma de canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="848b6-114">Retail channel schema</span></span>
-   <span data-ttu-id="848b6-115">Programmes de distribution de vente au détail</span><span class="sxs-lookup"><span data-stu-id="848b6-115">Retail distribution schedules</span></span>
-   <span data-ttu-id="848b6-116">Structures d'écran par défaut, qui incluent des grilles de boutons, des images et des rubriques</span><span class="sxs-lookup"><span data-stu-id="848b6-116">Default screen layouts, which include button grids, images, and themes</span></span>
-   <span data-ttu-id="848b6-117">Informations sur le fuseau horaire</span><span class="sxs-lookup"><span data-stu-id="848b6-117">Time zone information</span></span>
-   <span data-ttu-id="848b6-118">Opérations de point de vente (PDV)</span><span class="sxs-lookup"><span data-stu-id="848b6-118">Point-of-sale (POS) operations</span></span>
-   <span data-ttu-id="848b6-119">Autorisations PDV</span><span class="sxs-lookup"><span data-stu-id="848b6-119">POS permissions</span></span>
-   <span data-ttu-id="848b6-120">Rapports sur les canaux</span><span class="sxs-lookup"><span data-stu-id="848b6-120">Channel reports</span></span>
-   <span data-ttu-id="848b6-121">Métadonnées d'attribut</span><span class="sxs-lookup"><span data-stu-id="848b6-121">Attribute metadata</span></span>
-   <span data-ttu-id="848b6-122">Modèles de validation de l'entité</span><span class="sxs-lookup"><span data-stu-id="848b6-122">Entity validation templates</span></span>
-   <span data-ttu-id="848b6-123">Traitement par lots pour vider l'historique des sessions Commerce Data Exchange</span><span class="sxs-lookup"><span data-stu-id="848b6-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="848b6-124">En outre, l'enregistrement qui est liée à PCI (Payment Card Industry) est activé pour la base de données Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="848b6-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Dynamics 365 for Retail database.</span></span> <span data-ttu-id="848b6-125">**Remarque :** il existe une option pour configurer séparément le Retail Planification.</span><span class="sxs-lookup"><span data-stu-id="848b6-125">**Note:** There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="848b6-126">Cette option permet de rétablir les paramètres par défaut de la configuration de Retail Planification.</span><span class="sxs-lookup"><span data-stu-id="848b6-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span> <span data-ttu-id="848b6-127">Une fois l'initialisation terminée, vous devez configurer les données de vente au détail supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="848b6-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="848b6-128">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="848b6-128">Here are some examples:</span></span>

-   <span data-ttu-id="848b6-129">Paramètres des ventes au détail</span><span class="sxs-lookup"><span data-stu-id="848b6-129">Retail parameters</span></span>
-   <span data-ttu-id="848b6-130">Paramètres de Retail scheduler</span><span class="sxs-lookup"><span data-stu-id="848b6-130">Retail scheduler parameters</span></span>
-   <span data-ttu-id="848b6-131">Canaux de vente au détail</span><span class="sxs-lookup"><span data-stu-id="848b6-131">Retail channels</span></span>
-   <span data-ttu-id="848b6-132">Registres et périphériques</span><span class="sxs-lookup"><span data-stu-id="848b6-132">Registers and devices</span></span>
-   <span data-ttu-id="848b6-133">Assortiments</span><span class="sxs-lookup"><span data-stu-id="848b6-133">Assortments</span></span>





