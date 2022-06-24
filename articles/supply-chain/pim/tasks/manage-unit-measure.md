---
title: Gérer les unités de mesure
description: Cet article décrit comment définir une unité de mesure, fournir des traductions pour l’unité et sa description, et définir des règles de conversion pour les unités associées.
author: t-benebo
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8e2c21756b270ef7d914dc74a0cf61727953206a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863909"
---
# <a name="manage-units-of-measure"></a>Gérer les unités de mesure

[!include [banner](../../includes/banner.md)]

Cet article décrit comment définir une unité de mesure, fournir des traductions pour l’unité et sa description, et définir des règles de conversion pour les unités associées.

## <a name="open-the-units-page"></a>Ouvrir la page Unités

Pour créer et utiliser les unités de mesure disponibles dans votre système, accédez à **Administration d’organisation \> Paramétrage \> Unités \> Unités**.

Les sections restantes de cet article décrivent ce que vous pouvez faire sur la page **Unités**.

## <a name="create-standard-units-and-conversions"></a>Créer des unités standard et des conversions

Si votre système n'inclut pas déjà les unités de mesure les plus couramment utilisées pour le système métrique et/ou le système coutumier américain (USCS), l'assistant de configuration des unités peut vous aider à démarrer rapidement avec les définitions et les conversions d'unités de base. Pour exécuter l'assistant, sélectionnez **Assistant Création d'unités** dans le volet Actions, puis suivez les instructions à l'écran.

## <a name="create-or-edit-a-unit-of-measure"></a>Créer ou modifier une unité de mesure

Pour créer ou modifier une unité de mesure, procédez comme suit :

1. Utilisez l’une des procédures suivantes :

    - Pour modifier une unité existante, sélectionnez-la dans le volet de liste.
    - Pour créer une unité, sélectionnez **Nouveau** dans le volet Action.

1. Dans l’en-tête de l'enregistrement, définissez les champs suivants :

    - **Unité** - Entrez l'ID ou le symbole à utiliser pour faire référence à l'unité dans la langue du système. Cet identifiant ou symbole est généralement une abréviation courante pour l'unité, telle que *ch* pour chaque ou *cm* pour centimètre.
    - **Description** – Entrez un nom descriptif pour l’unité dans la langue du système. Ce nom est généralement le nom complet de l'unité, tel que *Chaque* ou *Centimètre*.

1. Dans l’organisateur **Général**, définissez les champs suivants :<!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - **Classe d'unité** - Sélectionnez la propriété que l'unité mesure (telle que la longueur, la surface, la masse ou la quantité).
    - **Système d'unités** - Sélectionnez le système de mesure auquel appartient l'unité (*Unités métriques* ou *Unités de mesure américaines*).
    - **Unité de base** - Définissez cette option sur *Oui* pour utiliser l'unité actuelle comme unité de base pour sa classe d'unité. Dans ce cas, il vous suffit de spécifier le facteur de conversion entre l'unité de base et chaque unité supplémentaire de la classe d'unités. Le système peut alors effectuer la conversion entre toutes les unités de cette classe d'unités. Par conséquent, il est plus facile de configurer des conversions.

        Par exemple, si le litre est l'unité de base de la classe d'unité *Volume*, il vous suffit de configurer des facteurs de conversion de gallon en litre et de litre en gallon. Le système peut alors également convertir de litre en pinte.

        Vous ne pouvez avoir qu'une seule unité de base par classe d'unités.

    - **Unité système** - Définissez cette option sur *Oui* pour utiliser l'unité actuelle comme unité supposée pour toutes les mesures non spécifiées dans une classe d'unités. Par exemple, si un champ utilisé pour saisir une quantité ne permet pas de spécifier une unité (ou si l'utilisateur n'en sélectionne pas), le système utilise l'unité définie comme unité système pour la classe d'unités *Quantité*. Vous ne pouvez avoir qu'une seule unité système par classe d'unités.
    - **Précision décimale** - Spécifiez le nombre de décimales auxquelles les valeurs spécifiées pour l'unité actuelle ou les conversions doivent être arrondies.

1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="define-unit-translations"></a>Définir des traductions d’unité

Pour définir les traductions de l'ID ou du symbole et la description d'une unité de mesure, procédez comme suit :

1. Créez ou sélectionnez l'unité pour laquelle créer des traductions.
1. Dans le volet Actions, cliquez sur **Textes d’unité**.

    La page **Textes d’unité** apparaît. Cette page permet de définir les traductions de l'ID ou du symbole de l'unité sélectionnée. Ces traductions peuvent ensuite être utilisées sur des documents externes dans des langues spécifiques au client ou au fournisseur.

1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Langue**, sélectionnez la langue dans laquelle traduire l'ID unité ou le symbole.
1. Dans le champ **Texte**, saisissez la traduction de l'ID unité ou du symbole dans la langue sélectionnée.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Fermez la page.
1. Dans le volet **Actions**, sélectionnez **Descriptions de l’unité traduite**.

    La page **Descriptions de l'unité traduite** apparaît. Cette page permet de définir des descriptions spécifiques à la langue de l'unité sélectionnée.

1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Langue**, sélectionnez la langue dans laquelle traduire la description de l’unité.
1. Dans le champ **Description**, saisissez la traduction de la description de l’unité dans la langue sélectionnée.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Fermez la page.

## <a name="define-unit-conversion-rules"></a>Définir des règles de conversion d’unités

Pour définir des règles de conversion entre unités de mesure, procédez comme suit :

1. Créez ou sélectionnez l'unité pour laquelle définir des règles de conversion.
1. Dans le volet Actions, cliquez sur **Conversions d'unités**.

    La page **Conversions d’unités** s’ouvre. Cette page permet de définir des règles pour convertir l’unité sélectionnée vers et depuis d’autres unités appartenant à la classe d’unités.

1. Sélectionnez l’un des onglets suivants, selon le type de conversion que vous souhaitez paramétrer :

    - **Conversions standard** – Pour paramétrer des règles de conversion standard qui s'appliquent à tous les produits.
    - **Conversions intra-classe** – Pour paramétrer des règles de conversion spécifiques à un produit pour les unités de mesure appartenant à la même classe d'unités.
    - **Conversions inter-classe** – Pour paramétrer des règles de conversion spécifiques à un produit pour les unités de mesure appartenant à plusieurs classes d'unités.

1. Utilisez l’une des procédures suivantes :

    - Pour créer une conversion, sélectionnez **Nouveau** dans la barre d'outils.
    - Pour modifier une conversion existante, sélectionnez la conversion dans la grille, puis sélectionnez **Modifier** dans la barre d'outils.

1. Dans la boîte de dialogue déroulante qui s’affiche, sélectionnez les champs suivants :

    - **Produit** - Sélectionnez le produit spécifique auquel s'applique la conversion. Ce champ n'est disponible que pour les conversions intra-classes et inter-classes.
    - **Disposition de la formule** - Laissez ce champ défini sur *Simple* pour spécifier une conversion simple qui a un seul facteur. Définissez ce champ sur *Avancé* pour mettre en place une équation plus complexe. Le format des équations avancées varie en fonction de la classe d'unité.
    - **Unité d’origine** - Ce champ affiche l'unité sélectionnée. En règle générale, vous ne devez pas modifier la valeur. (Si vous modifiez la valeur, vous devez ouvrir la page **Conversions d'unités** de l'unité sélectionnée pour afficher votre nouvelle conversion après l'avoir enregistrée.)
    - **Unité de destination** - Sélectionnez l'unité vers laquelle effectuer la conversion.
    - **Arrondi** - Sélectionnez la manière dont les fractions doivent être arrondies, en fonction de la valeur du champ **Précision décimale** de l'unité sélectionnée (*Au plus proche*, *Haut* ou *Bas*).
    - **Formule de conversion** - Utilisez les champs restants en haut de la boîte de dialogue déroulante pour spécifier la formule de conversion entre les deux unités. Les champs disponibles varient en fonction de la classe d'unité et de la disposition de formule que vous avez sélectionnées.

1. Cliquez sur **OK**.
1. Fermez la page.

> [!TIP]
> Vous pouvez également configurer des conversions d'unités par variante de produit. Pour plus d’informations, consultez [Conversion d’unité de mesure selon la variante de produit](../uom-conversion-per-product-variant.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
