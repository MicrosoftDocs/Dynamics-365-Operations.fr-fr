---
title: Utiliser le didacticiel Regression Suite Automation Tool
description: Cette rubrique explique comment utiliser l’outil RSAT (Regression Suite Automation Tool). Il en décrit les diverses fonctions et fournit des exemples qui utilisent l’écriture de script avancée.
author: robinarh
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 798717b276e68949a9425350720bf683a37d6fb5
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692988"
---
# <a name="regression-suite-automation-tool-tutorial"></a>Didacticiel Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Utilisez les outils du navigateur Internet pour télécharger et enregistrer cette page au format PDF. 

Ce didacticiel vous explique quelques-unes des fonctions avancées de l’outil RSAT (Regression Suite Automation Tool), inclut une mission de démonstration et décrit des points stratégiques et d’apprentissage clés. 

## <a name="notable-features-of-rsat-and-task-recorder"></a>Caractéristiques notables de RSAT et de l’enregistreur de tâches

### <a name="validate-a-field-value"></a>Valider une valeur du champ

RSAT vous permet d’inclure des étapes de validation dans votre scénario de test pour valider les valeurs attendues. Pour plus d’informations sur cette fonctionnalité, consultez l’article [Valider des valeurs prévues](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).

L’exemple suivant montre comment vous pouvez utiliser cette fonction pour vérifier si le stock disponible est supérieur à 0 (zéro).

1. Dans les données de démonstration de la société **USMF**, créez un enregistrement de tâche ayant les étapes suivantes :

    1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
    2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez une valeur **1000** pour le champ **Numéro d’article**.
    3. Sélectionnez **Stock disponible**.
    4. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez une valeur **1** pour le champ **Site**.
    5. Dans la liste, marquer la ligne sélectionnée.
    6. Vérifiez que la valeur du champ **Total disponible** est **411,0000000000000000**.

2. Enregistrez l’enregistrement de tâche et joignez-le à votre scénario de test dans Azure Devops.
3. Ajoutez le scénario de test au plan de test, puis chargez le scénario de test dans RSAT.
4. Ouvrez le fichier de paramètres Excel. Dans l’onglet **InventOnhandItem**, vous voyez une section **Valider InventOnhandItem** qui inclut un champ **Opérateur**.

    ![Champ Opérateur](./media/use_rsa_tool_08.png)

5. Pour vérifier si le stock disponible est toujours supérieur à 0, modifiez la valeur du champ **Valeur** de **411** à **0** et la valeur du champ **Opérateur** d’un signe égal (**=**) à un signe supérieur à (**\>**).

    ![Valeurs des champs Valeur et Opérateur modifiées](./media/use_rsa_tool_09.png)

6. Enregistrez et fermez le fichier de paramètres Excel.
7. Sélectionnez **Upload** pour enregistrer les modifications apportées au fichier de paramètres Excel dans Azure DevOps.

Désormais, si la valeur du champ **Total disponible** pour l’article spécifié en stock est supérieure à 0 (zéro), les tests réussiront, indépendamment de la valeur réelle du stock disponible.

### <a name="saved-variables-and-chaining-of-test-cases"></a>Variables enregistrées et enchaînement des cas de test

L’une des fonctionnalités principales de RSAT n’est autre que l’enchaînement de cas de test, autrement dit la possibilité pour un test de transmettre des variables à d’autres tests. Pour plus d’informations, consultez l’article [Copier des variables pour enchaîner des cas de test](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).

### <a name="derived-test-case"></a>Scénario de test dérivé

RSAT vous permet d’utiliser le même enregistrement de tâche avec plusieurs cas de test, permettant à une tâche de s’exécuter avec différentes configurations de données. Voir l’article [Cas de test dérivés](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md) pour plus d’informations.

### <a name="validate-notifications-and-messages"></a>Valider les notifications et les messages

Cette fonction peut être utilisée pour vérifier si une action s’est produite. Par exemple, lorsqu’un ordre de fabrication est créé, estimé, puis démarré, l’application présente un message « Production – démarrer » pour vous informer que l’ordre de fabrication a commencé.

![Notification Production – Démarrer](./media/use_rsa_tool_05.png)

Vous pouvez valider ce message dans RSAT en entrant le texte du message dans l’onglet **Validation du message** du fichier de paramètres Excel pour l’enregistrement approprié.

![Onglet Validation du message](./media/use_rsa_tool_06.png)

Une fois le scénario de test exécuté, le message du fichier de paramètres Excel est comparé au message qui s’affiche. Si les messages ne correspondent pas, le scénario de test échoue.

> [!NOTE]
> Vous pouvez entrer plusieurs messages dans l’onglet **Validation du message** du fichier de paramètres Excel. Les messages peuvent également être des messages d’erreur ou d’avertissement au lieu de messages d’information.

### <a name="snapshot"></a>Instantané

Cette fonction prend des captures d’écran des étapes qui ont été effectuées au cours de l’enregistrement de tâche. Il est utile à des fins d’audit ou de débogage.

- Pour utiliser cette fonction, ouvrez le fichier **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** sous le dossier d’installation de RSAT (par exemple, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), puis modifiez la valeur de l’élément suivant de **faux** à **vrai**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Lorsque vous exécutez le scénario de test, RSAT génère des instantanés (images) des étapes dans le dossier de lecture des scénarios de test dans le répertoire de travail. Si vous utilisez une version précédente de RSAT, les images sont sauvegardées vers **C:\\Utilisateurs\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, un dossier distinct est créé pour chaque cas de test exécuté.

## <a name="assignment"></a>Affectation

### <a name="scenario"></a>Scénario

1. Le concepteur de produit crée un nouveau produit lancé.
2. Le gestionnaire de production lance un ordre de fabrication pour amener le niveau de stock à deux unités.
3. La fabrication démarre et termine l’ordre de fabrication, et vérifie que la quantité disponible est de deux unités.
4. L’équipe commerciale reçoit une commande de quatre unités du nouveau produit. Par conséquent, l’équipe de vente présente les besoins nets via le plan dynamique. Comme aucune capacité supplémentaire n’est disponible, la stratégie de commande par défaut est définie sur « acheter plutôt que fabriquer ». Par conséquent, une commande fournisseur est créée.
5. L’acheteur ajoute un fournisseur, confirme la commande fournisseur prévisionnelle, puis confirme la commande fournisseur.
6. Lorsque les marchandises achetées arrivent au magasin, le magasinier recherche la commande fournisseur associée et réceptionne les marchandises. Comme la commande est maintenant terminée, les marchandises peuvent être prélevées et emballées conformément à la commande client.
7. Le service financier valide la facture fournisseur et la facture client.

La figure suivante présente une capture d’écran du flux de ce scénario.

![Flux du scénario de démonstration](./media/use_rsa_tool_14.png)

L’illustration suivante montre la hiérarchie des processus métier pour ce scénario dans le Concepteur de processus d’entreprise LCS.

![Processus métier pour le scénario de démonstration](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Stratégie – Points d’apprentissage clés

### <a name="data"></a>Données

- Assurez-vous d’avoir des volumes de données représentatifs (une copie des données de production/configuration Golden, plus des données migrées).
- Lorsque vous générez de nouvelles données via l’enregistreur de tâches, créez des noms de test qui ne seront pas en conflit avec des noms existants (par exemple, utilisez un préfixe tel que **RSATxxx**).
- Utilisez la restauration ponctuelle Azure pour réexécuter les tests dans des environnements de niveau autre que 1.
- Bien que vous puissiez utiliser les fonctions Excel **RANDOM** et **NOW** pour générer une combinaison unique, la charge de travail est considérable. Voici un exemple :

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a>Enregistreur de tâches

- Définissez les scénarios avant de commencer l’enregistrement. Un projet bien géré a des scénarios de test prédéfinis. Pour établir un scénario de test, prenez en compte la prédictibilité des résultats de ces scénarios de test.
- Fractionnez les enregistrements s’ils sont réalisés par des rôles différents, ou s’il existe un temps d’attente ou un événement externe avant l’étape suivante.
- Évitez de sélectionner des valeurs dans des listes. Au lieu de cela, utilisez des formats texte, tels que **FIFO**, **AudioRM** et **SiteWH**. Si vous faites une sélection dans une liste, c’est la position de la valeur dans la liste qui est enregistrée, pas la valeur elle-même. Si des articles sont ajoutés à cette liste, la position de la valeur peut changer. Par conséquent, l’enregistrement utilisera un paramètre différent, et le reste du scénario peut en être affecté.
- Pensez au comportement multi-utilisateur. Par exemple, ne supposez pas que votre commande client nouvellement créée sera toujours sélectionnée automatiquement. Au lieu de cela, utilisez toujours le filtre permettant de trouver la commande appropriée.
- Utilisez la fonction Copier dans l’enregistreur de tâches pour enregistrer le nom d’un produit nouvellement créé, de manière à l’utiliser dans des scénarios de test enchaînés.
- Utilisez la fonction Valider de l’enregistreur de tâches pour définir des points de contrôle pour vérifier que les étapes ont été exécutées correctement.

### <a name="rsat"></a>RSAT

- Pour exécuter le test sur une autre société, vous pouvez modifier la société sur l’onglet **Général** du fichier de paramètres Excel. Vérifiez que les paramètres et les données sont disponibles dans la société récemment sélectionnée.
- Vous pouvez modifier l’utilisateur du test dans l’onglet **Général** du fichier de paramètres Excel. Indiquez l’ID d’e-mail de l’utilisateur qui exécutera le scénario de test. Ainsi, le scénario de test pourra être exécuté à l’aide des autorisations de sécurité de l’utilisateur spécifié.
- Pour attendre le démarrage du test, vous pouvez définir une pause dans l’onglet **Général** du fichier de paramètres Excel. Cette pause peut être utilisée dans un traitement par lots (par exemple, si un workflow doit être exécuté avant que l’étape suivante ne puisse être réalisée.)

## <a name="advanced-scripting"></a>Écriture de script avancée

### <a name="cli"></a>CLI

RSAT peut être appelé à partir d’une fenêtre **Invite de commandes** ou **PowerShell**.

> [!NOTE]
> Vérifiez que la variable d’environnement **TestRoot** est définie sur le chemin d’installation de RSAT. (Dans Microsoft Windows, ouvrez **Panneau de configuration**, sélectionnez **Système et sécurité \> Système \> Paramètres système avancés**, puis sélectionnez **Variables d’environnement**.)

1. Ouvrez une fenêtre **Invite de commandes** ou **PowerShell** en tant qu’administrateur.
2. Accédez au répertoire d’installation de RSAT.

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. Répertoriez toutes les commandes.

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>? 
Affiche l’aide sur toutes les commandes disponibles et leurs paramètres.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a>Paramètres facultatifs

**``command``**


Où ``[command]`` est l’une des commandes spécifiées ci-dessous.


#### <a name="about"></a>à propos de
Affiche la version actuelle.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls
Efface l’écran.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a>télécharger
Télécharge les pièces jointes pour le scénario de test spécifié dans le répertoire de sortie. Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles. Utilisez n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a>Paramètres obligatoires
**``test_case_id``** Représente l’ID du scénario de test.  
**``output_dir``** Représente le répertoire de sortie. Le répertoire doit exister.

##### <a name="examples"></a>Exemples

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a>modifier
Vous permet d’ouvrir le fichier de paramètres dans le programme Excel et de le modifier.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a>Paramètres obligatoires
**``excel_file``** Doit contenir un chemin d’accès complet à un fichier Excel existant.

##### <a name="examples"></a>Exemples
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a>generate
Génère les fichiers d’exécution de tests et de paramètre pour le scénario de test spécifié dans le répertoire de sortie.
Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles. Utilisez n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a>Paramètres obligatoires
**``test_case_id``** Représente l’ID du scénario de test.  
**``output_dir``** Représente le répertoire de sortie. Le répertoire doit exister.

##### <a name="examples"></a>Exemples
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a>generatederived
Génère un nouveau scénario de test, dérivé du scénario de test fourni. Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles. Utilisez n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a>Paramètres obligatoires
**``parent_test_case_id``** Représente l’ID du scénario de test parent.  
**``test_plan_id``** Représente l’ID du plan de test.  
**``test_suite_id``** Représente l’ID de la suite de tests.

##### <a name="examples"></a>Exemples
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a>generatetestonly
Génère uniquement le fichier d’exécution de tests pour le scénario de test spécifié dans le répertoire de sortie. Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles. Utilisez n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a>Paramètres obligatoires
**``test_case_id``** Représente l’ID du scénario de test.  
**``output_dir``** Représente le répertoire de sortie. Le répertoire doit exister.

##### <a name="examples"></a>Exemples
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a>generatetestsuite
Génère tous les scénarios de test pour la suite spécifiée dans le répertoire de sortie.
Vous pouvez utiliser la commande ``listtestsuitenames`` pour obtenir toutes les suites de test disponibles. Utilisez n’importe quelle valeur de la colonne comme paramètre **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a>Paramètres obligatoires
**``test_suite_name``** Représente le nom de la suite de tests.  
**``output_dir``** Représente le répertoire de sortie. Le répertoire doit exister.

##### <a name="examples"></a>Exemples
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a>help
Identique à la commande [?](#section) .


#### <a name="list"></a>liste
Répertorie tous les scénarios de test disponibles.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a>listtestplans
Répertorie tous les plans de test disponibles.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a>listtestsuite
Répertorie les scénarios de test pour la suite de tests spécifiée. Vous pouvez utiliser la commande ``listtestsuitenames`` pour obtenir toutes les suites de test disponibles. Utilisez n’importe quelle valeur de la première colonne comme paramètre **suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a>Paramètres obligatoires
**``suite_name``** Nom de la suite souhaitée.

##### <a name="examples"></a>Exemples
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a>listtestsuitenames
Répertorie toutes les suites de test disponibles.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a>playback
Lit un scénario de test à l’aide d’un fichier Excel.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a>Paramètres obligatoires
**``excel_file``** Chemin d’accès complet au fichier Excel. Le fichier doit exister. 

##### <a name="examples"></a>Exemples
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a>playbackbyid
Lit plusieurs scénarios de test à la fois.
Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles. Utilisez n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a>Paramètres obligatoires
**``test_case_id1``** ID du scénario de test existant.  
**``test_case_id2``** ID du scénario de test existant.  
**``test_case_idN``** ID du scénario de test existant.  

##### <a name="examples"></a>Exemples
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a>playbackmany
Lit plusieurs scénarios de test à la fois, à l’aide de fichiers Excel.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a>Paramètres obligatoires
**``excel_file1``** Chemin d’accès complet au fichier Excel. Le fichier doit exister.  
**``excel_file2``** Chemin d’accès complet au fichier Excel. Le fichier doit exister.  
**``excel_fileN``** Chemin d’accès complet au fichier Excel. Le fichier doit exister.  

##### <a name="examples"></a>Exemples
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a>playbacksuite
Lit tous les scénarios de test à partir de la suite de tests spécifiée. Vous pouvez utiliser la commande ``listtestsuitenames`` pour obtenir toutes les suites de test disponibles. Utilisez n’importe quelle valeur de la première colonne comme paramètre **suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a>Paramètres obligatoires
**``suite_name``** Nom de la suite souhaitée.

##### <a name="examples"></a>Exemples
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a>quit
Ferme l’application.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a>upload
Charge tous les fichiers appartenant à la suite de tests ou aux scénarios de test spécifiés.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a>Paramètres obligatoires
**``suite_name``** Tous les fichiers appartenant à la suite de tests spécifiée seront chargés.
**``testcase_id``** Tous les fichiers appartenant aux scénarios de test spécifiés seront chargés.

##### <a name="examples"></a>Exemples
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a>uploadrecording
Charge uniquement le fichier d’enregistrement appartenant aux scénarios de test spécifiés.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a>Paramètres obligatoires
**``testcase_id``** Le fichier d’enregistrement appartenant aux scénarios de test spécifiés sera chargé.

##### <a name="examples"></a>Exemples
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a>usage
Affiche deux façons d’appeler cette application : l’une en utilisant un fichier de paramètre par défaut, l’autre en fournissant un fichier de paramètre.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a>Exemples Windows PowerShell

[!IMPORTANT] Les exemples de scripts ci-dessous sont fournis TELS QUELS à des fins d’illustration et ne sont pas pris en charge par Microsoft.

#### <a name="run-a-test-case-in-a-loop"></a>Exécuter un scénario de test dans une boucle

Vous avez un script de test qui crée un nouveau client. Grâce à l’écriture de script, ce scénario de test peut être exécuté en boucle en rendant aléatoires les données suivantes avant chaque itération de l’exécution :

- ID client
- Nom du client
- Adresse du client

L’ID client est au format *ATCUS\<number\>*, où \<number\> est une valeur comprise entre **000000001** et **999999999**.

L’exemple suivant utilise un paramètre, **début**, pour définir le premier numéro utilisé. Il utilise un deuxième paramètre, **nr**, pour définir le nombre de clients à créer. Pour chaque itération, les paramètres du fichier de paramètres Excel sont modifiés à l’aide d’une fonction UpdateCustomer. Ensuite, la ligne de commande RSAT est appelée dans une fonction RunTestCase.

Ouvrez l’environnement ISE ( PowerShell Integrated Scripting) de Microsoft Windows en mode administrateur, et collez le code suivant dans la fenêtre qui s’appelle **Untitled1.ps1**.

```powershell
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a>Exécuter un script qui dépend de données de Microsoft Dynamics 365

L’exemple suivant utilise un appel OData (Open Data Protocol) pour rechercher le statut d’une commande fournisseur. Si le statut n’est pas **facturé**, vous pouvez, par exemple, appeler un scénario de test RSAT qui valide la facture.

```xpp
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```
