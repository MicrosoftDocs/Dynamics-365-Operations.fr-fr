---
title: Paramétrer la consignation
description: Cette rubrique explique comment configurer les opérations de stock de consignation entrant.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5229559647274d4c845325c6b86afbdba43f29e0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834167"
---
# <a name="set-up-consignment"></a><span data-ttu-id="dc4d7-103">Paramétrer la consignation</span><span class="sxs-lookup"><span data-stu-id="dc4d7-103">Set up consignment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc4d7-104">Cette rubrique explique comment configurer les opérations de stock de consignation entrant.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-104">This topic explains how to configure inbound consignment inventory operations.</span></span>

<span data-ttu-id="dc4d7-105">Le stock de consignation est le stock qui appartient à un fournisseur, mais stocké à votre site.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-105">Consignment inventory is inventory that’s owned by a vendor, but stored at your site.</span></span> <span data-ttu-id="dc4d7-106">Lorsque vous êtes prêt à consommer ou à utiliser le stock, vous reprenez la propriété du stock.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-106">When you’re ready to consume or use the inventory, you take over the ownership of the inventory.</span></span> <span data-ttu-id="dc4d7-107">Cette rubrique décrit le paramétrage nécessaire pour activer les processus de consignation.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-107">This topic describes the setup needed to enable consignment processes.</span></span> <span data-ttu-id="dc4d7-108">Pour plus d’informations sur les processus de consignation, voir [Configurer la consignation](consignment.md).</span><span class="sxs-lookup"><span data-stu-id="dc4d7-108">For more information about consignment processes, see [Set up consignment](consignment.md).</span></span>

## <a name="inventory-owners"></a><span data-ttu-id="dc4d7-109">Propriétaires du stock</span><span class="sxs-lookup"><span data-stu-id="dc4d7-109">Inventory owners</span></span>
<span data-ttu-id="dc4d7-110">Pour enregistrer le stock de consignation entrant physique, vous devez définir un propriétaire fournisseur.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-110">In order to record physical inbound consignment inventory, you need to define a vendor owner.</span></span> <span data-ttu-id="dc4d7-111">Cette opération s’effectue sur la page **Propriétaire du stock**.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-111">This is done on the **Inventory owner** page.</span></span> <span data-ttu-id="dc4d7-112">Lorsque vous sélectionnez un **Compte fournisseur**, cette option génère des valeurs par défaut pour les champs **Nom** et **Propriétaire**.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-112">When you select a **Vendor account** this generates default values for the **Name** and **Owner** fields.</span></span> <span data-ttu-id="dc4d7-113">La valeur du champ **Propriétaire** est visible du fournisseur, vous pouvez le modifier si vos noms de comptes fournisseur ne sont pas faciles à reconnaître pour les personnes extérieures.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-113">The value in the **Owner** field will be visible to the vendor, so you might want to change it if your vendor account names aren’t easy for external people to recognize.</span></span> <span data-ttu-id="dc4d7-114">Il est possible de modifier le champ **Propriétaire**, mais uniquement jusqu’à ce que vous enregistriez l’enregistrement **Propriétaire du stock**.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-114">It’s possible to edit the **Owner** field, but only up to the point when you save the **Inventory owner** record.</span></span> <span data-ttu-id="dc4d7-115">Le champ **Nom** est rempli avec le nom du tiers auquel le compte fournisseur est associé, et il ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-115">The **Name** field is populated with the name of the party that the vendor account is associated with, and this cannot be changed.</span></span>

<span data-ttu-id="dc4d7-116">[![propriétaires du stock](./media/inventory-owners.png)](./media/inventory-owners.png)</span><span class="sxs-lookup"><span data-stu-id="dc4d7-116">[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)</span></span>

## <a name="tracking-dimension-group"></a><span data-ttu-id="dc4d7-117">Groupe de dimension de suivi</span><span class="sxs-lookup"><span data-stu-id="dc4d7-117">Tracking dimension group</span></span>
<span data-ttu-id="dc4d7-118">Les articles qui vont être utilisés dans les processus de consignation doivent être associés à un **Groupe de dimensions de suivi** dans lequel la dimension **Propriétaire** est définie sur **Active**.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-118">Items that are going to be used in consignment processes must be associated with a **Tracking dimension group** where the **Owner** dimension is set to **Active**.</span></span> <span data-ttu-id="dc4d7-119">La dimension du propriétaire a toujours les options **Stock physique** et **Stock financier** sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-119">The Owner dimension always has the **Physical inventory** and **Financial inventory** options selected.</span></span> <span data-ttu-id="dc4d7-120">Le **Plan de couverture par dimension** n ’est jamais sélectionné.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-120">The **Coverage plan by dimension** is never selected.</span></span>

<span data-ttu-id="dc4d7-121">[![groupe de dimensions de suivi](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span><span class="sxs-lookup"><span data-stu-id="dc4d7-121">[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span></span>

## <a name="inventory-ownership-change-journal"></a><span data-ttu-id="dc4d7-122">Journal des modifications de propriété du stock</span><span class="sxs-lookup"><span data-stu-id="dc4d7-122">Inventory ownership change journal</span></span>
<span data-ttu-id="dc4d7-123">Le journal **Modifications de propriété du stock** est utilisé pour enregistrer le transfert de propriété du stock de consignation du fournisseur à l’entité juridique qui le consomme.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-123">The **Inventory ownership change** journal is used to record the transfer of ownership of consignment inventory from the vendor to the legal entity that’s consuming it.</span></span> <span data-ttu-id="dc4d7-124">Comme tout autre journal de stock, il doit être identifié avec un nom de journal de stock.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-124">Like any inventory journal, it must be identified with an Inventory journal name.</span></span> <span data-ttu-id="dc4d7-125">Ces noms sont créés sur la page **Noms des journaux de stock** et **Type de journal** doit être défini sur **Modification de propriété**.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-125">These names are created on the **Inventory journal names** page, and the **Journal type** must be set to **Ownership change**.</span></span>

<span data-ttu-id="dc4d7-126">[![Journal des modifications de propriété du stock](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span><span class="sxs-lookup"><span data-stu-id="dc4d7-126">[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span></span>

## <a name="vendor-collaboration-in-consignment-processes"></a><span data-ttu-id="dc4d7-127">Collaboration fournisseur dans les processus de consignation</span><span class="sxs-lookup"><span data-stu-id="dc4d7-127">Vendor collaboration in consignment processes</span></span>
<span data-ttu-id="dc4d7-128">Si vos fournisseurs utilisent l’interface de collaboration fournisseur, ils peuvent utiliser cette option pour contrôler la consommation du stock sur votre site.</span><span class="sxs-lookup"><span data-stu-id="dc4d7-128">If your vendors are using the vendor collaboration interface, they can use this to monitor the consumption of inventory at your site.</span></span> <span data-ttu-id="dc4d7-129">Pour plus d’informations sur le paramétrage des fournisseurs pour utiliser la collaboration fournisseur, voir [Sécurité de l’utilisateur du portail de fournisseurs](../procurement/configure-security-vendor-portal-users.md).</span><span class="sxs-lookup"><span data-stu-id="dc4d7-129">For more information about setting up vendors to use vendor collaboration, see [Vendor portal user security](../procurement/configure-security-vendor-portal-users.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]