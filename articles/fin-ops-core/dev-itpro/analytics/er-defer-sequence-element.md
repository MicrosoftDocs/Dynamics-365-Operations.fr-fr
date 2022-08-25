---
title: Différer l’exécution des éléments de séquence aux formats ER
description: Cet article explique comment reporter l’exécution d’un élément de séquence au format d’état électronique (ER).
author: kfend
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-07-01
ms.dyn365.ops.version: AX 10.0.5
ms.custom: 58771
ms.assetid: ''
ms.search.form: EROperationDesigner
ms.openlocfilehash: bb42da7b17713430c6143444d87d6fe187dd1124
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281840"
---
# <a name="defer-the-execution-of-sequence-elements-in-er-formats"></a>Différer l’exécution des éléments de séquence aux formats ER

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Vue d’ensemble

Vous pouvez utiliser le concepteur des opérations du cadre [États électroniques (ER)](general-electronic-reporting.md) pour [configurer](tasks/er-format-configuration-2016-11.md) le composant de format d’une solution ER utilisée pour générer des documents sortants au format texte. La structure hiérarchique du composant de format configuré se compose d’éléments de format de différents types. Ces éléments de format sont utilisés pour remplir les documents générés avec les informations requises lors de l’exécution. Par défaut, lorsque vous exécutez un format ER, les éléments de format sont exécutés dans le même ordre qu’ils sont présentés dans la hiérarchie des formats : un par un, de haut en bas. Cependant, au moment de la conception, vous pouvez modifier l’ordre d’exécution pour tous les éléments de séquence du composant de format configuré.

En activant l’option <a name="DeferredSequenceExecution"></a>**Exécution différée** pour un élément de format de séquence au format configuré, vous pouvez différer (reporter) l’exécution de cet élément. Dans ce cas, l’élément n’est pas exécuté tant que tous les autres éléments de son parent n’ont pas été exécutés.

Pour en savoir plus sur cette fonctionnalité, exécutez l’exemple décrit dans cet article.

## <a name="limitations"></a>Limitations

L’option **Exécution différée** est prise en charge uniquement pour les éléments de séquence configurés pour un format ER utilisé pour générer des documents **sortants** au format texte.

L’option **Exécution différée** ne s’applique pas aux séquences qui ont été configurées comme séquences découpées où la longueur maximale est limitée.

## <a name="example-defer-the-execution-of-a-sequence-element-in-an-er-format"></a><a name="Example"></a>Exemple : différer l’exécution d’un élément de séquence au format ER

Les étapes suivantes expliquent comment un utilisateur du consultant fonctionnel de l’administrateur système ou des états électroniques [rôle ](../sysadmin/tasks/assign-users-security-roles.md)peut configurer un format ER qui contient un élément de séquence où l’ordre d’exécution diffère de l’ordre dans la hiérarchie des formats.

Ces étapes peuvent être effectuées dans la société fictive **USMF** dans Microsoft Dynamics 365 Finance.

### <a name="prerequisites"></a>Conditions préalables

Pour terminer cet exemple, vous devez avoir accès à la société **USMF** pour l’un des rôles suivants :

- Consultant fonctionnel des états électroniques
- Administrateur système

Si vous n’avez pas encore terminé l’exemple dans l’article [Différer l’exécution des éléments XML aux formats ER](er-defer-xml-element.md#Example), téléchargez les [configurations ](general-electronic-reporting.md#Configuration)suivantes de l’exemple de solution ER.

| Description du contenu            | Nom de fichier |
|--------------------------------|-----------|
| Configuration de modèle de données ER    | [Modèle d’apprentissage des éléments différés.version.1.xml](https://download.microsoft.com/download/7/6/0/760933ca-4ac3-4f50-bc0c-c35e596ee066/Modeltolearndeferredelements.version.1.xml) |
| Configuration de mise en correspondance de modèle ER | [Modèle d’apprentissage des éléments différés.version.1.1.xml](https://download.microsoft.com/download/c/9/c/c9c4b9dd-b700-4385-a087-a84ce9fc1d0f/Mappingtolearndeferredelements.version.1.1.xml) |

Avant de commencer, vous devez également télécharger et enregistrer la configuration suivante de l’exemple de solution ER.

| Description du contenu     |Nom de fichier |
|-------------------------|----------|
| Configuration de format ER | [Format d’apprentissage des séquences différées.version.1.1.xml](https://download.microsoft.com/download/0/f/5/0f55c341-8285-4d92-a46d-475d9a010927/Formattolearndeferredsequences.version.1.1.xml) |

### <a name="import-the-sample-er-configurations"></a>Importer l’exemple de configurations ER

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sélectionnez **Configurations des états**.
3. Sur la page **Configurations**, si la configuration **Modèle d’apprentissage des éléments différés** n’est pas disponible dans l’arborescence, importez la configuration du modèle de données ER :

    1. Sélectionner **Échanger**, puis sélectionnez **Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir**, recherchez et sélectionnez le fichier **Modèle d’apprentissage des éléments différés.1.xml**, puis sélectionnez **D’accord**.

4. Si la configuration **Apprentissage des éléments différés** n’est pas disponible dans l’arborescence, importez la configuration de mise en correspondance de modèle ER :

    1. Sélectionner **Échanger**, puis sélectionnez **Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir**, recherchez et sélectionnez le fichier **Apprentissage des éléments différés.1.1.xml**, puis sélectionnez **OK**.

5. Importer la configuration de format ER :

    1. Sélectionner **Échanger**, puis sélectionnez **Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir**, recherchez et sélectionnez le fichier **Format d’apprentissage des séquences différées.1.1.xml**, puis sélectionnez **OK**.

6. Dans l’arborescence de configuration, développez **Modèle d’apprentissage des éléments différés**.
7. Consultez la liste des configurations ER importées dans l’arborescence de configuration.

    ![Configurations ER importées sur la page Configurations.](./media/ER-DeferredSequence-Configurations.png)

### <a name="activate-a-configurations-provider"></a>Activer un fournisseur de configurations

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, vérifiez que le [fournisseur de configuration](general-electronic-reporting.md#Provider) pour l’exemple de société Litware, Inc. (`http://www.litware.com`) est répertorié, et qu’il est marqué comme actif. Si ce fournisseur de configuration n’est pas répertorié ou s’il n’est pas marqué comme actif, suivez les étapes de l’article [Créer un fournisseur de configuration et le marquer comme actif](./tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Exemple de société Litware, Inc. sur la page Configurations de localisation.](./media/ER-DeferredSequence-ElectronicReportingWorkspace.png)

### <a name="review-the-imported-model-mapping"></a>Examiner la mise en correspondance des modèles importés

Vérifiez les paramètres du composant de mise en correspondance de modèles ER configuré pour accéder aux transactions fiscales et exposer les données consultées sur demande.

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sélectionnez **Configurations des états**.
3. Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle d’apprentissage des éléments différés**.
4. Sélectionnez la configuration **Modèle d’apprentissage des éléments différés**.
5. Sélectionnez **Concepteur** pour ouvrir la liste des mises en correspondance.
6. Sélectionnez **Concepteur** pour consulter les détails de mise en correspondance.
7. Sélectionnez **Afficher les détails**.
8. Consultez les sources de données configurées pour accéder aux transactions fiscales :

    - La source de données **Transactions** du type *Enregistrement de table* est configurée pour accéder aux enregistrements de la table d’application **TaxTrans**.
    - La source de données **Pièces justificatives** du type *Champ calculé* est configurée pour renvoyer les codes de document requis (**INV-10000349** et **INV-10000350**) en tant que liste d’enregistrements.
    - La source de données **Filtré** du *Champ calculé* est configurée pour sélectionner, dans la source de données **Transactions**, seules les transactions fiscales des pièces justificatives requises.
    - Le domaine **\$TaxAmount** du type *Champ calculé* est ajouté pour la source de données **Filtré** pour exposer la valeur fiscale qui a le signe opposé.
    - La source de données **Groupé** du type *Grouper par* est configurée pour regrouper les transactions fiscales filtrées de la source de données **Filtré**.
    - Le champ d’agrégation **TotalSum** de la source de données **Groupé** est configuré pour résumer les valeurs du domaine **\$TaxAmount** de la source de données **Filtré** pour toutes les transactions fiscales filtrées de cette source de données.

        ![Champ d’agrégation TotalSum sur la page Modifier les paramètres « GroupBy ».](./media/ER-DeferredSequence-GroupByParameters.png)

9. Vérifiez comment les sources de données configurées sont liées au modèle de données et comment elles exposent les données accédées pour les rendre disponibles au format ER :

    - La source de données **Filtré** est liée au champ **Data.List** du modèle de données.
    - Le champ **\$TaxAmount** de la source de données **Filtré** est liée au champ **Data.List.Value** du modèle de données.
    - Le champ **TotalSum** de la source de données **Groupé** est liée au champ **Data.Summary.Total** du modèle de données.

    ![Page Concepteur de mise en correspondance de modèle.](./media/ER-DeferredSequence-ModelMapping.png)

10. Fermez les pages **Concepteur de mise en correspondance de modèle** et **Mappages de modèles**.

### <a name="review-the-imported-format"></a>Examiner le format importé

1. Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez la configuration **Format d’apprentissage des séquences différées**.
2. Sélectionnez **Concepteur** pour consulter les détails du format.
3. Sélectionnez **Afficher les détails**.
4. Vérifiez les paramètres des composants du format ER configurés pour générer un document sortant au format texte qui inclut les détails des transactions fiscales :

    - L’élément de format de séquence **Rapport \\Lignes** est configuré pour remplir le document sortant avec une seule ligne générée à partir des éléments de séquence imbriqués (**Entête**, **Enregistrement**, et **Récapitulatif**).

        ![Élément de format de séquence de lignes et éléments imbriqués sur la page Concepteur de format.](./media/ER-DeferredSequence-Format.png)

    - L’élément de format de séquence **Rapport \\Lignes \\Entête** est configuré pour remplir le document sortant avec une seule ligne d’en-tête qui indique la date et l’heure de début du traitement.
    - L’élément de format de séquence **Rapport \\Lignes \\Enregistrement** est configuré pour remplir le document sortant avec une seule ligne qui affiche les détails des transactions fiscales individuelles. Ces transactions fiscales sont séparées par un point-virgule.

        ![Élément de format de séquence d’enregistrement qui utilise un point-virgule comme délimiteur.](./media/ER-DeferredSequence-Format1.png)

    - L’élément de format de séquence **Rapport \\Lignes \\Récapitulatif** est configuré pour remplir le document sortant avec une seule ligne récapitulative qui inclut la somme des valeurs de taxe des transactions fiscales traitées.

4. Sur l’onglet **Mise en correspondance**, passez en revue les détails suivants :

    - L’élément **Rapport \\Lignes \\Entête** n’a pas besoin d’être lié à une source de données pour générer une seule ligne dans un document sortant.
    - L’élément **Prefix1** génère les symboles **P1** pour indiquer que la ligne ajoutée est la ligne d’en-tête du rapport.
    - L’élément **ExecutionDateTime** génère la date et l’heure (y compris les millisecondes) lorsque la ligne d’en-tête est ajoutée.
    - L’élément **Rapport \\Lignes \\Enregistrement** est lié à la liste **model.Data.List** pour générer une seule ligne pour chaque enregistrement à partir de la liste liée.
    - L’élément **Prefix2** génère les symboles **P2** pour indiquer que la ligne ajoutée est destinée aux détails de la transaction fiscale.
    - L’élément **TaxAmount** est lié à **model.Data.List.Value** (qui est représenté par **\@.Value** dans la vue du chemin relatif) pour générer la valeur fiscale de la transaction fiscale actuelle.
    - L’élément **RunningTotal** est un espace réservé pour le total cumulé des valeurs de taxe. Actuellement, cet élément n’a pas de sortie, car ni une liaison ni une valeur par défaut n’est configurée pour lui.
    - L’élément **ExecutionDateTime** génère la date et l’heure (y compris les millisecondes) lorsque la transaction en cours est traitée dans ce rapport.
    - L’élément **Rapport \\Lignes \\Récapitulatif** n’a pas besoin d’être lié à une source de données pour générer une seule ligne dans un document sortant.
    - L’élément **Prefix3** génère les symboles **P3** pour indiquer que la ligne ajoutée contient la valeur du total de la taxe.
    - L’élément **TotalTaxAmount** est lié à **model.Data.Summary.Total** pour générer la somme des valeurs fiscales des transactions fiscales traitées.
    - L’élément **ExecutionDateTime** génère la date et l’heure (y compris les millisecondes) lorsque la ligne récapitulative est ajoutée.

    ![Onglet Mise en correspondance de la page Concepteur de format.](./media/ER-DeferredSequence-Format2.png)

### <a name="run-the-imported-format"></a>Exécuter le format ER importé

1. Dans la page **Concepteur de format**, sélectionnez **Exécuter**.
2. Téléchargez le fichier proposé par le navigateur Web et ouvrez-le pour examen.

    ![Exemple de fichier d’état téléchargé.](./media/ER-DeferredSequence-Run.png)

Notez que la ligne récapitulative 22 présente la somme des valeurs fiscales pour les transactions traitées. Parce que le format est configuré pour utiliser le **model.Data.Summary.Total** utilisé pour retourner cette somme, la somme est calculée en appelant l’aggrégation **TotalSum** de la source de données **Groupé** du type *GroupBy* qui utilise la mise en correspondance de modèle. Pour calculer cette agrégation, le mappage de modèle itère sur toutes les transactions qui ont été sélectionnées dans la source de données **Filtré**. En comparant les temps d’exécution des lignes 21 et 22, vous pouvez déterminer que le calcul de la somme a pris 10 millisecondes (ms). En comparant les temps d’exécution des lignes 2 et 21, vous pouvez déterminer que la génération de toutes les lignes de transaction a pris 7 millisecondes (ms). Par conséquent, un total de 17 ms était nécessaire.

### <a name="modify-the-format-so-that-the-summing-is-based-on-generated-output"></a>Modifier le format pour que la somme soit basée sur la sortie générée

Si le volume des transactions est beaucoup plus important que le volume dans l’exemple actuel, le temps nécessaire pour générer la somme peut augmenter et entraîner des problèmes de performances. En modifiant le paramètre du format, vous pouvez éviter ces problèmes de performances. Étant donné que vous accédez aux valeurs de taxe pour les inclure dans le rapport généré, vous pouvez réutiliser ces informations pour additionner les valeurs de taxe. Pour plus d’informations, voir [Configurer le format pour effectuer le comptage et la synthèse](./tasks/er-format-counting-summing-1.md).

1. Sur la page **Concepteur de format**, dans l’onglet **Format**, sélectionnez l’élément de fichier **Rapport** dans l’arborescence de format.
2. Définissez l’option **Collecter les détails sur les sorties** sur **Oui**. Vous pouvez maintenant configurer ce format en utilisant le contenu d’un rapport existant comme source de données accessible à l’aide des fonctions ER intégrées dans la catégorie [Collecte de données](er-functions-category-data-collection.md).
3. Dans l’onglet **Mise en correspondance**, sélectionnez l’élément de séquence **Rapport \\Lignes**.
4. Configurez l’expression **Nom de clé de données collectées** comme `WsColumn`.
5. Configurez l’expression **Valeur de clé de données collectées** comme `WsRow`.

    ![Élément de séquence de lignes sur la page Concepteur de format.](./media/ER-DeferredSequence-Format3.png)

6. Sélectionnez l’élément numérique **Rapport \\Lignes \\Enregistrement \\TaxAmount**.
7. Configurez l’expression **Nom de clé de données collectées** comme `SummingAmountKey`.

    ![Élément numérique TaxAmount sur la page Concepteur de format.](./media/ER-DeferredSequence-Format4.png)

    Vous pouvez considérer ce paramètre comme la création d’une feuille de calcul virtuelle, où la valeur de la cellule A1 est ajoutée à la valeur du montant de la taxe de chaque transaction fiscale traitée.

8. Sélectionnez l’élément numérique **Rapport \\Lignes \\Enregistrement \\RunningTotal**, puis sélectionnez **Modifier la formule**.
9. Configurez l’expression `SUMIF(SummingAmountKey, WsColumn, WsRow)` en utilisant la fonction intégrée [SUMIF](er-functions-datacollection-sumif.md).
10. Sélectionnez **Enregistrer**.

    ![Expression SUMIF.](./media/ER-DeferredSequence-FormulaDesigner.png)

11. Fermez la page **Concepteur de formule**.
12. Sélectionnez **Enregistrer**, puis sélectionnez **Exécuter**.
13. Téléchargez et passez en revue le fichier proposé par le navigateur Web.

    ![Fichier téléchargé - Valeurs fiscales totales.](./media/ER-DeferredSequence-Run1.png)

    La ligne 21 contient le total cumulé des valeurs de taxe qui est calculé pour toutes les transactions traitées en utilisant la sortie générée comme source de données. Cette source de données commence au début du rapport et se poursuit jusqu’à la dernière transaction fiscale. La ligne 22 contient la somme des valeurs de taxe pour toutes les transactions traitées qui sont calculées dans le mappage de modèle en utilisant la source de données du type *GroupBy*. Notez que ces valeurs sont égales. Par conséquent, la somme basée sur la sortie peut être utilisée au lieu de **GroupBy**. En comparant les temps d’exécution des lignes 2 et 21, vous pouvez déterminer que la génération de toutes les lignes de transaction et de la somme a pris 9 millisecondes (ms). Par conséquent, en ce qui concerne la génération de lignes détaillées et la somme des valeurs fiscales, le format modifié est environ deux fois plus rapide que le format d’origine.

14. Sélectionnez l’élément numérique **Rapport \\Lignes \\Récapitulatif \\TotalTaxAmount**, puis sélectionnez **Modifier la formule**.
15. Entrez l’expression `SUMIF(SummingAmountKey, WsColumn, WsRow)`au lieu de l’expression existante.
16. Sélectionnez **Enregistrer**, puis sélectionnez **Exécuter**.
17. Téléchargez et passez en revue le fichier proposé par le navigateur Web.

    ![Fichier téléchargé avec formule modifiée.](./media/ER-DeferredSequence-Run2.png)

    Notez que le total cumulé des valeurs de taxe sur la dernière ligne de détails de transaction est désormais égal à la somme sur la ligne de résumé.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Placer les valeurs de la somme basée sur la sortie dans l’en-tête du rapport

Si, par exemple, vous devez présenter la somme des valeurs fiscales dans l’en-tête de votre rapport, vous pouvez modifier votre format.

1. Sur la page **Concepteur de format**, dans l’onglet **Format**, sélectionnez l’élément de séquence **Rapport\\Lignes\\Récapitulatif**.
2. Sélectionnez **Déplacer vers le haut**.
3. Sélectionnez **Enregistrer**, puis sélectionnez **Exécuter**.
4. Téléchargez et passez en revue le fichier proposé par le navigateur Web.

    ![Fichier téléchargé pour la somme dans l’en-tête de l’état.](./media/ER-DeferredSequence-Run3.png)

    Notez que la somme des valeurs de taxe sur la ligne récapitulative 2 est désormais égale à 0 (zéro), car cette somme est désormais calculée en fonction de la sortie générée. Lorsque la ligne 2 est générée, la sortie générée ne contient pas encore de lignes contenant les détails de transaction. Vous pouvez configurer ce format pour différer l’exécution de l’élément de séquence **Rapport \\Lignes \\Récapitulatif** jusqu’à ce que l’élément de séquence **Rapport \\Lignes \\Enregistrement** ait été exécuté pour toutes les transactions fiscales.

### <a name="defer-the-execution-of-the-summary-sequence-so-that-the-calculated-total-is-used"></a>Différer l’exécution de la séquence récapitulative pour que le total calculé soit utilisé

1. Sur la page **Concepteur de format**, dans l’onglet **Format**, sélectionnez l’élément de séquence **Rapport\\Lignes\\Récapitulatif**.
2. Définissez l’option **Exécution différée** sur **Oui**.

    ![Option d’exécution différée de l’élément de séquence récapitulatif sur la page Concepteur de format.](./media/ER-DeferredSequence-Format5.png)

3. Sélectionnez **Enregistrer**, puis sélectionnez **Exécuter**.
4. Téléchargez et passez en revue le fichier proposé par le navigateur Web.

    ![Fichier téléchargé - exécution différée.](./media/ER-DeferredSequence-Run4.png)

    L’élément de séquence **Rapport \\Lignes \\Récapitulatif** n’est désormais exécuté qu’après que tous les autres éléments imbriqués sous son élément parent, **Rapport \\Lignes**, ont été exécutés. Par conséquent, il est exécuté après que l’élément de séquence **Rapport \\Lignes \\Enregistrement** a été exécuté pour toutes les transactions fiscales de la source de données **model.Data.List**. Les temps d’exécution des lignes 1, 2 et 3 et de la dernière ligne 22 indiquent cela.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Configurer le format pour effectuer le comptage et la synthèse](./tasks/er-format-counting-summing-1.md)
- [Suivez l’exécution du format d’ER pour résoudre les problèmes de performances](trace-execution-er-troubleshoot-perf.md)
- [Différer l’exécution des éléments XML aux formats ER](er-defer-xml-element.md#Example)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
