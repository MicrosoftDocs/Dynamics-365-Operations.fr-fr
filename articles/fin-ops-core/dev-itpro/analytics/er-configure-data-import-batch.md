---
title: Importer les données depuis les fichiers sélectionnés manuellement en mode de traitement par lots
description: Cette rubrique explique comment importer des données à partir de fichiers sélectionnés manuellement en mode de traitement par lots.
author: NickSelin
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERImportFormatSourceTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: Release 10.0.25
ms.openlocfilehash: 8615b5a0623fd696c64f4ec03e481a2bcb16c0ac
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075610"
---
# <a name="import-data-from-manually-selected-files-in-batch-mode"></a>Importer les données depuis les fichiers sélectionnés manuellement en mode de traitement par lots

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Pour utiliser la structure [Gestion des états électroniques (ER)](general-electronic-reporting.md) pour importer des données à partir de fichiers entrants sélectionnés manuellement en mode de traitement par lots, configurez un [format](er-overview-components.md#format-component) ER qui prend en charge l’importation. Exécutez ensuite un [mappage du modèle](er-overview-components.md#model-mapping-component) de type **Vers la destination** qui utilise ce format comme source de données. Pour importer des données, accédez au fichier que vous souhaitez importer et sélectionnez-le manuellement. 

La nouvelle fonctionnalité ER qui prend en charge de l’importation des données en mode de traitement par lots permet à ce processus d’être configuré en mode sans assistance. Vous pouvez utiliser les configurations ER pour effectuer l’importation de données en planifiant une nouvelle tâche par lots à partir de l’interface utilisateur (IU) ER.

Cette rubrique explique comment exécuter l’importation des données à partir d’un fichier sélectionné manuellement en mode de traitement par lots. Les exemples utilisent les transactions fournisseur comme données commerciales. Ces étapes peuvent être effectuées dans la société fictive **USMF**. Aucun codage n’est requis.

## <a name="prerequisites"></a>Conditions préalables

Pour exécuter les exemples décrits dans cette rubrique, vous devez disposer de l’accès suivant :

- Un des rôles suivants :

    - Développeur d’états électroniques
    - Consultant fonctionnel de gestion des états électroniques
    - Administrateur système

- Configurations du format et du modèle ER pour les paiements de déclaration des honoraires

### <a name="create-the-required-er-configurations"></a>Créer les configurations ER requises

Pour créer les configurations ER requises et obtenir d’autres prérequis, suivez l’une de ces étapes :

- Lisez les guides de tâches **ER Importer des données à partir d’un fichier Microsoft Excel**, qui font partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**. Ces guides de tâches vous aident tout au long du processus de création et d’utilisation des configurations ER pour importer en mode interactif des transactions fournisseur à partir de fichiers Microsoft Excel. Pour plus d’informations, voir [Analyser les documents entrants au format Excel](parse-incoming-documents-excel.md).
- Complétez les exemples dans [Configurer l’importation de données depuis SharePoint](er-configure-data-import-sharepoint.md). Ces exemples vous guident tout au long du processus de création et d’utilisation des configurations ER pour importer en mode interactif des transactions fournisseur à partir de fichiers Excel enregistrés dans le dossier SharePoint.

### <a name="download-the-required-er-configurations"></a>Télécharger les configurations ER requises

1. Téléchargez les configurations ER suivantes et enregistrez-les localement.

    | Description du contenu | Fichier |
    |---------------------|------|
    | Configuration de modèle des données ER **Modèle de paiements de déclaration des honoraires** | [1099model.xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml) |
    | Configuration du format ER **Pour importation des transactions des fournisseurs (Excel)** | [1099format-import-from-excel.xml](https://download.microsoft.com/download/b/3/8/b38faf0a-fbaf-4e9e-84c2-dedae7464880/1099format-import-from-excel.xml) |

2. Utilisez l’option ER [Charger depuis un fichier XML](er-defer-sequence-element.md#import-the-sample-er-configurations) pour importer les configurations ER téléchargées dans votre instance de Dynamics 365 Finance dans l’ordre suivant :

    1. Configuration de modèle de données ER
    2. Configuration de format ER

### <a name="download-the-required-excel-files"></a>Télécharger les fichiers Excel requis

- Téléchargez l’exemple d’ensemble de données suivant et enregistrez-le localement.

    | Description du contenu | Fichier |
    |---------------------|------|
    | Fichier **1099import-data.xlsx** entrant contenant des exemples de données à importer | [1099import-data.xlsx](https://download.microsoft.com/download/f/f/4/ff4dbce9-8364-4391-adee-877945ff01f7/1099import-data.xlsx) |

### <a name="review-the-prerequisites"></a>Passer en revue les tâches préalables

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, passez en revue la solution ER préparée pour l’importation de données en mode batch.
3. Passez en revue la configuration du format **Pour importation des transactions des fournisseurs (Excel)**

    - Le composant de format de cette configuration est conçu pour analyser un fichier Excel entrant.
    - Le composant de mappage de modèle de cette configuration est utilisé pour remplir le modèle de données de base en utilisant les données du fichier Excel analysé.

    ![Configuration du format ER pour importer des données en mode de traitement par lots à partir de l’interface utilisateur ER.](./media/er-configure-data-import-batch-configurations-1.png)

4. Passez en revue la configuration du modèle des données **Modèle de paiements de déclaration des honoraires**.

    - Le composant de modèle de cette configuration représente la structure du modèle de données utilisé pour transmettre les données entre les composants ER en cours d’exécution.
    - Le composant de mappage de modèle de cette configuration est utilisé pour extraire les données du composant de format exécuté, puis mettre à jour les tables d’application.

    ![Configuration du modèle de données ER pour importer des données en mode de traitement par lots à partir de l’interface utilisateur ER.](./media/er-configure-data-import-batch-configurations-2.png)

5. Ouvrez le fichier **1099import-data.xlsx** dans Excel.

    ![Exemple de fichier Excel avec des données à importer en mode de traitement par lots.](./media/er-configure-data-import-batch-excel-content.png)

## <a name="enable-batch-data-import-for-er-from-the-ui"></a>Activer l’importation de données par lots pour ER à partir de l’interface utilisateur

1. Accédez à **Administration système** \> **Espaces de travail** \> **Gestion des fonctionnalités**.
2. Dans l’espace de travail **Gestion des fonctionnalités**, sélectionnez la fonctionnalité **Exécuter l’importation ER de documents chargés manuellement par lots**, puis sélectionnez **Activer maintenant**.

## <a name="import-data-from-manually-selected-excel-files"></a>Importer les données depuis les fichiers Excel sélectionnés manuellement

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, sélectionnez la configuration du modèle de données **Modèle de paiements de déclaration des honoraires**.
3. Sur le raccourci **Composants de configuration**, sélectionnez le lien **Pour l’importation des transactions manuelles de déclaration d’honoraires**.
4. Sur la page **Mappage du modèle à la source de données**, le mappage de modèle **Pour l’importation des transactions manuelles de déclaration d’honoraires** est présélectionné. Sélectionnez **Exécuter**.
5. Dans l’onglet **Paramètres**, sélectionnez **Parcourir**. Recherchez et sélectionnez le fichier **1099import-data.xlsx**, puis sélectionnez **OK**.
6. Dans le champ **Entrer l’ID du document**, saisissez **V-00001**.
7. Dans l’onglet **Exécuter en arrière-plan**, définissez l’option **Traitement par lots** sur **Oui**.

    Remarquez que le champ **Description de la tâche** est défini sur **Exécution du mappage de modèle « Pour l’importation des transactions manuelles de déclaration des honoraires », configuration « Modèle de paiements de déclaration des honoraires »**. Cette valeur indique que l’exécution du mappage de modèle sélectionné sera planifiée en tant que nouveau traitement par lots.

    ![Spécification des détails de l’importation des données en mode de traitement par lots dans la boîte de dialogue Paramètres du génération d’états électroniques.](./media/er-configure-data-import-batch-execution-parameters.png)

8. Cliquez sur **OK**. Un message vous informe qu’un nouveau traitement par lots a été planifié.

    ![Message concernant une nouvelle tâche par lots planifiée sur la page de mappage du modèle à la source de données.](./media/er-configure-data-import-batch-scheduled-job-info.png)

## <a name="review-the-data-import-results-on-the-batch-job-page"></a>Examinez les résultats de l’importation de données sur la page de traitement par lots

1. Allez dans **Commun** \> **Recherches** \> **Traitements par lots** \> **Mes traitements par lots**.
2. Sur la page **Traitement par lots**, filtrez la liste des traitements par lots pour rechercher le lot planifié, puis sélectionnez-le.
3. Sélectionnez le lien **ID de tâche** lien pour passer en revue les détails de la tâche.
4. Sur le raccourci **Traitements par lots**, sélectionnez **Journal**.

    ![Bouton Journal sur la page Traitement par lots.](./media/er-configure-data-import-batch-scheduled-job-record.png)

5. Examinez les détails de l’exécution.

    ![Journal d’exécution des traitements par lots planifiés sur la page Traitement par lots.](./media/er-configure-data-import-batch-scheduled-job-log.png)

## <a name="change-the-data-import-parameters"></a>Modifier les paramètres d’importation des données

Une fois votre lot planifié et tant qu’il n’a pas encore été exécuté, vous pouvez modifier les paramètres de l’importation de données planifiée.

1. Allez dans **Commun** \> **Recherches** \> **Traitements par lots** \> **Mes traitements par lots**.
2. Sur la page **Traitement par lots**, filtrez la liste des traitements par lots pour rechercher le lot planifié, puis sélectionnez-le.
3. Sélectionnez **Modifier le statut**.
4. Dans la boîte de dialogue **Sélectionner un nouveau statut**, sélectionnez **Retenir**, puis sélectionnez **OK**.
5. Sélectionnez le lien **ID de tâche** lien pour accéder aux détails de la tâche.
6. Sur le raccourci **Traitements par lots**, sélectionnez **Paramètres**.
7. Dans la boîte de dialogue **Paramètres des états électroniques**, procédez comme suit :

    1. Sélectionnez **Parcourir** pour sélectionner l’autre fichier pour l’importation des données.
    2. Sélectionnez **Entrer l’ID du bon** pour modifier le numéro de bon pour l’importation des transactions fournisseur.

        ![Modification des paramètres d’importation des données pour le traitement par lots planifié dans la boîte de dialogue Paramètres de génération des états électroniques.](./media/er-configure-data-import-batch-scheduled-job-parameters.png)

    3. Cliquez sur **OK**.

8. Assurez-vous que le lot est toujours sélectionné, puis sélectionnez à nouveau **Modifier le statut**.
9. Dans la boîte de dialogue **Sélectionner un nouveau statut**, sélectionnez **Attente**, puis sélectionnez **OK**.

## <a name="review-the-data-import-results-on-the-er-source-page"></a>Examinez les résultats de l’importation de données sur la page de source de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Gestion des états électroniques** \> **Source de la gestion des états électroniques**.
2. Sélectionnez l’enregistrement **Pour importation des transactions des fournisseurs (Excel)** créé automatiquement lors de l’importation des données.

    ![Enregistrement pour la configuration Pour l’importation des transactions des fournisseurs (Excel) sur la page Source de déclaration des états électroniques.](./media/er-configure-data-import-batch-files-source-1.png)

3. Sélectionnez **États de fichier pour les sources**.
4. Sur les raccourcis **Fichiers** et **Journaux source pour le format d’importation**, passez en revue les détails d’importation.
5. Sur le raccourci **Fichiers**, sélectionnez l’enregistrement. Notez que le fichier importé est joint à cet enregistrement.

    ![Fichier importé joint à l’enregistrement sur la page États du fichier pour les sources.](./media/er-configure-data-import-batch-files-source-2.png)

6. Sélectionnez **Pièces jointes** pour revoir le fichier importé.

    ![Fichier importé sur la page d’affichage du document.](./media/er-configure-data-import-batch-files-source-3.png)

    > [!TIP]
    > Pour conserver ces pièces jointes, le cadre de gestion des états électroniques utilise un type de document [défini](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) pour la société actuelle dans le champ **Autres** des paramètres de gestion des états électroniques.

## <a name="review-the-data-import-results-on-the-vendor-settlement-for-1099s-page"></a>Examinez les résultats de l’importation des données sur la page Règlement du fournisseur pour la déclaration des honoraires

1. Accédez à **Comptabilité fournisseur** \> **Tâches périodiques** \> **Taxe sur les honoraires** \> **Règlement fournisseur pour les déclarations d’honoraires**.
2. Dans le champ **Date de début**, entrez **12/31/2017** (31 décembre 2017).
3. Sélectionnez **Transactions manuelles de déclaration d’honoraires**.

    ![Transactions fournisseur importées sur la page Transactions de taxe sur les honoraires.](./media/er-configure-data-import-batch-imported-data.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des États électroniques](general-electronic-reporting.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
