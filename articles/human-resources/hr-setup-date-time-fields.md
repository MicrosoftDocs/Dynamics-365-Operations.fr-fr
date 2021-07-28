---
title: Comprendre les champs de date et d’heure
description: Présenter l’utilisation des champs de date et d’heure dans Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6e87781762112955902d8a5807092a842f53f6af
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356558"
---
# <a name="understand-date-and-time-fields"></a>Comprendre les champs de date et d’heure

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Les champs **Date et heure** sont un concept fondamental dans Dynamics 365 Human Resources. Il est important de bien comprendre l’utilisation des données de **Date et heure** dans des écrans, dans Dataverse, et dans des sources externes.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Comprendre la différence entre les types de données du champ Date et Date et heure

Les champs **Date et heure** contiennent des informations sur le fuseau horaire, mais pas les champs **Date**. Les champs **Date** affichent les mêmes informations partout. Lorsque vous entrez une date dans un champ **Date**, Human Resources écrit la même date dans la base de données.

Lors de l’affichage des données dans un champ de **Date et heure**, Human Resources ajuste la date et l’heure selon le fuseau horaire de l’utilisateur défini dans l’écran **Options utilisateur** (**Commun > Configuration > Options utilisateur**). Il est possible que les informations de date et d’heure que vous entrez dans le champ ne soient pas identiques à celles écrites dans la base de données.

[![Écran Options utilisateur.](./media/useroptionsform.png)](./media/useroptionsform.png)

## <a name="understanding-date-and-time-fields-in-forms"></a>Présentation des champs de date et d’heure dans les écrans 

Les données de **Date et heure** affichées dans l’écran ne sont pas identiques à celles stockées dans la base de données si le fuseau horaire de l’utilisateur n’est pas défini au format Heure universelle coordonnée (UTC). Les données des champs **Date et heure** sont toujours stockées au format UTC.

[![Écran du collaborateur.](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Présentation des champs de date et d’heure dans la base de données 

Lorsque l’application Human Resources écrit une valeur de **Date et heure** dans la base de données, les données sont enregistrées au format UTC. Cela permet aux utilisateurs de voir les données de **Date et heure** selon le fuseau horaire défini dans les options utilisateur.
 
Dans l’exemple ci-dessus, l’heure de début correspond à un moment précis et pas à une date particulière. En faisant passer le fuseau horaire de l’utilisateur connecté de GMT +12:00 à GMT UTC, le même enregistrement s’affiche sous la forme 30/04/2019 12:00:00 au lieu de 05/01/2019 12:00:00.
  
Dans l’exemple ci-dessous, le poste de l’employé 000724 devient actif au même moment, quel que soit le fuseau horaire. L’employé sera actif le 30/04/2019 dans le fuseau horaire GMT, qui est le même que le 05/01/2019 dans le fuseau horaire GMT+12:00. Les deux font référence au même moment et pas à une date spécifique. 

[![Écran du collaborateur.](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a>Données de date et d’heure dans Data Management Framework, Excel, Dataverse et Power BI 

Data Management Framework, le module complémentaire Excel, Dataverse et la génération d’états Power BI sont conçus pour interagir avec des données directement au niveau de la base de données. Comme il n’y a aucun client pour ajuster les données de **Date et heure** sur le fuseau horaire de l’utilisateur, toutes les valeurs de **Date et heure** sont en UTC, ce qui peut aboutir à certains hypothèses incorrectes lors de la saisie ou de l’affichage des données.  
 
Les données de **Date et heure** envoyées via DMF, Excel, ou Dataverse sont supposées être en UTC par la base de données. Cela peut entraîner de la confusion lorsque la valeur de **Date et heure** soumise ne s’affiche pas comme prévu car l’utilisateur qui affiche les données n’a pas défini son fuseau horaire sur UTC. 
 
Il peut se produire la même chose dans le sens inverse, lorsque les données sont exportées. Les données de **Date et heure** de l’entité DMF exportée peuvent être différentes que ce qui est affiché dans le client Dynamics. 
 
Lors de l’utilisation de sources externes telles que DMF pour afficher ou créer des données, gardez à l’esprit que les valeurs de **Date et heure** sont par défaut considérées comme étant en UTC quel que soit le fuseau horaire de l’ordinateur de l’utilisateur ou de ses paramètres de fuseau horaire. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Exemples du même enregistrement affiché dans différents endroits du produit 

**Human Resources avec le fuseau horaire de l’utilisateur défini sur UTC**

[![Écran du collaborateur défini sur UTC.](./media/worker-form3.png)](./media/worker-form3.png)

**Human Resources avec le fuseau horaire de l’utilisateur défini sur GMT +12:00** 

[![Écran du collaborateur défini sur GMT.](./media/worker-form4.png)](./media/worker-form4.png)

**Excel Via OData**

[![Excel Via OData.](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**Phase intermédiaire DMF**

[![Phase intermédiaire DMF.](./media/DMFStaging.png)](./media/DMFStaging.png)

**Exportation DMF**

[![Exportation DMF.](./media/DMFexport.png)](./media/DMFexport.png)

**Excel via Dataverse**

[![Excel via Dataverse.](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>Voir également :

[Données de date/d’heure](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Fuseaux horaires favoris de l’utilisateur](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]