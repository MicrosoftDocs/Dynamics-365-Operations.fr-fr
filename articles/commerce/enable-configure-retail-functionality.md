---
title: Initialisation des données d'origine dans de nouveaux environnements Commerce
description: Cet article décrit les données créées dans le cadre du processus d'initialisation de Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a12bd7a178d8d40db8c919410a00fbf021625f50
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238748"
---
# <a name="initialize-seed-data-in-new-commerce-environments"></a><span data-ttu-id="1d958-103">Initialisation des données d'origine dans de nouveaux environnements Commerce</span><span class="sxs-lookup"><span data-stu-id="1d958-103">Initialize seed data in new Commerce environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1d958-104">Cet article décrit les données créées dans le cadre du processus d'initialisation de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1d958-104">This article describes the data that's created as part of the initialization process for Dynamics 365 Commerce.</span></span>

<span data-ttu-id="1d958-105">Une fois la solution Commerce déployée via Microsoft Dynamics Lifecycle Services (LCS), vous devez initialiser la configuration de Commerce pour créer les données de configuration de base.</span><span class="sxs-lookup"><span data-stu-id="1d958-105">After the Commerce solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the Commerce configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d958-106">Avant d'initialiser la configuration de Commerce, vérifiez que vous avez spécifié une langue et une adresse postale pour chaque entité juridique dans laquelle vous paramétrez des magasins.</span><span class="sxs-lookup"><span data-stu-id="1d958-106">Before you initialize the commerce configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up stores.</span></span> <span data-ttu-id="1d958-107">Cette étape doit être exécutée pour chaque entité juridique que vous utilisez pour Commerce.</span><span class="sxs-lookup"><span data-stu-id="1d958-107">This step must be completed for each legal entity that you use for commerce.</span></span>

<span data-ttu-id="1d958-108">Pour initialiser la configuration, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1d958-108">To initialize the configuration, follow these steps.</span></span>

1. <span data-ttu-id="1d958-109">Démarrez le client Commerce.</span><span class="sxs-lookup"><span data-stu-id="1d958-109">Start the Commerce client.</span></span>
2. <span data-ttu-id="1d958-110">Cliquez sur **Commerce et vente au détail** &gt; **Configuration du siège** &gt; **Paramètres** &gt; **Paramètres des ventes au détail**.</span><span class="sxs-lookup"><span data-stu-id="1d958-110">Click **Retail and Commerce** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Commerce parameters**.</span></span>
3. <span data-ttu-id="1d958-111">Cliquez sur **Initialiser**.</span><span class="sxs-lookup"><span data-stu-id="1d958-111">Click **Initialize**.</span></span>

<span data-ttu-id="1d958-112">L'initialisation crée les données de configuration par défaut suivantes :</span><span class="sxs-lookup"><span data-stu-id="1d958-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="1d958-113">Tâches et sous-tâches de Planificateur de commerce</span><span class="sxs-lookup"><span data-stu-id="1d958-113">Commerce scheduler jobs and subjobs</span></span>
- <span data-ttu-id="1d958-114">Schéma de canal commercial</span><span class="sxs-lookup"><span data-stu-id="1d958-114">Commerce channel schema</span></span>
- <span data-ttu-id="1d958-115">Programmes de distribution Commerce</span><span class="sxs-lookup"><span data-stu-id="1d958-115">Commerce distribution schedules</span></span>
- <span data-ttu-id="1d958-116">Structures d'écran par défaut, qui incluent des grilles de boutons, des images et des rubriques</span><span class="sxs-lookup"><span data-stu-id="1d958-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="1d958-117">Informations sur le fuseau horaire</span><span class="sxs-lookup"><span data-stu-id="1d958-117">Time zone information</span></span>
- <span data-ttu-id="1d958-118">Opérations de point de vente (PDV)</span><span class="sxs-lookup"><span data-stu-id="1d958-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="1d958-119">Autorisations PDV</span><span class="sxs-lookup"><span data-stu-id="1d958-119">POS permissions</span></span>
- <span data-ttu-id="1d958-120">Rapports sur les canaux</span><span class="sxs-lookup"><span data-stu-id="1d958-120">Channel reports</span></span>
- <span data-ttu-id="1d958-121">Métadonnées d'attribut</span><span class="sxs-lookup"><span data-stu-id="1d958-121">Attribute metadata</span></span>
- <span data-ttu-id="1d958-122">Modèles de validation de l'entité</span><span class="sxs-lookup"><span data-stu-id="1d958-122">Entity validation templates</span></span>
- <span data-ttu-id="1d958-123">Traitement par lots pour vider l'historique des sessions Commerce Data Exchange</span><span class="sxs-lookup"><span data-stu-id="1d958-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="1d958-124">En outre, l'enregistrement qui est lié à PCI (Payment Card Industry) est activé pour la base de données Commerce.</span><span class="sxs-lookup"><span data-stu-id="1d958-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Commerce database.</span></span>

> [!NOTE]
> <span data-ttu-id="1d958-125">Il existe une option pour configurer séparément le Planificateur de commerce.</span><span class="sxs-lookup"><span data-stu-id="1d958-125">There is an option to separately configure the Commerce scheduler.</span></span> <span data-ttu-id="1d958-126">Cette option permet de rétablir les paramètres par défaut de la configuration du Planificateur de commerce.</span><span class="sxs-lookup"><span data-stu-id="1d958-126">This option lets you reset the Commerce scheduler configuration to its default settings.</span></span>

<span data-ttu-id="1d958-127">Une fois l'initialisation terminée, vous devez configurer les données de Commerce supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="1d958-127">After initialization is completed, you must configure additional commerce data.</span></span> <span data-ttu-id="1d958-128">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="1d958-128">Here are some examples:</span></span>

- <span data-ttu-id="1d958-129">Paramètres commerciaux</span><span class="sxs-lookup"><span data-stu-id="1d958-129">Commerce parameters</span></span>
- <span data-ttu-id="1d958-130">Paramètres de planification commerciale</span><span class="sxs-lookup"><span data-stu-id="1d958-130">Commerce scheduler parameters</span></span>
- <span data-ttu-id="1d958-131">Canaux de Commerce</span><span class="sxs-lookup"><span data-stu-id="1d958-131">Commerce channels</span></span>
- <span data-ttu-id="1d958-132">Registres et périphériques</span><span class="sxs-lookup"><span data-stu-id="1d958-132">Registers and devices</span></span>
- <span data-ttu-id="1d958-133">Assortiments</span><span class="sxs-lookup"><span data-stu-id="1d958-133">Assortments</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]