---
title: Utiliser la date et l'heure dans Microsoft Dynamics 365 Talent
description: Présenter l'utilisation des champs de date et d'heure dans Microsoft Dynamics 365 Talent. Savoir à quoi s'attendre lors de l'échange de données de date et d'heure dans un écran dans Talent, une source externe, ou Common Data Service.
author: Darinkramer
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-06-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: abd215243cbda68ba3f57b5fa41054a10745d11f
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551024"
---
# <a name="work-with-date-and-time-in-microsoft-dynamics-365-talent"></a><span data-ttu-id="2b76c-104">Utiliser la date et l'heure dans Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="2b76c-104">Work with date and time in Microsoft Dynamics 365 Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2b76c-105">Les champs **Date et heure** sont un concept fondamental dans Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="2b76c-105">**Date and Time** fields are a fundamental concept in Dynamics 365 Talent.</span></span> <span data-ttu-id="2b76c-106">Il est important de bien comprendre l'utilisation des données de **Date et heure** dans un écran de Dynamics 365, dans Common Data Service, et des sources externes.</span><span class="sxs-lookup"><span data-stu-id="2b76c-106">It's important to understand how to work with **Date and Time** data in a Dynamics 365 form, Common Data Service, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="2b76c-107">Comprendre la différence entre les types de données du champ Date et Date et heure</span><span class="sxs-lookup"><span data-stu-id="2b76c-107">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="2b76c-108">Les champs**Date et heure** contiennent des informations sur le fuseau horaire, mais pas les champs **Date**.</span><span class="sxs-lookup"><span data-stu-id="2b76c-108">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="2b76c-109">Les champs **Date** affichent les mêmes informations partout.</span><span class="sxs-lookup"><span data-stu-id="2b76c-109">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="2b76c-110">Lorsque vous entrez une date dans un champ **Date**, Talent écrit la même date dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2b76c-110">When you enter a date into a **Date** field, Talent writes that same date to the database.</span></span>

<span data-ttu-id="2b76c-111">Lors de l'affichage des données dans un champ de **Date et heure**, Talent ajuste la date et l'heure selon le fuseau horaire de l'utilisateur défini dans l'écran **Options utilisateur** (**Commun > Configuration > Options utilisateur**).</span><span class="sxs-lookup"><span data-stu-id="2b76c-111">When displaying data in a **Date and Time** field, Talent adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="2b76c-112">Il est possible que les informations de date et d'heure que vous entrez dans le champ ne soient pas identiques à celles écrites dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2b76c-112">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="2b76c-113">[![Écran Options utilisateur](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="2b76c-113">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="2b76c-114">Présentation des champs de date et d'heure dans les écrans</span><span class="sxs-lookup"><span data-stu-id="2b76c-114">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="2b76c-115">Lorsque vous entrez des données dans un champ de **Date et heure**, les données affichées dans l'écran ne sont pas identiques à celles stockées dans la base de données si le fuseau horaire de l'utilisateur n'est pas défini au format Heure universelle coordonnée (UTC).</span><span class="sxs-lookup"><span data-stu-id="2b76c-115">When entering data in a **Date and Time** field, the data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="2b76c-116">Les données des champs **Date et heure** sont toujours stockées au format UTC.</span><span class="sxs-lookup"><span data-stu-id="2b76c-116">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="2b76c-117">[![Écran du collaborateur](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="2b76c-117">[![Worker form](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="2b76c-118">Présentation des champs de date et d'heure dans la base de données</span><span class="sxs-lookup"><span data-stu-id="2b76c-118">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="2b76c-119">Lorsque Talent écrit une valeur de **Date et heure** dans la base de données, il enregistre les données au format UTC.</span><span class="sxs-lookup"><span data-stu-id="2b76c-119">When Talent writes a **Date and time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="2b76c-120">Cela permet aux utilisateurs de voir les données de **Date et heure** selon le fuseau horaire défini dans les options utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2b76c-120">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="2b76c-121">Dans l'exemple ci-dessus, l'heure de début correspond à un moment précis et pas à une date particulière.</span><span class="sxs-lookup"><span data-stu-id="2b76c-121">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="2b76c-122">En faisant passer le fuseau horaire de l'utilisateur connecté de GMT +12:00 à GMT UTC, le même enregistrement qui vient d'être créé s'affiche sous la forme 30/04/2019 12:00:00 au lieu de 05/01/2019 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="2b76c-122">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record just created shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="2b76c-123">Dans l'exemple ci-dessous, le poste de l'employé 000724 devient actif au même moment, quel que soit le fuseau horaire.</span><span class="sxs-lookup"><span data-stu-id="2b76c-123">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="2b76c-124">L'employé sera actif le 30/04/2019 dans le fuseau horaire GMT, qui est le même que le 05/01/2019 dans le fuseau horaire GMT+12:00.</span><span class="sxs-lookup"><span data-stu-id="2b76c-124">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="2b76c-125">Les deux font référence au même moment et pas à une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="2b76c-125">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="2b76c-126">[![Écran du collaborateur](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="2b76c-126">[![Worker form](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a><span data-ttu-id="2b76c-127">Données de date et d'heure dans Data Management Framework, Excel, Common Data Service et Power BI</span><span class="sxs-lookup"><span data-stu-id="2b76c-127">Date and Time data in Data Management Framework, Excel, Common Data Service, and Power BI</span></span> 

<span data-ttu-id="2b76c-128">Data Management Framework, le module complémentaire Excel, Common Data Service et la génération d'états Power BI sont conçus pour interagir avec des données directement au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="2b76c-128">The Data Management Framework, Excel Add-In, Common Data Service, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="2b76c-129">Comme il n'y a aucun client pour ajuster les données de **Date et heure** sur le fuseau horaire de l'utilisateur, toutes les valeurs de **Date et heure** sont en UTC, ce qui peut aboutir à certains hypothèses incorrectes lors de la saisie ou de l'affichage des données.</span><span class="sxs-lookup"><span data-stu-id="2b76c-129">Since there is no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="2b76c-130">Les données de **Date et heure** qui sont envoyées via DMF, Excel, ou Common Data Service sont supposées être en UTC par la base de données.</span><span class="sxs-lookup"><span data-stu-id="2b76c-130">**Date and Time** data that is submitted via DMF, Excel, or Common Data Service is assumed to be in UTC by the database.</span></span> <span data-ttu-id="2b76c-131">Cela peut entraîner de la confusion lorsque la valeur de **Date et heure** soumise ne s'affiche pas comme prévu car l'utilisateur qui affiche les données n'a pas défini son fuseau horaire sur UTC.</span><span class="sxs-lookup"><span data-stu-id="2b76c-131">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="2b76c-132">Il peut se produire la même chose dans le sens inverse, lorsque les données sont exportées.</span><span class="sxs-lookup"><span data-stu-id="2b76c-132">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="2b76c-133">Les données de **Date et heure** de l'entité DMF exportée peuvent être différentes que ce qui est affiché dans le client Dynamics.</span><span class="sxs-lookup"><span data-stu-id="2b76c-133">The **Date and Time** data in the exported DMF entity can be different then what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="2b76c-134">Lors de l'utilisation de sources externes telles que DMF pour afficher ou créer des données, il est important de garder à l'esprit que les valeurs de **Date et heure** sont par défaut considérées comme étant en UTC quel que soit le fuseau horaire de l'ordinateur de l'utilisateur ou de ses paramètres de fuseau horaire.</span><span class="sxs-lookup"><span data-stu-id="2b76c-134">When using external sources like DMF to view or author data, it is important to keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="2b76c-135">Exemples du même enregistrement affiché dans différents endroits du produit</span><span class="sxs-lookup"><span data-stu-id="2b76c-135">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="2b76c-136">**Talent avec le fuseau horaire de l'utilisateur défini sur UTC**</span><span class="sxs-lookup"><span data-stu-id="2b76c-136">**Talent with user time zone set to UTC**</span></span>

<span data-ttu-id="2b76c-137">[![Écran du collaborateur](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="2b76c-137">[![Worker form](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="2b76c-138">**Talent avec le fuseau horaire de l'utilisateur défini sur GMT +12:00**</span><span class="sxs-lookup"><span data-stu-id="2b76c-138">**Talent with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="2b76c-139">[![Écran du collaborateur](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="2b76c-139">[![Worker form](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="2b76c-140">**Excel Via OData**</span><span class="sxs-lookup"><span data-stu-id="2b76c-140">**Excel Via OData**</span></span>

<span data-ttu-id="2b76c-141">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="2b76c-141">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="2b76c-142">**Phase intermédiaire DMF**</span><span class="sxs-lookup"><span data-stu-id="2b76c-142">**DMF Staging**</span></span>

<span data-ttu-id="2b76c-143">[![Phase intermédiaire DMF](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="2b76c-143">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="2b76c-144">**Exportation DMF**</span><span class="sxs-lookup"><span data-stu-id="2b76c-144">**DMF Export**</span></span>

<span data-ttu-id="2b76c-145">[![Phase intermédiaire DMF](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="2b76c-145">[![DMF Staging](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="2b76c-146">**Excel via Common Data Service**</span><span class="sxs-lookup"><span data-stu-id="2b76c-146">**Excel via Common Data Service**</span></span>

<span data-ttu-id="2b76c-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="2b76c-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

### <a name="see-also"></a><span data-ttu-id="2b76c-148">Voir également :</span><span class="sxs-lookup"><span data-stu-id="2b76c-148">See also</span></span>

[<span data-ttu-id="2b76c-149">Données de date/d'heure</span><span class="sxs-lookup"><span data-stu-id="2b76c-149">Date and time data</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="2b76c-150">Fuseaux horaires favoris de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="2b76c-150">User preferred time zones</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
