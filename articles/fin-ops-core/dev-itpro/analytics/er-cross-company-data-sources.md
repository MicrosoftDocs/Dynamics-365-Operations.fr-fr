---
title: Sources de données de société croisée dans la gestion des états électroniques (ER)
description: Cette rubrique explique comment utiliser les sources de données de société croisée dans la gestion des états électroniques.
author: NickSelin
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, ERFormatMappingLegalEntityFilterTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 7528a84bae388dd8b159405043570b647d6e2cb4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753742"
---
# <a name="cross-company-data-sources-in-electronic-reporting-er"></a>Sources de données de société croisée dans la gestion des états électroniques (ER)

[!include[banner](../includes/banner.md)]

Vous pouvez créer des formats de gestion des états électroniques pour générer des documents sortants dans différents formats. Lorsqu’un document est généré, un format ER appelle les sources de données configurées dans une mise en correspondance des modèles ER correspondante. Pour configurer l’accès aux tables d’application pour la récupération des enregistrements, vous pouvez utiliser les sources de données ER du type **Enregistrements de la table**. Lorsque la table d’accès est une table partagée (c’est-à-dire, une table dans laquelle les données sont enregistrées sans identificateur de société), cette source de données renvoie tous les enregistrements. Lorsque la table d’accès est une table dépendante de la société (c’est-à-dire, une table dans laquelle les données sont enregistrées par société), cette source de données renvoie uniquement les enregistrements enregistrés pour la société actuelle (c’est-à-dire, le contexte de société dans lequel le format ER s’exécute).

Chaque source de données du type **Enregistrements de la table** dans une mise en correspondance des modèles peut maintenant être marquée comme source de données de société croisée. Par conséquent, vous pouvez utiliser les sources de données du type **Enregistrements de la table** pour accéder aux données de société croisée des tables d’application.

Si vous marquez une source de données comme société croisée, le comportement suivant se produit :

- Pour une source de données qui fait référence à une table partagée, à l’exception de CompanyInfo, la source de données renvoie tous les enregistrements qui existent dans la table référencée. 
- Pour une source de données qui fait référence à la table CompanyInfo, même si CompanyInfo est une table partagée, la source de données renvoie les enregistrements contenant l’identificateur d’une société à partir de la portée définie.
- Pour une table dépendante de la société, la source de données renvoie les enregistrements de la table référencée contenant l’identificateur d’une société à partir de la portée définie.

Dans la boîte de dialogue de requête du système, lorsque l’option **Demander une requête** est activée pour une source de données marquée comme société croisée, vous pouvez sélectionner manuellement une ou plusieurs sociétés à inclure dans l’onglet **Plage de la société**.

> [!IMPORTANT]
> Comme les autres filtres, le filtre de société est conservé en tant que dernière valeur utilisée pour les requêtes lorsque vous exécutez un format ER. Le filtre n’est pas automatiquement modifié si vous modifiez la valeur de société croisée pour une source de données. Pour utiliser une valeur de société croisée différente pour une autre source de données, supprimez la sélection spécifique à l’utilisateur correspondante.

Pour chaque source de données marquée comme société croisée, vous pouvez sélectionner les enregistrements souhaités à l’aide des fonctions **FILTER** et **WHERE** des expressions ER. Le champ **dataAreaID** peut également être utilisé comme identificateur de société. Pour le moment, le champ **dataAreaID** est limité aux types suivants de conditions lorsque la fonction **FILTER** est utilisée :

- Seules les conditions qui ont une comparaison de champ **dataAreaID** unique sont prises en charge.
- Seules les comparaisons qui ont des expressions qui ne dépendent pas des éléments de liste d’enregistrements sont autorisées.

Par conséquent, l’expression suivante est valide.

```ER Expression
FILTER (MyTable, MyTable.dataAreaID = $StringUserInputParameter)
While shown below expressions will not pass the validation:
FILTER (MyTable, MyTable.dataAreaID = MyTable2RecordsList.MyField)
FILTER (MyTable, 
    OR(
        MyTable.dataAreaID = $StringUserInputParameter1,
        MyTable.dataAreaID = $StringUserInputParameter2
    )
)
```

Par défaut, la portée comprend toutes les sociétés de l’application actuelle. Toutefois, elle peut être limitée. Pour limiter la portée de l’accès aux données de société croisée pour un format ER unique, affectez une hiérarchie d’organisation spécifique au format. Lorsqu’une hiérarchie est définie pour un format ER, seuls les enregistrements des entités juridiques présentées dans la hiérarchie affectée sont renvoyés, même si le format appelle les sources de données de société croisée. Lorsqu’une référence à une hiérarchie qui n’existe plus est définie pour un format ER, la portée par défaut est appliquée et le format appelle les sources de données de société croisée. Dans ce cas, les enregistrements de toutes les sociétés d’application sont renvoyés.

Notez que lorsque l’option **Utiliser un brouillon** est activée pour la hiérarchie d’organisation affectée à un format ER unique, les entités juridiques de la version provisoire de cette hiérarchie sont utilisées pour identifier la portée des sources de données de société croisée. Si la version provisoire n’existe pas, les entités juridiques de la dernière version publiée de cette hiérarchie d’organisation sont utilisées.

Notez que lorsque l’option **Utiliser un brouillon** est désactivée pour la hiérarchie d’organisation affectée à un format ER unique, les entités juridiques de la dernière version publiée de cette hiérarchie d’organisation sont utilisées pour identifier la portée des sources de données de société croisée. La date d’entrée en vigueur des hiérarchies d’organisation n’est pas encore prise en charge dans la structure ER.

La hiérarchie peut être affectée à un format dans une page spécifique accessible à partir de l’espace de travail de gestion des états électroniques ou à l’aide de l’élément de menu **Administration d’organisation \> Gestion des états électroniques \> Filtre d’entité juridique** pour les formats. Pour accéder à la page, le privilège **Tenir à jour les filtres d’entité juridique pour les formats** (ERMaintainFormatMappingLegalEntityFilters) doit être accordé à un utilisateur. La restriction de la portée des entités juridiques basées sur la hiérarchie pour le format est appliquée en plus de la restriction que l’utilisateur peut spécifier manuellement dans la boîte de dialogue de requête du système. L’intersection de ces restrictions est utilisée lorsque le format est exécuté.

Pour plus d’informations sur cette fonction, lisez le guide de tâches, **ER Accéder aux enregistrements des tables dépendantes de la société en mode de société croisée**, qui fait partie du processus d’entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677) et qui peut être téléchargé à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Ce guide de tâches vous guide tout au long du processus de configuration du modèle ER et du format ER pour accéder aux tables d’application en mode de société croisée.

Téléchargez les fichiers suivants pour exécuter le guide de tâches :

- [Configuration du modèle ER – CrossCompanyDataAccessModel.xml](https://go.microsoft.com/fwlink/?linkid=874111)
- [Configuration du format ER – CrossCompanyDataAccessFormat.xml](https://go.microsoft.com/fwlink/?linkid=874111)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]