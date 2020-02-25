---
title: Utiliser le didacticiel Regression Suite Automation Tool
description: Cette rubrique explique comment utiliser l'outil RSAT (Regression Suite Automation Tool). Il en décrit les diverses fonctions et fournit des exemples qui utilisent l'écriture de script avancée.
author: kfend
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 026d1d743b5150f152ef70aa642dcf6841a4e398
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025802"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a>Utiliser le didacticiel Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Utilisez les outils du navigateur Internet pour télécharger et enregistrer cette page au format PDF. 

Ce didacticiel vous explique quelques-unes des fonctions avancées de l'outil RSAT (Regression Suite Automation Tool), inclut une mission de démonstration et décrit des points stratégiques et d'apprentissage clés.

## <a name="features-of-rsattask-recorder"></a>Fonctions de RSAT/Enregistreur de tâches

### <a name="validate-a-field-value"></a>Valider une valeur du champ

Pour plus d'informations sur cette fonction, voir [Créer un nouvel enregistrement de tâche possédant une fonction de validation](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).

### <a name="saved-variable"></a>Variable enregistrée

Pour plus d'informations sur cette fonction, voir [Modifier un enregistrement de tâche existant pour créer une variable enregistrée](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).

### <a name="derived-test-case"></a>Scénario de test dérivé

1. Ouvrez l'outil RSAT (Regression Suite Automation Tool), puis sélectionnez les deux scénarios de test que vous avez créés dans [Didacticiel Configurer et installer l'outil Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).
2. Sélectionnez **Nouveau \> Créer un scénario de test dérivé**.

    ![Commande Créer un scénario de test dérivé dans le menu Nouveau](./media/use_rsa_tool_01.png)

3. Vous recevez un message indiquant qu'un scénario de test dérivé sera créé pour chaque scénario de test sélectionné dans la suite de tests actuelle, et que chaque scénario de test dérivé aura sa propre copie du fichier de paramètres Excel. Cliquez sur **OK**.

    > [!NOTE]
    > Lorsque vous exécutez un scénario de test dérivé, il utilise l'enregistrement de tâche de son scénario de test parent et sa propre copie du fichier de paramètres Excel. De cette manière, vous pouvez exécuter le même test avec différents paramètres, sans devoir mettre à jour plusieurs enregistrement de tâches. Un scénario de test dérivé n'est pas obligé de faire partie de la même suite de tests que son scénario de test parent.

    ![Zone de message](./media/use_rsa_tool_02.png)

    Deux scénarios de test dérivés supplémentaires sont créés, et la case à cocher **Dérivé ?** est sélectionnée pour eux.

    ![Scénarios de test dérivés créés](./media/use_rsa_tool_03.png)

    Un scénario de test dérivé est automatiquement créé dans Azure DevOps. Il s'agit d'un élément enfant du scénario de test **Créer un nouveau produit** et il est étiqueté avec un mot clé spécial : **RSAT: DerivedTestSteps**. Ces scénarios de test sont automatiquement ajoutés au plan de test dans Azure DevOps.

    ![Mot clé RSAT:DerivedTestSteps](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > Si, pour une raison quelconque, les scénarios de test dérivés qui sont créés ne sont pas dans l'ordre correct, accédez à Azure DevOps et réorganisez les scénarios de test dans la suite de tests, de sorte que RSAT puisse les exécuter dans l'ordre correct.

4. Sélectionnez les scénarios de test dérivés, puis sélectionnez **Modifier** pour ouvrir les fichiers de paramètres Excel correspondants.
5. Modifiez les fichiers de paramètres Excel de la même manière que vous avez modifié les fichiers parents. En d'autres termes, vérifiez que l'ID produit est défini afin d'être généré automatiquement. Assurez-vous également que la variable enregistrée est copiée dans les champs appropriés.
6. Dans l'onglet **Général** des deux fichiers de paramètres Excel, mettez à jour la valeur du champ **Société** sur **USSI**, afin que les scénarios de test dérivés soient exécutés avec une autre entité juridique que le scénario de test parent. Pour exécuter les scénarios de test pour un utilisateur spécifique (ou le rôle qui est associé à un utilisateur spécifique), vous pouvez mettre à jour la valeur du champ **Utilisateur du test**.
7. Sélectionnez **Exécuter**, puis vérifiez le produit est créé dans l'entité juridique USMF et l'entité juridique USSI.

### <a name="validate-notifications"></a>Valider les notifications

Cette fonction peut être utilisée pour vérifier si une action s'est produite. Par exemple, lorsqu'un ordre de fabrication est créé, estimé, puis démarré, l'application présente un message « Production – démarrer » pour vous informer que l'ordre de fabrication a commencé.

![Notification Production – Démarrer](./media/use_rsa_tool_05.png)

Vous pouvez valider ce message dans RSAT en entrant le texte du message dans l'onglet **Validation du message** du fichier de paramètres Excel pour l'enregistrement approprié.

![Onglet Validation du message](./media/use_rsa_tool_06.png)

Une fois le scénario de test exécuté, le message du fichier de paramètres Excel est comparé au message qui s'affiche. Si les messages ne correspondent pas, le scénario de test échoue.

> [!NOTE]
> Vous pouvez entrer plusieurs messages dans l'onglet **Validation du message** du fichier de paramètres Excel. Les messages peuvent également être des messages d'erreur ou d'avertissement au lieu de messages d'information.

### <a name="validate-values-by-using-operators"></a>Valider les valeurs à l'aide d'opérateurs

Dans les versions précédentes de RSAT, vous ne pouviez valider les valeurs que si une valeur de contrôle était égale à une valeur attendue. La nouvelle fonction permet de valider qu'une variable n'est pas égale à, est inférieure à, ou est supérieure à une valeur spécifiée.

- Pour utiliser cette fonction, ouvrez le fichier **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** sous le dossier d'installation de RSAT (par exemple, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), puis modifiez la valeur de l'élément suivant de **faux** à **vrai**.

    ```xml
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    Dans le fichier de paramètres Excel, un nouveau champ **Opérateur** apparaît.

    > [!NOTE]
    > Si vous utilisiez une version plus ancienne de RSAT, vous devez générer de nouveaux fichiers de paramètres Excel.

    ![Champ Opérateur](./media/use_rsa_tool_07.png)

L'exemple suivant montre comment vous pouvez utiliser cette fonction pour vérifier si le stock disponible est supérieur à 0 (zéro).

1. Dans les données de démonstration de la société **USMF**, créez un enregistrement de tâche ayant les étapes suivantes :

    1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
    2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez une valeur **1000** pour le champ **Numéro d'article**.
    3. Sélectionnez **Stock disponible**.
    4. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez une valeur **1** pour le champ **Site**.
    5. Dans la liste, marquer la ligne sélectionnée.
    6. Vérifiez que la valeur du champ **Total disponible** est **411,0000000000000000**.

2. Enregistrez l'enregistrement de tâche dans la bibliothèque BPM de LCS et synchronisez-la avec Azure DevOps.
3. Ajoutez le scénario de test au plan de test, puis chargez le scénario de test dans RSAT.
4. Ouvrez le fichier de paramètres Excel. Dans l'onglet **InventOnhandItem**, vous voyez une section **Valider InventOnhandItem** qui inclut un champ **Opérateur**.

    ![Champ Opérateur](./media/use_rsa_tool_08.png)

5. Pour vérifier si le stock disponible est toujours supérieur à 0, modifiez la valeur du champ **Valeur** de **411** à **0** et la valeur du champ **Opérateur** d'un signe égal (**=**) à un signe supérieur à (**\>**).

    ![Valeurs des champs Valeur et Opérateur modifiées](./media/use_rsa_tool_09.png)

6. Enregistrez et fermez le fichier de paramètres Excel.
7. Sélectionnez **Upload** pour enregistrer les modifications apportées au fichier de paramètres Excel dans Azure DevOps.

Désormais, si la valeur du champ **Total disponible** pour l'article spécifié en stock est supérieure à 0 (zéro), les tests réussiront, indépendamment de la valeur réelle du stock disponible.

### <a name="generator-logs"></a>Journaux Générateur

Cette fonction permet de créer un dossier contenant les journaux des scénarios de test qui ont été exécutés.

- Pour utiliser cette fonction, ouvrez le fichier **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** sous le dossier d'installation de RSAT (par exemple, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), puis modifiez la valeur de l'élément suivant de **faux** à **vrai**.

    ```xml
    <add key="LogGeneration" value="false" />
    ```

Une fois les scénarios de test exécutés, vous pouvez trouver les fichiers journaux sous **C:\\Utilisateurs\\\<Nom d'utilisateur\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.

![Dossier GeneratorLogs](./media/use_rsa_tool_10.png)

> [!NOTE]
> S'il y a des scénarios de test existants avant de modifier la valeur du fichier .config, les journaux ne seront pas générés pour ces scénarios de test jusqu'à ce que vous ayez généré de nouveaux fichiers d'exécution de test.
> 
> ![Commande Générer des fichiers d'exécution de test uniquement dans le menu Nouveau](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a>Instantané

Cette fonction prend des captures d'écran des étapes qui ont été effectuées au cours de l'enregistrement de tâche.

- Pour utiliser cette fonction, ouvrez le fichier **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** sous le dossier d'installation de RSAT (par exemple, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), puis modifiez la valeur de l'élément suivant de **faux** à **vrai**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Sous **C:\\Utilisateurs\\\<Nom d'utilisateur\>\\AppData\\Roaming\\regressionTool\\playback**, un dossier distinct est créé pour chaque scénario de test qui est exécuté.

![Dossier Instantané pour un scénario de test](./media/use_rsa_tool_12.png)

Dans chacune de ces dossiers, vous pouvez trouver des instantanés des étapes qui ont été effectuées lorsque les scénarios de test ont été effectués.

![Fichiers d'instantané](./media/use_rsa_tool_13.png)

## <a name="assignment"></a>Affectation

### <a name="scenario"></a>Scénario

1. Le concepteur de produit crée un nouveau produit lancé.
2. Le gestionnaire de production lance un ordre de fabrication pour amener le niveau de stock à deux unités.
3. La fabrication démarre et termine l'ordre de fabrication, et vérifie que la quantité disponible est de deux unités.
4. L'équipe commerciale reçoit une commande de quatre unités du nouveau produit. Par conséquent, l'équipe de vente présente les besoins nets via le plan dynamique. Comme aucune capacité supplémentaire n'est disponible, la stratégie de commande par défaut est définie sur « acheter plutôt que fabriquer ». Par conséquent, une commande fournisseur est créée.
5. L'acheteur ajoute un fournisseur, confirme la commande fournisseur prévisionnelle, puis confirme la commande fournisseur.
6. Lorsque les marchandises achetées arrivent au magasin, le magasinier recherche la commande fournisseur associée et réceptionne les marchandises. Comme la commande est maintenant terminée, les marchandises peuvent être prélevées et emballées conformément à la commande client.
7. Le service financier valide la facture fournisseur et la facture client.

La figure suivante présente une capture d'écran du flux de ce scénario.

![Flux du scénario de démonstration](./media/use_rsa_tool_14.png)

La figure suivante présente les processus métier de ce scénario dans RSAT.

![Processus métier pour le scénario de démonstration](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Stratégie – Points d'apprentissage clés

### <a name="data"></a>Données

- Assurez-vous d'avoir des volumes de données représentatifs (une copie des données de production/configuration Golden, plus des données migrées).
- Lorsque vous générez de nouvelles données via l'enregistreur de tâches, créez des noms de test qui ne seront pas en conflit avec des noms existants (par exemple, utilisez un préfixe tel que **RSATxxx**).
- Utilisez la restauration ponctuelle Azure pour réexécuter les tests dans des environnements de niveau autre que 1.
- Bien que vous puissiez utiliser les fonctions Excel **RANDOM** et **NOW** pour générer une combinaison unique, la charge de travail est considérable. Voici un exemple :

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a>Enregistreur de tâches

- Définissez les scénarios avant de commencer l'enregistrement. Un projet bien géré a des scénarios de test prédéfinis. Pour établir un scénario de test, prenez en compte la prédictibilité des résultats de ces scénarios de test.
- Fractionnez les enregistrements s'ils sont réalisés par des rôles différents, ou s'il existe un temps d'attente ou un événement externe avant l'étape suivante.
- Évitez de sélectionner des valeurs dans des listes. Au lieu de cela, utilisez des formats texte, tels que **FIFO**, **AudioRM** et **SiteWH**. Si vous faites une sélection dans une liste, c'est la position de la valeur dans la liste qui est enregistrée, pas la valeur elle-même. Si des articles sont ajoutés à cette liste, la position de la valeur peut changer. Par conséquent, l'enregistrement utilisera un paramètre différent, et le reste du scénario peut en être affecté.
- Pensez au comportement multi-utilisateur. Par exemple, ne supposez pas que votre commande client nouvellement créée sera toujours sélectionnée automatiquement. Au lieu de cela, utilisez toujours le filtre permettant de trouver la commande appropriée.
- Utilisez la fonction Copier dans l'enregistreur de tâches pour enregistrer le nom d'un produit nouvellement créé, de manière à l'utiliser dans des scénarios de test enchaînés.
- Utilisez la fonction Valider de l'enregistreur de tâches pour définir des points de contrôle pour vérifier que les étapes ont été exécutées correctement.

### <a name="rsat"></a>RSAT

- Pour exécuter le test sur une autre société, vous pouvez modifier la société sur l'onglet **Général** du fichier de paramètres Excel. Vérifiez que les paramètres et les données sont disponibles dans la société récemment sélectionnée.
- Vous pouvez modifier l'utilisateur du test dans l'onglet **Général** du fichier de paramètres Excel. Indiquez l'ID d'e-mail de l'utilisateur qui exécutera le scénario de test. Ainsi, le scénario de test pourra être exécuté à l'aide des autorisations de sécurité de l'utilisateur spécifié.
- Pour attendre le démarrage du test, vous pouvez définir une pause dans l'onglet **Général** du fichier de paramètres Excel. Cette pause peut être utilisée dans un traitement par lots (par exemple, si un workflow doit être exécuté avant que l'étape suivante ne puisse être réalisée.)

## <a name="advanced-scripting"></a>Écriture de script avancée

### <a name="command-line"></a>Ligne de commande

RSAT peut être appelé à partir d'une fenêtre **Invite de commandes**.

> [!NOTE]
> Vérifiez que la variable d'environnement **TestRoot** est définie sur le chemin d'installation de RSAT. (Dans Microsoft Windows, ouvrez **Panneau de configuration**, sélectionnez **Système et sécurité \> Système \> Paramètres système avancés**, puis sélectionnez **Variables d'environnement**.)

1. Ouvrez une fenêtre d'**invite de commande** en tant qu'administrateur.
2. Exécutez l'outil à partir du répertoire d'installation.

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
        list
        listtestsuite suite_name
        download test_case_id output_dir
        generate test_case_id output_dir
        generatederived parent_test_case_id test_plan_id test_suite_id
        generatetestonly test_case_id output_dir
        edit excel_file
        playback excel_file
        playbackmany excel_file1 [excel_file2 [.. excel_fileN]]
        playbackbyid test_case_id1 [test_case_id2 [.. test_case_idN]]
        playbacksuite suite_name
        clear
        help
        about
        quit
    ```

### <a name="windows-powershell-examples"></a>Exemples Windows PowerShell

#### <a name="run-a-test-case-in-a-loop"></a>Exécuter un scénario de test dans une boucle

Vous avez un script de test qui crée un nouveau client. Grâce à l'écriture de script, ce scénario de test peut être exécuté en boucle en rendant aléatoires les données suivantes avant chaque itération de l'exécution :

- ID client
- Nom du client
- Adresse du client

L'ID client est au format *ATCUS\<numéro\>*, où \<numéro\> est une valeur comprise entre **000000001** et **999999999**.

L'exemple suivant utilise un paramètre, **début**, pour définir le premier numéro utilisé. Il utilise un deuxième paramètre, **nr**, pour définir le nombre de clients à créer. Pour chaque itération, les paramètres du fichier de paramètres Excel sont modifiés à l'aide d'une fonction UpdateCustomer. Ensuite, la ligne de commande RSAT est appelée dans une fonction RunTestCase.

Ouvrez l'environnement ISE ( PowerShell Integrated Scripting) de Microsoft Windows en mode administrateur, et collez le code suivant dans la fenêtre qui s'appelle **Untitled1.ps1**.

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
$excelFilename = "full path to excel file parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a>Exécuter un script qui dépend de données de Microsoft Dynamics 365

L'exemple suivant utilise un appel OData (Open Data Protocol) pour rechercher le statut d'une commande fournisseur. Si le statut n'est pas **facturé**, vous pouvez, par exemple, appeler un scénario de test RSAT qui valide la facture.

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
