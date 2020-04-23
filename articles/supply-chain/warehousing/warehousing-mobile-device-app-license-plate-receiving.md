---
title: Réception du contenant via l'application mobile Entrepôt
description: Cette rubrique explique comment configurer l'application mobile Entrepôt pour prendre en charge l'utilisation d'un processus de réception de contenant pour recevoir le stock physique.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 98cd608edea1d5365d0d3532244f1fcdb6293d3c
ms.sourcegitcommit: 3a823444005d316bd95fc663e2dbc8252ac7d93a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261330"
---
# <a name="license-plate-receiving-via-the-warehousing-mobile-app"></a><span data-ttu-id="1b7de-103">Réception du contenant via l'application mobile Entrepôt</span><span class="sxs-lookup"><span data-stu-id="1b7de-103">License plate receiving via the Warehousing mobile app</span></span>

<span data-ttu-id="1b7de-104">Cette rubrique explique comment configurer l'application mobile Entrepôt pour prendre en charge l'utilisation d'un processus de réception de contenant pour recevoir le stock physique.</span><span class="sxs-lookup"><span data-stu-id="1b7de-104">This topic explains how to set up the Warehousing mobile app so that it supports using a license plate receiving process to receive physical inventory.</span></span>

<span data-ttu-id="1b7de-105">Vous pouvez utiliser cette fonctionnalité pour enregistrer rapidement la réception du stock entrant lié à un avis préalable d'expédition (APE).</span><span class="sxs-lookup"><span data-stu-id="1b7de-105">You can use this functionality to quickly record the receipt of inbound inventory that is related to an advance ship notice (ASN).</span></span> <span data-ttu-id="1b7de-106">Le système crée automatiquement un APE lorsque des processus de gestion d'entrepôt sont utilisés pour expédier un ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="1b7de-106">The system automatically creates an ASN when warehouse management processes are used to ship a transfer order.</span></span> <span data-ttu-id="1b7de-107">Pour le processus de commande fournisseur, un APE peut être enregistré manuellement ou il peut être automatiquement importé à l'aide d'un processus d'entité de données APE entrant.</span><span class="sxs-lookup"><span data-stu-id="1b7de-107">For the purchase order process, an ASN can be manually recorded, or it can be automatically imported by using an inbound ASN data entity process.</span></span>

<span data-ttu-id="1b7de-108">Les données de l'APE sont liées aux chargements et expéditions via les *structures d'emballage*, où les palettes (contenants parent) peuvent contenir des caisses (contenants imbriqués).</span><span class="sxs-lookup"><span data-stu-id="1b7de-108">The ASN data is linked to loads and shipments via the *packing structures*, where pallets (parent license plates) can contain cases (nested license plates).</span></span>

> [!NOTE]
> <span data-ttu-id="1b7de-109">Pour réduire le nombre de transactions de stock lorsque des structures d'emballage qui ont des contenants imbriqués sont utilisées, le système enregistre l'inventaire physique disponible sur le contenant parent.</span><span class="sxs-lookup"><span data-stu-id="1b7de-109">To reduce the number of inventory transactions when packing structures that have nested license plates are used, the system records the physical on-hand inventory on the parent license plate.</span></span> <span data-ttu-id="1b7de-110">Pour déclencher le mouvement de l'inventaire physique en stock du contenant parent vers les contenants imbriqués, en fonction des données de structure d'emballage, l'appareil mobile doit fournir un élément de menu basé sur le processus de création de travaux *Conditionner dans des contenants imbriqués*.</span><span class="sxs-lookup"><span data-stu-id="1b7de-110">To trigger the movement of the physical on-hand inventory from the parent license plate to the nested license plates, based on the packing structure data, the mobile device must provide a menu item that is based on the *Pack to nested license plates* work creation process.</span></span>

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a><span data-ttu-id="1b7de-111">Afficher ou ignorer la page récapitulative de réception</span><span class="sxs-lookup"><span data-stu-id="1b7de-111">Show or skip the receiving summary page</span></span>

<span data-ttu-id="1b7de-112">Vous pouvez utiliser la fonctionnalité *Contrôler s'il faut afficher une page récapitulative de réception sur les appareils mobiles* pour bénéficier d'un flux d'application Entrepôt détaillé supplémentaire dans le cadre du processus de réception des contenants.</span><span class="sxs-lookup"><span data-stu-id="1b7de-112">You can use the *Control whether to display a receiving summary page on mobile devices* feature to take advantage of an additional detailed Warehouse app flow as part of the license plate receiving process.</span></span>

<span data-ttu-id="1b7de-113">Avant de pouvoir utiliser cette fonctionnalité, vous devez l'activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="1b7de-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="1b7de-114">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1b7de-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="1b7de-115">Dans l'espace de travail **Gestion des fonctionnalités**, cette fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="1b7de-115">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="1b7de-116">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="1b7de-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="1b7de-117">**Nom de la fonctionnalité :** *Contrôler s'il faut afficher une page récapitulative de réception sur les appareils mobiles*</span><span class="sxs-lookup"><span data-stu-id="1b7de-117">**Feature name:** *Control whether to display a receiving summary page on mobile devices*</span></span>

<span data-ttu-id="1b7de-118">Lorsque cette fonction est activée, les options de menu d'appareil mobile pour la réception des contenants ou la réception et le rangement des contenants fourniront un paramètre **Afficher la page récapitulative de réception**.</span><span class="sxs-lookup"><span data-stu-id="1b7de-118">When this feature is turned on, mobile device menu items for license plate receiving or license plate receiving and put-away will provide a **Display receiving summary page** setting.</span></span> <span data-ttu-id="1b7de-119">Ce paramètre a les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1b7de-119">This setting has the following options:</span></span>

- <span data-ttu-id="1b7de-120">**Afficher un résumé détaillé** - Pendant la réception des contenants, les collaborateurs verront une page supplémentaire qui affiche les informations complètes de l'APE.</span><span class="sxs-lookup"><span data-stu-id="1b7de-120">**Display a detailed summary** – During license plate receiving, workers will see an extra page that shows the full ASN information.</span></span>
- <span data-ttu-id="1b7de-121">**Ignorer le récapitulatif** - Les collaborateurs ne verront pas les informations complètes de l'APE.</span><span class="sxs-lookup"><span data-stu-id="1b7de-121">**Skip the summary** – Workers won't see the full ASN information.</span></span> <span data-ttu-id="1b7de-122">Les collaborateurs de l'entrepôt ne sont également pas en mesure de définir un code de disposition ou d'ajouter des exceptions pendant le processus de réception.</span><span class="sxs-lookup"><span data-stu-id="1b7de-122">Warehouse workers also won't be able to set a disposition code or add exceptions during the receiving process.</span></span>

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a><span data-ttu-id="1b7de-123">Empêcher les contenants expédiés par ordre de transfert d'être utilisés dans des entrepôts autres que l'entrepôt de destination</span><span class="sxs-lookup"><span data-stu-id="1b7de-123">Prevent transfer order–shipped license plates from being used at warehouses other than the destination warehouse</span></span>

<span data-ttu-id="1b7de-124">Un processus de réception des contenants ne peut pas être utilisé si un APE contient un ID de contenant qui existe déjà et possède des données physiques à portée de main à un emplacement d'entrepôt autre que l'emplacement de l'entrepôt où l'enregistrement de contenant a lieu.</span><span class="sxs-lookup"><span data-stu-id="1b7de-124">A license plate receiving process can't be used if an ASN contains a license plate ID that already exists and has physical on-hand data at a warehouse location other than the warehouse location where the license plate registration is occurring.</span></span>

<span data-ttu-id="1b7de-125">Pour les scénarios d'ordre de transfert dans lesquels l'entrepôt de transit ne suit pas les contenants (et ne suit donc pas non plus l'inventaire physique en stock par contenant), vous pouvez utiliser la fonctionnalité *Empêcher l'utilisation des contenants expédiés par ordre de transfert dans d'autres entrepôts que l'entrepôt de destination* pour empêcher les mises à jour physiques des contenants en transit.</span><span class="sxs-lookup"><span data-stu-id="1b7de-125">For transfer order scenarios where the transit warehouse doesn't track license plates (and therefore also doesn't track physical on-hand inventory per license plate), you can use the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature to prevent physical on-hand updates of license plates that are in transit.</span></span>

<span data-ttu-id="1b7de-126">Avant de pouvoir utiliser cette fonctionnalité, vous devez l'activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="1b7de-126">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="1b7de-127">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1b7de-127">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="1b7de-128">Dans l'espace de travail **Gestion des fonctionnalités**, cette fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="1b7de-128">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="1b7de-129">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="1b7de-129">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="1b7de-130">**Nom de la fonctionnalité :** *Empêcher l'utilisation des contenants expédiés par ordre de transfert dans d'autres entrepôts que l'entrepôt de destination*</span><span class="sxs-lookup"><span data-stu-id="1b7de-130">**Feature name:** *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse*</span></span>

<span data-ttu-id="1b7de-131">Pour gérer la fonctionnalité lorsque cette fonctionnalité est disponible, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1b7de-131">To manage the functionality when this feature is available, follow these steps.</span></span>

1. <span data-ttu-id="1b7de-132">Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="1b7de-132">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="1b7de-133">Sur l'onglet **Général**, sur le raccourci **Contenants**, définissez le champ **Stratégie de contenant de l'entrepôt de transit** sur l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="1b7de-133">On the **General** tab, on the **License plates** FastTab, set the **Transit warehouse license plate policy** field to one of the following values:</span></span>

    - <span data-ttu-id="1b7de-134">**Autoriser la réutilisation de contenant non suivi** - Le système fonctionne de la même manière qu'il fonctionne lorsque la fonctionnalité *Empêcher l'utilisation des contenants expédiés par ordre de transfert dans d'autres entrepôts que l'entrepôt de destination* n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="1b7de-134">**Allow reuse of non-tracked license plate** – The system works the same way that it works when the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature isn't available.</span></span> <span data-ttu-id="1b7de-135">Cette valeur est le paramètre par défaut lors de la première activation de la fonction.</span><span class="sxs-lookup"><span data-stu-id="1b7de-135">This value is the default setting when you first activate the feature.</span></span>
    - <span data-ttu-id="1b7de-136">**Empêcher la réutilisation du contenant non suivi** - Seules les mises à jour en rapport avec un contenant expédié seront autorisées dans l'entrepôt de destination jusqu'à réception de l'ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="1b7de-136">**Prevent reuse of non-tracked license plate** – Only on-hand updates that are related to a shipped license plate will be allowed at the destination warehouse until the transfer order has been received.</span></span>

## <a name="more-information"></a><span data-ttu-id="1b7de-137">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1b7de-137">More information</span></span>

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

<span data-ttu-id="1b7de-138">Pour plus d'informations sur les éléments de menu des appareils mobiles, voir [Configurer des appareils mobiles pour le travail en entrepôt](configure-mobile-devices-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="1b7de-138">For more information about mobile device menu items, see [Set up mobile devices for warehouse work](configure-mobile-devices-warehouse.md).</span></span>
