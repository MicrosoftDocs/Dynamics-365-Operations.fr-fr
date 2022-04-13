---
title: Didacticiel Regression Suite Automation Tool
description: Cette rubrique explique comment utiliser l’outil RSAT (Regression Suite Automation Tool). Il en décrit les diverses fonctions et fournit des exemples qui utilisent l’écriture de script avancée.
author: FrankDahl
ms.date: 09/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: e2273aefb98880a1ae746ef7ec65b4f2262f3560
ms.sourcegitcommit: 49c97b0c94e916db5efca5672d85df70c3450755
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2022
ms.locfileid: "8492918"
---
# <a name="regression-suite-automation-tool-tutorial"></a>Didacticiel Regression Suite Automation Tool

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Utilisez les outils du navigateur Internet pour télécharger et enregistrer cette page au format PDF.

Ce didacticiel vous explique quelques-unes des fonctions avancées de l’outil RSAT (Regression Suite Automation Tool), inclut une mission de démonstration et décrit des points stratégiques et d’apprentissage clés.

## <a name="notable-features-of-rsat-and-task-recorder"></a>Caractéristiques notables de RSAT et de l’enregistreur de tâches

### <a name="validate-a-field-value"></a>Valider une valeur du champ

RSAT vous permet d’inclure des étapes de validation dans votre scénario de test pour valider les valeurs attendues. Pour plus d’informations sur cette fonctionnalité, consultez l’article [Valider des valeurs prévues](rsat-validate-expected.md).

L’exemple suivant montre comment vous pouvez utiliser cette fonction pour vérifier si le stock disponible est supérieur à 0 (zéro).

1. Dans les données de démonstration de la société **USMF**, créez un enregistrement de tâche ayant les étapes suivantes :

    1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
    2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez une valeur **1000** pour le champ **Numéro d’article**.
    3. Sélectionnez **Stock disponible**.
    4. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez une valeur **1** pour le champ **Site**.
    5. Dans la liste, marquer la ligne sélectionnée.
    6. Vérifiez que la valeur du champ **Total disponible** est **411,0000000000000000**.

2. Enregistrez l’enregistrement de tâche en tant qu’**enregistrement pour développeur** et joignez-le à votre scénario de test dans Azure DevOps.
3. Ajoutez le scénario de test au plan de test, puis chargez le scénario de test dans RSAT.
4. Ouvrez le fichier de paramètre Excel et accédez à l’onglet **TestCaseSteps**.
5. Pour valider si le stock disponible sera toujours supérieur à **0**, accédez à l’étape **Valider le total disponible** et modifiez sa valeur de **411** en **0**. Modifiez la valeur du champ **Opérateur** du signe égal (**=**) en signe supérieur à (**\>**).
6. Enregistrez et fermez le fichier de paramètres Excel.
7. Sélectionnez **Upload** pour enregistrer les modifications apportées au fichier de paramètres Excel dans Azure DevOps.

Désormais, si la valeur du champ **Total disponible** pour l’article spécifié en stock est supérieure à 0 (zéro), les tests réussiront, indépendamment de la valeur réelle du stock disponible.

### <a name="saved-variables-and-chaining-of-test-cases"></a>Variables enregistrées et enchaînement des cas de test

L’une des fonctionnalités principales de RSAT n’est autre que l’enchaînement de cas de test, autrement dit la possibilité pour un test de transmettre des variables à d’autres tests. Pour plus d’informations, consultez l’article [Copier des variables pour enchaîner des cas de test](rsat-chain-test-cases.md).

### <a name="derived-test-case"></a>Scénario de test dérivé

RSAT vous permet d’utiliser le même enregistrement de tâche avec plusieurs cas de test, permettant à une tâche de s’exécuter avec différentes configurations de données. Voir l’article [Cas de test dérivés](rsat-derived-test-cases.md) pour plus d’informations.

### <a name="validate-notifications-and-messages"></a>Valider les notifications et les messages

Cette fonction peut être utilisée pour vérifier si une action s’est produite. Par exemple, lorsqu’un ordre de fabrication est créé, estimé, puis démarré, l’application présente un message « Production – démarrer » pour vous informer que l’ordre de fabrication a commencé.

![Notification Production – Démarrer.](./media/use_rsa_tool_05.png)

Vous pouvez valider ce message dans RSAT en entrant le texte du message dans l’onglet **Validation du message** du fichier de paramètres Excel pour l’enregistrement approprié.

![Onglet Validation du message.](./media/use_rsa_tool_06.png)

Une fois le scénario de test exécuté, le message du fichier de paramètres Excel est comparé au message qui s’affiche. Si les messages ne correspondent pas, le scénario de test échoue.

> [!NOTE]
> Vous pouvez entrer plusieurs messages dans l’onglet **Validation du message** du fichier de paramètres Excel. Les messages peuvent également être des messages d’erreur ou d’avertissement au lieu de messages d’information.

### <a name="snapshot"></a>Instantané

Cette fonction prend des captures d’écran des étapes qui ont été effectuées au cours de l’enregistrement de tâche. Il est utile à des fins d’audit ou de débogage.

- Pour utiliser cette fonction lors de l’exécution de RSAT avec l’interface utilisateur, ouvrez le fichier **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** sous le dossier d’installation de RSAT (par exemple, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), puis modifiez la valeur de l’élément suivant de **False** à **True**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

- Pour utiliser cette fonction lors de l’exécution de RSAT par la CLI (par exemple, Azure DevOps), ouvrez le fichier **Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe.config** sous le dossier d’installation de RSAT (par exemple, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), puis modifiez la valeur de l’élément suivant de **False** à **True**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Lorsque vous exécutez des scénarios de test, RSAT génère des instantanés (images) des étapes et les enregistre dans le dossier de lecture des scénarios de test dans le répertoire de travail. Dans le dossier de lecture, un sous-dossier distinct est créé nommé **StepSnapshots**. Ce dossier contient des instantanés des scénarios de test exécutés.

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

![Flux du scénario de démonstration.](./media/use_rsa_tool_14.png)

L’illustration suivante montre la hiérarchie des processus métier pour ce scénario dans le Concepteur de processus d’entreprise LCS.

![Processus métier pour le scénario de démonstration.](./media/use_rsa_tool_15.png)

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
        downloadsuite
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitebyid
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        playbacksuitebyid
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>?

Répertorie toutes les commandes ou affiche l’aide d’une commande spécifique, ainsi que les paramètres disponibles.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="-optional-parameters"></a>? : paramètres facultatifs

`command` : Où``[command]`` est l’une des commandes de la liste précédente.

#### <a name="about"></a>à propos de

Affiche la version RSAT installée.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls

Efface l’écran.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**

#### <a name="download"></a>télécharger

Télécharge les pièces jointes (fichiers Recording, Execution et Parameter) pour le scénario de test spécifié issu de Azure DevOps dans le répertoire de sortie. Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles et utiliser n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="download-optional-switches"></a>download : commutateurs en option

+ `/retry[=seconds]` : si ce commutateur est spécifié et que les scénarios de test sont bloqués par d’autres instances RSAT, le processus de téléchargement attendra le nombre de secondes spécifié, puis réessayera. La valeur par défaut de \[seconds\] est 120 secondes. Sans ce commutateur, le processus sera immédiatement annulé si les scénarios de test sont bloqués.

##### <a name="download-required-parameters"></a>download : paramètres obligatoires

+ `test_case_id` : représente l’ID du scénario de test.

##### <a name="download-optional-parameters"></a>download : paramètres facultatifs

+ `output_dir` : représente le répertoire de travail de sortie. Le répertoire doit exister. Le répertoire de travail issu des paramètres sera utilisé si ce paramètre n’est pas spécifié.

##### <a name="download-examples"></a>download : exemples

`download 123 c:\temp\rsat`

`download /retry=240 765`

#### <a name="downloadsuite"></a>downloadsuite

Télécharge les pièces jointes (fichiers Recording, Execution et Parameter) pour tous les scénarios de test de la suite de tests spécifiée issue de Azure DevOps dans le répertoire de sortie. Vous pouvez utiliser la command ``listtestsuitenames`` pour obtenir toutes les suites de test disponibles et utiliser n’importe quelle valeur comme paramètre **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``downloadsuite``**``[/retry[=<seconds>]] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="downloadsuite-optional-switches"></a>downloadsuite : commutateurs en option

+ `/retry[=seconds]` : si ce commutateur est spécifié et que les scénarios de test sont bloqués par d’autres instances RSAT, le processus de téléchargement attendra le nombre de secondes spécifié, puis réessayera. La valeur par défaut de \[seconds\] est 120 secondes. Sans ce commutateur, le processus sera immédiatement annulé si les scénarios de test sont bloqués.
+ `/byid` : ce commutateur indique que la suite de tests souhaitée est identifiée par son ID Azure DevOps au lieu du nom de la suite de tests.

##### <a name="downloadsuite-required-parameters"></a>downloadsuite : paramètres obligatoires

+ `test_suite_name` : représente le nom de la suite de tests. Ce paramètre est requis si le commutateur /byid **n’est pas** spécifié. Ce nom est le nom de la suite de tests Azure DevOps.
+ `test_suite_id` : représente l’ID de la suite de tests. Ce paramètre est requis si le commutateur /byid **est** spécifié. Cet ID est un ID de suite de tests Azure DevOps.

##### <a name="downloadsuite-optional-parameters"></a>downloadsuite : paramètres facultatifs

+ `output_dir` : représente le répertoire de travail de sortie. Le répertoire doit exister. Le répertoire de travail issu des paramètres sera utilisé si ce paramètre n’est pas spécifié.

##### <a name="downloadsuite-examples"></a>download : exemples

`downloadsuite NameOfTheSuite c:\temp\rsat`

`downloadsuite /byid 123 c:\temp\rsat`

`downloadsuite /retry=240 /byid 765`

`downloadsuite /retry=240 /byid 765 c:\temp\rsat`

#### <a name="edit"></a>modifier

Vous permet d’ouvrir le fichier de paramètres dans le programme Excel et de le modifier.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="edit-required-parameters"></a>edit : paramètres obligatoires

+ `excel_file` : doit contenir un chemin d’accès complet à un fichier Excel existant.

##### <a name="edit-examples"></a>edit : exemples

`edit c:\RSAT\123\TestCase_123_Base.xlsx`

`edit e:\temp\TestCase_456_Base.xlsx`

#### <a name="generate"></a>generate

Génère les fichiers d’exécution de tests et de paramètre pour le scénario de test spécifié dans le répertoire de sortie. Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles. Utilisez n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] [test_case_id] [output_dir]``

##### <a name="generate-optional-switches"></a>generate : commutateurs en option

+ `/retry[=seconds]` : si ce commutateur est spécifié et que les scénarios de test sont bloqués par d’autres instances RSAT, le processus de génération attendra le nombre de secondes spécifié, puis réessayera. La valeur par défaut de \[seconds\] est 120 secondes. Sans ce commutateur, le processus sera immédiatement annulé si les scénarios de test sont bloqués.
+ `/dllonly` : Génère uniquement les fichiers d’exécution de test. Ne génère pas de nouveau le fichier de paramètres Excel.
+ `/keepcustomexcel` : met à niveau le fichier de paramètres existant. Régénère également les fichiers Execution.

##### <a name="generate-required-parameters"></a>generate : paramètres obligatoires

+ `test_case_id` : représente l’ID du scénario de test.

##### <a name="generate-optional-parameters"></a>generate : paramètres facultatifs

+ `output_dir` : représente le répertoire de travail de sortie. Le répertoire doit exister. Le répertoire de travail issu des paramètres sera utilisé si ce paramètre n’est pas spécifié.

##### <a name="generate-examples"></a>generate : exemples

`generate 123 c:\temp\rsat`

`generate /retry=240 765 c:\rsat\last`

`generate /retry=240 /dllonly 765`

`generate /retry=240 /keepcustomexcel 765`

#### <a name="generatederived"></a>generatederived

Génère un nouveau scénario de test dérivé (scénario de test enfant) du scénario de test fourni. Le nouveau scénario de test est également ajouté à la suite de tests spécifiée. Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles et utiliser n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[/retry[=<seconds>]] [parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="generatederived-optional-switches"></a>generatederived : commutateurs en option

+ `/retry[=seconds]` : si ce commutateur est spécifié et que les scénarios de test sont bloqués par d’autres instances RSAT, le processus de génération attendra le nombre de secondes spécifié, puis réessayera. La valeur par défaut de \[seconds\] est 120 secondes. Sans ce commutateur, le processus sera immédiatement annulé si les scénarios de test sont bloqués.

##### <a name="generatederived-required-parameters"></a>generatederived : paramètres obligatoires

+ `parent_test_case_id` : représente l’ID du scénario de test parent.
+ `test_plan_id` : représente l’ID du plan de test.
+ `test_suite_id` : représente l’ID de la suite de tests.

##### <a name="generatederived-examples"></a>generatederived : exemples

`generatederived 123 8901 678`

`generatederived /retry 123 8901 678`

#### <a name="generatetestonly"></a>generatetestonly

Génère uniquement les fichiers d’exécution de tests pour le scénario de test spécifié. Il ne génère pas le nouveau fichier de paramètres Excel. Les fichiers sont générés dans le répertoire de sortie spécifié. Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles et utiliser n’importe quelle valeur de la première colonne comme paramètre **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="generatetestonly-optional-switches"></a>generatetestonly : commutateurs en option

+ `/retry[=seconds]` : si ce commutateur est spécifié et que les scénarios de test sont bloqués par d’autres instances RSAT, le processus de génération attendra le nombre de secondes spécifié, puis réessayera. La valeur par défaut de \[seconds\] est 120 secondes. Sans ce commutateur, le processus sera immédiatement annulé si les scénarios de test sont bloqués.

##### <a name="generatetestonly-required-parameters"></a>generatetestonly : paramètres obligatoires

+ `test_case_id` : représente l’ID du scénario de test.

##### <a name="generatetestonly-optional-parameters"></a>generatetestonly : paramètres facultatifs

+ `output_dir` : représente le répertoire de travail de sortie. Le répertoire doit exister. Le répertoire de travail issu des paramètres sera utilisé si ce paramètre n’est pas spécifié.

##### <a name="generatetestonly-examples"></a>generatetestonly : exemples

`generatetestonly 123 c:\temp\rsat`

`generatetestonly /retry=240 765`

#### <a name="generatetestsuite"></a>generatetestsuite

Génère les fichiers d’automatisation des tests pour tous les scénarios de test de la suite de tests spécifiée. Vous pouvez utiliser la command ``listtestsuitenames`` pour obtenir toutes les suites de test disponibles et utiliser n’importe quelle valeur comme paramètre **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="generatetestsuite-optional-switches"></a>generatetestsuite : commutateurs en option

+ `/retry[=seconds]` : si ce commutateur est spécifié et que les scénarios de test sont bloqués par d’autres instances RSAT, le processus de génération attendra le nombre de secondes spécifié, puis réessayera. La valeur par défaut de \[seconds\] est 120 secondes. Sans ce commutateur, le processus sera immédiatement annulé si les scénarios de test sont bloqués.
+ `/dllonly` : Génère uniquement les fichiers d’exécution de test. Ne génère pas de nouveau le fichier de paramètres Excel.
+ `/keepcustomexcel` : met à niveau le fichier de paramètres existant. Régénère également les fichiers Execution.
+ `/byid` : ce commutateur indique que la suite de tests souhaitée est identifiée par son ID Azure DevOps au lieu du nom de la suite de tests.

##### <a name="generatetestsuite-required-parameters"></a>generatetestsuite : paramètres obligatoires

+ `test_suite_name` : représente le nom de la suite de tests. Ce paramètre est requis si le commutateur /byid **n’est pas** spécifié. Ce nom est le nom de la suite de tests Azure DevOps.
+ `test_suite_id` : représente l’ID de la suite de tests. Ce paramètre est requis si le commutateur /byid **est** spécifié. Cet ID est un ID de suite de tests Azure DevOps.

##### <a name="generatetestsuite-optional-parameters"></a>generatetestsuite : paramètres facultatifs

+ `output_dir` : représente le répertoire de travail de sortie. Le répertoire doit exister. Le répertoire de travail issu des paramètres sera utilisé si ce paramètre n’est pas spécifié.

##### <a name="generatetestsuite-examples"></a>generatetestsuite : exemples

`generatetestsuite Tests c:\temp\rsat`

`generatetestsuite /retry Purchase c:\rsat\last`

`generatetestsuite /dllonly /byid 121`

`generatetestsuite /keepcustomexcel /byid 121`

#### <a name="help"></a>help

Identique à la commande [?](#section) .

#### <a name="list"></a>liste

Répertorie tous les scénarios de test disponibles dans le plan de test actuel.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**

#### <a name="listtestplans"></a>listtestplans

Répertorie tous les plans de test disponibles.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**

#### <a name="listtestsuite"></a>listtestsuite

Répertorie les scénarios de test pour la suite de tests spécifiée. Vous pouvez utiliser la command ``listtestsuitenames`` pour obtenir toutes les suites de test disponibles et utiliser n’importe quelle valeur de la liste comme paramètre **suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[test_suite_name]``

##### <a name="listtestsuite-required-parameters"></a>listtestsuite : paramètres obligatoires

+ `test_suite_name` : nom de la suite souhaitée.

##### <a name="listtestsuite-examples"></a>listtestsuite : exemples

`listtestsuite "sample suite name"`

`listtestsuite NameOfTheSuite`

#### <a name="listtestsuitebyid"></a>listtestsuitebyid

Répertorie les scénarios de test pour la suite de tests spécifiée.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitebyid``**``[test_suite_id]``

##### <a name="listtestsuitebyid-required-parameters"></a>listtestsuitebyid : paramètres obligatoires

+ `test_suite_id` : ID de la suite souhaitée.

##### <a name="listtestsuitebyid-examples"></a>listtestsuitebyid : exemples

`listtestsuitebyid 12345`

#### <a name="listtestsuitenames"></a>listtestsuitenames

Répertorie toutes les suites de test disponibles dans le plan de test actuel.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**

#### <a name="playback"></a>playback

Lit le scénario de test associé au fichier de paramètres Excel spécifié. Cette commande utilise les fichiers d’automatisation locaux existants et ne télécharge pas de fichiers à partir de Azure DevOps. Cette commande n’est pas prise en charge pour les scénarios de test de PDV du commerce.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file]``

##### <a name="playback-optional-switches"></a>playback : commutateurs en option

+ `/retry[=seconds]` : si ce commutateur est spécifié et que les scénarios de test sont bloqués par d’autres instances RSAT, le processus de lecture attendra le nombre de secondes spécifié, puis réessayera. La valeur par défaut de \[seconds\] est 120 secondes. Sans ce commutateur, le processus sera immédiatement annulé si les scénarios de test sont bloqués.
+ `/comments[="comment"]` : fournit une chaîne d’informations personnalisée qui sera incluse dans le champ **Commentaires** sur les pages de résumé et de résultat de test pour les exécutions de scénario de test Azure DevOps.

##### <a name="playback-required-parameters"></a>playback : paramètres obligatoires

+ `excel_parameter_file` : Le chemin complet d’un fichier de paramètres Excel. Le fichier doit exister.

##### <a name="playback-examples"></a>playback : exemples

`playback c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playback /retry e:\temp\test.xlsx`

`playback /retry=300 e:\temp\test.xlsx`

`playback /comments="Payroll solution 10.0.0" e:\temp\test.xlsx`

#### <a name="playbackbyid"></a>playbackbyid

Lit plusieurs scénarios de test simultanément. Les cas de test sont identifiés par leur ID. Cette commande téléchargera les fichiers à partir de Azure DevOps. Vous pouvez utiliser la commande ``list`` pour obtenir tous les scénarios de test disponibles et utiliser n’importe laquelle des valeurs de la première colonne comme paramètre **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[/retry[=<seconds>]] [/comments[="comment"]] [test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="playbackbyid-optional-switches"></a>playbackbyid : commutateurs en option

+ `/retry[=seconds]` : si ce commutateur est spécifié et que les scénarios de test sont bloqués par d’autres instances RSAT, le processus de lecture attendra le nombre de secondes spécifié, puis réessayera. La valeur par défaut de \[seconds\] est 120 secondes. Sans ce commutateur, le processus sera immédiatement annulé si les scénarios de test sont bloqués.
+ `/comments[="comment"]` : fournit une chaîne d’informations personnalisée qui sera incluse dans le champ **Commentaires** sur les pages de résumé et de résultat de test pour les exécutions de scénario de test Azure DevOps.

##### <a name="playbackbyid-required-parameters"></a>playbackbyid : paramètres obligatoires

+ `test_case_id1` : ID d’un scénario de test existant.
+ `test_case_id2` : ID d’un scénario de test existant.
+ `test_case_idN` : ID d’un scénario de test existant.

##### <a name="playbackbyid-examples"></a>playbackbyid : exemples

`playbackbyid 878`

`playbackbyid 2345 667 135`

`playbackbyid /comments="Payroll solution 10.0.0" 2345 667 135`

`playbackbyid /retry /comments="Payroll solution 10.0.0" 2345 667 135`

#### <a name="playbackmany"></a>playbackmany

Lit de nombreux scénarios de test simultanément. Les scénarios de test sont identifiés par des fichiers de paramètres Excel. Cette commande utilise les fichiers d’automatisation locaux existants et ne télécharge pas de fichiers à partir de Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file1] [excel_parameter_file2] ... [excel_parameter_fileN]``

##### <a name="playbackmany-optional-switches"></a>playbackmany : commutateurs en option

+ `/retry[=seconds]` : si ce commutateur est spécifié et que les scénarios de test sont bloqués par d’autres instances RSAT, le processus de lecture attendra le nombre de secondes spécifié, puis réessayera. La valeur par défaut de \[seconds\] est 120 secondes. Sans ce commutateur, le processus sera immédiatement annulé si les scénarios de test sont bloqués.
+ `/comments[="comment"]` : fournit une chaîne d’informations personnalisée qui sera incluse dans le champ **Commentaires** sur les pages de résumé et de résultat de test pour les exécutions de scénario de test Azure DevOps.

##### <a name="playbackmany-required-parameters"></a>playbackmany : paramètres obligatoires

+ `excel_parameter_file1` : Le chemin complet du fichier de paramètres Excel. Le fichier doit exister.
+ `excel_parameter_file2` : Le chemin complet du fichier de paramètres Excel. Le fichier doit exister.
+ `excel_parameter_fileN` : Le chemin complet du fichier de paramètres Excel. Le fichier doit exister.

##### <a name="playbackmany-examples"></a>playbackmany : exemples

`playbackmany c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playbackmany e:\temp\test.xlsx f:\RSAT\sample1.xlsx c:\RSAT\sample2.xlsx`

`playbackmany /retry=180 /comments="Payroll solution 10.0.0" e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx`

#### <a name="playbacksuite"></a>playbacksuite

Lit tous les scénarios de test à partir d’une ou plusieurs suites de tests spécifiées. Si le commutateur /local est spécifié, les pièces jointes locales seront utilisées pour la lecture. Sinon, les pièces jointes seront téléchargées depuis Azure DevOps. Vous pouvez utiliser la command ``listtestsuitenames`` pour obtenir toutes les suites de test disponibles et utiliser n’importe quelle valeur de la première colonne comme paramètre **suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] ([test_suite_name1] .. [test_suite_nameN] | [/byid] [test_suite_id1] .. [test_suite_idN])``

##### <a name="playbacksuite-optional-switches"></a>playbacksuite : commutateurs en option

+ `/updatedriver` : si ce commutateur est spécifié, le pilote Web du navigateur Internet sera mis à jour selon les besoins avant l’exécution du processus de lecture.
+ `/local` : ce commutateur indique que les pièces jointes locales doivent être utilisées pour la lecture au lieu de télécharger des fichiers depuis Azure DevOps.
+ `/retry[=seconds]` : si ce commutateur est spécifié et que les scénarios de test sont bloqués par d’autres instances RSAT, le processus de lecture attendra le nombre de secondes spécifié, puis réessayera. La valeur par défaut de \[seconds\] est 120 secondes. Sans ce commutateur, le processus sera immédiatement annulé si les scénarios de test sont bloqués.
+ `/comments[="comment"]` : fournit une chaîne d’informations personnalisée qui sera incluse dans le champ **Commentaires** sur les pages de résumé et de résultat de test pour les exécutions de scénario de test Azure DevOps.
+ `/byid` : ce commutateur indique que la suite de tests souhaitée est identifiée par son ID Azure DevOps au lieu du nom de la suite de tests.

##### <a name="playbacksuite-required-parameters"></a>playbacksuite : paramètres obligatoires

+ `test_suite_name1` : représente le nom de la suite de tests. Ce paramètre est requis si le commutateur /byid **n’est pas** spécifié. Ce nom est le nom de la suite de tests Azure DevOps.
+ `test_suite_nameN` : représente le nom de la suite de tests. Ce paramètre est requis si le commutateur /byid **n’est pas** spécifié. Ce nom est le nom de la suite de tests Azure DevOps.
+ `test_suite_id1` : représente l’ID de la suite de tests. Ce paramètre est requis si le commutateur /byid **est** spécifié. Cet ID est l’ID de suite de tests Azure DevOps.
+ `test_suite_idN` : représente l’ID de la suite de tests. Ce paramètre est requis si le commutateur /byid **est** spécifié. Cet ID est l’ID de suite de tests Azure DevOps.

##### <a name="playbacksuite-examples"></a>playbacksuite : exemples

`playbacksuite suiteName`

`playbacksuite suiteName suiteNameToo`

`playbacksuite /updatedriver /local /retry=180 /byid 151 156`

`playbacksuite /updatedriver /local /comments="Payroll solution 10.0.0" /byid 150`

#### <a name="playbacksuitebyid"></a>playbacksuitebyid

Exécute tous les scénarios de test de la suite de tests Azure DevOps spécifiée.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuitebyid``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] [test_suite_id]``

##### <a name="playbacksuitebyid-optional-switches"></a>playbacksuitebyid : commutateurs en option

+ `/retry[=seconds]` : si ce commutateur est spécifié et que les scénarios de test sont bloqués par d’autres instances RSAT, le processus de lecture attendra le nombre de secondes spécifié, puis réessayera. La valeur par défaut de \[seconds\] est 120 secondes. Sans ce commutateur, le processus sera immédiatement annulé si les scénarios de test sont bloqués.
+ `/comments[="comment"]` : fournit une chaîne d’informations personnalisée qui sera incluse dans le champ **Commentaires** sur les pages de résumé et de résultat de test pour les exécutions de scénario de test Azure DevOps.
+ `/byid` : ce commutateur indique que la suite de tests souhaitée est identifiée par son ID Azure DevOps au lieu du nom de la suite de tests.

##### <a name="playbacksuitebyid-required-parameters"></a>playbacksuitebyid : paramètres obligatoires

+ `test_suite_id` : représente l’ID de la suite de tests tel qu’il existe dans Azure DevOps.

##### <a name="playbacksuitebyid-examples"></a>playbacksuitebyid : exemples

`playbacksuitebyid 2900`

`playbacksuitebyid /retry 2099`

`playbacksuitebyid /retry=200 2099`

`playbacksuitebyid /retry=200 /comments="some comment" 2099`

#### <a name="quit"></a>quit

Ferme l’application. Cette commande n’est utile que lorsque les applications s’exécutent en mode interactif.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**

##### <a name="quit-examples"></a>quit : exemples

`quit`

#### <a name="upload"></a>upload

Charge les fichier joints (fichiers Recording, Execution, and Parameter) qui appartiennent à une suite de tests ou à des scénarios de test spécifiés vers Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``([test_suite_name] | [test_case_id1] .. [test_case_idN])``

##### <a name="upload-required-parameters"></a>upload : paramètres obligatoires

+ `test_suite_name` : tous les fichiers appartenant à la suite de tests spécifiée seront chargés.
+ `test_case_id1` : représente le premier ID de scénario de test qui doit être chargé. Utilisez ce paramètre uniquement lorsqu’aucun nom de suite de tests n’a été fourni.
+ `test_case_idN` : représente le dernier ID de scénario de test qui doit être chargé. Utilisez ce paramètre uniquement lorsqu’aucun nom de suite de tests n’a été fourni.

##### <a name="upload-examples"></a>upload : exemples

`upload sample_suite`

`upload 2900`

`upload 123 456`

#### <a name="uploadrecording"></a>uploadrecording

Charge uniquement le fichier Recording appartenant à un ou plusieurs scénarios de test Azure DevOps spécifiés.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[test_case_id1] .. [test_case_idN]``

##### <a name="uploadrecording-required-parameters"></a>uploadrecording : paramètres obligatoires

+ `test_case_id1` : représente le premier ID de scénario de test pour l’enregistrement qui doit être chargé vers Azure DevOps.
+ `test_case_idN` : représente le dernier ID de scénario de test pour l’enregistrement qui doit être chargé vers Azure DevOps.

##### <a name="uploadrecording-examples"></a>uploadrecording : exemples

`uploadrecording 123`

`uploadrecording 123 456`

#### <a name="usage"></a>usage

Affiche les trois modes d’utilisation de cette application.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**

Exécution interactive de l’application :

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``

Exécution de l’application en spécifiant une commande :

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp ``**``[command]``**

Exécution de l’application en fournissant un fichier de paramètres :

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``/settings [drive:\Path to\file.settings] [command]``**

### <a name="windows-powershell-examples"></a>Exemples Windows PowerShell

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

```powershell
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


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
