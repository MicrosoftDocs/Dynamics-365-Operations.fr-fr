---
title: Concevoir des configurations pour la gestion des états électroniques pour supprimer les caractères de nomenclature dans les fichiers générés
description: Cette rubrique explique comment configurer un format de gestion des états électroniques pour générer des rapports qui suppriment les caractères de marque d’ordre d’octet (BOM).
author: NickSelin
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d5ada93c0192aadac70c38c8c8c4f3af86ff6fc3
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893274"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a>Concevoir des configurations pour la gestion des états électroniques pour supprimer les caractères de nomenclature dans les fichiers générés

[!include [banner](../includes/banner.md)]

Vous pouvez créer une [solution](er-quick-start1-new-solution.md) de [gestion des états électroniques](general-electronic-reporting.md) pour générer des documents sortants. Pour générer les documents sous forme de fichiers texte ou XML, la solution doit inclure une [configuration](general-electronic-reporting.md#Configuration) de la gestion des états électroniques qui contient un composant de [format](general-electronic-reporting.md#FormatComponentOutbound) de gestion des états électroniques. Pour spécifier l’[encodage de caractère](/windows/win32/intl/character-sets) qui représente le jeu de caractères dans les fichiers générés, le format de gestion des états électroniques doit contenir l’élément de format **Common\\File**. Pour configurer le composant de format de gestion des états électroniques, vous devez ouvrir la version [Brouillon](general-electronic-reporting.md#component-versioning) de la configuration de gestion des états électroniques créée dans le concepteur de format de gestion des états électroniques et ajouter l’élément **Common\\File**. Dans le fichier **Codage**, spécifiez le codage des fichiers sortants générés lors de l’exécution à l’aide de ce composant.

> [!NOTE]
> Si le format contient un nom de codage incorrect, une erreur est générée lorsque vous enregistrez vos modifications des paramètres du format.

![Ajouter un élément racine sur la page Concepteur de format](./media/er-suppress-bom-characters-image1.gif)

Si vous spécifiez **UTF-8**, **UTF-16** ou **UTF-32** comme encodage, l’option **Supprimer les caractères de marque d’ordre d’octet** devient disponible. Définissez cette option sur **Oui** pour supprimer les [ caractères de marque d’ordre d’octet](/globalization/encoding/byte-order-mark) dans les fichiers sortants générés lors de l’exécution du format de gestion des états électroniques modifiable.

> [!NOTE]
> Si vous laissez le champ **Codage** vide, la valeur par défaut **UTF-8** est utilisée.

![Définition de l’option Supprimer les caractères de marque d’ordre d’octet sur la page Concepteur de format](./media/er-suppress-bom-characters-image2.gif)

Pour examiner la fonctionnalité au moment de l’exécution, suivez la procédure appropriée. Par exemple, suivez les étapes de la rubrique [Différer l’exécution des éléments XML aux formats ER](er-defer-xml-element.md). Une fois que vous avez terminé les étapes de la section [Modifier le format pour que le calcul soit basé sur la sortie générée](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) de cette rubrique, suivez ces étapes supplémentaires.

1. Spécifiez le codage UTF :

    1. Sélectionnez l’élément **État** de type **Common\\File**.
    2. Dans le champ **Codage**, spécifiez le codage **UTF-8**.

2. Générez un fichier XML qui comprend un caractère de marque d’ordre d’octet :

    1. définissez l’option **Supprimer les caractères de marque d’ordre d’octet** sur **Non** pour inclure des caractères de marque d’ordre d’octet dans les fichiers XML générés.
    2. Suivez les étapes de la section [Différer l’exécution de l’élément XML récapitulatif pour que le total calculé soit utilisé](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) de la rubrique [Différer l’exécution des éléments XML aux formats ER](er-defer-xml-element.md) et enregistrez le fichier généré sous **SampleXmlReport.xml**.

3. Générez un fichier XML qui ne comprend pas un caractère de marque d’ordre d’octet :

    1. définissez l’option **Supprimer les caractères de marque d’ordre d’octet** sur **Oui** pour supprimer des caractères de marque d’ordre d’octet dans les fichiers XML générés.
    2. Suivez les étapes de la section [Différer l’exécution de l’élément XML récapitulatif pour que le total calculé soit utilisé](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) de la rubrique [Différer l’exécution des éléments XML aux formats ER](er-defer-xml-element.md) et enregistrez le fichier généré sous **SampleXmlReport (1).xml**.

4. Dans un utilitaire de comparaison de fichiers, comparez les fichiers générés.

    La première différence que vous remarquerez est dans l’en-tête du fichier. Le fichier SampleXmlReport.xml contient un caractère de marque d’ordre d’octet, contrairement au fichier SampleXmlReport (1).xml.

    ![Comparaison des fichiers générés avec un utilitaire de comparaison de fichiers](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a>Voir également :

- [Différer l’exécution des éléments XML aux formats ER](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]