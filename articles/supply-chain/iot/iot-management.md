---
title: Surveiller et gérer l’intelligence IoT
description: Cette rubrique explique comment surveiller et gérer l’intelligence IoT.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 15021281b9ec33cd0552bca16e3054d0d3cdd589
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2020
ms.locfileid: "3803063"
---
# <a name="monitor-and-manage-iot-intelligence"></a><span data-ttu-id="d7714-103">Surveiller et gérer l’intelligence IoT</span><span class="sxs-lookup"><span data-stu-id="d7714-103">Monitor and manage IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d7714-104">Cette rubrique explique comment surveiller et gérer l’intelligence IoT.</span><span class="sxs-lookup"><span data-stu-id="d7714-104">This topic explains how to monitor and manage IoT Intelligence.</span></span>

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a><span data-ttu-id="d7714-105">Surveiller des scénarios dans Microsoft Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="d7714-105">Monitor scenarios in Microsoft Dynamics 365 Supply Chain Management</span></span>

<span data-ttu-id="d7714-106">Vous pouvez surveiller le traitement de l’intelligence IoT à plusieurs endroits :</span><span class="sxs-lookup"><span data-stu-id="d7714-106">You can monitor IoT Intelligence processing from several places:</span></span>

+ <span data-ttu-id="d7714-107">**Modules \> Contrôle de la production \> Recherches et états \> Intelligence IoT \> Notifications** – Affichez la liste des notifications non résolues.</span><span class="sxs-lookup"><span data-stu-id="d7714-107">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Notifications** – View the list of unresolved notifications.</span></span>
+ <span data-ttu-id="d7714-108">**Modules \> Contrôle de la production \> Recherches et états \> Intelligence IoT \> Notifications clôturées** – Affichez la liste des notifications résolues ou ignorées.</span><span class="sxs-lookup"><span data-stu-id="d7714-108">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Closed notifications** – View the list of notifications that have been resolved or dismissed.</span></span>
+ <span data-ttu-id="d7714-109">**Modules \> Contrôle de la production \> Recherches et états \> Intelligence IoT \> Clés métriques** – Affichez les clés métriques pour les graphiques des séries chronologiques **Statut des ressources**.</span><span class="sxs-lookup"><span data-stu-id="d7714-109">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Metric keys** – View the metric keys for the **Resource Status** times series charts.</span></span>
+ <span data-ttu-id="d7714-110">**Modules \> Contrôle de la production \> Contrôle et suivi de la production \> Statut des ressources** – Suivez des mesures spécifiques en utilisant la boite de dialogue **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="d7714-110">**Modules \> Production control \> Manufacturing execution \> Resource status** – Track specific metrics by using the **Configure** dialog box.</span></span> <span data-ttu-id="d7714-111">Si un scénario détecte une exception, une notification en affiche les détails.</span><span class="sxs-lookup"><span data-stu-id="d7714-111">If a scenario detects an exception, a notification shows the details of the exception.</span></span>
+ <span data-ttu-id="d7714-112">**Espaces de travail \> Gestion de l’atelier de production \> Notifications** – Affichez la liste des notifications non résolues</span><span class="sxs-lookup"><span data-stu-id="d7714-112">**Workspaces \> Production floor management \> Notifications** – View the list of unresolved notifications.</span></span>

## <a name="modify-a-running-iot-intelligence-scenario"></a><span data-ttu-id="d7714-113">Modifier un scénario d’intelligence IoT en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="d7714-113">Modify a running IoT Intelligence scenario</span></span>

<span data-ttu-id="d7714-114">Lorsqu’un scénario est en cours d’exécution, vous pouvez apporter les modifications suivantes :</span><span class="sxs-lookup"><span data-stu-id="d7714-114">When a scenario is running, you can make these changes:</span></span>

+ <span data-ttu-id="d7714-115">Ajouter de nouvelles définitions de schéma de capteur.</span><span class="sxs-lookup"><span data-stu-id="d7714-115">Add new sensor schema definitions.</span></span>
+ <span data-ttu-id="d7714-116">Sélectionner de nouvelles valeurs de données de signal.</span><span class="sxs-lookup"><span data-stu-id="d7714-116">Select new signal data values.</span></span>
+ <span data-ttu-id="d7714-117">Annuler la sélection des valeurs de données de signal existantes.</span><span class="sxs-lookup"><span data-stu-id="d7714-117">Cancel the selection of existing signal data values.</span></span>
+ <span data-ttu-id="d7714-118">Ajouter et mapper de nouvelles valeurs de données de signal.</span><span class="sxs-lookup"><span data-stu-id="d7714-118">Add and map new signal data values.</span></span>
+ <span data-ttu-id="d7714-119">Mettre à jour les valeurs de seuil.</span><span class="sxs-lookup"><span data-stu-id="d7714-119">Update threshold values.</span></span>

<span data-ttu-id="d7714-120">Lorsqu’un scénario est en cours d’exécution, ces modifications sont interdites :</span><span class="sxs-lookup"><span data-stu-id="d7714-120">When a scenario is running, these changes are prohibited:</span></span>

+ <span data-ttu-id="d7714-121">Supprimez ou modifiez les définitions de schéma actuellement utilisées par un scénario activé.</span><span class="sxs-lookup"><span data-stu-id="d7714-121">Delete or modify any schema definitions that are currently consumed by an enabled scenario.</span></span>
+ <span data-ttu-id="d7714-122">Modifiez les chemins de schéma sélectionnés du scénario activé.</span><span class="sxs-lookup"><span data-stu-id="d7714-122">Change the enabled scenario's selected schema paths.</span></span>

## <a name="simulation-options"></a><span data-ttu-id="d7714-123">Options de simulation</span><span class="sxs-lookup"><span data-stu-id="d7714-123">Simulation options</span></span>

<span data-ttu-id="d7714-124">Vous pouvez simuler des signaux de machine d’usine.</span><span class="sxs-lookup"><span data-stu-id="d7714-124">You can simulate factory machine signals.</span></span> <span data-ttu-id="d7714-125">Pour plus d’informations, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="d7714-125">For more information, see these topics:</span></span>

+ [<span data-ttu-id="d7714-126">Connecter IoT DevKit AZ3166 au hub IoT Azure</span><span class="sxs-lookup"><span data-stu-id="d7714-126">Connect IoT DevKit AZ3166 to Azure IoT Hub</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [<span data-ttu-id="d7714-127">Connecter le simulateur Raspberry Pi en ligne au hub IoT Azure (Node.js)</span><span class="sxs-lookup"><span data-stu-id="d7714-127">Connect Raspberry Pi online simulator to Azure IoT Hub (Node.js)</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [<span data-ttu-id="d7714-128">Présentation de l’accélérateur de solution de simulation de périphérique</span><span class="sxs-lookup"><span data-stu-id="d7714-128">Device Simulation solution accelerator overview</span></span>](https://docs.microsoft.com/azure/iot-accelerators/iot-accelerators-device-simulation-overview)
