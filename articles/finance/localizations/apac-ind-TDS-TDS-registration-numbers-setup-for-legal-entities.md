---
title: Configurer les numéros d'enregistrement TDS pour les personnes morales
description: Cette rubrique explique comment configurer les numéros d'enregistrement de taxe déduite à la source (TDS) pour les personnes morales.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3550b2b7b305702ffc337ba0a9bb79f60a9de120
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023235"
---
# <a name="set-up-tds-registration-numbers-for-legal-entities"></a><span data-ttu-id="cb838-103">Configurer les numéros d'enregistrement TDS pour les personnes morales</span><span class="sxs-lookup"><span data-stu-id="cb838-103">Set up TDS registration numbers for legal entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cb838-104">Cette rubrique explique comment configurer les numéros d'enregistrement de taxe déduite à la source (TDS) pour les personnes morales.</span><span class="sxs-lookup"><span data-stu-id="cb838-104">This topic explains how to set up Tax Deducted at Source (TDS) registration numbers for legal entities.</span></span>

1. <span data-ttu-id="cb838-105">Accédez à **Administration d’organisation \> Organisations \> Entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="cb838-105">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>

    <span data-ttu-id="cb838-106">[![Page Entités juridiques](./media/apac-ind-TDS-4.png)](./media/apac-ind-TDS-4.png)</span><span class="sxs-lookup"><span data-stu-id="cb838-106">[![Legal entities page](./media/apac-ind-TDS-4.png)](./media/apac-ind-TDS-4.png)</span></span>

2. <span data-ttu-id="cb838-107">Dans le raccourci **Informations fiscales**, dans le champ **Numéro de compte permanent**, entrez le numéro de compte permanent (PAN) de l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="cb838-107">On the **Tax information** FastTab, in the **Permanent account number** field, enter the permanent account number (PAN) of the legal entity.</span></span>
3. <span data-ttu-id="cb838-108">Dans le champ **Numéro du cercle**, entrez le numéro de cercle de l'autorité TDS.</span><span class="sxs-lookup"><span data-stu-id="cb838-108">In the **Circle number** field, enter the circle number of the TDS authority.</span></span>
4. <span data-ttu-id="cb838-109">Dans le champ **Numéro de quartier**, entrez le numéro de quartier de l'autorité TDS.</span><span class="sxs-lookup"><span data-stu-id="cb838-109">In the **Ward number** field, enter the ward number of the TDS authority.</span></span>
5. <span data-ttu-id="cb838-110">Dans le champ **Officier évaluateur**, entrez les coordonnées de l'officier évaluateur pour l'autorité TDS.</span><span class="sxs-lookup"><span data-stu-id="cb838-110">In the **Assessing officer** field, enter the details of the assessing officer for the TDS authority.</span></span>
6. <span data-ttu-id="cb838-111">Dans le champ **Type de déducteur**, sélectionnez la catégorie de type de déducteur pour l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="cb838-111">In the **Type of deductor** field, select the deductor type category for the legal entity.</span></span>
7. <span data-ttu-id="cb838-112">Dans le volet Actions, sélectionnez **ID d'enregistrement** pour ouvrir la page **Gérer les adresses**.</span><span class="sxs-lookup"><span data-stu-id="cb838-112">On the Action Pane, select **Registration IDs** to open the **Manage addresses** page.</span></span>
8. <span data-ttu-id="cb838-113">Dans le raccourci **Informations fiscales**, sélectionnez **Ajouter** ou **Modifier** pour ouvrir la page **Gérer les informations fiscales** où vous pouvez gérer l'entrée d'enregistrement de taxe.</span><span class="sxs-lookup"><span data-stu-id="cb838-113">On the **Tax information** FastTab, select **Add** or **Edit** to open the **Manage tax information** page, where you can maintain the tax registration entry.</span></span>

    <span data-ttu-id="cb838-114">[![Page Gérer les adresses](./media/apac-ind-TDS-5.png)](./media/apac-ind-TDS-5.png)</span><span class="sxs-lookup"><span data-stu-id="cb838-114">[![Manage addresses page](./media/apac-ind-TDS-5.png)](./media/apac-ind-TDS-5.png)</span></span>

9. <span data-ttu-id="cb838-115">Dans le raccourci **Retenue à la source**, dans le champ **Numéro de compte fiscal (TAN)**, entrez le numéro d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="cb838-115">On the **Withholding tax** FastTab, in the **Tax Account Number (TAN)** field, enter the registration number.</span></span> <span data-ttu-id="cb838-116">Ce numéro doit être composé de quatre caractères alphabétiques, puis de cinq caractères numériques, puis d'un caractère alphabétique.</span><span class="sxs-lookup"><span data-stu-id="cb838-116">This number must consist of four alphabetic characters, then five numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="cb838-117">Voici un exemple : **AXDF87645F**.</span><span class="sxs-lookup"><span data-stu-id="cb838-117">Here is an example: **AXDF87645F**.</span></span>
10. <span data-ttu-id="cb838-118">Dans le champ **Nom ou description**, entrez une description pour le numéro d'enregistrement de la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="cb838-118">In the **Name or description** field, enter a description of the withholding tax registration number.</span></span>

    <span data-ttu-id="cb838-119">[![Page Gérer les informations fiscales](./media/apac-ind-TDS-5-1.png)](./media/apac-ind-TDS-5-1.png)</span><span class="sxs-lookup"><span data-stu-id="cb838-119">[![Manage tax information page](./media/apac-ind-TDS-5-1.png)](./media/apac-ind-TDS-5-1.png)</span></span>

11. <span data-ttu-id="cb838-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cb838-120">Close the page.</span></span>