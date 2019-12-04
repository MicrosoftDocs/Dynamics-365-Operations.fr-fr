---
title: Définir les paramètres d'un format de gestion des états électroniques par entité juridique
description: Cette rubrique explique comment vous pouvez définir les paramètres d'un format gestion des états électroniques par entité juridique.
author: NickSelin
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 9c5884bba494d2dd44f9204667144402a88ddec8
ms.sourcegitcommit: d6196d83c7b9166ddb4fe43a91e6bd0ad9da2099
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2019
ms.locfileid: "2694336"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>Définir les paramètres d'un format de gestion des états électroniques par entité juridique

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a>Conditions préalables

Pour effectuer cette procédure, vous devez suivre les étapes de la rubrique [Configurer les formats de gestion des états électroniques pour utiliser les paramètres spécifiés par entité juridique](er-app-specific-parameters-configure-format.md).

Pour terminer les exemples de cette rubrique, vous devez avoir accès à Microsoft Dynamics 365 Finance (Finance) pour un des rôles suivants :

- Développeur d'états électroniques
- Consultant fonctionnel des états électroniques
- Administrateur système

## <a name="import-er-configurations"></a>Importer les configurations ER

1.  Connectez-vous à votre environnement.
2.  Dans le tableau de bord par défaut, sélectionnez **Gestion des états électroniques**.
3.  Sélectionnez **Configurations des états**.
4.  Importez, dans l'instance actuelle de Finance, les configurations exportées depuis RCS lorsque vous exécutez ces étapes dans la rubrique [Configurer les formats de gestion des états électroniques pour utiliser les paramètres qui sont spécifiques par entité juridique](er-app-specific-parameters-configure-format.md). Procédez comme suit pour chaque configuration de gestion des états électroniques, dans l'ordre suivant : modèle de données, mise en correspondance de modèle et formats.

    1. Sélectionnez **Échanger \> Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir** pour sélectionner le fichier pour la configuration de gestion des états électroniques requise au format XML.
    3. Cliquez sur **OK**.
    
    L'illustration suivante présente les configurations que vous devez avoir lorsque vous avez fini.

    ![Page Configurations d'ER](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>Définir les paramètres pour l'entreprise DEMF

Vous pouvez utiliser la structure de gestion des états électroniques pour configurer les paramètres spécifiques à l'application pour un format de gestion des états électroniques.

1.  Sélectionnez l'entité juridique **DEMF**.
2.  Dans l'arborescence des configurations, sélectionnez le format **Format pour apprendre comment rechercher les données LE**.
3.  Dans le volet Actions, sous l'onglet **Configurations**, dans le groupe **Paramètres spécifiques à l'application**, sélectionnez **Configurer**.

    ![Page Paramètres spécifiques à l'application de la gestion des états électroniques](./media/GER-AppSpecParms-LookupForm.PNG)
    
    Sur la page **Paramètres spécifiques à l'application**, vous pouvez configurer les règles pour la source données **Sélecteur** du format **Format pour apprendre comment rechercher les données LE**.
    
    Si le format de gestion des états électroniques de base contient plusieurs sources de données de type **Recherche**, vous devez sélectionner la source de données souhaitée dans l'organisateur **Recherches** avant de commencer à configurer l'ensemble de règles pour la source de données.
    
    Pour chaque source de données, vous pouvez configurer des règles différentes pour chaque version du format de gestion des états électroniques sélectionné.
    
    L'ensemble des règles pour toutes les sources de données de recherche qui sont disponibles dans la version sélectionnée du format de gestion des états électroniques de base constitue les paramètres spécifiques à l'application pour le format de gestion des états électroniques.

4.  Sélectionnez la version **1.1.1** du format de gestion des états électroniques.
5.  Dans l'organisateur **Conditions**, sélectionnez **Ajouter**.
6.  Dans le champ **Code** du nouvel enregistrement, sélectionnez la flèche du menu déroulant pour ouvrir la recherche.

    La recherche affiche la liste des codes taxe pour la sélection. Cette liste est renvoyée par la source de données **Model.Data.Tax** qui a été configurée dans le format de gestion des états électroniques de base. Parce que cette source de données contient le champ **Nom**, le nom de chaque code taxe s'affiche dans la recherche.

    ![Page Paramètres spécifiques à l'application de la gestion des états électroniques](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  Sélectionnez le code taxe **VAT19**.
8.  Dans le champ **Résultat de la recherche** du nouvel enregistrement, sélectionnez la flèche du menu déroulant pour ouvrir la recherche. La recherche affiche la liste des valeurs pour l'énumération de format TaxationLevel pour la sélection.

    Notez que, si l'allemand est sélectionné comme langue préférée de l'utilisateur sous lequel vous êtes connecté, les libellés des valeurs dans la recherche seront en allemand, à condition qu'ils aient été traduits au format de gestion des états électroniques de base. En outre, si le libellé d'une source de données de recherche a été traduit, ce libellé apparaîtra dans la langue préférée de l'utilisateur dans l'onglet **Recherches**.

    ![Page Paramètres spécifiques à l'application de la gestion des états électroniques](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  Sélectionnez la valeur **Imposition normale**.

    En ajoutant cet enregistrement, vous définissez la règle suivante : dès que la source de données de recherche **Sélecteur** est demandée, et que le code taxe **VAT19** est transmis comme argument, **Imposition normale** sera renvoyée comme le niveau d'imposition demandé.

10. Sélectionnez **Ajouter**, puis procédez comme suit :

    1. Dans le champ **Code**, sélectionnez le code taxe **InVAT19**.
    2. Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Imposition normale**.
    
11. Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :

    1. Dans le champ **Code**, sélectionnez le code taxe **VAT7**.
    2. Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Imposition réduite**.
    
12. Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :

    1. Dans le champ **Code**, sélectionnez le code taxe **InVAT7**.
    2. Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Imposition réduite**.
    
13. Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :

    1. Dans le champ **Code**, sélectionnez le code taxe **THIRD**.
    2. Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Aucune imposition**.
    
14. Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :

    1. Dans le champ **Code**, sélectionnez le code taxe **InVAT0**.
    2. Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Aucune imposition**.
    
15. Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :

    1. Dans le champ **Code**, sélectionnez l'option **\*Non vide\***.
    2. Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Autre**.
    
    En ajoutant ce dernier enregistrement, vous définissez la règle suivante : dès que le code taxe transmis comme argument ne répond plus aux règles précédentes, la source de données de recherche renverra **Autre** comme le niveau d'imposition demandé.

    ![Page Paramètres spécifiques à l'application de la gestion des états électroniques](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. Dans le champ **État**, sélectionnez **Terminé**.

    Lorsque vous exécutez une version de format de gestion des états électroniques avec un état défini sur **Terminé** ou **Partagé**, cet ensemble de règles doit être à l'état **Terminé**. Sinon, l'exécution du format de gestion des états électroniques de base est interrompue lorsque le format essaye de charger les données provenant de cet ensemble de règles tandis que la source de données de recherche **Sélecteur** est exécutée.
    
    Lorsque vous exécutez une version de format de gestion des états électroniques avec un état défini sur **Brouillon**, le format de gestion des états électroniques de base peut accéder à cet ensemble de règles, quel que soit son état.
    
17. Sélectionnez **Enregistrer**.
18. Fermez la page **Paramètres spécifiques de l'application**.

## <a name="run-the-er-format-in-the-demf-company"></a>Exécuter le format de gestion des états électroniques dans la société DEMF

1.  Dans l'arborescence des configurations, sélectionnez le format **Format pour apprendre comment rechercher les données LE**.
2.  Dans le volet Actions, sélectionnez **Exécuter**.
3.  Dans la boîte de dialogue qui apparaît, sélectionnez **OK**.
4.  Téléchargez le relevé qui est généré et enregistrez-le localement.

    Dans le relevé généré, notez que la synthèse du code taxe **InVAT7** est passée au niveau **Réduite**, et que les synthèses de codes taxe **VAT19** et **InVA19** sont passées au niveau **Normale**. Ce comportement est déterminé par la configuration dans l'ensemble de règles dépendant de l'entité juridique.
    
5.  Accédez à **Taxe \> Taxes indirectes \> Taxe \> Codes taxe**.
6.  Sélectionnez le code taxe **InVAT7**.
7.  Dans le volet Actions, sous l'onglet **Code taxe**, au groupe **Recherches**, sélectionnez **Taxe validée** permet d'afficher des informations sur la valeur de taxe et le taux appliqué de taxe par code taxe.

    ![Page de la taxe validée](./media/GER-AppSpecParms-Statement.PNG)

8.  Fermez la page Taxe validée.

## <a name="set-up-parameters-for-the-usmf-company"></a>Définir les paramètres pour l'entreprise USMF

1.  Sélectionnez l'entité juridique **USMF**.
2.  Accédez à **Administration d'organisation \> États électroniques \> Configurations**.
3.  Dans l'arborescence des configurations, développez l'article **Modèle pour apprendre les appels paramétrés**, développez l'article **Format pour apprendre les appels paramétrés**, puis sélectionnez le format **Format pour apprendre comment rechercher les données LE**.
4.  Dans le volet Actions, sous l'onglet **Configurations**, dans le groupe **Paramètres spécifiques à l'application**, sélectionnez **Configurer**.
5.  Sélectionnez la version **1.1.1** du format de gestion des états électroniques sélectionné.
6.  Dans l'organisateur **Conditions**, sélectionnez **Ajouter**.
7.  Dans le champ **Code** du nouvel enregistrement, sélectionnez la flèche du menu déroulant pour ouvrir la recherche.

    La recherche affiche désormais la liste des codes taxe pour la taxe de société **USMF** pour sélection.

    ![Page Paramètres spécifiques à l'application de la gestion des états électroniques](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  Sélectionnez le code taxe **EXEMPT**.
9.  Dans le champ **Résultat de la recherche** du nouvel enregistrement, sélectionnez la valeur **Aucune imposition**.
10. Sélectionnez à nouveau **Ajouter**.
11. Dans le champ **Code** du nouvel enregistrement, sélectionnez l'option **\*Non vide\***.
12. Dans le champ **Résultat de la recherche** du nouvel enregistrement, sélectionnez la valeur **Imposition normale**.
13. Dans le champ **État**, sélectionnez **Terminé**.
14. Sélectionnez **Enregistrer**.

    ![Page Paramètres spécifiques à l'application de la gestion des états électroniques](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. Fermez la page **Paramètres spécifiques de l'application**.

## <a name="run-the-er-format-in-the-usmf-company"></a>Exécuter le format de gestion des états électroniques dans la société USMF

1.  Dans l'arborescence des configurations, sélectionnez le format **Format pour apprendre comment rechercher les données LE**.
2.  Dans le volet Actions, sélectionnez **Exécuter**.
3.  Dans la boîte de dialogue qui apparaît, sélectionnez **OK**.
4.  Téléchargez le relevé qui est généré et enregistrez-le localement.

    Dans le relevé généré, notez que vous avez désormais réutilisé le même format de gestion des états électroniques pour une autre entité juridique, mais sans faire d'ajustement au format de gestion des états électroniques.

## <a name="reuse-legal-entitydependent-parameters"></a>Réutiliser les paramètres dépendant de l'entité juridique

### <a name="export-parameters"></a>Exporter les paramètres

1.  Allez dans **Administration d'organisation \> Espaces de travail \> États électroniques**.
2.  Sélectionnez **Configurations des états**.
3.  Dans l'arborescence des configurations, sélectionnez le format **Format pour apprendre comment rechercher les données LE**.
4.  Dans le volet Actions, sous l'onglet **Configurations**, dans le groupe **Paramètres spécifiques à l'application**, sélectionnez **Configurer**.
5.  Sélectionnez la version **1.1.1** du format de gestion des états électroniques.
6.  Dans le volet Actions, sélectionnez **Exporter**.
7.  Téléchargez le fichier qui est généré et enregistrez-le localement.

    L'ensemble configuré des paramètres spécifiques à l'application est désormais exporté comme fichier XML.

### <a name="import-parameters"></a>Importer les paramètres

1.  Sélectionnez la version **1.1.2** du format de gestion des états électroniques.
2.  Dans la volet Actions, sélectionnez **Importer**.
3.  Sélectionnez **Oui** pour confirmer que vous souhaitez remplacer les paramètres spécifiques à l'application existants pour cette version de format.
4.  Sélectionnez **Parcourir** pour rechercher le fichier qui contient les paramètres spécifiques à l'application exportés pour la version **1.1.1**.
5.  Cliquez sur **OK**.

    La version **1.1.2** du format de gestion des états électroniques a désormais les mêmes paramètres spécifiques à l'application que vous avez précédemment configurés pour la version **1.1.1**.
    
    Notez que les paramètres spécifiques à l'application d'un format de gestion des états électroniques dépendent de l'entité juridique. Pour réutiliser les paramètres spécifiques à l'application qui ont été configurés pour une entité juridique dans une autre entité juridique, vous devez les exporter alors que vous êtes connecté à la première entité juridique, puis les importer ensuite après vous être connecté à l'autre entité juridique.

    Vous pouvez également utiliser cette approche pour transférer les paramètres spécifiques à l'application associés à la gestion des états électroniques qui étaient configurés dans une instance de Finance vers une autre instance de Finance.

    Notez que si vous configurez les paramètres spécifiques à l'application pour une version d'un format de gestion des états électroniques et si vous importez une version supérieure du même format dans l'instance actuelle de Finance, les paramètres spécifiques à l'application existants ne seront pas appliqués pour la version importée.
    
    Tenez également compte que, lorsque vous sélectionnez un fichier pour importation, la structure des paramètres spécifiques à l'application de ce fichier est comparée à la structure de la source de données correspondante du type **Recherche** dans le format de gestion des états électroniques sélectionné pour importation. L'importation est effectuée lors de la structure de chaque paramètre spécifique à l'application correspond la structure de la source de données correspondante dans le format de gestion des états électroniques sélectionné pour importation. Si les structures ne correspondent pas, vous recevez un message d'avertissement informant que l'importation ne peut pas avoir lieu. Si vous forcez l'importation, les paramètres spécifiques à l'application existants pour le format de gestion des états électroniques sélectionné seront effacés et vous devrez les configurer à partir de zéro.

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>Relation entre les paramètres spécifiques à l'application et un format de gestion des états électroniques

La relation entre un format de gestion des états électroniques et ses paramètres spécifiques à l'application est établie par le code d'identification unique indépendant de l'instance du format de gestion des états électroniques. Par conséquent, lorsque vous supprimez un format de gestion des états électroniques de Finance, les paramètres spécifiques à l'application qui sont configurés pour le format de gestion des états électroniques sont conservés dans l'instance actuelle de Finance. Ils peuvent être consultés dès que le format de gestion des états électroniques de base est réimporté dans cette instance de Finance.

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>Accéder aux paramètres spécifiques à l'application en utilisant la structure de gestion des états électroniques

Dans l'exemple précédent, vous avez accédé aux paramètres spécifiques à l'application d'un format de gestion des états électroniques à l'aide de la structure de gestion des états électroniques. Cette approche ne vous permet pas limiter l'accès aux paramètres spécifiques à l'application d'un format de gestion des états électroniques spécifique. Si vous devez appliquer de telles restrictions, procédez comme suit. 

1.  Réutilisez un élément de menu **ERSolutionAppSpecificParametersDesigner** existant, ou mettez en œuvre votre propre élément de menu **ERSolutionAppSpecificParametersDesigner**.

    ![Page Visual Studio](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  Utilisez l'une des procédures suivantes :

    1.  Créez un bouton d'option de menu, et liez-le à l'enregistrement correspondant depuis la table **ERSolutionTable** en définissant sa propriété **Source de données** sur **ERSolutionTable**.
    
        ![Page Visual Studio](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  Créez un bouton unique, et remplacez la méthode **Cliqué** comme indiqué dans l'exemple suivant.
    
        Grâce à cette approche, vous pouvez spécifier un ID unique de solution (défini à l'aide de la valeur **GUID**) pour autoriser l'accès aux paramètres spécifiques à l'application d'un seul format de gestion des états électroniques spécifique et de copies racines qui en sont dérivées.
        
        ```
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a>Ressources supplémentaires

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Configurer des formats de gestion des états électroniques pour utiliser les paramètres spécifiés par entité juridique](er-app-specific-parameters-configure-format.md)
