---
title: Définir les paramètres d’un format de gestion des états électroniques par entité juridique
description: Cette rubrique explique comment vous pouvez définir les paramètres d’un format gestion des états électroniques par entité juridique.
author: NickSelin
ms.date: 10/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 0fce566bea6340b4016e559b1f5f1764a6881e28
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2021
ms.locfileid: "7675391"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>Définir les paramètres d’un format de gestion des états électroniques par entité juridique

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a>Conditions préalables

Pour effectuer cette procédure, vous devez suivre les étapes de [Configurer les formats de gestion des états électroniques pour utiliser les paramètres spécifiés par entité juridique](er-app-specific-parameters-configure-format.md).

Pour terminer les exemples de cette rubrique, vous devez avoir accès à Microsoft Dynamics 365 Finance pour l’un des rôles suivants :

- Développeur de gestion des états électroniques
- Consultant fonctionnel de gestion des états électroniques
- Administrateur système

## <a name="import-er-configurations"></a>Importer les configurations ER
Pour importer des configurations de gestion des états électroniques, procédez comme suit : 

1. Connectez-vous à votre environnement.
2. Dans le tableau de bord par défaut, sélectionnez **Gestion des états électroniques**.
3. Sélectionnez **Configurations des états**.
4. Dans l’instance actuelle de Finance, importez les configurations exportées depuis Regulatory Configuration Services (RCS) lorsque vous exécutez ces étapes dans [Configurer les formats de gestion des états électroniques pour utiliser les paramètres qui sont spécifiques par entité juridique](er-app-specific-parameters-configure-format.md). Procédez comme suit pour chaque configuration [de gestion des états électroniques](general-electronic-reporting.md) dans l’ordre suivant : modèle de données, mise en correspondance de modèle et formats.

    1. Sélectionnez **Échanger \> Charger depuis le fichier XML**.
    2. Sélectionnez **Parcourir** pour sélectionner le fichier pour la configuration de gestion des états électroniques requise au format XML.
    3. Cliquez sur **OK**.

    L’illustration suivante présente les configurations que vous devez avoir lorsque vous avez fini.

    ![Page Configurations ER.](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>Définir les paramètres pour l’entreprise DEMF

Vous pouvez utiliser la structure de gestion des états électroniques pour configurer les paramètres spécifiques à l’application pour un format de gestion des états électroniques.

1. Sélectionnez l’entité juridique **DEMF**.
2. Dans l’arborescence des configurations, sélectionnez le format **Format pour apprendre comment rechercher les données LE**.
3. Dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres spécifiques à l’application**, sélectionnez **Configurer**.

    ![Page des paramètres spécifiques à l’application d’états électroniques pour configurer les paramètres.](./media/GER-AppSpecParms-LookupForm.PNG)

    Sur la page **Paramètres spécifiques à l’application**, vous pouvez configurer les règles pour la source données **Sélecteur** du format **Format pour apprendre comment rechercher les données LE**.

    Si le format de gestion des états électroniques de base contient plusieurs sources de données de type **Recherche**, vous devez sélectionner la source de données souhaitée dans l’organisateur **Recherches** avant de commencer à configurer l’ensemble de règles pour la source de données.

    Pour chaque source de données, vous pouvez configurer des règles différentes pour chaque version du format de gestion des états électroniques sélectionné.

    L’ensemble des règles pour toutes les sources de données de recherche qui sont disponibles dans la version sélectionnée du format de gestion des états électroniques de base constitue les paramètres spécifiques à l’application pour le format de gestion des états électroniques.

4. Sélectionnez la version **1.1.1** du format de gestion des états électroniques.
5. Dans l’organisateur **Conditions**, sélectionnez **Ajouter**.
6. Dans le champ **Code** du nouvel enregistrement, sélectionnez la flèche du menu déroulant pour ouvrir la recherche.

    La recherche affiche la liste des codes taxe pour la sélection. Cette liste est renvoyée par la source de données **Model.Data.Tax** qui a été configurée dans le format de gestion des états électroniques de base. Parce que cette source de données contient le champ **Nom**, le nom de chaque code taxe s’affiche dans la recherche.

    ![Recherche de champs de code dans la page de paramètres spécifiques à l’application des états électroniques.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)

7. Sélectionnez le code taxe **VAT19**.
8. Dans le champ **Résultat de la recherche** du nouvel enregistrement, sélectionnez la flèche du menu déroulant pour ouvrir la recherche. La recherche affiche la liste des valeurs pour l’énumération de format TaxationLevel pour la sélection.

    Notez que, si vous avez sélectionné l’allemand comme langue préférée pour l’utilisateur sous lequel vous êtes connecté, les libellés des valeurs dans la recherche seront en allemand, à condition qu’ils aient été traduits au format de gestion des états électroniques de base. En outre, si le libellé d’une source de données de recherche a été traduit, ce libellé apparaîtra dans la langue préférée de l’utilisateur dans l’onglet **Recherches**.

    ![Champ de recherche traduit en allemand sur la page des paramètres spécifiques à l’application des états électroniques.](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9. Sélectionnez la valeur **Imposition normale**.

    En ajoutant cet enregistrement, vous définissez la règle suivante : lorsque la source de données de recherche **Sélecteur** est demandée, et que le code taxe **VAT19** est transmis comme argument, **Imposition normale** sera renvoyé comme le niveau d’imposition demandé.

10. Sélectionnez **Ajouter**, puis procédez comme suit :

    1. Dans le champ **Code**, sélectionnez le code taxe **InVAT19**.
    2. Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Imposition normale**.

11. Sélectionnez **Ajouter**, puis procédez comme suit :

    1. Dans le champ **Code**, sélectionnez le code taxe **VAT7**.
    2. Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Imposition réduite**.

12. Sélectionnez **Ajouter**, puis procédez comme suit :

    1. Dans le champ **Code**, sélectionnez le code taxe **InVAT7**.
    2. Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Imposition réduite**.

13. Sélectionnez **Ajouter**, puis procédez comme suit :

    1. Dans le champ **Code**, sélectionnez le code taxe **THIRD**.
    2. Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Aucune imposition**.

14. Sélectionnez **Ajouter**, puis procédez comme suit :

    1. Dans le champ **Code**, sélectionnez le code taxe **InVAT0**.
    2. Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Aucune imposition**.

15. Sélectionnez **Ajouter**, puis procédez comme suit :

    1. Dans le champ **Code**, sélectionnez l’option **\*Non vide\***.
    2. Dans le champ **Résultat de la recherche**, sélectionnez la valeur **Autre**.

    En ajoutant ce dernier enregistrement, vous définissez la règle suivante : lorsque le code taxe transmis comme argument ne répond plus aux règles précédentes, la source de données de recherche renverra **Autre** comme le niveau d’imposition demandé.

    ![Dernier enregistrement ajouté dans la page de paramètres spécifiques à l’application des états électroniques.](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)

16. Dans le champ **État**, sélectionnez **Terminé**.

    Lorsque vous exécutez une version de format de gestion des états électroniques avec un état défini sur **Terminé** ou **Partagé**, cet ensemble de règles doit être à l’état **Terminé**. Sinon, l’exécution du format de gestion des états électroniques de base est interrompue lorsque le format essaye de charger les données provenant de cet ensemble de règles tandis que la source de données de recherche **Sélecteur** est exécutée.

    Lorsque vous exécutez une version de format de gestion des états électroniques avec un état défini sur **Brouillon**, le format de gestion des états électroniques de base peut accéder à cet ensemble de règles, quel que soit son état.

17. Sélectionnez **Enregistrer**.
18. Fermez la page **Paramètres spécifiques de l’application**.

## <a name="run-the-er-format-in-the-demf-company"></a>Exécuter le format de gestion des états électroniques dans la société DEMF
Pour exécuter le format des états électroniques dans la société DEMF, procédez comme suit : 

1. Dans l’arborescence des configurations, sélectionnez le format **Format pour apprendre comment rechercher les données LE**.
2. Dans le volet Actions, sélectionnez **Exécuter**.
3. Dans la boîte de dialogue qui apparaît, sélectionnez **OK**.
4. Téléchargez le relevé qui est généré et enregistrez-le localement.

    Dans le relevé généré, notez que la synthèse du code taxe **InVAT7** est au niveau **Réduit**, et que les synthèses de codes taxe **VAT19** et **InVA19** sont au niveau **Normal**. Ce comportement est déterminé par la configuration dans l’ensemble de règles dépendant de l’entité juridique.

5. Accédez à **Taxe \> Taxes indirectes \> Taxe \> Codes taxe**.
6. Sélectionnez le code taxe **InVAT7**.
7. Dans le volet Actions, sous l’onglet **Code taxe**, au groupe **Recherches**, sélectionnez **Taxe validée** permet d’afficher des informations sur la valeur de taxe et le taux appliqué de taxe par code taxe.

    ![Page de la taxe validée.](./media/GER-AppSpecParms-Statement.PNG)

8. Fermez la page **Taxe validée**.

## <a name="set-up-parameters-for-the-usmf-company"></a>Définir les paramètres pour l’entreprise USMF
Pour configurer les paramètres de la société USMF, procédez comme suit : 

1. Sélectionnez l’entité juridique **USMF**.
2. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
3. Dans l’arborescence des configurations, développez l’article **Modèle pour apprendre les appels paramétrés**, développez l’article **Format pour apprendre les appels paramétrés**, puis sélectionnez le format **Format pour apprendre comment rechercher les données LE**.
4. Dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres spécifiques à l’application**, sélectionnez **Configurer**.
5. Sélectionnez la version **1.1.1** du format de gestion des états électroniques sélectionné.
6. Dans l’organisateur **Conditions**, sélectionnez **Ajouter**.
7. Dans le champ **Code** du nouvel enregistrement, sélectionnez la flèche du menu déroulant pour ouvrir la recherche.

    La recherche affiche désormais la liste des codes taxe pour la taxe de société **USMF** pour sélection.

    ![Codes taxe pour la taxe de société USMF.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)

8. Sélectionnez le code taxe **EXEMPT**.
9. Dans le champ **Résultat de la recherche** du nouvel enregistrement, sélectionnez la valeur **Aucune imposition**.
10. Sélectionnez **Ajouter**.
11. Dans le champ **Code** du nouvel enregistrement, sélectionnez l’option **\*Non vide\***.
12. Dans le champ **Résultat de la recherche** du nouvel enregistrement, sélectionnez la valeur **Imposition normale**.
13. Dans le champ **État**, sélectionnez **Terminé**.
14. Sélectionnez **Enregistrer**.

    ![Page Paramètres spécifiques à l’application de la gestion des états électroniques.](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)

15. Fermez la page **Paramètres spécifiques de l’application**.

## <a name="run-the-er-format-in-the-usmf-company"></a>Exécuter le format de gestion des états électroniques dans la société USMF
Pour exécuter le format des états électroniques dans la société USMF, procédez comme suit :

1. Dans l’arborescence des configurations, sélectionnez le format **Format pour apprendre comment rechercher les données LE**.
2. Dans le volet Actions, sélectionnez **Exécuter**.
3. Dans la boîte de dialogue qui apparaît, sélectionnez **OK**.
4. Téléchargez le relevé qui est généré et enregistrez-le localement.

    Dans le relevé généré, notez que vous avez désormais réutilisé le même format de gestion des états électroniques pour une autre entité juridique, mais sans faire d’ajustement au format de gestion des états électroniques.

## <a name="reuse-legal-entitydependent-parameters"></a>Réutiliser les paramètres dépendant de l’entité juridique

### <a name="duplicate-existing-parameters"></a>Dupliquer les paramètres existants

#### <a name="export-parameters"></a>Exporter les paramètres
Pour exporter les paramètres, procédez comme suit :

1. Allez dans **Administration d’organisation \> Espaces de travail \> États électroniques**.
2. Sélectionnez **Configurations des états**.
3. Dans l’arborescence des configurations, sélectionnez le format **Format pour apprendre comment rechercher les données LE**.
4. Dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres spécifiques à l’application**, sélectionnez **Configurer**.
5. Sélectionnez la version **1.1.1** du format de gestion des états électroniques.
6. Dans le volet Actions, sélectionnez **Exporter**.
7. Téléchargez le fichier qui est généré et enregistrez-le localement.

    L’ensemble configuré des paramètres spécifiques à l’application est désormais exporté comme fichier XML.

#### <a name="import-parameters"></a>Importer les paramètres
Pour importer les paramètres, procédez comme suit :

1. Sélectionnez la version **1.1.2** du format de gestion des états électroniques.
2. Dans la volet Actions, sélectionnez **Importer**.
3. Sélectionnez **Oui** pour confirmer que vous souhaitez remplacer les paramètres spécifiques à l’application existants pour cette version de format.
4. Sélectionnez **Parcourir** pour rechercher le fichier qui contient les paramètres spécifiques à l’application exportés pour la version **1.1.1**.
5. Cliquez sur **OK**.

    La version **1.1.2** du format de gestion des états électroniques a désormais les mêmes paramètres spécifiques à l’application que vous avez précédemment configurés pour la version **1.1.1**.

##### <a name="applicability-considerations"></a>Considérations relatives à l’applicabilité

Les paramètres spécifiques à l’application d’un format de gestion des états électroniques dépendent de l’entité juridique. Pour réutiliser les paramètres spécifiques à l’application qui ont été configurés pour une entité juridique dans une autre entité juridique, vous devez les exporter lorsque vous êtes connecté à la première entité juridique. Ensuite, importez-les après vous être connecté à l’autre entité juridique.

Vous pouvez également utiliser cette approche d’importation-exportation pour transférer les paramètres spécifiques à l’application associés à la gestion des états électroniques qui étaient configurés dans une instance de Finance vers une autre instance de Finance.

Si vous configurez des paramètres spécifiques à l’application pour une version d’un format de gestion des états électroniques, puis importez une version ultérieure du même format dans l’instance Finance actuelle, les paramètres spécifiques à l’application existants ne seront pas appliqués à la version importée, sauf si vous utilisez la fonctionnalité **Utiliser les paramètres spécifiques à l’application des versions précédentes de formats de rapport électronique**. Pour plus d’informations, voir la section [Réutiliser les paramètres existants](#reuse-existing-parameters) plus loin dans cette rubrique.

Lorsque vous sélectionnez un fichier pour importation, la structure des paramètres spécifiques à l’application de ce fichier est comparée à la structure des sources de données correspondantes du type **Recherche** dans le format de gestion des états électroniques sélectionné pour importation. Par défaut, l’importation est terminée uniquement si la structure de chaque paramètre spécifique à l’application correspond à la structure de la source de données correspondante dans le format de gestion des états électroniques sélectionné pour importation. Si les structures ne correspondent pas, un message d’avertissement vous informe que l’importation ne peut pas être finalisée. Si vous forcez l’importation, les paramètres spécifiques à l’application existants pour le format de gestion des états électroniques sélectionné seront effacés et vous devrez les configurer à partir de zéro.

À partir de Dynamics 365 Finance version 10.0.23, vous pouvez modifier le comportement par défaut et éviter de recevoir un message d’avertissement en activant la fonctionnalité **Aligner les paramètres spécifiques à l’application de rapports électroniques lors de l’importation** dans l’espace de travail **Gestion des fonctionnalités**. Lorsque cette fonctionnalité est activée, si la structure des paramètres spécifiques à l’application que vous importez est différente de celle des sources de données correspondantes dans le format de gestion des états électroniques sélectionné pour importation, l’importation sera effective dans les cas suivants.

- La structure du format de gestion des états électroniques cible a été modifiée par l’ajout de nouvelles colonnes de condition à toutes les sources de données existantes du type **Recherche**. Une fois l’importation terminée, les paramètres spécifiques à l’application sont mis à jour. Dans tous les enregistrements importés de paramètres spécifiques à l’application, les valeurs de chaque colonne de condition ajoutée sont initialisées avec la valeur par défaut pour le [type de données](er-formula-supported-data-types-primitive.md) de cette colonne.
- La structure du format de gestion des états électroniques cible a été modifiée par la suppression de colonnes de condition de toutes les sources de données existantes du type **Recherche**. Une fois l’importation terminée, les paramètres spécifiques à l’application sont mis à jour. Dans tous les enregistrements importés de paramètres spécifiques à l’application, les valeurs de chaque colonne de condition supprimée sont supprimées.
- La structure du format de gestion des états électroniques cible a été modifiée par l’ajout de nouvelles sources de données du type **Recherche**. Une fois l’importation terminée, les recherches ajoutées sont ajoutées aux paramètres spécifiques à l’application.
- La structure du format de gestion des états électroniques cible a été modifiée par la suppression de certaines sources de données existantes du type **Recherche**. Une fois l’importation terminée, tous les artefacts liés aux sources de données du type **Recherche** qui ont été supprimés du format de gestion des états électroniques cible sont supprimés des paramètres spécifiques à l’application importés.

Lorsque l’importation est terminée, en plus des modifications qui viennent d’être décrites, l’état des paramètres spécifiques à l’application importés est remplacé par **En cours**. Un message d’avertissement vous informe que les paramètres spécifiques à l’application ajustés automatiquement doivent être modifiés manuellement.

### <a name="reuse-existing-parameters"></a>Réutiliser les paramètres existants

À partir de Dynamics 365 Finance version 10.0.23, vous pouvez réutiliser les paramètres spécifiques à l’application qui ont été configurés pour une version d’un format de gestion des états électroniques, lorsque vous exécutez une version supérieure du même format. Pour cela, activez la fonctionnalité **Utiliser les paramètres spécifiques à l’application des versions précédentes de formats de rapport électronique** dans l’espace de travail **Gestion des fonctionnalités**. Lorsque cette fonctionnalité est activée et que vous exécutez une version d’un format de gestion des états électroniques qui essaie de lire les paramètres spécifiques à l’application, la gestion des états électroniques tentera de trouver les paramètres spécifiques à l’application qui ont été configurés pour la version en cours d’exécution de ce format. Ou, lorsqu’ils ne sont pas disponibles, pour la version antérieure la plus proche de ce format.

> [!NOTE]
> Vous ne pouvez réutiliser les paramètres spécifiques à l’application que dans le cadre de l’entité juridique actuelle.
>
> Une erreur s’affiche au moment de l’exécution lorsque vous exécutez une version ultérieure d’un format de gestion des états électroniques qui tente de réutiliser des paramètres spécifiques à l’application qui ont été configurés pour une version antérieure du même format et que la structure d’au moins une source de données du type **Recherche** dans la version de format ultérieur a changé.

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>Relation entre les paramètres spécifiques à l’application et un format de gestion des états électroniques

La relation entre un format de gestion des états électroniques et ses paramètres spécifiques à l’application est établie par le code d’identification unique indépendant de l’instance du format de gestion des états électroniques. Par conséquent, lorsque vous supprimez un format de gestion des états électroniques de Finance, les paramètres spécifiques à l’application qui sont configurés pour le format de gestion des états électroniques sont conservés dans l’instance actuelle de Finance. Ils peuvent être consultés lorsque le format de gestion des états électroniques de base est réimporté dans cette instance de Finance.

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>Accéder aux paramètres spécifiques à l’application en utilisant la structure de gestion des états électroniques

Dans l’exemple précédent, vous avez accédé aux paramètres spécifiques à l’application d’un format de gestion des états électroniques à l’aide de la structure de gestion des états électroniques. Cette approche ne vous permet pas limiter l’accès aux paramètres spécifiques à l’application d’un format de gestion des états électroniques spécifique. Si vous devez appliquer de telles restrictions, procédez comme suit. 

1. Réutilisez un élément de menu **ERSolutionAppSpecificParametersDesigner** existant, ou mettez en œuvre votre propre élément de menu **ERSolutionAppSpecificParametersDesigner**.

    ![Affichage des éléments de menu de ERSolutionAppSpecificParametersDesigner.](./media/GER-AppSpecParms-LookupForm-Access1.PNG)

2. Utilisez l’une des procédures suivantes :

    1. Créez un bouton d’option de menu, et liez-le à l’enregistrement correspondant depuis la table **ERSolutionTable** en définissant sa propriété **Source de données** sur **ERSolutionTable**.

        ![Affichage des nouveaux paramètres des éléments de menu.](./media/GER-AppSpecParms-LookupForm-Access2.PNG)

    2. Créez un bouton unique, et remplacez la méthode **Cliqué** comme indiqué dans l’exemple suivant.

        Grâce à cette approche, vous pouvez spécifier un ID unique de solution (défini à l’aide de la valeur **GUID**) pour autoriser l’accès aux paramètres spécifiques à l’application d’un seul format de gestion des états électroniques spécifique et de copies racines qui en sont dérivées.
        
        ```xpp
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

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
