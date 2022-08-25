---
title: Utilisation des sources de données USER INPUT PARAMETER pour spécifier les paramètres d’un état
description: Cet article explique comment utiliser les sources de données USER INPUT PARAMETER pour spécifier les paramètres des états que vous générez.
author: kfend
ms.date: 04/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.27
ms.custom: 220314
ms.assetid: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
ms.openlocfilehash: c6d0f1a0d9c5eb70a9812459a25d5b14407cce7a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278705"
---
# <a name="use-user-input-parameter-data-sources-to-specify-parameters-for-a-report"></a>Utilisation des sources de données USER INPUT PARAMETER pour spécifier les paramètres d’un état

[!include[banner](../includes/banner.md)]

Lorsque vous concevez des composants de [gestion des états électroniques](general-electronic-reporting.md) (ER) [mise en correspondance des modèles](er-overview-components.md#model-mapping-component) et [format](er-overview-components.md#format-component) ER, vous pouvez utiliser les sources de données de type *USER INPUT PARAMETER* pour obtenir les valeurs requises qui peuvent être spécifiées dans les champs de saisie de données de la boîte de dialogue lors de l’exécution, avant le début de l’exécution d’un format ER. Cet article décrit les sources de données *USER INPUT PARAMETER* actuellement prises en charge.

## <a name="mandatory-properties"></a><a name="mandatory-properties"></a>Propriétés obligatoires

Vous devez spécifier les propriétés suivantes pour les sources de données de chaque type *USER INPUT PARAMETER* :

- Dans le champ **Nom**, entrez un nom interne pour la source de données. Vous pouvez utiliser ce nom dans d’autres [expressions](er-formula-language.md) et liaisons du composant de mise en correspondance des modèles ou du format configuré.

## <a name="optional-properties"></a><a name="optional-properties"></a>Propriétés facultatives

Vous pouvez spécifier les propriétés suivantes pour les sources de données de type *USER INPUT PARAMETER* :

- Dans le champ **Étiquette**, spécifiez l’étiquette utilisée pour le champ de saisie de données associé dans la boîte de dialogue lors de l’exécution. Vous pouvez ajouter un texte d’étiquette différent pour différents codes de langue en activant le champ **Étiquette**, puis en sélectionnant **Traduire**.
- Dans le champ **Aide**, spécifiez le texte d’aide qui s’affiche au moment de la conception au bas de la page **Concepteur de formats** ou de la page **Concepteur de mise en correspondance des modèles** lorsqu’une source de données modifiable de type *USER INPUT PARAMETER* est sélectionnée. Ce texte peut fournir des détails supplémentaires sur la source de données pour aider les utilisateurs lorsqu’ils configurent le format modifiable ou le composant de mise en correspondance des modèles. Vous pouvez ajouter un texte d’aide différent pour différents codes de langue en sélectionnant **Traduire**.

    > [!NOTE]
    > Le bouton **Traduire** que vous pouvez utiliser pour ajouter des [étiquettes et du texte spécifiques à la langue](er-design-multilingual-reports.md#format-component) devient disponible uniquement après avoir ajouté la source de données, enregistré vos modifications, puis rouvert la source de données pour modification.

- Dans le champ **Lecture seule**, configurez une expression qui renvoie une valeur *[booléenne](er-formula-supported-data-types-primitive.md#boolean)*.

    - Si l’expression configurée renvoie une valeur **True** lors de l’exécution, le champ de saisie des données associé apparaît grisé dans la boîte de dialogue et vous ne pouvez pas modifier sa valeur.
    - Si l’expression configurée renvoie une valeur **False** lors de l’exécution, ou si aucune expression n’est configurée, le champ de saisie des données associé est disponible dans la boîte de dialogue et vous ne pouvez pas modifier sa valeur.

- Dans le champ **Valeur par défaut**, configurez une expression qui renvoie la valeur du type de paramètre référencé. Cette valeur peut être utilisée pour remplir une valeur par défaut pour le champ de saisie de données associé dans la boîte de dialogue lors de l’exécution.

    Lorsque vous exécutez un format ER, la valeur que vous saisissez dans le champ de saisie de données associé de la boîte de dialogue au moment de l’exécution est enregistrée en mémoire en tant que valeur précédemment utilisée. Les valeurs précédemment utilisées sont enregistrées individuellement pour chaque champ exécutant le format ER, de l’utilisateur actuel et de l’organisation actuelle (entreprise).

    - Définissez l’option **Toujours rétablir la valeur par défaut** sur **Oui** si la valeur renvoyée par l’expression **Valeur par défaut** doit toujours être utilisée comme valeur par défaut, quelle que soit la valeur précédemment utilisée.
    - Définissez l’option **Toujours rétablir la valeur par défaut** sur **Non** si la valeur renvoyée par l’expression **Valeur par défaut** doit être utilisée comme valeur par défaut, uniquement lorsque la valeur précédemment utilisée est manquante.

    > [!NOTE]
    > Si vous définissez l’option **Toujours rétablir la valeur par défaut** sur **Oui**, une expression doit être configurée dans le champ **Valeur par défaut**.

- Si vous définissez l’option **Autoriser la sélection multiple** sur **Oui**, vous pouvez sélectionner plusieurs valeurs pour le paramètre configuré lors de l’exécution. Si vous définissez cette option sur **Non**, vous ne pouvez sélectionner qu’une seule valeur.

    > [!NOTE]
    > Cette option n’est pas applicable à tous les types *USER INPUT PARAMETER*. Au moment de la conception, une exception est levée pour informer l’utilisateur que le paramètre d’entrée utilisateur configuré ne prend pas en charge la sélection multiple et qu’une seule valeur peut être sélectionnée ou saisie.
    >
    > Si vous définissez l’option **Autoriser la sélection multiple** sur **Oui**, et si vous avez spécifié une expression dans le champ **Valeur par défaut**, cette expression peut être utilisée pour définir une seule valeur par défaut.

- Sélectionnez l’option **Modifier la visibilité** pour spécifier si le paramètre configuré doit être affiché dans la boîte de dialogue lors de l’exécution.

    > [!NOTE]
    > La visibilité par défaut des sources de données d’un type *USER INPUT PARAMETER* dépend du composant ER qui les contient.
    >
    > - Si une source de données est configurée dans le composant de format, elle est visible par défaut.
    > - Si une source de données est configurée dans le composant de mise en correspondance des modèles, elle est visible uniquement si la valeur de la source de données affecte le résultat lorsqu’un composant ER est exécuté. Par exemple, si vous avez ajouté une source de données mais ne l’avez pas utilisée dans les expressions et les liaisons du composant de mise en correspondance des modèles actuel. Dans ce cas, par défaut, le champ de saisie de données pertinent ne sera pas affiché dans la boîte de dialogue lors de l’exécution. 

    Sur la page **Concepteur de formule**, dans le champ **Formule**, configurez une expression qui renvoie une valeur *booléenne*.

    - Si l’expression configurée renvoie une valeur **True** lors de l’exécution, ou si aucune expression n’est configurée, le champ de saisie des données associé est visible dans la boîte de dialogue lors de l’exécution.
    - Si l’expression configurée renvoie une valeur **False**, le champ de saisie de données associé est masqué dans la boîte de dialogue lors de l’exécution. Lorsqu’elle est appelée par d’autres expressions au moment de l’exécution, elle renvoie la valeur par défaut, la valeur précédemment utilisée ou la valeur par défaut pour la valeur du type de données actuel, en fonction d’autres paramètres.

## <a name="type-specific-properties"></a>Propriétés spécifiques au type

### <a name="application-dependent-user-input-parameter"></a>Paramètre d’entrée utilisateur dépendant de l’application

Utilisez une source de données de type **Général** \> **Paramètre d’entrée utilisateur** pour obtenir la ou les valeurs requises d’un type de données spécifié pour l’instance actuelle de l’application Microsoft Dynamics 365 Finance. Lorsque vous ajoutez une source de données de ce type à un composant ER, spécifiez les propriétés suivantes :

- Dans le champ **Nom du type de données Operations (EDT, enum)**, sélectionnez une application [type de données étendu (EDT)](../extensibility/extensible-edts.md) ou une énumération d’applications.

> [!NOTE]
> Nous vous recommandons de passer en revue les expressions configurées dans les champs **Lecture seule** et **Valeur par défaut** lorsque vous modifiez la référence **Nom du type de données Operations (EDT, enum)** dans une source de données modifiable de type *USER INPUT PARAMETER*.

L’illustration suivante montre les propriétés de la source de données `$TaxRegNum` qui ont été configurées dans la configuration de format ER **Instat XML (DE)**. Cette source de données est configurée pour utiliser le type de données étendu (EDT) *Description* pour offrir le champ de saisie de données **Numéro d’identification fiscale** dans la boîte de dialogue lors de l’exécution.

![Propriétés d’une source de données de type USER INPUT PARAMETER dans la boîte de dialogue de la page Concepteur de formats.](./media/er-user-input-parameter-data-sources-01.png)

L’illustration suivante montre la boîte de dialogue qui s’affiche lors de l’exécution lorsque la configuration de format ER **Instat XML (DE)** est exécutée pour [générer](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md) la déclaration Intrastat. Notez que le champ **Numéro d’identification fiscale** est disponible pour la saisie de données.

![Boîte de dialogue État de déclaration d’échanges de biens du format ER en cours d’exécution sur la page de déclaration d’échanges de biens.](./media/er-user-input-parameter-data-sources-02.png)

### <a name="data-model-enumeration-user-input-parameter"></a>Paramètre d’entrée utilisateur de l’énumération du modèle de données

Utilisez une source de données de type **Modèle de données** \> **Paramètre d’entrée utilisateur de l’énumération** pour obtenir la ou les valeurs requises d’une [énumération](er-formula-supported-data-types-primitive.md#enumeration) de modèle de données unique. Lorsque vous ajoutez une source de données de ce type à un composant ER, spécifiez les propriétés suivantes :

- Dans le champ **Modèle**, spécifiez une référence au modèle de données de base.
- Dans le champ **Énumération du modèle**, spécifiez une référence à une énumération du modèle de données référencé.
- Dans le champ **Version**, sélectionnez le numéro de révision du composant de modèle de données ER qui contient l’énumération de modèle référencée.

    > [!TIP]
    > Au moment de la conception, vous pouvez laisser le champ **Version** vide pour accéder à la liste des énumérations du composant de modèle de données référencé qui réside dans la version brouillon de la configuration de modèle de données ER correspondante. De cette manière, vous pouvez modifier simultanément la version brouillon du composant de mise en correspondance des modèles ou de format et la version brouillon du composant de modèle de données de base.
    >
    > Cependant, notez que le champ **Version** peut être laissé vide uniquement dans la version brouillon du composant de mise en correspondance des modèles ou de format. Lorsque vous remplacez le statut **Brouillon** d’une mise en correspondance des modèles ER ou d’une configuration de format par **Terminé**, ce champ est automatiquement renseigné par le numéro de révision de modèle le plus élevé disponible dans l’instance Finance actuelle. Si vous introduisez une nouvelle énumération ou une nouvelle valeur d’énumération dans la version brouillon de votre modèle de données de base et y faites référence dans la mise en correspondance des modèles modifiable ou le composant de format, complétez cette version brouillon de la configuration du modèle de données de base avant que la version brouillon de votre mise en correspondance des modèles ER ou de la configuration de format ER soit terminée. Sinon, une exception « Chemin d’accès introuvable » sera générée lorsque vous allez remplacer le statut **Brouillon** de la mise en correspondance des modèles ou de la configuration du format par **Terminé**. Ce message vous informe que l’énumération référencée ou la valeur d’énumération est manquante dans le modèle de données de base.

L’illustration suivante montre les propriétés de la source de données `$ReportDirection` qui ont été configurées dans la configuration de format ER **Instat XML (DE) Contoso**. La configuration **Instat XML (DE) Contoso** a été [dérivée](general-electronic-reporting.md#Configuration) de la configuration **Instat XML (DE)**. Cette source de données est configurée pour utiliser l’énumération du modèle *ReportDirection* pour offrir le champ de recherche approprié dans la boîte de dialogue lors de l’exécution.

![Propriétés de la source de données de type USER INPUT PARAMETER dans la boîte de dialogue de la page Concepteur de formats.](./media/er-user-input-parameter-data-sources-03.png)

### <a name="format-enumeration-user-input-parameter"></a>Paramètre d’entrée utilisateur de l’énumération de format

Utilisez une source de données du type **Énumération de format** \> **Paramètre d’entrée utilisateur de l’énumération** pour obtenir la ou les valeurs requises d’une énumération de format unique. Lorsque vous ajoutez une source de données de ce type à un composant ER, spécifiez les propriétés suivantes :

- Dans le champ **Énumération de format**, spécifiez une énumération de format modifiable.

> [!NOTE]
> Les sources de données de ce type ne peuvent être configurées que dans le cadre du composant de format modifiable.

## <a name="additional-resources"></a>Ressources supplémentaires

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Initier les valeurs de source de données du type USER INPUT PARAMETER à partir du code source](er-initiate-uip-data-source-value-from-source-code.md)
