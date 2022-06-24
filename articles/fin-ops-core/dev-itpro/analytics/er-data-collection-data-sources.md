---
title: Utiliser les sources de données COLLECTION DE DONNÉES dans des formats de gestion d’états électroniques
description: Cet article explique comment utiliser les sources de données de type COLLECTION DE DONNÉES dans des formats de gestion des états électroniques (ER).
author: NickSelin
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 7591bed5d01ce2c2f434f0e7c81e441eda98483e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883844"
---
# <a name="use-data-collection-data-sources-in-electronic-reporting-formats"></a>Utiliser les sources de données COLLECTION DE DONNÉES dans des formats de gestion d’états électroniques

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser le concepteur des opérations du cadre [États électroniques (ER)](general-electronic-reporting.md) pour configurer le composant de format d’une solution ER utilisée pour générer des documents sortants dans différents formats. La structure hiérarchique du composant de format configuré se compose d’éléments de format de différents types. Ces éléments de format sont utilisés pour remplir les documents générés avec les informations requises lors de l’exécution. Par défaut, lorsque vous exécutez un format ER, les éléments de format sont exécutés dans le même ordre qu’ils sont présentés dans la hiérarchie des formats : un par un, de haut en bas.

Lorsque la gestion des états électroniques exécute un élément de format qui contient une liaison, la formule de cette liaison est exécutée et l’élément de format ajoute la valeur à un document généré. Par exemple, la liaison peut passer la valeur d’un champ modèle de données à un élément de format. Vous pouvez configurer une source de données COLLECTION DE DONNÉES pour collecter les valeurs des champs du modèle de données au moment de l’exécution, effectuer l’addition des valeurs et remplir un document généré avec les valeurs collectées. Pour utiliser cette approche, modifiez la liaison initiale afin que la source de données COLLECTION DE DONNÉES configurée soit utilisée pour transmettre la valeur d’un champ de modèle de données à un élément de format. En transmettant des valeurs via la source de données COLLECTION DE DONNÉES, vous pouvez recueillir les détails requis pour une utilisation ultérieure.

Lorsque vous configurez une source de données COLLECTION DE DONNÉES, spécifiez un type de valeur qui sera géré dans la source de données. Les [types de données](er-formula-supported-data-types-primitive.md) sont actuellement pris en charge pour la collecte de valeurs :

- Booléen
- Date
- Date et heure
- GUID
- Int64
- Entier
- Réel
- Chaîne
- Heure

Vous pouvez utiliser la méthode `Collect(Value)` d’une source de données COLLECTION DE DONNÉES pour transmettre une valeur à une source de données pour la collecte. Dans cette méthode, l’argument `Value` est soit une constante, soit le chemin valide d’un champ de source de données du type de données pertinent.

Utilisez la propriété `Result` d’une source de données COLLECTION DE DONNÉES pour accéder à la liste des valeurs collectées. Cette propriété renvoie une [liste des enregistrements](er-formula-supported-data-types-composite.md#record-list). Les enregistrements de la liste des enregistrements contiennent le champ `Value` que vous pouvez utiliser pour accéder aux valeurs collectées.

Par défaut, une source de données COLLECTION DE DONNÉES ne collecte que des valeurs uniques.

Pour collecter toutes les valeurs, définissez le champ **Collecter toutes les valeurs** de la source de données COLLECTION DE DONNÉES configurée sur **Oui**. Quand le champ **Collecter toutes les valeurs** est défini sur **Oui**, la propriété paramétrée `Sum(Flag)` devient disponible. Vous pouvez utiliser cette propriété pour obtenir le montant total de toutes les valeurs actuellement collectées. Dans cette propriété, l’argument `Flag` est une valeur [booléenne](er-formula-supported-data-types-primitive.md#boolean) utilisée pour indiquer si la valeur totale doit être réinitialisée.

- Lorsque la valeur **False** est fournie, l’addition se poursuit à partir du montant précédemment collecté.
- Lorsque la valeur **True** est fournie, une nouvelle addition est lancée.

Les types de données actuellement pris en charge pour addition :

- Int64
- Entier
- Réel

Pour en savoir plus sur cette fonction, réalisez l’exemple suivant.

## <a name="example-configure-an-er-format-to-do-counting-and-summing-by-using-a-data-collection-data-source"></a>Exemple : Configurer un format ER pour effectuer le décompte et l’addition à l’aide d’une source de données COLLECTION DE DONNÉES

Cet exemple montre comment un utilisateur ayant le rôle d’administrateur système ou de consultant fonctionnel de gestion des états électroniques peut configurer un format ER ayant une source de données COLLECTION DE DONNÉES utilisée pour calculer les totaux cumulés et collecter les valeurs additionnées.

Les procédures de cet exemple peuvent être effectuées dans la compagnie USMF dans Microsoft Dynamics 365 Finance.

### <a name="upload-and-use-the-provided-er-solution"></a>Télécharger et utiliser la solution ER fournie

1. [Importer les exemples de configurations ER](er-defer-sequence-element.md#import-the-sample-er-configurations).
2. [Activer un fournisseur de configuration](er-defer-sequence-element.md#activate-a-configurations-provider).
3. [Examiner la mise en correspondance des modèles importés](er-defer-sequence-element.md#review-the-imported-model-mapping).
4. [Examiner le format importé](er-defer-sequence-element.md#review-the-imported-format).
5. [Exécuter le format importé](er-defer-sequence-element.md#run-the-imported-format).

### <a name="run-the-format-of-the-provided-er-solution"></a>Exécuter le format de la solution ER fournie

1. Dans la page **Concepteur de format**, sélectionnez **Exécuter**.
2. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, sélectionnez **OK**.
3. Téléchargez et passez en revue le fichier proposé par le navigateur Web.

    ![Fichier téléchargé contenant les résultats de l’exécution du format initial](./media/er-data-collection-data-sources-01.png)

### <a name="modify-the-format-of-the-er-solution-to-calculate-the-running-tax-total"></a>Modifier le format de la solution ER pour calculer le total des taxes courantes

Si le volume des transactions est beaucoup plus important que le volume dans l’exemple actuel, le temps nécessaire pour générer la somme peut augmenter et entraîner des problèmes de performances. En modifiant le paramètre du format, vous pouvez éviter ces problèmes de performances. Étant donné que vous accédez aux valeurs de taxe pour les inclure dans le rapport généré, vous pouvez réutiliser ces informations pour additionner les valeurs de taxe.

1. Dans la page **Concepteur de formats**, sur l’onglet **Mise en correspondance**, sélectionnez **Ajouter racine**.
2. Dans la boîte de dialogue **Ajouter une source de données**, sélectionnez **Fonctions** \> **Collection de données**.
3. Dans la boîte de dialogue **Propriétés de la source de données "Collection de données"**, procédez comme suit :

    1. Dans le champ **Nom**, entrez **CollectedTaxValues**.
    2. Dans le champ **Type d’article**, sélectionnez **Réel**.
    3. Dans le champ **Collecter toutes les valeurs**, sélectionnez **Oui**.
    4. Cliquez sur **OK**.

4. Sélectionnez l’élément de format numérique **Rapport\\Lignes\\Enregistrement\\TaxAmount**.

    > [!NOTE]
    > Actuellement, la liaison `@.Value` est configurée pour cet élément. Par conséquent, un document est généré s’il est complété avec les valeurs fiscales du champ `model.Data.List.Value`.

5. Sélectionnez **Modifier la formule**.
6. Sur la page **Concepteur de formule**, procédez comme suit :

    1. Dans le champ **Formule**, remplacez `@.Value` avec `CollectedTaxValues.Collect(@.Value)`.
    2. Enregistrez vos modifications et fermez la page.

    > [!NOTE]
    > La nouvelle liaison transmet les mêmes valeurs de taxe à un document généré. Cependant, ces valeurs sont également collectées dans la source de données **CollectedTaxValues**.

7. Sélectionnez l’élément de format numérique **Rapport\\Lignes\\Enregistrement\\RunningTotal**.
8. Sélectionnez **Modifier la formule**.
9. Sur la page **Concepteur de formule**, procédez comme suit :

    1. Dans le champ **Formule**, saisissez `CollectedTaxValues.Sum(false)`.
    2. Enregistrez vos modifications et fermez la page.

    > [!NOTE]
    > La nouvelle liaison transmet, à un document généré, le montant total des valeurs fiscales déjà saisies.

    ![Éléments numériques ayant mis à jour les liaisons sur la page Concepteur de format](./media/er-data-collection-data-sources-02.png)

10. Sélectionnez **Enregistrer**, puis sélectionnez **Exécuter**.
11. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, sélectionnez **OK**.
12. Téléchargez et passez en revue le fichier proposé par le navigateur Web.

    ![Fichier téléchargé contenant les résultats de l’exécution du format modifié](./media/er-data-collection-data-sources-03.png)

### <a name="modify-the-format-to-evaluate-the-list-of-collected-tax-values"></a>Modifier le format pour évaluer la liste des valeurs fiscales collectées

1. Sur la page **Concepteur de formats**, sur l’onglet **Format**, sélectionnez l’élément au format numérique **Report\\Lines\\Record\\RunningTotal** élément de format numérique, puis procédez comme suit :

    1. Dans le champ **Type numérique**, modifiez la valeur de **Réel** à **Entier**.
    2. Dans le champ **Format numérique** changez la valeur de **F2** vers **F0**.

3. Sur l’onglet **Mise en correspondance**, sélectionnez **Modifier la formule**.
4. Sur la page **Concepteur de formule**, procédez comme suit :

    1. Dans le champ **Formule**, saisissez `COUNT(CollectedTaxValues.Result)`.
    2. Enregistrez vos modifications et fermez la page.

    > [!NOTE]
    > La nouvelle liaison transmet, à un document généré, le nombre d’enregistrements de la liste où les valeurs fiscales sont collectées.

5. Sélectionnez **Enregistrer**, puis sélectionnez **Exécuter**.
6. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, sélectionnez **OK**.
7. Téléchargez et passez en revue le fichier proposé par le navigateur Web.

    ![Fichier téléchargé contenant les résultats de l’exécution d’un autre format modifié](./media/er-data-collection-data-sources-04.png)

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions"></a>Si je dois calculer des totaux cumulés et collecter des données, quelle est la différence entre l’utilisation d’une source de données COLLECTION DE DONNÉES et l’utilisation des fonctions intégrées COLLECTION DE DONNÉES ?

À la fois une source de données COLLECTION DE DONNÉES et les fonctions [COLLECTION DE DONNÉES](er-functions-category-data-collection.md) peuvent être utilisées pour la collecte, l’addition et le comptage de données, en fonction des informations transmises à un document sortant généré. Cependant, lorsque vous essayez de décider quelle technique utiliser, vous devez tenir compte des points suivants.

| Source de données | Fonctions intégrées |
|-------------| ------------------ |
| Seules les valeurs sont collectées. | <p>Les valeurs nommées sont collectées. Par conséquent, les totaux peuvent être calculés pour des groupes de valeurs distincts.</p><p>De plus, les groupes peuvent être extraits sous forme de liste.</p><p>Les valeurs de texte peuvent également être collectées.</p> |
| Les valeurs uniques sont automatiquement collectées. | Des paramètres supplémentaires sont nécessaires pour extraire une liste de valeurs uniques à partir des valeurs collectées. |
| Les performances dépendent du volume de valeurs collectées. | En pratique, les performances ne dépendent pas du volume de valeurs collectées. |
| Cette technique fonctionne pour tous les types de documents sortants. | Cette technique ne fonctionne que pour les documents texte et XML. |

## <a name="additional-resources"></a>Ressources supplémentaires

- [Configurer le format pour effectuer le comptage et la synthèse](./tasks/er-format-counting-summing-1.md)
- [Différer l’exécution des éléments de séquence aux formats ER](er-defer-sequence-element.md#Example)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
