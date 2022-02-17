---
title: Regrouper les enregistrements et agréger les calculs à l’aide des sources de données GROUPBY
description: Cette rubrique explique comment utiliser les sources de données de type GROUPBY dans la gestion des états électroniques (ER).
author: NickSelin
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a6cdc486c5f799bdedafa38e90be989fd328c96
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075620"
---
# <a name="group-records-and-aggregate-calculations-by-using-groupby-data-sources"></a>Regrouper les enregistrements et agréger les calculs à l’aide des sources de données GROUPBY

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Lors de la configuration des mises en correspondance ou des formats de modèle de [gestion des états électroniques (ER)](general-electronic-reporting.md), vous pouvez [ajouter](#AddMmDataSource2) les sources de données nécessaires de type **GroupBy**.

Au moment de la conception, une source de données **GroupBy** est configurée pour identifier les éléments suivants :

- Une [source de données de base](#BaseDataSource) qui contient des enregistrements qui seront regroupés lors de l’exécution
- [Champs de regroupement](#GroupingFields) de la source de données de base, qui sera utilisée pour le regroupement d’enregistrements lors de l’exécution
- [Fonctions d’agrégation](#AggregateFunctions) qui spécifient les calculs agrégés qui seront effectués pour chaque groupe découvert lors de l’exécution

Au moment de l’exécution, une source de données **GroupBy** configurée regroupe les enregistrements qui ont les mêmes valeurs dans les champs de regroupement, puis renvoie une liste des enregistrements. Chaque enregistrement représente un seul groupe. Pour chaque groupe, la source de données expose les valeurs de champ par lesquelles les enregistrements initiaux ont été regroupés, les valeurs des fonctions d’agrégation calculées et la liste des enregistrements de la source de données de base qui appartient au groupe.

## <a name="aggregate-functions"></a><a name="AggregateFunctions"></a>Fonction d’agrégation

Lors de l’exécution, chaque calcul agrégé est effectué pour chaque groupe d’enregistrements. Ce calcul est effectué en utilisant la valeur d’un seul champ ou d’une expression dans les enregistrements d’une source de données qui a été sélectionnée pour le regroupement dans la source de données modifiable du type **GroupBy**. Les fonctions d’agrégation suivantes sont actuellement prises en charge :

- **AVG** : cette fonction renvoie la moyenne des valeurs d’un groupe. Elle peut être utilisée uniquement avec des champs numériques.
- **COUNT** : cette fonction renvoie le nombre d’éléments trouvés dans un groupe.
- **Min** : cette fonction renvoie la valeur minimale parmi les valeurs d’un groupe.
- **Max** : cette fonction renvoie la valeur maximale parmi les valeurs d’un groupe.
- **SUM** : cette fonction renvoie la somme de toutes les valeurs d’un groupe. Elle peut être utilisée uniquement avec des champs numériques.

## <a name="execution-location"></a><a name="ExecutionLocation"></a>Emplacement d’exécution

Lorsque vous modifiez une source de données **GroupBy** et indiquez la source de données de base contenant les enregistrements à regrouper, le système détecte automatiquement l’[emplacement](#ExecutionLocation) le plus efficace pour l’exécution de cette source de données **GroupBy**. Si la source de données de base est [interrogeable](er-functions-list-filter.md#usage-notes) (c’est-à-dire, si elle peut être exécutée au niveau de la base de données), la base de données de l’application est également spécifiée comme emplacement d’exécution de la source de données **GroupBy** modifiable. Sinon, la mémoire du serveur d’applications est spécifiée comme emplacement d’exécution.

Vous pouvez modifier manuellement l’emplacement d’exécution détecté automatiquement en sélectionnant l’emplacement applicable à la source de données configurée. Si l’emplacement d’exécution sélectionné n’est pas applicable, une [erreur de validation](er-components-inspections.md#i5) est lancée au moment de la conception.

> [!TIP]
> Nous vous recommandons d’utiliser l’emplacement de la base de données pour regrouper les sources de données qui exposent un grand nombre d’enregistrements.

## <a name="memory-consumption"></a><a name="MemoryConsumption"></a>Consommation de mémoire

Par défaut, si une source de données **GroupBy** est exécutée en mémoire, la mémoire du serveur d’applications est utilisée pour stocker les enregistrements de la source de données de base qui appartient à chaque groupe découvert en tant qu’enregistrements d’un seul groupe. Pour permettre de réduire la consommation de mémoire, vous pouvez supprimer le stockage des enregistrements pour les sources de données **GroupBy** si elles ont été configurées pour calculer uniquement des fonctions agrégées et que les enregistrements de leur groupe ne sont pas utilisés lors de l’exécution. Pour réduire la consommation de mémoire de cette manière, activez la fonctionnalité **Réduire l’utilisation de la mémoire dans ER lorsque le regroupement d’enregistrements n’est utilisé que pour calculer les agrégations** dans l’espace de travail **Gestion des fonctionnalités**.

## <a name="alternatives"></a><a name="Alternatives"></a>Alternatives

Des agrégations similaires peuvent être calculées en utilisant [différents](er-data-collection-data-sources.md#if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions) types de sources de données ou fonctions intégrées ER.

Pour en savoir plus sur cette fonction, réalisez l’exemple suivant.

## <a name="example-use-a-groupby-data-source-for-aggregate-calculations-and-record-grouping"></a><a name="Example"></a>Exemple : Utiliser une source de données GROUPBY pour les calculs globaux et le regroupement des enregistrements

Cet exemple montre comment un utilisateur ayant le rôle d’administrateur système ou de consultant fonctionnel de gestion des états électroniques peut configurer un mappage de modèle de gestion des états électroniques ayant une source de données **GROUPBY** utilisée pour calculer les fonctions globales et les enregistrements de groupe. Ce mappage de modèle est utilisé pour imprimer le rapport de contrôle lors de la génération de la déclaration d’échanges de biens. Cet état vous permet de passer en revue les transactions d’échanges de biens déclarées.

Les procédures de cet exemple peuvent être effectuées dans la compagnie **DEMF** dans Microsoft Dynamics 365 Finance. 

### <a name="prepare-sample-data"></a>Préparer des exemples de données

Assurez-vous que vous disposez des transactions de déclaration d’échanges de biens pour la génération d’états sur la page **Déclaration d’échanges de biens**. Vous devez avoir des transactions pour différents codes de transport, car vous regrouperez les transactions par champ **Transport** dans cet exemple.

![Préparation des transactions de déclaration d’échanges de bien sur la page de déclaration d’échanges de biens.](./media/er-groupby-data-sources-prepare-transactions.png)

### <a name="configure-the-er-framework"></a>Configurer la structure de gestion des états électroniques

Procédez comme suit dans [Configurer la structure des états électroniques](er-quick-start2-customize-report.md#ConfigureFramework) pour configurer l’ensemble minimum de paramètres d’état électronique. Vous devez terminer cette configuration avant de commencer à utiliser la structure des états électroniques pour concevoir un mappage de modèle de gestion des états électroniques.

### <a name="import-the-standard-er-format-configuration"></a>Importer la configuration du format de gestion des états électroniques standard

Suivez les étapes de l’action [Importer la configuration du format de gestion des états électroniques standard](er-quick-start2-customize-report.md#ImportERSolution1) pour ajouter les configurations des états électroniques standard à votre instance actuelle de Dynamics 365 Finance. Importer la version 1 de la configuration du **modèle de la déclaration d’échanges de biens** depuis le référentiel.

### <a name="create-a-custom-data-model-configuration"></a>Créer une configuration du modèle de données personnalisée

Suivez la procédure dans [Ajouter une configuration du modèle de données personnalisée](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) pour ajouter manuellement une nouvelle configuration de modèle de données de gestion des états électroniques **Modèle de déclaration d’échanges de biens (Litware)** issue de la configuration du **modèle de déclaration d’échanges de biens** importée.

### <a name="configure-a-custom-data-model-component"></a>Configurer un composant du modèle de données personnalisé

Suivez ces étapes pour apporter les modifications requises au modèle de données **Modèle de déclaration d’échanges de biens (Litware)**, afin qu’il puisse être utilisé pour exposer les codes de transport qui ont les détails requis.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Modèle de déclaration d’échanges de biens (Litware)**.
3. Sélectionnez **Concepteur**.
4. Sur la page **Concepteur de modèle de données**, dans l’arborescence de modèle, sélectionnez **Déclaration d’échanges de biens**.
5. Sélectionnez **Nouvelle** pour ajouter un nouveau nœud imbriqué pour le nœud **Déclaration d’échanges de biens**. Dans la boîte de dialogue déroulante pour ajouter un nœud de modèle de données, procédez comme suit :

    1. Dans le champ **Nom**, entrez **Transport**.
    2. Dans le champ **Type d’article**, sélectionnez **Liste d’enregistrements**.
    3. Pour ajouter le nouveau rôle, sélectionnez **Ajouter**.

6. Sélectionnez **Nouveau** pour ajouter un nouveau nœud imbriqué pour le nœud **Transport** que vous venez d’ajouter. Dans la boîte de dialogue déroulante pour ajouter un nœud de modèle de données, procédez comme suit :

    1. Dans le champ **Nom**, entrez **Code**.
    2. Dans le champ **Type d’article**, sélectionnez **Chaîne**.
    3. Pour ajouter le nouveau rôle, sélectionnez **Ajouter**.

7. Sélectionnez **Nouveau** pour ajouter un autre nouveau nœud imbriqué pour le nœud **Transport**. Dans la boîte de dialogue déroulante pour ajouter un nœud de modèle de données, procédez comme suit :

    1. Dans le champ **Nom**, entrez **TotalInvoicedAmount**.
    2. Dans le champ **Type d’article**, sélectionnez **Réel**.
    3. Pour ajouter le nouveau rôle, sélectionnez **Ajouter**.

8. Sélectionnez **Nouveau** pour ajouter un autre nouveau nœud imbriqué pour le nœud **Transport**. Dans la boîte de dialogue déroulante pour ajouter un nœud de modèle de données, procédez comme suit :

    1. Dans le champ **Nom**, entrez **NumberOfTransactions**.
    2. Dans le champ **Type d’article**, sélectionnez **Entier**.
    3. Pour ajouter le nouveau rôle, sélectionnez **Ajouter**.

9. Sélectionnez **Nouveau** pour ajouter un autre nouveau nœud imbriqué pour le nœud **Transport**. Dans la boîte de dialogue déroulante pour ajouter un nœud de modèle de données, procédez comme suit :

    1. Dans le champ **Nom**, entrez **Transaction**.
    2. Dans le champ **Type d’article**, sélectionnez **Liste d’enregistrements**.
    3. Pour ajouter le nouveau rôle, sélectionnez **Ajouter**.

10. Pour le nœud **Transaction** que vous venez d’ajouter, sur le raccourci **Nœud**, sélectionnez **Basculer la référence d’élément**.
11. Dans la boîte de dialogue **Basculer la référence d’élément**, dans l’arborescence du modèle de données, sélectionnez **CommodityRecord**. Puis sélectionnez **OK**.

![Modèle de données configuré dans le concepteur de modèle de données ER.](./media/er-groupby-data-sources-configure-data-model.png)

### <a name="complete-the-design-of-a-custom-data-model"></a>Terminer la conception d’un modèle de données personnalisé

Suivez les étapes de la procédure [Terminer la conception du modèle de données](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) pour compléter la conception du modèle de données dérivé **Modèle de déclaration d’échanges de biens (Litware)**.

### <a name="create-a-new-model-mapping-configuration"></a>Créer une configuration de mise en correspondance de modèles

Suivez la procédure dans [Créer une configuration de mappage du modèle](er-quick-start1-new-solution.md#CreateModelMapping) pour ajouter manuellement une nouvelle configuration de mappage du modèle de gestion des états électroniques **Exemple de mappage de déclaration d’échanges de biens** pour la configuration dérivée du **modèle de déclaration d’échanges de biens (Litware)**.

### <a name="add-a-new-model-mapping-component"></a>Ajouter un nouveau composant de mappage de modèle

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez la configuration **Modèle de déclaration d’échanges de biens**.
3. Sélectionnez la configuration **Exemple de mappage de déclaration d’échanges de biens**.
4. Sélectionnez **Concepteur** pour ouvrir la liste des mises en correspondance.
5. Sélectionnez **Supprimer** pour supprimer le composant de mappage existant.
6. Sélectionnez **Nouveau** pour ajouter un nouveau composant de mappage.
7. Dans le champ **Définition**, sélectionnez **Déclaration d’échanges de biens**.
8. Dans le champ **Nom**, tapez **Mappage de la déclaration d’échanges de biens**.
9. Sélectionnez **Concepteur** pour configurer le nouveau mappage.

### <a name="design-the-added-model-mapping-component"></a>Concevoir le composant de mappage de modèles ajouté

#### <a name="add-a-data-source-to-access-an-application-table"></a><a name="AddMmDataSource1"></a>Ajouter une source de données pour accéder à une table d’application

Configurez une source de données pour accéder aux tables d’application qui contiennent les détails des transactions de déclaration d’échanges de biens.

1. Sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Types de sources de données**, sélectionnez **Dynamics 365 for Operations\\Enregistrements de la table**.
2. Dans le volet **Sources de données**, sélectionnez **Ajouter une racine** pour ajouter une nouvelle source de données qui sera utilisée pour accéder à la table **Intrastat**. Chaque enregistrement dans la table **Déclaration d’échanges de biens** représente une seule transaction de déclaration d’échanges de biens.
3. Dans la boîte de dialogue **Propriétés de la source de données**, dans le champ **Nom**, saisissez **Transaction**.
4. Dans le champ **Table**, entrez **Déclaration d’échanges de biens**.
5. Sélectionner **OK** pour ajouter la nouvelle source de données.

#### <a name="add-a-data-source-to-group-intrastat-transactions"></a><a name="AddMmDataSource2"></a>Ajouter une source de données pour regrouper les transactions de déclaration d’échanges de biens

Configurez une source de données **GroupBy** pour regrouper les transactions de déclaration d’échanges de biens et calculer les fonctions d’agrégation.

1. Sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Types de sources de données**, sélectionnez **Fonctions\\Regrouper par**.
2. Dans le volet **Sources de données**, sélectionnez **Ajouter une racine** pour ajouter une nouvelle source de données qui sera utilisée pour regrouper les transactions de déclaration d’échanges de biens et les fonctions d’agrégation des calculs.
3. Dans la boîte de dialogue **Propriétés de la source de données**, dans le champ **Nom**, saisissez **TransportRecord**.
4. Sélectionnez **Modifier le groupe par** pour configurer les conditions de regroupement.
5. Sur la page **Modifier les paramètres « Regrouper par »**, dans la liste des sources de données du volet de droite, sélectionnez la source de données **Transaction** et développez-la.
6. Sélectionnez **Ajouter un champ à \> Éléments à grouper** pour indiquer que la source de données **Transaction** est sélectionnée comme la <a name="BaseDataSource">source de données de base</a> pour la source de données **GroupBy** configurée. Les enregistrements de la source de données **Transaction** seront regroupés et les valeurs de champ de cette source de données seront utilisées pour les calculs dans les fonctions d’agrégation.
7. Sélectionnez le champ **Transaction\Transport**, puis sélectionnez **Ajouter le champ à \>Champ regroupé** pour indiquer que le champ **Transport** de la source de données de base est sélectionné comme <a name="GroupingFields">critère de regroupement</a> pour la source de données **GroupBy** configurée. En d’autres termes, les enregistrements de la source de données **Transaction** seront regroupés en fonction de la valeur du champ **Transport**. Chaque enregistrement de la source de données **GroupBy** représentera un code de transport unique qui a été trouvé dans les enregistrements de la source de données de base.
8. Sélectionnez le champ **Transaction\AmountMST**, puis procédez comme suit :

    1. Sélectionnez **Ajouter un champ à \> Agréger les champs** pour indiquer qu’une <a name="AggregateFunctions">fonction d’agrégation</a> sera calculée pour ce champ.
    2. Dans le volet **Agrégations**, dans l’enregistrement qui a été ajouté au champ **Transaction\AmountMST** sélectionné, dans le champ **Méthode**, sélectionnez la fonction **Somme**.
    3. Dans le champ facultatif **Nom**, entrez **TotalInvoicedAmount**.

    Ces paramètres spécifient que, pour chaque groupe de transport, le montant total du champ **Transaction\AmountMST** sera calculé.

9. Sélectionnez le champ **Transaction\RecId**, puis procédez comme suit :

    1. Sélectionnez **Ajouter un champ à \> Agréger les champs** pour indiquer qu’une fonction d’agrégation sera calculée pour ce champ.
    2. Dans le volet **Agrégations**, dans l’enregistrement qui a été ajouté au champ **Transaction\RecId** sélectionné, dans le champ **Méthode**, sélectionnez la fonction **Nombre**.
    3. Dans le champ facultatif **Nom**, entrez **NumberOfTransactions**.

    Ces paramètres spécifient que, pour chaque groupe de transport, le nombre de transactions dans le groupe sera calculé.

10. Cliquez sur **Enregistrer**.
11. Passez en revue les paramètres d’<a name="ExecutionLocation">exécution</a> de la source de données modifiable. Vous observerez que **Détection automatique** a été sélectionnée de façon automatique dans le champ **Emplacement d’exécution** et que le champ **Exécution à** contient la valeur **SQL**. Ces paramètres spécifient que la source de données de base **Transaction** est actuellement interrogeable et vous pouvez exécuter la source de données modifiable **GroupBy** au niveau de la base de données.
12. Ouvrez la recherche pour le champ **Emplacement d’exécution** pour consulter la liste des valeurs disponibles. Notez que vous pouvez sélectionner **Requête** ou **En mémoire** pour forcer l’exécution de cette source de données **GroupBy** au niveau de la base de données ou dans la mémoire du serveur d’applications.
13. Sélectionnez **Enregistrer**, puis fermez la page **Modifier les paramètres « Regrouper par »**.
14. Sélectionnez **OK** pour terminer les réglages de la source de données **GroupBy**.

#### <a name="bind-the-groupby-data-source-to-data-model-fields"></a><a name="AddMmBindings"></a>Lier la source de données GroupBy aux champs d’un modèle de données

Liez la source de données configurée aux champs du modèle de données pour spécifier la manière dont le modèle de données sera rempli avec les données d’application au moment de l’exécution.

1. Sur la page **Concepteur de mise en correspondance de modèles**, dans le volet **Modèle de données**, développez le nœud **Transport**.
2. Dans le volet **Sources de données**, développez la source de données **TransportRecord**.
3. Ajoutez une liaison pour exposer la liste des groupes de transport découverts :

    1. Dans le volet **Modèle de données**, sélectionnez l’élément **Transport**.
    2. Dans le volet **Sources de données**, sélectionnez la source de données **TransportRecord**.
    3. Sélectionnez **Lier**.

4. Ajoutez une liaison pour exposer le code de transport de chaque groupe de transport découvert :

    1. Sélectionnez l’éléent du modèle de données **Transport.Code**.
    2. Sélectionnez le champ regroupé **TransportRecord.grouped.TransportMode**.
    3. Sélectionnez **Lier**.

5. Ajoutez une liaison pour exposer les valeurs des fonctions d’agrégation calculées pour chaque groupe de transport découvert :

    1. Sélectionnez l’élément du modèle de données **Transport.NumberOfTransactions**.
    2. Sélectionnez le champ agrégé **TransportRecord.agregated.NumberOfTransactions**.
    3. Sélectionnez **Lier**.
    4. Sélectionnez l’élément du modèle de données **Transport.TotalInvoicedAmount**.
    5. Sélectionnez le champ agrégé **TransportRecord.agregated.TotalInvoicedAmount**.
    6. Sélectionnez **Lier**.

6. Ajoutez une liaison pour exposer les enregistrements de transaction appartenant à chaque groupe de transport découvert :

    1. Sélectionnez l’éléent du modèle de données **Transport.Transaction**.
    2. Sélectionnez le champ **TransportRecord.lines**.
    3. Sélectionnez **Lier**.

    Vous pouvez continuer à configurer des liaisons pour les éléments imbriqués de l’élément du modèle de données **Transport.Transaction** et le champ de source de données **TransportRecord.lines** pour exposer, lors de l’exécution, les détails des transactions de déclaration d’échanges de biens qui appartiennent à chaque groupe de transport découvert.

![Mise en correspondance des modèles configurée dans le concepteur de mise en correspondance des modèles de gestion des états électroniques.](./media/er-groupby-data-sources-configure-model-mapping.png)

### <a name="debug-the-added-model-mapping-component"></a>Déboguer le composant de mappage de modèles ajouté

Utilisez le [Débogueur de source de données ER](er-debug-data-sources.md) pour tester le mappage de modèle configuré.

1. Sur la page **Concepteur de mappage de modèles**, sélectionnez **Démarrer le débogage**.
2. Sur la page **Déboguer les sources de données**, dans le volet de gauche, sélectionnez la source de données **TransportRecord**, puis sélectionnez **Lire tous les enregistrements**.
3. Développez la source de données **TransportRecord**, puis procédez comme suit :

    1. Sélectionnez la source de données **TransportRecord.grouped.TransportMode**.
    2. Sélectionnez **Obtenir la valeur**.
    3. Sélectionnez la source de données **TransportRecord.grouped.NumberOfTransactions**.
    4. Sélectionnez **Obtenir la valeur**.
    5. Sélectionnez la source de données **TransportRecord.grouped.TotalInvoicedAmount**.
    6. Sélectionnez **Obtenir la valeur**.

4. Dans le volet droit, sélectionnez **Développer tout**.

La source de données **TransportRecord** expose deux enregistrements et présente deux codes de transport. Pour chaque code de transport, le nombre de transactions et le montant total facturé sont calculés.

> [!NOTE]
> L’approche de « lecture à la demande » est utilisée lorsqu’une source de données **GroupBy** est appelée pour optimiser les appels de base de données. Par conséquent, certaines des valeurs de champ d’une source de données **GroupBy** sont calculées dans le débogueur de source de données ER uniquement lorsqu’elles sont liées à des champs de modèle de données.

![Résultats du débogage de la source de données sur la page Déboguer les sources de données.](./media/er-groupby-data-sources-debug-datasource.png)

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="is-there-any-way-to-calculate-grand-totals-when-the-group-totals-are-calculated"></a>Existe-t-il un moyen de calculer les totaux généraux lorsque les totaux du groupe sont calculés ?

Oui. Pour calculer les totaux généraux, configurez une autre source de données **GroupBy** où la source de données **GroupBy** précédemment configurée est utilisée comme source de données de base. L’illustration suivante indique la source de données **Totaux** de type **GroupBy** utilisée pour calculer la fonction **SUM** agrégée, selon l’agrégation **SUM** de la source de données **TransportRecord** du type **GroupBy**.

![Source de données Totaux dans le concepteur de mise en correspondance de modèles ER.](./media/er-groupby-data-sources-configure-model-mapping2.png)

L’illustration suivante montre les résultats du débogage de la source de données **Totaux**.

![Résultats du débogage de la source de données Totaux sur la page Déboguer les sources de données.](./media/er-groupby-data-sources-debug-datasource2.png)

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des États électroniques](general-electronic-reporting.md)
- [Déboguer les sources de données d’un format ER exécuté pour analyser le flux de données et la transformation](er-debug-data-sources.md)
- [Utiliser les sources de données COLLECTION DE DONNÉES dans des formats de gestion d’états électroniques](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
