---
title: Utiliser la date et l'heure dans Microsoft Dynamics 365 for Talent
description: Présenter l'utilisation des champs de date et d'heure dans Microsoft Dynamics 365 for Talent. Savoir à quoi s'attendre lors de l'échange de données de date et d'heure dans un écran dans Dynamics 365 for Talent, une source externe, ou Common Data Service.
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
ms.openlocfilehash: b4c652992272ed1a5aecbb4c78f0d11f077149d1
ms.sourcegitcommit: 46bded82aa072adfedcf443629c2adc69f512c09
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/26/2019
ms.locfileid: "1791208"
---
# <a name="date-and-time-fields-in-talent"></a>Champs de date et d'heure dans Talent

[!include [banner](includes/banner.md)]

Les champs **Date et heure** sont un concept fondamental dans Dynamics 365 for Talent. Il est important de bien comprendre l'utilisation des données de **Date et heure** dans un écran de Dynamics 365, dans Common Data Service, et des sources externes.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Comprendre la différence entre les types de données du champ Date et Date et heure

Les champs**Date et heure** contiennent des informations sur le fuseau horaire, mais pas les champs **Date**. Les champs **Date** affichent les mêmes informations partout. Lorsque vous entrez une date dans un champ **Date**, Talent écrit la même date dans la base de données.

Lors de l'affichage des données dans un champ de **Date et heure**, Talent ajuste la date et l'heure selon le fuseau horaire de l'utilisateur défini dans l'écran **Options utilisateur** (**Commun > Configuration > Options utilisateur**). Il est possible que les informations de date et d'heure que vous entrez dans le champ ne soient pas identiques à celles écrites dans la base de données.

[![Écran Options utilisateur](./media/useroptionsform.png)](./media/useroptionsform.png)

## <a name="understanding-date-and-time-fields-in-forms"></a>Présentation des champs de date et d'heure dans les écrans 

Lorsque vous entrez des données dans un champ de **Date et heure**, les données affichées dans l'écran ne sont pas identiques à celles stockées dans la base de données si le fuseau horaire de l'utilisateur n'est pas défini au format Heure universelle coordonnée (UTC). Les données des champs **Date et heure** sont toujours stockées au format UTC.

[![Écran du collaborateur](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Présentation des champs de date et d'heure dans la base de données 

Lorsque Talent écrit une valeur de **Date et heure** dans la base de données, il enregistre les données au format UTC. Cela permet aux utilisateurs de voir les données de **Date et heure** selon le fuseau horaire défini dans les options utilisateur.
 
Dans l'exemple ci-dessus, l'heure de début correspond à un moment précis et pas à une date particulière. En faisant passer le fuseau horaire de l'utilisateur connecté de GMT +12:00 à GMT UTC, le même enregistrement qui vient d'être créé s'affiche sous la forme 30/04/2019 12:00:00 au lieu de 05/01/2019 12:00:00.
  
Dans l'exemple ci-dessous, le poste de l'employé 000724 devient actif au même moment, quel que soit le fuseau horaire. L'employé sera actif le 30/04/2019 dans le fuseau horaire GMT, qui est le même que le 05/01/2019 dans le fuseau horaire GMT+12:00. Les deux font référence au même moment et pas à une date spécifique. 

[![Écran du collaborateur](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a>Données de date et d'heure dans Data Management Framework, Excel, Common Data Service et Power BI 

Data Management Framework, le module complémentaire Excel, Common Data Service et la génération d'états Power BI sont conçus pour interagir avec des données directement au niveau de la base de données. Comme il n'y a aucun client pour ajuster les données de **Date et heure** sur le fuseau horaire de l'utilisateur, toutes les valeurs de **Date et heure** sont en UTC, ce qui peut aboutir à certains hypothèses incorrectes lors de la saisie ou de l'affichage des données.  
 
Les données de **Date et heure** qui sont envoyées via DMF, Excel, ou Common Data Service sont supposées être en UTC par la base de données. Cela peut entraîner de la confusion lorsque la valeur de **Date et heure** soumise ne s'affiche pas comme prévu car l'utilisateur qui affiche les données n'a pas défini son fuseau horaire sur UTC. 
 
Il peut se produire la même chose dans le sens inverse, lorsque les données sont exportées. Les données de **Date et heure** de l'entité DMF exportée peuvent être différentes que ce qui est affiché dans le client Dynamics. 
 
Lors de l'utilisation de sources externes telles que DMF pour afficher ou créer des données, il est important de garder à l'esprit que les valeurs de **Date et heure** sont par défaut considérées comme étant en UTC quel que soit le fuseau horaire de l'ordinateur de l'utilisateur ou de ses paramètres de fuseau horaire. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Exemples du même enregistrement affiché dans différents endroits du produit 

**Talent avec le fuseau horaire de l'utilisateur défini sur UTC**

[![Écran du collaborateur](./media/worker-form3.png)](./media/worker-form3.png)

**Talent avec le fuseau horaire de l'utilisateur défini sur GMT +12:00** 

[![Écran du collaborateur](./media/worker-form4.png)](./media/worker-form4.png)

**Excel Via OData**

[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**Phase intermédiaire DMF**

[![Phase intermédiaire DMF](./media/DMFStaging.png)](./media/DMFStaging.png)

**Exportation DMF**

[![Phase intermédiaire DMF](./media/DMFexport.png)](./media/DMFexport.png)

**Excel via Common Data Service**

[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)

### <a name="see-also"></a>Voir également :

[Données de date/d'heure](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Fuseaux horaires favoris de l'utilisateur](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
