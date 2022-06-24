---
title: Comprendre les champs de date et d’heure
description: Cet article explique l’utilisation des champs de date et d’heure dans Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e314efa5ac08288bc7d00c197be59ba9decac203
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856307"
---
# <a name="understand-date-and-time-fields"></a>Comprendre les champs de date et d’heure

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Les champs **Date et heure** sont un concept fondamental dans Microsoft Dynamics 365 Human Resources. Il est important de bien comprendre l’utilisation des données de **Date et heure** sur les pages, dans Dataverse, et dans des sources externes.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Comprendre la différence entre les types de données du champ Date et Date et heure

Les champs **Date et heure** contiennent des informations sur le fuseau horaire, au contraire des champs **Date**. Les champs **Date** présentent les mêmes informations partout. Lorsque vous entrez une date dans un champ **Date**, la même date est écrite dans la base de données.

Lorsque des données sont affichées dans un champ de **Date et heure**, la date et l’heure sont ajustées selon le fuseau horaire de l’utilisateur sélectionné sur la page **Options utilisateur** (**Commun \> Configuration \> Options utilisateur**). Les informations de date et d’heure que vous entrez dans le champ peuvent ne pas être identiques à celles écrites dans la base de données.

[![Page Options utilisateur.](./media/Useroptionsform.png)](./media/Useroptionsform.png)

## <a name="understanding-date-and-time-fields-on-pages"></a>Présentation des champs de date et d’heure sur les pages 

Les données de **Date et heure** affichées dans l’écran ne sont pas identiques à celles stockées dans la base de données si le fuseau horaire de l’utilisateur n’est pas défini au format Heure universelle coordonnée (UTC). Les données des champs **Date et heure** sont toujours stockées au format UTC.

[![UTC de la page Collaborateur.](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Présentation des champs de date et d’heure dans la base de données 

Lorsqu’une valeur de **Date et heure** est écrite dans la base de données, les données sont stockées au format UTC. Par conséquent, les utilisateurs peuvent voir les données de **Date et heure** selon le fuseau horaire défini dans les options utilisateur.
 
Dans l’exemple ci-dessus, l’heure de début correspond à un moment précis et pas à une date particulière. En faisant passer le fuseau horaire de l’utilisateur connecté de GMT +12:00 à GMT UTC, le même enregistrement s’affiche sous la forme 30/04/2019 12:00:00 au lieu de 05/01/2019 12:00:00.

Dans l’exemple ci-dessous, le poste de l’employé 000724 devient actif au même moment, quel que soit le fuseau horaire. L’employé sera actif le 30/04/2019 dans le fuseau horaire GMT, qui est le même que le 05/01/2019 dans le fuseau horaire GMT+12:00. Les deux font référence au même moment et pas à une date spécifique. 

[![GMT de la page Collaborateur.](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a>Données de date et d’heure dans Data Management Framework, Excel, Dataverse et Power BI 

Data Management Framework (DMF), le module complémentaire Excel, Dataverse et la génération d’états Power BI sont conçus pour interagir avec des données directement au niveau de la base de données. Comme il n’y a aucun client pour ajuster les données de **Date et heure** sur le fuseau horaire de l’utilisateur, toutes les valeurs de **Date et heure** sont en UTC, ce qui peut aboutir à certains hypothèses incorrectes lors de la saisie ou de l’affichage des données.
 
Lorsque les données de **Date et heure** sont envoyées via DMF, Excel, ou Dataverse, la base de données présume qu’elles sont en UTC. Cependant, si les utilisateurs qui consultent les données n’ont pas leur fuseau horaire défini sur UTC, la valeur **Date et l’heure** n’apparaîtra pas comme prévu et les utilisateurs pourraient en être confus. 
 
Il peut se produire la même chose dans le sens inverse, lorsque les données sont exportées. Les données de **Date et heure** de l’entité DMF exportée peuvent être différentes que ce qui est affiché dans le client Dynamics. 
 
Lors de l’utilisation de sources externes telles que DMF pour afficher ou créer des données, gardez à l’esprit que les valeurs de **Date et heure** sont par défaut considérées comme étant en UTC quel que soit le fuseau horaire de l’ordinateur de l’utilisateur ou de ses paramètres de fuseau horaire. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Exemples du même enregistrement affiché dans différents endroits du produit 

**Human Resources avec le fuseau horaire de l’utilisateur défini sur UTC**

[![Page du collaborateur définie sur UTC.](./media/worker-form3.png)](./media/worker-form3.png)

**Human Resources avec le fuseau horaire de l’utilisateur défini sur GMT +12:00** 

[![Page du collaborateur définie sur GMT.](./media/worker-form4.png)](./media/worker-form4.png)

**Excel Via OData**

[![Excel Via OData.](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**Phase intermédiaire DMF**

[![Phase intermédiaire DMF.](./media/DMFStaging.png)](./media/DMFStaging.png)

**Exportation DMF**

[![Exportation DMF.](./media/DMFExport.png)](./media/DMFExport.png)

**Excel via Dataverse**

[![Excel via Dataverse.](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>Voir également :

[Données de date/d’heure](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Fuseaux horaires favoris de l’utilisateur](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
