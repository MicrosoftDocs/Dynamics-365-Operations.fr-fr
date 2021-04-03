---
title: Comprendre les champs de date et d’heure
description: Présenter l’utilisation des champs de date et d’heure dans Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 924d7369129d4115d45f23864e7b851d318c52a4
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467359"
---
# <a name="understand-date-and-time-fields"></a><span data-ttu-id="f9b94-103">Comprendre les champs de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="f9b94-103">Understand Date and Time fields</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f9b94-104">Les champs **Date et heure** sont un concept fondamental dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f9b94-104">**Date and Time** fields are a fundamental concept in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f9b94-105">Il est important de bien comprendre l’utilisation des données de **Date et heure** dans des écrans, dans Dataverse, et dans des sources externes.</span><span class="sxs-lookup"><span data-stu-id="f9b94-105">It's important to understand how to work with **Date and Time** data in forms, Dataverse, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="f9b94-106">Comprendre la différence entre les types de données du champ Date et Date et heure</span><span class="sxs-lookup"><span data-stu-id="f9b94-106">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="f9b94-107">Les champs **Date et heure** contiennent des informations sur le fuseau horaire, mais pas les champs **Date**.</span><span class="sxs-lookup"><span data-stu-id="f9b94-107">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="f9b94-108">Les champs **Date** affichent les mêmes informations partout.</span><span class="sxs-lookup"><span data-stu-id="f9b94-108">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="f9b94-109">Lorsque vous entrez une date dans un champ **Date**, Human Resources écrit la même date dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="f9b94-109">When you enter a date into a **Date** field, Human Resources writes that same date to the database.</span></span>

<span data-ttu-id="f9b94-110">Lors de l’affichage des données dans un champ de **Date et heure**, Human Resources ajuste la date et l’heure selon le fuseau horaire de l’utilisateur défini dans l’écran **Options utilisateur** (**Commun > Configuration > Options utilisateur**).</span><span class="sxs-lookup"><span data-stu-id="f9b94-110">When displaying data in a **Date and Time** field, Human Resources adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="f9b94-111">Il est possible que les informations de date et d’heure que vous entrez dans le champ ne soient pas identiques à celles écrites dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="f9b94-111">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="f9b94-112">[![Écran Options utilisateur](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="f9b94-112">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="f9b94-113">Présentation des champs de date et d’heure dans les écrans</span><span class="sxs-lookup"><span data-stu-id="f9b94-113">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="f9b94-114">Les données de **Date et heure** affichées dans l’écran ne sont pas identiques à celles stockées dans la base de données si le fuseau horaire de l’utilisateur n’est pas défini au format Heure universelle coordonnée (UTC).</span><span class="sxs-lookup"><span data-stu-id="f9b94-114">**Date and Time** data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="f9b94-115">Les données des champs **Date et heure** sont toujours stockées au format UTC.</span><span class="sxs-lookup"><span data-stu-id="f9b94-115">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="f9b94-116">[![UTS de l’écran du collaborateur](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="f9b94-116">[![Worker form UTC](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="f9b94-117">Présentation des champs de date et d’heure dans la base de données</span><span class="sxs-lookup"><span data-stu-id="f9b94-117">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="f9b94-118">Lorsque l’application Human Resources écrit une valeur de **Date et heure** dans la base de données, les données sont enregistrées au format UTC.</span><span class="sxs-lookup"><span data-stu-id="f9b94-118">When Human Resources writes a **Date and Time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="f9b94-119">Cela permet aux utilisateurs de voir les données de **Date et heure** selon le fuseau horaire défini dans les options utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f9b94-119">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="f9b94-120">Dans l’exemple ci-dessus, l’heure de début correspond à un moment précis et pas à une date particulière.</span><span class="sxs-lookup"><span data-stu-id="f9b94-120">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="f9b94-121">En faisant passer le fuseau horaire de l’utilisateur connecté de GMT +12:00 à GMT UTC, le même enregistrement s’affiche sous la forme 30/04/2019 12:00:00 au lieu de 05/01/2019 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="f9b94-121">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="f9b94-122">Dans l’exemple ci-dessous, le poste de l’employé 000724 devient actif au même moment, quel que soit le fuseau horaire.</span><span class="sxs-lookup"><span data-stu-id="f9b94-122">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="f9b94-123">L’employé sera actif le 30/04/2019 dans le fuseau horaire GMT, qui est le même que le 05/01/2019 dans le fuseau horaire GMT+12:00.</span><span class="sxs-lookup"><span data-stu-id="f9b94-123">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="f9b94-124">Les deux font référence au même moment et pas à une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="f9b94-124">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="f9b94-125">[![GMT de l’écran du collaborateur](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="f9b94-125">[![Worker form GMT](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a><span data-ttu-id="f9b94-126">Données de date et d’heure dans Data Management Framework, Excel, Dataverse et Power BI</span><span class="sxs-lookup"><span data-stu-id="f9b94-126">Date and Time data in Data Management Framework, Excel, Dataverse, and Power BI</span></span> 

<span data-ttu-id="f9b94-127">Data Management Framework, le module complémentaire Excel, Dataverse et la génération d’états Power BI sont conçus pour interagir avec des données directement au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="f9b94-127">The Data Management Framework, Excel Add-In, Dataverse, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="f9b94-128">Comme il n’y a aucun client pour ajuster les données de **Date et heure** sur le fuseau horaire de l’utilisateur, toutes les valeurs de **Date et heure** sont en UTC, ce qui peut aboutir à certains hypothèses incorrectes lors de la saisie ou de l’affichage des données.</span><span class="sxs-lookup"><span data-stu-id="f9b94-128">Since there's no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="f9b94-129">Les données de **Date et heure** envoyées via DMF, Excel, ou Dataverse sont supposées être en UTC par la base de données.</span><span class="sxs-lookup"><span data-stu-id="f9b94-129">**Date and Time** data submitted via DMF, Excel, or Dataverse is assumed to be in UTC by the database.</span></span> <span data-ttu-id="f9b94-130">Cela peut entraîner de la confusion lorsque la valeur de **Date et heure** soumise ne s’affiche pas comme prévu car l’utilisateur qui affiche les données n’a pas défini son fuseau horaire sur UTC.</span><span class="sxs-lookup"><span data-stu-id="f9b94-130">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="f9b94-131">Il peut se produire la même chose dans le sens inverse, lorsque les données sont exportées.</span><span class="sxs-lookup"><span data-stu-id="f9b94-131">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="f9b94-132">Les données de **Date et heure** de l’entité DMF exportée peuvent être différentes que ce qui est affiché dans le client Dynamics.</span><span class="sxs-lookup"><span data-stu-id="f9b94-132">The **Date and Time** data in the exported DMF entity can be different than what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="f9b94-133">Lors de l’utilisation de sources externes telles que DMF pour afficher ou créer des données, gardez à l’esprit que les valeurs de **Date et heure** sont par défaut considérées comme étant en UTC quel que soit le fuseau horaire de l’ordinateur de l’utilisateur ou de ses paramètres de fuseau horaire.</span><span class="sxs-lookup"><span data-stu-id="f9b94-133">When using external sources like DMF to view or author data, keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="f9b94-134">Exemples du même enregistrement affiché dans différents endroits du produit</span><span class="sxs-lookup"><span data-stu-id="f9b94-134">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="f9b94-135">**Human Resources avec le fuseau horaire de l’utilisateur défini sur UTC**</span><span class="sxs-lookup"><span data-stu-id="f9b94-135">**Human Resources with user time zone set to UTC**</span></span>

<span data-ttu-id="f9b94-136">[![Écran du collaborateur défini sur UTC](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="f9b94-136">[![Worker form set to UTC](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="f9b94-137">**Human Resources avec le fuseau horaire de l’utilisateur défini sur GMT +12:00**</span><span class="sxs-lookup"><span data-stu-id="f9b94-137">**Human Resources with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="f9b94-138">[![Écran du collaborateur défini sur GMT](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="f9b94-138">[![Worker form set to GMT](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="f9b94-139">**Excel Via OData**</span><span class="sxs-lookup"><span data-stu-id="f9b94-139">**Excel Via OData**</span></span>

<span data-ttu-id="f9b94-140">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="f9b94-140">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="f9b94-141">**Phase intermédiaire DMF**</span><span class="sxs-lookup"><span data-stu-id="f9b94-141">**DMF Staging**</span></span>

<span data-ttu-id="f9b94-142">[![Phase intermédiaire DMF](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="f9b94-142">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="f9b94-143">**Exportation DMF**</span><span class="sxs-lookup"><span data-stu-id="f9b94-143">**DMF Export**</span></span>

<span data-ttu-id="f9b94-144">[![Exportation DMF](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="f9b94-144">[![DMF Export](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="f9b94-145">**Excel via Dataverse**</span><span class="sxs-lookup"><span data-stu-id="f9b94-145">**Excel via Dataverse**</span></span>

<span data-ttu-id="f9b94-146">[![Excel via Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="f9b94-146">[![Excel via Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="f9b94-147">Voir également :</span><span class="sxs-lookup"><span data-stu-id="f9b94-147">See also</span></span>

[<span data-ttu-id="f9b94-148">Données de date/d’heure</span><span class="sxs-lookup"><span data-stu-id="f9b94-148">Date and time data</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="f9b94-149">Fuseaux horaires favoris de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="f9b94-149">User preferred time zones</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]