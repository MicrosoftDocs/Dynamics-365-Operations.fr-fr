---
title: Configurer les sources de données de recherche pour utiliser les paramètres spécifiques à l’application d’états électroniques
description: Cette rubrique explique comment vous pouvez configurer des sources de données de recherche dans les formats de gestion des états électroniques pour utiliser les paramètres propres à une application ER.
author: NickSelin
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 131d14f1f1aa329bd71b1f8a4015192736bd8e44
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022573"
---
# <a name="configure-lookup-data-sources-to-use-er-application-specific-parameters"></a>Configurer les sources de données de recherche pour utiliser les paramètres spécifiques à l’application d’états électroniques 

[!include[banner](../includes/banner.md)]

La [Gestion des états électroniques (ER)](general-electronic-reporting.md) vous permet de configurer le filtrage des données dans un format de gestion des états électroniques de telle sorte qu’il soit basé sur un ensemble de règles abstraites. Cet ensemble de règles peut être configuré pour utiliser la source de données du type **Recherche** disponible dans un format de gestion des états électroniques. Vous pouvez spécifier des règles réelles au delà des concepteurs de composants de gestion des états électroniques à l’aide de l’interface utilisateur qui est automatiquement générée selon les paramètres de la source de données **Recherche** au format de gestion des états électroniques correspondant et les données actuelles de l’entité juridique. Finalement, les règles spécifiées seront accessibles par la source de données **Recherche** de la gestion des états électroniques lorsque ce format ER est exécuté.

> [!NOTE]
> Utilisez les sources de données configurées du format ER modifiable pour spécifier quelles données d'application seront utilisées pour configurer les règles réelles.

Utilisez le [Concepteur d’opérations de gestion des états électroniques](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) pour convertir une source de données du type **Recherche** dans votre format ER. La source de données doit être configurée pour décrire l'apparence de vos règles abstraites, y compris les éléments suivants :

   - L'ensemble de paramètres d'un certain type de données dont la valeur est fournie pour spécifier une seule règle.
   - Le type de valeur d'un certain type de données renvoyé par une règle unique lorsque cette règle est considérée comme la plus appropriée parmi d'autres.

Vous pouvez configurer les types suivants de sources de données de **Recherche** en fonction du type de valeur renvoyée par une règle configurée :

   - Utilisez le type **Modèle de données\Recherche** lorsqu'une valeur d'énumération de modèle doit être renvoyée.
   - Utilisez le type **Opérations Dynamics 365\Recherche** lorsqu'une valeur d'énumération d'application ou une valeur de [type de données étendu](../extensibility/extensible-edts.md) d'application doit être renvoyée.
   - Utilisez le type **Énumération de format\Recherche** lorsqu'une valeur d'énumération de format doit être renvoyée.

L'illustration suivante montre comment une énumération de format peut être configurée dans l'exemple de format ER.

   ![Affichage d'une énumération de format comme base de la source de données de recherche configurée](./media/er-lookup-data-sources-img1.gif)

L'illustration suivante montre les composants de format qui ont été configurés pour établir le rapport de différents types de taxes dans une section différente d'un rapport généré.

   ![Affichage des sections de format pour rapporter séparément différents types de taxes](./media/er-lookup-data-sources-img2.png)

L'illustration suivante montre comment le Concepteur d’opérations de gestion des états électroniques permet d'ajouter une source de données du type **Énumération de format\Recherche**.  La source de données ajoutée est configurée pour renvoyer une valeur de l'énumération de format `List of taxation levels`.

   ![Ajout d'une source de données ER de type Énumération de format\Recherche](./media/er-lookup-data-sources-img3.gif)

L'illustration suivante montre comment la source de données ajoutée est configurée pour utiliser le champ **Code** de la liste d'enregistrements **Model.Data.Tax** de la source de données **Modèle** en tant que paramètre qui doit être spécifié pour chaque règle configurée.

![Configuration des paramètres de la source de données ajoutée du type Énumération de format\Recherche](./media/er-lookup-data-sources-img4.gif)

La source de données `Model.Data.Tax` ajoutée est configurée pour spécifier un code taxe pour chaque règle configurée en accédant aux enregistrements de la table d'application **TaxTable**.

   ![Examen de la source de données de recherche d'une seule société du type Énumération de format\Recherche](./media/er-lookup-data-sources-img5.gif)

Vous pouvez configurer les règles de recherche pour le format ER sélectionné à l'aide de l'interface utilisateur qui est automatiquement alignée sur la structure de la source de données configurée. Actuellement, cette interface utilisateur requiert que pour chaque règle, vous spécifiiez la valeur renvoyée comme la valeur d'énumération de format `List of taxation levels` ainsi que le code taxe en tant que paramètre.

   ![Configurer les règles pour la source de données configurée](./media/er-lookup-data-sources-img6.gif)

L'illustration suivante montre comment la source de données `Model.Data.Summary.LevelByLookup` du type **Champ calculé** peut être configurée pour appeler la source de données **Recherche** fournissant les paramètres requis. Pour traiter cet appel au moment de l'exécution, la Gestion des états électroniques parcourt la liste des règles configurées dans l'ordre défini pour localiser la première règle qui satisfait les conditions stipulées. Dans cet exemple, c'est la règle qui contient le code taxe qui correspond à celui fourni. Par conséquent, la règle la plus appropriée est trouvée et la valeur d'énumération configurée pour la règle trouvée est renvoyée par cette source de données.

> [!NOTE]
> Une exception est levée lorsqu'aucune règle applicable n'est trouvée. Pour éviter ces exceptions, configurez des règles supplémentaires à la fin de la liste de règles pour gérer les cas où une valeur non configurée ou aucune valeur n'est fournie. Utilisez les options **\*Non vide\*** et **\*Vide\*** en conséquence.  
>
> ![Ajouter une source de données pour appeler la source de données Recherche configurée](./media/er-lookup-data-sources-img7.png)

Lorsque vous définissez l'option **Intersociétés** sur **Oui** pour la source de données de recherche modifiable, vous ajoutez un nouveau paramètre requis **Société** à l'ensemble de paramètres de cette source de données. La valeur du paramètre **Société** doit être spécifiée au moment de l'exécution lorsque la source de données de recherche est appelée. Lorsque le code société est spécifié au moment de l'exécution, les règles configurées pour cette société sont utilisées pour rechercher la règle la plus appropriée et la valeur correspondante est renvoyée. L'illustration suivante montre comment procéder et comment le jeu de paramètres de la source de données modifiable est modifié.

   ![Examen de la source de données de recherche intersociétés du type Énumération de format\Recherche](./media/er-lookup-data-sources-img8.gif)

> [!NOTE]
> Sélectionnez chaque société séparément pour configurer l'ensemble de règles pour cette source de données de recherche du format ER modifiable. Une exception est levée lors de l'exécution lorsque la recherche intersociétés est appelée avec le code de la société pour laquelle la configuration de la recherche n'a pas été menée à bien.
>
> Assurez-vous que vous accordez des autorisations à un utilisateur qui exécute le format ER avec la source de données **Recherche** intersociétés pour accéder aux données de chaque société faisant partie de l'étendue de cette source de données. Sinon, une exception est levée au moment de l'exécution.

À partir de la version 10.0.19, les fonctionnalités étendues de la source de données **Recherche** sont disponibles. Lorsque vous définissez l'option **Étendue** sur **Oui** pour la source de données de recherche modifiable, la source de données de recherche configurée est transformée en source de données structurée qui offre les fonctionnalités supplémentaires d'analyse de l'ensemble de règles configuré. L’illustration suivante présente cette transformation.

   ![Examen de la source de données de recherche structurée du type Énumération de format\Recherche](./media/er-lookup-data-sources-img9.gif)

- Le sous-élément **Lookup** est conçu comme une fonction permettant de trouver la règle la plus appropriée parmi l'ensemble de règles configurables en fonction de l'ensemble de paramètres fourni.
- Le sous-élément **IsLookupResultSet** est conçu comme une fonction permettant d'accepter la valeur fournie de la source de données d'énumération de base et de renvoyer la valeur *Booléenne* **True** lorsque l'ensemble de règles contient au moins une règle pour laquelle la valeur d'énumération fournie a été configurée comme valeur renvoyée. Cette fonction renvoie la valeur *Booléenne* **False** lorsqu'aucune règle n'est configurée pour renvoyer la valeur d'énumération fournie.
- Le sous-élément **Setting** est conçu comme une fonction qui renvoie l'ensemble des règles configurées sous forme d'enregistrements d'une liste d'enregistrements. Les valeurs renvoyées et l'ensemble des paramètres des règles configurées sont présentés dans chaque enregistrement renvoyé sous forme de champs des types de données pertinents :

    - La valeur renvoyée est présentée comme le champ **Résultat de la recherche**.
    - Les paramètres configurés sont présentés sous forme de champs ayant des noms de paramètres (champ **Code** dans cet exemple).

Pour plus d'informations sur la configuration de la source de données **Recherche**, voir [Configurer les formats ER pour utiliser les paramètres spécifiés par entité juridique](er-app-specific-parameters-configure-format.md). Pour savoir comment définir les règles de recherche, voir [Configurer les paramètres d'un format ER par entité juridique](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer des formats de gestion des états électroniques pour utiliser les paramètres spécifiés par entité juridique](er-app-specific-parameters-configure-format.md)

[Définir les paramètres d’un format de gestion des états électroniques par entité juridique](er-app-specific-parameters-set-up.md)
