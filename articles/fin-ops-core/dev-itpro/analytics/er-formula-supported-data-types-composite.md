---
title: Types de données composites pris en charge pour les formules des États électroniques
description: Cette rubrique fournit des informations sur les types de données composites pris en charge dans les formules des États électroniques (ER).
author: NickSelin
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7ed9e62751b6be9fad6de3bf262d37d7977d192
ms.sourcegitcommit: 15aacd0e109b05c7281407b5bba4e6cd99116c28
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6224090"
---
# <a name="supported-composite-data-types-for-electronic-reporting-formulas"></a>Types de données composites pris en charge pour les formules des États électroniques

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les types de données composites pris en charge dans les expressions des [États électroniques (ER)](general-electronic-reporting.md) expressions. Les types de données composites sont [classe](#class), [conteneur](#container), [enregistrement](#record), [liste d’enregistrements](#record-list) et [objet](#object).

## <a name="class"></a><a name="class"></a>Classe

Le type de données *classe* fait référence à une classe d’application publique. Dans la génération d’états électroniques, il est représenté comme un [*enregistrement*](#record) contenant un champ séparé pour chaque méthode publique de la classe référencée. Lorsque l’appel de la méthode est paramétré, vous devez également spécifier les arguments requis des types appropriés dans une expression ER configurée pour appeler la méthode.

Dans les composants ER [mappage](general-electronic-reporting.md#data-model-and-model-mapping-components) et [format](general-electronic-reporting.md#FormatComponentOutbound), vous pouvez ajouter la source de données **Classe** qui est présentée comme une source de données et qui renvoie une valeur du type *classe*. Cette source de données expose les méthodes publiques de la classe qui peuvent être appelées au moment de l’exécution.

> [!NOTE]
> Seules les méthodes qui renvoient une valeur peuvent être appelées à partir d’expressions ER.
>
> Seules les méthodes qui ont de zéro à huit arguments peuvent être appelées à partir d’expressions ER.

La valeur par défaut d’une *classe* est **null**.

L’illustration suivante montre comment la source de données **Informations système (xInfo)** du type **Classe** est ajouté pour rendre l’instance de la classe d’application **xInfo** et appeler sa méthode **productName()** pour recevoir le nom de l’application en cours. Le nom de l’application en cours est récupéré au moment de l’exécution par l’exécution de la liaison `xInfo.productName` qui a été configurée pour le champ **Nom du logiciel (SoftwareName)** du modèle de données ER. Cette liaison appelle la méthode `productName()` de la classe d’application **xInfo** qui est représentée dans le mappage de modèle actuel en tant que source de données **Informations système (xInfo)**.

[![Configuration d’une source de données Classe dans le concepteur de mappage de modèle ER](./media/er-formula-supported-data-types-composite-class1.gif)](./media/er-formula-supported-data-types-composite-class1.gif)

L’illustration suivante montre comment le format ER est configuré pour placer le nom d’application fourni dans les documents générés. Le champ **Nom du logiciel (SoftwareName)** du modèle de données utilisé était lié au composant **Chaîne** imbriqué sous l’élément XML **softwareUsed** du format ER. Ainsi, le nom de l’application en cours est placé au moment de l’exécution dans l’élément XML **softwareUsed** d’un document généré au format XML.

[![Configuration de la structure d’un document électronique sortant dans le concepteur de format ER](./media/er-formula-supported-data-types-composite-class2.png)](./media/er-formula-supported-data-types-composite-class2.png)

## <a name="container"></a><a name="container"></a>Conteneur

Le type de données *conteneur* contient un contenu binaire. Une valeur *conteneur* peut être utilisée pour transmettre des informations spécifiques du stockage à un document généré. Dans le cadre ER, ce type de données est fréquemment utilisé pour mettre du contenu multimédia, tel qu’un logo d’entreprise, dans les documents générés.

> [!NOTE]
> Bien que chaque élément multimédia puisse être représenté comme une valeur *conteneur*, toutes les valeurs *conteneur* ne représentent pas un élément multimédia. Par conséquent, si vous configurez un format ER pour qu’il utilise un *conteneur* pour mettre une image dans les documents générés, mais que le *conteneur* référencé ne renvoie pas de contenu multimédia, une exception semblable à l’exemple suivant peut être levée : « Erreur d’exécution du code : binaire (objet), méthode constructFromContainer appelée avec des paramètres non valides. »

La valeur par défaut d’un *conteneur* est **null**.

L’illustration suivante montre comment le champ **Bitmap(Image)** du type *Conteneur* est lié au champ **Logo** du modèle de données du type **Conteneur** dans le mappage du modèle **Facture de vente**. Cette liaison rend le logo de l’entreprise disponible dans n’importe quel format ER conçu pour la définition racine **Facture de vente** et qui utilise ce mappage de modèle au moment de l’exécution.

[![Liaison d’un champ du type Conteneur au concepteur de mappage de modèle ER](./media/er-formula-supported-data-types-composite-container.png)](./media/er-formula-supported-data-types-composite-container.png)

## <a name="record"></a><a name="record"></a>Enregistrer

Un *enregistrement* est une collection de champs nommés, dont chacun est associé à une valeur d’un type de données [primitif](er-formula-supported-data-types-primitive.md) ou d’un type de données composite. Habituellement, un *enregistrement* sert à représenter un seul enregistrement d’une liste d’enregistrements. Dans ce cas, chaque élément représente des champs, des méthodes et des relations distincts.

La valeur par défaut d’un *enregistrement* est **vide**.

> [!NOTE]
> Lorsque vous récupérez la valeur d’un champ d’un *enregistrement* vide, la valeur par défaut du type de données approprié est renvoyée.

Un *enregistrement* peut être obtenu à l’aide des fonctions suivantes :

- [FIRST](er-functions-list-first.md)
- [FIRSTORNULL](er-functions-list-firstornull.md)
- [EMPTYRECORD](er-functions-record-emptyrecord.md)
- [NULLCONTAINER](er-functions-record-nullcontainer.md)

Pour plus d’informations sur la transformation des valeurs *enregistrement*, voir [Liste des fonctions ER dans la catégorie de liste](er-functions-category-list.md).

## <a name="record-list"></a><a name="record-list"></a>Liste d’enregistrements

Une *liste d’enregistrements* est une liste d’éléments du type *enregistrement*. Habituellement, une *liste d’enregistrements* est utilisée pour représenter la liste des enregistrements extraits d’une table de base de données.

Par défaut, les enregistrements d’une *liste d’enregistrements* sont accessibles de manière séquentielle. Pour accéder à un enregistrement spécifique, vous pouvez utiliser la fonction [INDEX](er-functions-list-index.md) et spécifier l’indice *entier*.

La valeur par défaut d’une *liste d’enregistrements* est **vide**. Vous pouvez utiliser la fonction [ISEMPTY](/er-functions-list-isempty.md) pour évaluer si une *liste d’enregistrements* est vide.

> [!NOTE]
> Si une *liste d’enregistrements* est vide, toute tentative d’obtenir une valeur de champ d’un *enregistrement* dedans provoque la levée d’une exception au moment de l’exécution. Pour savoir comment empêcher les exceptions d’exécution de ce type, consultez [Prise en compte des cas de liste vide](er-components-inspections.md#i9).

Une *liste d’enregistrements* peut être initiée à l’aide des fonctions suivantes :

- [ALLITEMS](er-functions-list-allitems.md)
- [ALLITEMSQUERY](er-functions-list-allitemsquery.md)
- [EMPTYLIST](er-functions-list-emptylist.md)
- [LIST](er-functions-list-list.md)
- [LISTDISTINCT](er-functions-list-listdistinct.md)

Pour plus d’informations sur la transformation des valeurs *liste d’enregistrements*, voir [Liste des fonctions ER dans la catégorie de liste](er-functions-category-list.md). Pour apprendre à introduire des éléments de *liste d’enregistrements*, les renseigner avec des données d’application, puis utiliser les données pour générer des documents commerciaux, voir [Concevoir une nouvelle solution de gestion des états électroniques pour imprimer un état personnalisé](er-quick-start1-new-solution.md).

## <a name="object"></a><a name="object"></a>Objet

Un *objet* fait référence à une instance avec état d’une *classe*. Habituellement, un *objet* est initié dans le code source. Il est ensuite transmis à un mappage de modèle ER et fournit des détails sur le contexte d’exécution.

La valeur par défaut d’un *objet* est **null**.

L’illustration suivante montre comment la source de données **ReportDataContract** du type *Objet* est ajoutée pour transmettre des informations sur une facture générée du code source au modèle de mappage **Facture de projet**. Par exemple, le texte de l’instance de facture est transmis dans le cadre du contexte d’exécution. Ce texte est extrait du code source à l’exécution par l’exécution de la liaison `ReportDataContract.parmInvoiceInstanceText` qui a été configurée pour le champ **Note** du modèle de données ER. Cette liaison appelle la méthode `parmInvoiceInstanceText()` de la classe d’application **PSAProjInvoiceContract** qui est représentée dans le mappage de modèle actuel en tant que source de données **ReportDataContract**.

[![Configuration d’une source de données Objet dans le concepteur de mappage de modèle ER](./media/er-formula-supported-data-types-composite-object.gif)](./media/er-formula-supported-data-types-composite-object.gif)

Pour savoir comment transmettre les détails du contexte d’exécution du code source à la solution ER en cours d’exécution, consultez [Développer des artefacts d’application pour appeler l’état conçu](er-quick-start1-new-solution.md#DevelopCustomCode).

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des États électroniques](general-electronic-reporting.md)
- [Langage de formule dans la gestion des états électroniques](er-formula-language.md)
- [Types de données primitifs pris en charge](er-formula-supported-data-types-primitive.md)
