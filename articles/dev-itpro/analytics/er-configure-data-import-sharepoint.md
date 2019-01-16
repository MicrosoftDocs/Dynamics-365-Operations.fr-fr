---
title: "Configurer l'importation des données à partir de SharePoint"
description: "Cette rubrique décrit la procédure d'importation des données à partir de Microsoft SharePoint."
author: NickSelin
manager: AnnBe
ms.date: 11/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 060c3dec71e2b953d9341c5b5c89e60925fda34d
ms.openlocfilehash: 8053b0316c86c614b87b0e658dffade3a135f2cc
ms.contentlocale: fr-fr
ms.lasthandoff: 12/08/2018

---
# <a name="configure-data-import-from-sharepoint"></a>Configurer l'importation des données à partir de SharePoint

[!include[banner](../includes/banner.md)]

Pour importer des données à partir d'un fichier entrant à l'aide de la structure de gestion des états électroniques, vous devez configurer un format ER prenant en charge l'importation et exécuter une mise en correspondance de modèles du type **Vers la destination** qui utilise ce format comme source de données. Pour importer des données, vous devez accéder au fichier à importer. Le fichier entrant peut être sélectionné manuellement par l'utilisateur. Avec la nouvelle fonctionnalité ER de prise en charge de l'importation des données à partir de Microsoft SharePoint, ce processus peut être configuré en mode sans assistance. Vous pouvez utiliser les configurations ER pour procéder à l'importation des données à partir des fichiers stockés dans les dossiers Microsoft SharePoint. Cette rubrique explique comment effectuer l'importation de SharePoint vers Microsoft Dynamics 365 for Finance and Operations. Les exemples utilisent les transactions fournisseur comme données commerciales.

## <a name="prerequisites"></a>Logiciels requis
Pour exécuter les exemples décrits dans cette rubrique, vous devez disposer de l'accès suivant :

- L'accès à Finance and Operations pour l'un des rôles suivants :

    - Développeur de gestion des états électroniques
    - Consultant fonctionnel de gestion des états électroniques
    - Administrateur système

- L'accès à l'instance de Microsoft SharePoint Server qui est configurée pour être utilisée avec Finance and Operations.
- Configurations du format et du modèle ER pour les paiements 1099.

### <a name="create-required-er-configurations"></a>Créer les configurations ER requises
Lisez les guides de tâches **ER Importer des données à partir d'un fichier Microsoft Excel**, qui font partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**. Ces guides de tâches vous aident tout au long du processus de création et d'utilisation des configurations ER pour importer en mode interactif des transactions fournisseur à partir de fichiers Microsoft Excel. Pour plus d'informations, voir [Analyser les documents entrants dans Microsoft Excel](parse-incoming-documents-excel.md). Après avoir terminé les guides de tâche, vous devrez effectuer le paramétrage suivant.

#### <a name="er-configurations"></a>Configurations ER

- Configuration du modèle ER, **Modèle de paiements de déclaration des honoraires**
- Configuration du format ER, **Format d'importation des transactions des fournisseurs à partir d'Excel**

![Configurations ER pour l'importation des données à partir de SharePoint](./media/GERImportFromSharePoint-01-Configurations.PNG)

#### <a name="sample-of-the-incoming-file-for-data-import"></a>Exemple de fichier entrant pour l'importation des données

- Fichier Excel **1099import-data.xlsx**, avec les transactions fournisseur qui doivent être importées dans Finance and Operations.

![Exemple de fichier Microsoft Excel pour l'importation à partir de SharePoint](./media/GERImportFromSharePoint-02-Excel.PNG)
    
> [!NOTE]
> Le format d'importation des transactions fournisseur est sélectionné comme mise en correspondance des modèles par défaut. Par conséquent, si vous exécutez une mise en correspondance du **Modèle de paiements de déclaration des honoraires** et si cette mise en correspondance du modèle est de type **Vers la destination**, la mise en correspondance des modèles exécute ce format pour importer les données à partir de fichiers externes. Elle utilise ensuite ces données pour mettre à jour les tables d'application.

## <a name="configure-access-to-sharepoint-for-file-storage"></a>Configuration de l'accès à SharePoint pour le stockage des fichiers
Pour stocker des fichiers d'état électroniques dans un emplacement SharePoint, vous devez configurer l'accès à l'instance de SharePoint Server qui sera utilisée par la société actuelle. Dans cet exemple, la société est USMF. Pour obtenir des instructions, voir [Configurer le stockage SharePoint](../../fin-and-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage).

1. Effectuez les étapes dans [Configurer le stockage SharePoint](../../fin-and-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage).
2. Ouvrez le site SharePoint configuré.
3. Créez les dossiers suivants dans lesquels les fichiers de gestion des états électroniques entrants peuvent être enregistrés :

     - Source d'importation de fichiers (principale) (exemple affiché dans la capture d'écran ci-dessous)
     - Source d'importation de fichiers (secondaire)

    ![Source d'importation de fichiers (principale)](./media/GERImportFromSharePoint-04-SharePointFolder1.png)

4. (Facultatif) Créez les dossiers suivants dans lesquels les fichiers peuvent être stockés après l'importation. 

    - Dossier d'archivage de fichiers - Ce dossier serait dédié aux fichiers importés avec succès.
    - Dossier d'avertissement de fichiers - Ce dossier serait dédié aux fichiers importés avec un avertissement.
    - Dossier d'erreur de fichiers - Ce dossier serait dédié aux fichiers dont l'importation aurait échoué.

4. Dans Finance and Operations, accédez à **Administration d'organisation > Gestion des documents > Types de documents**.
5. Créez les types de documents suivants qui seront utilisés pour accéder aux dossiers SharePoint que vous venez de créer. Pour obtenir des instructions, voir [Configurer les types de documents](../../fin-and-ops/organization-administration/configure-document-management.md#configure-document-types).

|Type de document       | Regrouper              | Entrepôt      | Dossier SharePoint      |
|--------------------|--------------------|---------------|------------------------|
|SP principal             |Fichier                |SharePoint     |Source d'importation de fichiers (principale)|
|SP secondaire             |Fichier                |SharePoint     |Source d'importation de fichiers (secondaire)|
|Archive SP             |Fichier                |SharePoint     |Dossier d'archivage de fichiers|
|Avertissement SP             |Fichier                |SharePoint     |Dossier d'avertissement de fichiers|
|Erreur SP             |Fichier                |SharePoint     |Dossier d'erreur de fichiers|

![Paramètre SharePoint – Nouveau type de document](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)

## <a name="configure-er-sources-for-the-er-format"></a>Configurer les sources ER pour le format ER
1. Cliquez sur **Administration d'organisation** \> **Gestion des états électroniques** \> **Source de la gestion des états électroniques**.
2. Dans la page **Source de la gestion des états électroniques**, configurez les fichiers source pour l'importation des données à l'aide du format ER configuré.
3. Définissez un masque de nom de fichier, afin que seuls les fichiers portant l'extension .xlsx soient importés. Le masque de nom de fichier est facultatif et est utilisé uniquement s'il a été défini. Vous ne pouvez définir qu'un seul masque pour chaque format ER.
4. Modifiez **Trier les fichiers avant l'importation** avec **Ne pas trier**, s'il existe de nombreux fichiers d'importation et que l'ordre d'importation n'est pas important
5. Sélectionnez tous les dossiers SharePoint que vous avez créés précédemment.

    [![Paramètre de source de fichiers ER](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)

> [!NOTE]
> - La *source* ER est définie individuellement pour chaque société d'application. En revanche, les *configurations* ER sont partagées entre les sociétés.
> - Lorsque vous supprimez un paramètre de source ER pour un format ER, tous les états de fichier connectés (voir ci-dessous) sont également supprimés sur confirmation.

## <a name="review-the-files-states-for-the-er-format"></a>Examiner les états de fichier pour le format ER
1. Dans la page **Source de la gestion des états électroniques**, sélectionnez **États de fichier pour les sources** pour examiner le contenu des sources de fichier configurées pour le format ER actuel.
2. Dans la section **Fichiers**, examinez la liste des fichiers. Cette liste affiche les éléments suivants :

    - Fichiers source applicables, selon le masque de nom de fichier (si un masque de nom de fichier est défini), et prêts pour l'importation des données. Pour ces fichiers, la section **Journaux source pour le format d'importation** est vide.
    - Fichiers précédemment importés. Pour chacun de ces fichiers, dans la section **Journaux source pour le format d'importation**, vous pouvez examiner l'historique d'importation de ce fichier.

Vous pouvez également ouvrir la page **États de fichier pour les sources** en sélectionnant **Administration d'organisation** \> **Gestion des états électroniques** \> **États de fichier pour les sources**. Dans ce cas, la page fournit des informations sur les sources de fichier pour tous les formats ER pour lesquels les sources de fichier ont été configurées dans la société à laquelle vous êtes actuellement connecté.

## <a name="import-data-from-excel-files-that-are-in-a-sharepoint-folder"></a>Importer des données à partir de fichiers Excel contenus dans un dossier SharePoint
1. Dans SharePoint, transférez le fichier Microsoft Excel **1099import-data.xlsx** contenant les transactions fournisseur vers le dossier SharePoint **Source d'importation de fichiers (principale)** que vous avez créé précédemment.

    [![Contenu SharePoint – Fichier Microsoft Excel pour l'importation](./media/GERImportFromSharePoint-08-UploadFile.png)](./media/GERImportFromSharePoint-08-UploadFile.png)

2. Dans Finance and Operations, dans la page **États de fichier pour les sources**, sélectionnez **Actualiser** pour actualiser la page. Notez que le fichier Excel qui a été transféré vers SharePoint est affiché sur cette page avec le statut **Prêt**. Les statuts suivants sont actuellement pris en charge :

    - **Prêt** – Affecté automatiquement pour chaque nouveau fichier dans un dossier SharePoint. Ce statut signifie que le fichier est prêt pour l'importation.
    - **Importation** – Affecté automatiquement par un état électronique lorsque le fichier est verrouillé par le processus d'importation pour empêcher son utilisation par d'autres processus (si plusieurs d'entre eux sont exécutés simultanément).
    - **Importé** – Affecté automatiquement par un état électronique lorsque l'importation du fichier s'est déroulée correctement. Ce statut signifie que le fichier importé a été supprimé de la source de fichier configurée (dossier SharePoint).
    - **Échec** – Affecté automatiquement par un état électronique lorsque l'importation du fichier s'est terminée avec des erreurs ou des exceptions.
    - **En attente** – Affecté manuellement par l'utilisateur sur cette page. Ce statut signifie que le fichier n'est pas importé pour l'instant. Ce statut peut être utilisé pour différer l'importation de certains fichiers.

    [![Page d'états de fichier ER pour les sources sélectionnées](./media/GERImportFromSharePoint-09-FileStatesForm.png)](./media/GERImportFromSharePoint-09-FileStatesForm.png)

## <a name="import-data-from-sharepoint-files"></a>Importer des données à partir de fichiers SharePoint
1. Ouvrez l'arborescence des configurations ER, sélectionnez **Modèle de paiements de déclaration des honoraires**, puis développez la liste des composants de modèle ER.
2. Sélectionnez le nom de la mise en correspondance des modèles pour ouvrir la liste des mises en correspondance de modèles de la configuration de modèle ER sélectionnée.

    [![Page d'états de fichier ER pour les sources sélectionnées](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)

3. Sélectionnez **Exécuter** pour exécuter la mise en correspondance des modèles sélectionnée. Comme vous avez configuré les sources de fichier pour le format ER, vous pouvez modifier le paramètre de l'option **Source de fichier**, si nécessaire. Si vous conservez le paramètre de cette option, les fichiers .xslx sont importés à partir des sources configurées (les dossiers SharePoint, dans cet exemple).

    Dans cet exemple, vous n'importez qu'un seul fichier. Toutefois, s'il existe plusieurs fichiers, ils sont sélectionnés pour l'importation dans leur ordre d'ajout au dossier SharePoint. Chaque exécution d'un format ER importe un fichier sélectionné unique.

    [![Exécuter la mise en correspondance des modèles ER](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)

4. La mise en correspondance des modèles peut s'exécuter sans assistance en mode de traitement par lots. Dans ce cas, chaque fois qu'un traitement par lots exécute ce format ER, un fichier unique est importé à partir des sources de fichier configurées.

    Lorsqu'un fichier est correctement importé depuis le dossier SharePoint, il est supprimé de celui-ci et est déplacé vers le dossier des fichiers importés correctement ou vers le dossier des fichiers importés avec des avertissements. Sinon il est déplacé vers le dossier des fichiers ayant échoué ou reste dans ce dossier si le dossier des fichiers ayant échoué n'est pas paramétré. 

5. Entrez l'ID du document, tel que **V-00001**, puis cliquez sur **OK**.

    [![Exécuter la mise en correspondance des modèles ER](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)

6. Dans la page **États de fichier pour les sources**, sélectionnez **Actualiser** pour actualiser la page.

    [![Page d'états de fichier ER pour les sources sélectionnées](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)

7. Dans la section **Fichiers**, examinez la liste des fichiers. La section **Journaux source pour le format d'importation** fournit l'historique de l'importation du fichier Excel. Comme ce fichier a été correctement importé, il est marqué comme **Supprimé** dans le dossier SharePoint.
8. Examinez le dossier SharePoint **Source d'importation de fichiers (principale)**. Les fichiers Excel qui ont été correctement importés ont été supprimés de ce dossier.
9. Dans Finance and Operations, sélectionnez **Comptabilité fournisseur** \> **Tâches périodiques** \> **Taxe sur les honoraires** \> **Règlement fournisseur pour les déclarations d'honoraires**.
10. Dans les champs **Date de début** et **Date de fin**, entrez les valeurs appropriées. Sélectionnez ensuite **Transactions manuelles de déclaration d'honoraires**.

    Les transactions fournisseur qui ont été importées à partir des fichiers Excel dans SharePoint pour le document **V-00001** sont affichées sur la page.

    [![Page des transactions fournisseur de déclaration d'échanges de biens](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)

## <a name="prepare-an-excel-file-for-import"></a>Préparer un fichier Excel pour l'importation
1. Ouvrez le fichier Excel que vous avez précédemment utilisé. Dans la ligne 3 colonne 1, ajoutez un code de fournisseur qui n'existe pas dans l'application. Ajoutez des informations fournisseur supplémentaires à la ligne.

    [![Exemple de fichier Microsoft Excel pour l'importation à partir de SharePoint](./media/GERImportFromSharePoint-15-Excel.PNG)](./media/GERImportFromSharePoint-15-Excel.PNG)

2. Transférez le fichier Excel mis à jour contenant les transactions fournisseur vers le dossier SharePoint **Source d'importation de fichiers (principale)**.
3. Dans Finance and Operations, ouvrez l'arborescence des configurations ER, sélectionnez **Modèle de paiements de déclaration des honoraires**, puis développez la liste des composants de modèle ER.
4. Sélectionnez le nom de la mise en correspondance des modèles pour mettre à jour la mise en correspondance des modèles afin que le code fournisseur incorrect soit considéré comme une erreur au cours du processus d'importation.
5. Sélectionnez **Concepteur**.
6. Sous l'onglet **Validations**, vous devez modifier l'action de post-validation pour la règle de validation qui a été configurée pour évaluer si le compte fournisseur importé existe dans l'application. Mettez à jour la valeur du champ **Action de post-validation** sur **Arrêter l'exécution**, enregistrez vos modifications, puis fermez la page.

    [![Page du concepteur de mise en correspondance des modèles ER](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)

7. Enregistrez vos modifications et fermez le concepteur de mise en correspondance des modèles ER.
8. Sélectionnez **Exécuter** pour exécuter la mise en correspondance des modèles ER modifiée.
9. Entrez l'ID du document, tel que **V-00002**, puis cliquez sur **OK**.

    Notez que la fenêtre Informations contient une notification indiquant qu'il existe un fichier dans le dossier SharePoint contenant un compte fournisseur incorrect et qu'il ne peut pas être importé.

    [![Exécuter la mise en correspondance des modèles ER](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)

10. Dans la page **États de fichier pour les sources**, sélectionnez **Actualiser**, puis, dans la section **Fichiers**, examinez la liste des fichiers.

    [![Page d'états de fichier ER pour les sources sélectionnées](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)

   La section **Journaux source pour le format d'importation** indique que le processus d'importation a échoué et que le fichier se trouve toujours dans le dossier Erreur de fichiers SharePoint (la case à cocher **Est supprimé** n'est pas sélectionnée). Si vous corrigez ce fichier dans SharePoint en ajoutant le code fournisseur adéquat, que vous le déplacez vers le dossier SharePoint (principal) source d'importation de fichiers, vous pouvez importer le fichier de nouveau.

11. Dans Finance and Operations, sélectionnez **Comptabilité fournisseur** \> **Tâches périodiques** \> **Taxe sur les honoraires** \> **Règlement fournisseur pour les déclarations d'honoraires**, entrez les valeurs appropriées dans les champs **Date de début** et **Date de fin**, puis sélectionnez **Transactions manuelles de déclaration d'honoraires**.

    Seules les transactions pour le document V-00001 sont disponibles. Aucune transaction pour le document V-00002 n'est disponible même si l'erreur pour la dernière transaction importée a été trouvée dans le fichier Excel.

