---
title: Définir des dimensions financières
description: Ce guide illustre l'ajout d'une dimension financière soutenue par une entité et d'une dimension financière personnalisée.
author: aprilolson
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6fbe739eec0cfa1e7b0276872640bd4f82be3ef7
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138334"
---
# <a name="define-financial-dimensions"></a><span data-ttu-id="df353-103">Définir des dimensions financières</span><span class="sxs-lookup"><span data-stu-id="df353-103">Define financial dimensions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="df353-104">Ce guide illustre l'ajout d'une dimension financière soutenue par une entité et d'une dimension financière personnalisée.</span><span class="sxs-lookup"><span data-stu-id="df353-104">This task guide demonstrates adding an entity backed financial dimension and a custom financial dimension.</span></span>  <span data-ttu-id="df353-105">La société fictive USMF sert d'exemple dans ce guide.</span><span class="sxs-lookup"><span data-stu-id="df353-105">The guide uses the USMF demo company.</span></span>


## <a name="create-an-entity-backed-financial-dimension"></a><span data-ttu-id="df353-106">Créer une dimension financière soutenue par une entité</span><span class="sxs-lookup"><span data-stu-id="df353-106">Create an entity backed financial dimension</span></span>
1. <span data-ttu-id="df353-107">Accédez au **volet Navigation > Modules > Comptabilité > Plan de comptes > Dimensions > Dimensions financières**.</span><span class="sxs-lookup"><span data-stu-id="df353-107">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Dimensions > Financial dimensions**.</span></span>
2. <span data-ttu-id="df353-108">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="df353-108">Click **New**.</span></span>
3. <span data-ttu-id="df353-109">Dans le champ du **formulaire Valeur utilisateur**, sélectionnez une entité définie par le système sur laquelle baser la dimension financière.</span><span class="sxs-lookup"><span data-stu-id="df353-109">In the **User values form** field, select a system-defined entity to base the financial dimension on.</span></span> 
4. <span data-ttu-id="df353-110">Dans le champ **Nom de la dimension**, entrez une valeur pour décrire la dimension financière.</span><span class="sxs-lookup"><span data-stu-id="df353-110">In the **Dimension name** field, type a value to describe the financial dimension.</span></span> <span data-ttu-id="df353-111">Le nom peut être différent de celui de l'entité définie par le système mais ne peut pas contenir d'espaces ou de caractères spéciaux.</span><span class="sxs-lookup"><span data-stu-id="df353-111">The name can be different than the system-defined entity but cannot contain spaces or special characters.</span></span>
5. <span data-ttu-id="df353-112">Cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="df353-112">Click **Activate**.</span></span> <span data-ttu-id="df353-113">L'activation de la dimension financière met à jour la table avec le nom de dimension financière et supprime les dimensions supprimées.</span><span class="sxs-lookup"><span data-stu-id="df353-113">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="df353-114">Vous pouvez entrer des valeurs de dimension avant d'activer une dimension financière, mais une dimension financière ne peut pas être utilisée tant qu'elle n'est pas activée.</span><span class="sxs-lookup"><span data-stu-id="df353-114">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="df353-115">Cliquez sur **Fermer** dans le message d'activation.</span><span class="sxs-lookup"><span data-stu-id="df353-115">Click **Close** on the activation message.</span></span>
7. <span data-ttu-id="df353-116">Cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="df353-116">Click **Activate**.</span></span> <span data-ttu-id="df353-117">L'activation de la dimension peut être programmée pour être exécutée par lots à une date et heure spécifiques.</span><span class="sxs-lookup"><span data-stu-id="df353-117">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
8. <span data-ttu-id="df353-118">Dans le **volet Actions**, cliquez sur **Valeurs de dimension**.</span><span class="sxs-lookup"><span data-stu-id="df353-118">On **Action pane**, click **Dimension values**.</span></span> <span data-ttu-id="df353-119">Certaines valeurs de dimension sont spécifiques à la société.</span><span class="sxs-lookup"><span data-stu-id="df353-119">Some dimension values are company specific.</span></span> <span data-ttu-id="df353-120">Vous pouvez vérifier si elles sont spécifiques à la société en regardant si le nom de la société apparaît dans la liste des valeurs de dimension.</span><span class="sxs-lookup"><span data-stu-id="df353-120">You can verify if they are company specific by if the company name is showing in the dimension values list.</span></span>  

## <a name="create-a-custom-financial-dimension"></a><span data-ttu-id="df353-121">Créez une dimension financière personnalisée.</span><span class="sxs-lookup"><span data-stu-id="df353-121">Create a custom financial dimension</span></span>
1. <span data-ttu-id="df353-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="df353-122">Close the page.</span></span>
2. <span data-ttu-id="df353-123">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="df353-123">Click **New**.</span></span>
3. <span data-ttu-id="df353-124">Dans le champ **Utiliser les valeurs de**, sélectionnez **Dimension personnalisée**.</span><span class="sxs-lookup"><span data-stu-id="df353-124">In the **Use values from** field, select **Custom dimension**.</span></span>
4. <span data-ttu-id="df353-125">Dans le champ **Nom de la dimension**, entrez une valeur pour décrire la dimension financière.</span><span class="sxs-lookup"><span data-stu-id="df353-125">In the **Dimension name** field, type a value to describe the financial dimension.</span></span>
    - <span data-ttu-id="df353-126">Le nom ne peut pas contenir d'espaces ou de caractères spéciaux.</span><span class="sxs-lookup"><span data-stu-id="df353-126">The name cannot contain spaces or special characters.</span></span>  
    - <span data-ttu-id="df353-127">Vous pouvez également spécifier un compte pour limiter la quantité et le type d'informations que vous pouvez entrer pour les valeurs de dimension.</span><span class="sxs-lookup"><span data-stu-id="df353-127">You can also specify an account mask to limit the amount and type of information that you can enter for dimension values.</span></span>   
    - <span data-ttu-id="df353-128">Vous pouvez entrer des caractères qui restent identiques pour chaque valeur de dimension, telles que des lettres ou un trait d'union.</span><span class="sxs-lookup"><span data-stu-id="df353-128">You can enter characters that remain the same for each dimension value, such as letters or a hyphen.</span></span> <span data-ttu-id="df353-129">Vous pouvez également entrer des signes dièse (#) et des esperluettes (&) comme espaces réservés pour les lettres et des chiffres qui changent chaque fois qu'une valeur de dimension est créée.</span><span class="sxs-lookup"><span data-stu-id="df353-129">You can also enter number signs (#) and ampersands (&) as placeholders for letters and numbers that will change every time that a dimension value is created.</span></span> <span data-ttu-id="df353-130">Utilisez un symbole dièse (#) comme espace réservé pour un nombre et une esperluette (&) comme espace réservé pour une lettre.</span><span class="sxs-lookup"><span data-stu-id="df353-130">Use a number sign (#) as a placeholder for a number and an ampersand (&) as a placeholder for a letter.</span></span>  <span data-ttu-id="df353-131">Exemple : pour limiter la valeur de dimension aux lettres CC et trois chiffres, entrez CC-### comme un masque de format.</span><span class="sxs-lookup"><span data-stu-id="df353-131">Example: To limit the dimension value to the letters CC and three numbers, you enter CC-### as the format mask.</span></span>  
5. <span data-ttu-id="df353-132">Cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="df353-132">Click **Activate**.</span></span> <span data-ttu-id="df353-133">L'activation de la dimension financière met à jour la table avec le nom de dimension financière et supprime les dimensions supprimées.</span><span class="sxs-lookup"><span data-stu-id="df353-133">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="df353-134">Vous pouvez entrer des valeurs de dimension avant d'activer une dimension financière, mais une dimension financière ne peut pas être utilisée tant qu'elle n'est pas activée.</span><span class="sxs-lookup"><span data-stu-id="df353-134">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>     
6. <span data-ttu-id="df353-135">Cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="df353-135">Click **Activate**.</span></span> <span data-ttu-id="df353-136">L'activation de la dimension peut être programmée pour être exécutée par lots à une date et heure spécifiques.</span><span class="sxs-lookup"><span data-stu-id="df353-136">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>      
7. <span data-ttu-id="df353-137">Dans le **volet Actions**, cliquez sur **Valeurs de dimension**.</span><span class="sxs-lookup"><span data-stu-id="df353-137">On **Action pane**, click **Dimension values**.</span></span>
8. <span data-ttu-id="df353-138">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="df353-138">Click **New**.</span></span>
9. <span data-ttu-id="df353-139">Dans le champ **Valeur de la dimension**, entrez un nom pour décrire votre valeur de la dimension financière.</span><span class="sxs-lookup"><span data-stu-id="df353-139">In the **Dimension value** field, type a name to describe your financial dimension value.</span></span>
10. <span data-ttu-id="df353-140">Dans le champ **Description**, entrez une description qui décrit votre valeur de la dimension financière.</span><span class="sxs-lookup"><span data-stu-id="df353-140">In the **Description** field, type a description that describes your financial dimension value.</span></span>

