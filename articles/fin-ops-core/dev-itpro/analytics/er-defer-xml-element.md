---
title: Différer l'exécution des éléments XML aux formats ER
description: Cette rubrique explique comment reporter l'exécution d'un élément XML au format d'état électronique (ER).
author: NickSelin
manager: kfend
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 58381f491cda199d77e555e5d3da04714b6a5f8f
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138921"
---
# <a name="defer-the-execution-of-xml-elements-in-er-formats"></a>Différer l'exécution des éléments XML aux formats ER

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Vue d'ensemble

Vous pouvez utiliser le concepteur des opérations du cadre [États électroniques (ER)](general-electronic-reporting.md) pour [configurer](./tasks/er-format-configuration-2016-11.md) le [composant de format](general-electronic-reporting.md#FormatComponentOutbound) d'une solution ER utilisée pour générer des documents sortants au format XML. La structure hiérarchique du composant de format configuré se compose d'éléments de format de différents types. Ces éléments de format sont utilisés pour remplir les documents générés avec les informations requises lors de l'exécution. Par défaut, lorsque vous exécutez un format ER, les éléments de format sont exécutés dans le même ordre qu'ils sont présentés dans la hiérarchie des formats : un par un, de haut en bas. Cependant, au moment de la conception, vous pouvez modifier l'ordre d'exécution pour tous les éléments XML du composant de format configuré.

En activant l'option <a name="DeferredXmlElementExecution"></a>**Exécution différée** pour un élément XML au format configuré, vous pouvez différer (reporter) l'exécution de cet élément. Dans ce cas, l'élément n'est pas exécuté tant que tous les autres éléments de son parent n'ont pas été exécutés.

Pour en savoir plus sur cette fonctionnalité, exécutez l'exemple décrit dans cette rubrique.

## <a name="limitations"></a>Limites

L'option **Exécution différée** est prise en charge uniquement pour les éléments XML configurés pour un format ER utilisé pour générer des documents **sortants** au format XML.

L'option **Exécution différée** est prise en charge uniquement pour les éléments XML qui résident dans un seul autre élément XML. Par conséquent, il ne s'applique pas aux éléments XML qui résident dans d'autres types d'éléments de format (par exemple, dans un élément **Séquence XML**).

L'option **Exécution différée** n'est pas prise en charge pour les éléments XML qui résident dans l'élément de format **Commun \\Fichier** lorsque l'option **Diviser le fichier** est définie sur **Oui**. Pour plus d'informations sur le fractionnement des fichiers XML, voir [Fractionner les fichiers XML générés selon la taille et la quantité de contenu](er-split-files.md).

## <a name="example-defer-the-execution-of-an-xml-element-in-an-er-format"></a><a name="Example"></a>Exemple : différer l'exécution d'un élément XML au format ER

Les étapes suivantes expliquent comment un utilisateur du consultant fonctionnel de l'administrateur système ou des états électroniques [rôle](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/assign-users-security-roles) peut configurer un format ER qui contient un élément XML où l'ordre d'exécution diffère de l'ordre dans la hiérarchie des formats.

Ces étapes peuvent être effectuées dans la société fictive **USMF** dans Microsoft Dynamics 365 Finance.

### <a name="prerequisites"></a>Conditions préalables

Pour terminer cet exemple, vous devez avoir accès à la société **USMF** pour l'un des rôles suivants :

- Consultant fonctionnel des états électroniques
- Administrateur système

Si vous n'avez pas encore terminé l'exemple dans la rubrique [Différer l'exécution des éléments de séquence aux formats ER](er-defer-sequence-element.md#Example), téléchargez les [configurations](general-electronic-reporting.md#Configuration) suivantes de l'exemple de solution ER.

| Description du contenu            | Nom de fichier |
|--------------------------------|-----------|
| Configuration de modèle de données ER    | [Modèle d'apprentissage des éléments différés.version.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Configuration de mise en correspondance de modèle ER | [Modèle d'apprentissage des éléments différés.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

Avant de commencer, vous devez également télécharger et enregistrer la configuration suivante de l'exemple de solution ER sur votre ordinateur local.

| Description du contenu     | Nom de fichier |
|-------------------------|-----------|
| Configuration de format ER | [Format d'apprentissage des éléments XML différés.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

### <a name="import-the-sample-er-configurations"></a>Importer l'exemple de configurations ER

1. Accédez à **Administration d'organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sélectionnez **Configurations des états**.
3. Sur la page **Configurations**, si la configuration **Modèle d'apprentissage des éléments différés** n'est pas disponible dans l'arborescence, importez la configuration du modèle de données ER :

    1. Sélectionner **Échanger**, puis sélectionnez **Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir**, recherchez et sélectionnez le fichier **Modèle d'apprentissage des éléments différés.1.xml**, puis sélectionnez **D'accord**.

4. Si la configuration **Apprentissage des éléments différés** n'est pas disponible dans l'arborescence, importez la configuration de mise en correspondance de modèle ER :

    1. Sélectionner **Échanger**, puis sélectionnez **Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir**, recherchez et sélectionnez le fichier **Apprentissage des éléments différés.1.1.xml**, puis sélectionnez **OK**.

5. Importer la configuration de format ER :

    1. Sélectionner **Échanger**, puis sélectionnez **Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir**, recherchez et sélectionnez le fichier **Format d'apprentissage des éléments XML différés.1.1.xml**, puis sélectionnez **OK**.

6. Dans l'arborescence de configuration, développez **Modèle d'apprentissage des éléments différés**.
7. Consultez la liste des configurations ER importées dans l'arborescence de configuration.

    ![Configurations ER importées sur la page Configurations](./media/ER-DeferredXml-Configurations.png)

### <a name="activate-a-configuration-provider"></a>Activer un fournisseur de configuration

1. Accédez à **Administration d'organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, vérifiez que le [fournisseur de configuration](general-electronic-reporting.md#Provider) pour l'exemple de société Litware, Inc. (`http://www.litware.com`) est répertorié, et qu'il est marqué comme actif. Si ce fournisseur de configuration n'est pas répertorié ou s'il n'est pas marqué comme actif, suivez les étapes de la rubrique [Créer un fournisseur de configuration et le marquer comme actif](./tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Exemple de société Litware, Inc. sur la page Configurations de localisation](./media/ER-DeferredXml-ElectronicReportingWorkspace.png)

### <a name="review-the-imported-model-mapping"></a>Examiner la mise en correspondance des modèles importés

Vérifiez les paramètres du composant de mise en correspondance de modèles ER configuré pour accéder aux transactions fiscales et exposer les données consultées sur demande.

1. Accédez à **Administration d'organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sélectionnez **Configurations des états**.
3. Sur la page **Configurations**, dans l'arborescence de configuration, développez **Modèle d'apprentissage des éléments différés**.
4. Sélectionnez la configuration **Modèle d'apprentissage des éléments différés**.
5. Sélectionnez **Concepteur** pour ouvrir la liste des mises en correspondance.
6. Sélectionnez **Concepteur** pour consulter les détails de mise en correspondance.
7. Sélectionnez **Afficher les détails**.
8. Consultez les sources de données configurées pour accéder aux transactions fiscales :

    - La source de données **Transactions** du type *Enregistrement de table* est configurée pour accéder aux enregistrements de la table d'application **TaxTrans**.
    - La source de données **Pièces justificatives** du type *Champ calculé* est configurée pour renvoyer les codes de document requis (**INV-10000349** et **INV-10000350**) en tant que liste d'enregistrements.
    - La source de données **Filtré** du *Champ calculé* est configurée pour sélectionner, dans la source de données **Transactions**, seules les transactions fiscales des pièces justificatives requises.
    - Le domaine **\$TaxAmount** du type *Champ calculé* est ajouté pour la source de données **Filtré** pour exposer la valeur fiscale qui a le signe opposé.
    - La source de données **Groupé** du type *Grouper par* est configurée pour regrouper les transactions fiscales filtrées de la source de données **Filtré**.
    - Le champ d'agrégation **TotalSum** de la source de données **Groupé** est configuré pour résumer les valeurs du domaine **\$TaxAmount** de la source de données **Filtré** pour toutes les transactions fiscales filtrées de cette source de données.

        ![Champ d'agrégation TotalSum sur la page Modifier les paramètres « GroupBy »](./media/ER-DeferredXml-GroupByParameters.png)

9. Vérifiez comment les sources de données configurées sont liées au modèle de données et comment elles exposent les données accédées pour les rendre disponibles au format ER :

    - La source de données **Filtré** est liée au champ **Data.List** du modèle de données.
    - Le champ **\$TaxAmount** de la source de données **Filtré** est liée au champ **Data.List.Value** du modèle de données.
    - Le champ **TotalSum** de la source de données **Groupé** est liée au champ **Data.Summary.Total** du modèle de données.

    ![Page Concepteur de mise en correspondance de modèle](./media/ER-DeferredXml-ModelMapping.png)

10. Fermez les pages **Concepteur de mise en correspondance de modèle** et **Mappages de modèles**.

### <a name="review-the-imported-format"></a>Examiner le format importé

1. Sur la page **Configurations**, dans l'arborescence de configuration, sélectionnez la configuration **Format d'apprentissage des éléments XML différés**.
2. Sélectionnez **Concepteur** pour consulter les détails du format.
3. Sélectionnez **Afficher les détails**.
4. Vérifiez les paramètres des composants du format ER configurés pour générer un document sortant au format XML qui inclut les détails des transactions fiscales :

    - L'élément XML **Rapport \\Message** est configuré pour remplir le document sortant avec un seul nœud qui inclut les éléments XML imbriqués (**Entête**, **Enregistrement**, et **Récapitulatif**).
    - L'élément de format XML **Rapport \\Message \\Entête** est configuré pour remplir le document sortant avec un seul nœud d'en-tête qui indique la date et l'heure de début du traitement.
    - L'élément XML **Rapport \\Message \\Enregistrement** est configuré pour remplir le document sortant avec un seul nœud d'enregistrement qui affiche les détails d'une transaction individuelle.
    - L'élément XML **Rapport \\Message \\Récapitulatif** est configuré pour remplir le document sortant avec un seul nœud récapitulatif qui inclut la somme des valeurs de taxe des transactions fiscales traitées.

    ![Élément XML de message et éléments XML imbriqués sur la page Concepteur de format](./media/ER-DeferredXml-Format.png)

5. Sur l'onglet **Mise en correspondance**, passez en revue les détails suivants :

    - L'élément **Rapport \\Message \\Entête** n'a pas besoin d'être lié à une source de données pour générer un seul nœud dans un document sortant.
    - L'attribut **ExecutionDateTime** génère la date et l'heure (y compris les millisecondes) lorsque le nœud d'en-tête est ajouté.
    - L'élément **Rapport \\Message \\Enregistrement** est lié à la liste **model.Data.List** pour générer un seul nœud d'enregistrement pour chaque enregistrement à partir de la liste liée.
    - L'attribut **TaxAmount** est lié à **model.Data.List.Value** (qui est représenté par **\@.Value** dans la vue du chemin relatif) pour générer la valeur fiscale de la transaction fiscale actuelle.
    - L'attribut **RunningTotal** est un espace réservé pour le total cumulé des valeurs de taxe. Actuellement, cet attribut n'a pas de sortie, car ni une liaison ni une valeur par défaut n'est configurée pour lui.
    - L'attribut **ExecutionDateTime** génère la date et l'heure (y compris les millisecondes) lorsque la transaction en cours est traitée dans ce rapport.
    - L'élément **Rapport \\Message \\Récapitulatif** n'a pas besoin d'être lié à une source de données pour générer un seul nœud dans un document sortant.
    - L'attribut **TotalTaxAmount** est lié à **model.Data.Summary.Total** pour générer la somme des valeurs fiscales des transactions fiscales traitées.
    - L'attribut **ExecutionDateTime** génère la date et l'heure (y compris les millisecondes) lorsque le nœud récapitulatif est ajouté.

    ![Onglet Mise en correspondance de la page Concepteur de format](./media/ER-DeferredXml-Format2.png)

### <a name="run-the-imported-format"></a>Exécuter le format ER importé

1. Dans la page **Concepteur de format**, sélectionnez **Exécuter**.
2. Téléchargez le fichier proposé par le navigateur Web et ouvrez-le pour examen.

    ![Fichier téléchargé](./media/ER-DeferredXml-Run.png)

Notez que le nœud récapitulatif présente la somme des valeurs fiscales pour les transactions traitées. Parce que le format est configuré pour utiliser le **model.Data.Summary.Total** utilisé pour retourner cette somme, la somme est calculée en appelant l'aggrégation **TotalSum** de la source de données **Groupé** du type *GroupBy* dans la mise en correspondance de modèle. Pour calculer cette agrégation, le mappage de modèle itère sur toutes les transactions qui ont été sélectionnées dans la source de données **Filtré**. En comparant les temps d'exécution du nœud récapitulatif et du dernier nœud d'enregistrement, vous pouvez déterminer que le calcul de la somme a pris 12 millisecondes (ms). En comparant les temps d'exécution du premier nœud et du dernier nœud d'enregistrement, vous pouvez déterminer que la génération de tous les nœuds d'enregistrement a pris 9 millisecondes (ms). Par conséquent, un total de 21 ms était nécessaire.

### <a name="modify-the-format-so-that-the-calculation-is-based-on-generated-output"></a>Modifier le format pour que la calcul soit basé sur la sortie générée

Si le volume de transaction est beaucoup plus important que le volume dans l'exemple actuel, le temps nécessaire pour générer le calcul peut augmenter et entraîner des problèmes de performances. En modifiant le paramètre du format, vous pouvez éviter ces problèmes de performances. Étant donné que vous accédez aux valeurs de taxe pour les inclure dans le rapport généré, vous pouvez réutiliser ces informations pour calculer les valeurs de taxe. Pour plus d'informations, voir [Configurer le format pour effectuer le comptage et la synthèse](./tasks/er-format-counting-summing-1.md).

1. Sur la page **Concepteur de format**, dans l'onglet **Format**, sélectionnez l'élément de fichier **Rapport** dans l'arborescence de format.
2. Définissez l'option **Collecter les détails sur les sorties** sur **Oui**. Vous pouvez maintenant configurer ce format en utilisant le contenu d'un rapport généré comme source de données accessible à l'aide des fonctions ER intégrées dans la catégorie [Collecte de données](er-functions-category-data-collection.md).
3. Dans l'onglet **Mise en correspondance**, sélectionnez l'élément XML **Rapport\\Message\\Enregistrement**.
4. Configurez l'expression **Nom de clé de données collectées** comme `WsColumn`.
5. Configurez l'expression **Valeur de clé de données collectées** comme `WsRow`.

    ![Élément XML d'enregistrement sur la page Concepteur de format](./media/ER-DeferredXml-Format3.png)

6. Sélectionnez l'attribut **Rapport \\Message \\Enregistrement \\TaxAmount**.
7. Configurez l'expression **Nom de clé de données collectées** comme `SummingAmountKey`.

    ![Attribut TaxAmount sur la page Concepteur de format](./media/ER-DeferredXml-Format4.png)

    Vous pouvez considérer ce paramètre comme la création d'une feuille de calcul virtuelle, où la valeur de la cellule A1 est ajoutée à la valeur du montant de la taxe de chaque transaction fiscale traitée.

8. Sélectionnez l'attribut **Rapport \\Message \\Enregistrement \\RunningTotal**, puis sélectionnez **Modifier la formule**.
9. Configurez l'expression `SUMIF(SummingAmountKey, WsColumn, WsRow)` en utilisant la fonction ER intégrée [SUMIF](er-functions-datacollection-sumif.md), puis sélectionnez **Enregistrer**.

    ![Expression SUMIF](./media/ER-DeferredXml-FormulaDesigner.png)

10. Fermez la page **Concepteur de formule**.
11. Sélectionnez **Enregistrer**, puis sélectionnez **Exécuter**.
12. Téléchargez et passez en revue le fichier proposé par le navigateur Web.

    ![Fichier téléchargé](./media/ER-DeferredXml-Run1.png)

    Le dernier nœud d'enregistrement contient le total cumulé des valeurs de taxe qui est calculé pour toutes les transactions traitées en utilisant la sortie générée comme source de données. Cette source de données commence au début du rapport et se poursuit jusqu'à la dernière transaction fiscale. Le nœud récapitulatif contient la somme des valeurs de taxe pour toutes les transactions traitées qui sont calculées dans le mappage de modèle en utilisant la source de données du type *GroupBy*. Notez que ces valeurs sont égales. Par conséquent, la somme basée sur la sortie peut être utilisée au lieu de **GroupBy**. En comparant les temps d'exécution du premier nœud et du nœud récapitulatif, vous pouvez déterminer que la génération de tous les nœuds d'enregistrement et de la somme a pris 11 millisecondes (ms). Par conséquent, en ce qui concerne la génération des nœuds d'enregistrement et de la somme des valeurs fiscales, le format modifié est environ deux fois plus rapide que le format d'origine.

13. Sélectionnez l'attribut **Rapport \\Message \\Récapitulatif \\TotalTaxAmount**, puis sélectionnez **Modifier la formule**.
14. Entrez l'expression `SUMIF(SummingAmountKey, WsColumn, WsRow)` au lieu de l'expression existante.
15. Sélectionnez **Enregistrer**, puis sélectionnez **Exécuter**.
16. Téléchargez et passez en revue le fichier proposé par le navigateur Web.

    ![Fichier téléchargé](./media/ER-DeferredXml-Run2.png)

    Notez que le total cumulé des valeurs de taxe dans le dernier nœud d'enregistrement est désormais égal à la somme dans le nœud récapitulatif.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Placer les valeurs de la somme basée sur la sortie dans l'en-tête du rapport

Si, par exemple, vous devez présenter la somme des valeurs fiscales dans l'en-tête de votre rapport, vous pouvez modifier votre format.

1. Sur la page **Concepteur de format**, dans l'onglet **Format**, sélectionnez l'élément XML **Rapport\\Message\\Récapitulatif**.
2. Sélectionnez **Déplacer vers le haut**.
3. Sélectionnez **Enregistrer**, puis sélectionnez **Exécuter**.
4. Téléchargez et passez en revue le fichier proposé par le navigateur Web.

    ![Fichier téléchargé](./media/ER-DeferredXml-Run3.png)

    Notez que la somme des valeurs de taxe dans le nœud récapitulatif est désormais égale à 0 (zéro), car cette somme est désormais calculée en fonction de la sortie générée. Lorsque le premier nœud d'enregistrement est généré, la sortie générée ne contient pas encore de nœuds d'enregistrement contenant les détails de transaction. Vous pouvez configurer ce format pour différer l'exécution de l'élément de séquence **Rapport \\Message \\Récapitulatif** jusqu'à ce que l'élément de séquence **Rapport \\Message \\Enregistrement** ait été exécuté pour toutes les transactions fiscales.

### <a name="defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used"></a>Différer l'exécution de l'élément XML récapitulatif pour que le total calculé soit utilisé

1. Sur la page **Concepteur de format**, dans l'onglet **Format**, sélectionnez l'élément XML **Rapport\\Message\\Récapitulatif**.
2. Définissez l'option **Exécution différée** sur **Oui**.

    ![Option d'exécution différée de l'élément XML récapitulatif sur la page Concepteur de format](./media/ER-DeferredXml-Format5.png)

3. Sélectionnez **Enregistrer**, puis sélectionnez **Exécuter**.
4. Téléchargez et passez en revue le fichier proposé par le navigateur Web.

    ![Fichier téléchargé](./media/ER-DeferredXml-Run4.png)

    L'élément **Rapport \\Message \\Récapitulatif** n'est désormais exécuté qu'après que tous les autres éléments imbriqués sous son élément parent, **Rapport \\Message**, ont été exécutés. Par conséquent, il est exécuté après que l'élément **Rapport \\Message \\Enregistrement** a été exécuté pour toutes les transactions fiscales de la source de données **model.Data.List**. Les temps d'exécution des premier et dernier nœuds d'enregistrement, ainsi que des nœuds d'en-tête et de résumé, révèlent ce fait.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Configurer le format pour effectuer le comptage et la synthèse](./tasks/er-format-counting-summing-1.md)
- [Suivez l'exécution du format d'ER pour résoudre les problèmes de performances](trace-execution-er-troubleshoot-perf.md)
- [Différer l'exécution des éléments de séquence aux formats ER](er-defer-sequence-element.md#Example)
