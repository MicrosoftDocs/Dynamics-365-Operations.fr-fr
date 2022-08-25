---
title: Configurer des formats de gestion des états électroniques pour utiliser les paramètres spécifiés par entité juridique
description: Cet article explique comment vous pouvez configurer des formats de gestion des états électroniques pour utiliser les paramètres propres à une entité juridique.
author: kfend
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.custom: ''
ms.assetid: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
ms.openlocfilehash: b81c9c8fd1639b9af53c8e15a041c00db8c19752
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292674"
---
# <a name="configure-er-formats-to-use-parameters-that-are-specified-per-legal-entity"></a>Configurer des formats de gestion des états électroniques pour utiliser les paramètres spécifiés par entité juridique

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Vue d’ensemble

Dans de nombreux formats de gestion de données électroniques que vous concevrez, vous devez filtrer les données à l’aide d’un ensemble de valeurs propres à chaque entité juridique de votre instance (par exemple, un ensemble de codes taxe pour filtrer les transactions de taxe). Actuellement, lorsque le filtrage de ce type est configuré dans un format de gestion des états électroniques, les valeurs qui dépendent de l’entité juridique (par exemple, les codes taxe) sont utilisées dans des expressions du format de gestion des états électroniques pour préciser les règles de filtrage des données. Par conséquent, le format de gestion des états électroniques est rendu spécifique à une entité juridique, et pour générer les états requis, vous devez créer des copies dérivées du format d’origine de gestion des états électroniques pour chaque entité juridique dans laquelle vous devez exécuter le format de gestion des états électroniques. Chaque format de gestion des états électroniques (ER) dérivé doit être modifié pour y insérer des valeurs propres à l’entité juridique, rebasé lorsque la version d’origine (de base) a été mise à jour, exporté d’un environnement de test, puis importé dans un environnement de production lorsqu’il doit être déployé pour un usage en production, etc. Par conséquent, la maintenance de ce type de solution de gestion des états électroniques configurée est complexe et chronophage pour plusieurs raisons :

-   Plus il y a d’entités juridiques, plus il y a de mises à jour des configurations de format de gestion des états électroniques à faire.
-   La mise à jour des configurations de gestion des états électroniques exige des utilisateurs professionnels des connaissances en matière de gestion des états électroniques.

La fonctionnalité des paramètres propres à l’application de gestion des états électroniques permet aux utilisateurs avancés de configurer le filtrage des données dans un format de gestion des états électroniques de telle sorte qu’il soit basé sur un ensemble de règles non valides. Cet ensemble de règles peut être configuré pour utiliser les sources de données disponibles dans un format de gestion des états électroniques. Les utilisateurs professionnels peuvent spécifier de règles réelles au delà de la structure de gestion des états électroniques à l’aide de l’interface utilisateur qui est automatiquement générée selon les paramètres du format de gestion des états électroniques correspondant et les données actuelles de l’entité juridique qui seront accessibles par les sources de données du format de gestion des états électroniques. L’ensemble de règles qui est spécifié pour un format de gestion des états électroniques peut être exporté depuis l’entité juridique actuelle de l’instance de Dynamics 365 Finance (Finance). Il peut être ensuite importé dans une autre entité juridique de la même instance de Finance ou d’une autre instance en tant qu’ensemble de règles pour le même format de gestion des états électroniques.

## <a name="prerequisites"></a>Conditions préalables

Pour exécuter les exemples de cet article, vous devez avoir accès à l’instance de Regulatory Configuration Services (RCS) qui a été mise en service pour le même locataire que Finance and Operations, pour un des rôles suivants :

- Développeur d’états électroniques
- Consultant fonctionnel des états électroniques
- Administrateur système

Nous vous recommandons d’effectuer les étapes de l’article [Prendre en charge les appels paramétrés des sources de données des états électroniques de type de CHAMP CALCULÉ](er-calculated-field-type.md). Si vous avez déjà procédé comme suit, vous pouvez ignorer les étapes suivantes de la section **Importer les configurations de gestion des états électroniques dans RCS**.

## <a name="import-er-configurations-into-rcs"></a>Importer les configurations de gestion des états électroniques dans RCS

Téléchargez et stockez localement les configurations ER suivantes.

| **Description du contenu**                        | **Nom de fichier**                                        |
|------------------------------------------------|------------------------------------------------------|
| Exemple de fichier de configuration **Modèle de données de gestion des états électroniques**    | [Model to learn parameterized calls.version.1.xml](https://download.microsoft.com/download/2/d/b/2db913a0-3622-494e-91a2-97fc494af9b9/Modeltolearnparameterizedcalls.version.1.xml)     |
| Exemple de fichier de configuration **Métadonnées de gestion des états électroniques**      | [Metadata to learn parameterized calls.version.1.xml](https://download.microsoft.com/download/1/b/3/1b343968-5a47-4000-b5a8-6487698ef4c0/Metadatatolearnparameterizedcalls.version.1.xml)  |
| Exemple de fichier de configuration **Mise en correspondance de modèle de gestion des états électroniques** | [Mapping to learn parameterized calls.version.1.1.xml](https://download.microsoft.com/download/8/6/6/866e0ab6-2e05-4d98-9d52-d2da2038f6e4/Mappingtolearnparameterizedcalls.version.1.1.xml) |
| Exemple de configuration **Format de gestion des états électroniques**             | [Format to learn parameterized calls.version.1.1.xml](https://download.microsoft.com/download/e/3/9/e392eadc-b9b4-4834-95c3-b8066dd00b9c/Formattolearnparameterizedcalls.version.1.1.xml)  |

Ensuite, connectez-vous à votre instance RCS.

Dans cet exemple, vous créerez une configuration pour la société fictive, Litware, Inc. Avant de pouvoir réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure de l’article [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md) dans RCS.

1.  Dans le tableau de bord par défaut, sélectionnez **Gestion des états électroniques**.
2.  Sélectionnez **Configurations des états**.
3.  Importez les configurations de gestion des états électroniques téléchargées précédemment dans RCS, dans l’ordre suivant : modèle de données, métadonnées, mise en correspondance des modèles et format. Pour chaque configuration de gestion des états électroniques, procédez comme suit :

    1.  Sélectionnez **Exchange**.
    2.  Sélectionnez **Charger depuis le fichier XML**.
    3.  Sélectionnez **Parcourir** pour sélectionner le fichier pour la configuration de gestion des états électroniques requise au format XML.
    4.  Cliquez sur **OK**.

## <a name="review-the-er-solution-that-is-provided"></a>Examen de la solution de gestion des états électroniques fournie

1.  Dans l’arborescence de configuration, développez les contenus de l’article **Modèle pour apprendre les appels paramétrés**.
2.  Sélectionnez l’article **Format pour apprendre les appels paramétrés**.
3.  Sélectionnez **Concepteur**.
4.  Sélectionnez **Développer/Réduire**.

    Le format de gestion des états électroniques **Format pour apprendre les appels paramétrés** est conçu pour générer une déclaration de taxe au format XML qui présente plusieurs niveaux d’imposition (normale, réduite et aucune). Chaque niveau se distingue par un nombre différent de détails.

    ![Plusieurs niveaux de format ER, Format pour l’apprentissage des appels paramétrés.](./media/RCS-AppSpecParms-ReviewFormat.PNG)

5.  Dans l’onglet **Mise en correspondance**, développez **Modèle**, **Données**, et les éléments **Synthèse**.

    La source de données **Model.Data.Summary** renvoie la liste des transactions de taxe. Ces transactions sont répertoriées par code taxe. Pour cette source de données, le champ calculé **Model.Data.Summary.Level** a été configuré pour renvoyer le code pour le niveau d’imposition de chaque enregistrement résumé. Pour tout code taxe qui peut être récupéré depuis la source de données **Model.Data.Summary** au moment de l’exécution, le champ calculé renvoie le code du niveau d’imposition (**Normale**, **Réduite**, **Aucune** ou **Autre**) comme valeur de texte. Le champ calculé **Model.Data.Summary.Level** permet de filtrer les enregistrements de la source de données **Model.Data.Summary** et de saisir les données filtrées dans chaque élément XML qui représente un niveau d’imposition à l’aide des champs **Model.Data2.Level1**, **Model.Data2.Level2** et **Model.Data2.Level3**.

    ![La liste des transactions de taxe de la source de données Model.Data.Summary.](./media/RCS-AppSpecParms-ReviewFormat-Data2Fld.PNG)

    Le champ calculé **Model.Data.Summary.Level** a été configuré de manière à ce que il contienne une expression de gestion des états électroniques. Les codes taxe (**VAT19**, **InVAT19**, **VAT7**, **InVAT7**, **THIRD** et **InVAT0**) sont codés en dur dans cette configuration. Par conséquent, ce format de gestion des états électroniques dépend de l’entité juridique où ces codes taxe ont été configurés.

    ![Le champ calculé Model.Data.Summary.Level avec des codes taxe codés en dur.](./media/RCS-AppSpecParms-ReviewFormat-LevelFld.PNG)

    Pour prendre en charge un ensemble de différents codes taxe pour chaque entité juridique, procédez comme suit :

    - Créez une version dérivée du format de gestion des états électroniques pour chaque entité juridique.
    - Mettez les codes taxe à jour dans le champ calculé **Model.Data.Summary.Level**, selon le paramètre d’entité juridique.

6.  Fermez la page **Concepteur de format**.

## <a name="create-a-derived-format"></a>Créer un format dérivé

Ensuite, vous utiliserez les paramètres spécifiques à l’application de gestion des états électroniques pour prendre en charge un ensemble différent de codes taxe pour chaque entité juridique dans un format de gestion des états électroniques simple.

1.  Dans l’arborescence de configuration, développez les contenus de l’article **Modèle pour apprendre les appels paramétrés**.
2.  Sélectionnez l’article **Format pour apprendre les appels paramétrés**.
3.  Sélectionnez **Créer une configuration**.
4.  Sélectionnez l’option **Provenant du nom : Format pour apprendre les appels paramétrés, Microsoft**.
5.  Dans le champ **Nom**, entrez **Format pour apprendre comment rechercher les données LE**.
6.  Sélectionnez **Créer une configuration**.

## <a name="configure-a-derived-format"></a>Configurer un format dérivé

### <a name="add-a-format-enumeration"></a>Ajouter une énumération de format

Ensuite, vous ajoutez une nouvelle énumération de format de gestion des états électroniques. Les valeurs de cette énumération de format seront présentées aux utilisateurs professionnels, qui spécifieront les ensembles de codes taxe dépendant de l’entité juridique pour les différents niveaux d’imposition utilisés dans le format de gestion des états électroniques.

1.  Sélectionnez **Concepteur**.
2.  Sélectionnez **Énumérations de format**.
3.  Sélectionnez **Ajouter**.
4.  Dans le champ **Nom**, entrez **Liste des niveaux d’imposition**.
5.  Sélectionnez **Enregistrer**.
6.  Dans l’onglet **Formater les valeurs d’énumération**, sélectionnez **Ajouter**.
7.  Dans le champ **Nom**, entrez **Imposition normale**.
8.  Sélectionnez à nouveau **Ajouter**.
9.  Dans le champ **Nom**, entrez **Imposition réduite**.
10. Sélectionnez à nouveau **Ajouter**.
11. Dans le champ **Nom**, entrez **Aucune imposition**.
12. Sélectionnez à nouveau **Ajouter**.
13. Dans le champ **Nom**, entrez **Autre**.

    ![Nouvel enregistrement sur la page Énumérations de format.](./media/RCS-AppSpecParms-ConfigureFormat-Enum.PNG)

    Comme les utilisateurs professionnels peuvent utiliser différentes langues pour spécifier les ensembles de codes taxe dépendant de l’entité juridique, nous vous recommandons de traduire les valeurs de cette énumération dans les langues qui sont configurées comme langues préférées pour ces utilisateurs de Finance.

14. Sélectionnez l’enregistrement **Aucune imposition**.
15. Cliquez sur le champ **Libellé**.
16. Sélectionnez **Traduire**.
17. Dans le volet **Traduction de texte**, dans le champ **ID de libellé**, saisissez **LBL_LEVELENUM_NO**.
18. Dans le champ **Texte de la langue par défaut**, entrez **Aucune imposition**.
19. Dans le champ **Langue**, sélectionnez **DE**.
20. Entrez le texte dans le champ **Texte traduit**, saisissez **keine Besteuerung**.
21. Sélectionnez **Traduire**.

    ![Menu coulissant de traduction de texte.](./media/RCS-AppSpecParms-ConfigureFormat-EnumTranslate.PNG)

22. Sélectionnez **Enregistrer**.
23. Fermez la page **Énumérations de format**.

### <a name="add-a-new-lookup-data-source"></a>Ajouter une nouvelle source de données de recherche

Ensuite, vous ajouterez une nouvelle source de données pour préciser comment les utilisateurs professionnels préciseront des règles selon l’entité juridique pour reconnaître le niveau d’imposition approprié pour chaque enregistrement de transaction résumé.

1.  Dans l’onglet **Mise en correspondance**, sélectionnez **Ajouter**.
2.  Sélectionnez **Énumération de format\Rechercher**.

    Vous venez d’identifier que chaque règle que les utilisateurs professionnels spécifient pour la reconnaissance du niveau d’imposition renverra une valeur d’énumération au format de gestion des états électroniques. Notez que le type de source de données **Recherche** est accessible sous **Modèle de données** ainsi que sous les blocs **Dynamics 365 for Operations**, en plus du bloc **Énumération de format**. Par conséquent, les énumérations de modèle de données de gestion des états électroniques et les énumérations d’application peuvent être utilisées pour spécifier le type de valeurs renvoyées pour les sources de données de ce type. Pour en savoir plus sur la source de données de **Recherche**, voir [Configurer les sources de données de Recherche pour utiliser les paramètres spécifiques à la fonction de gestion des états électroniques](er-lookup-data-sources.md).
    
3.  Dans le champ **Nom**, entrez **Sélecteur**.
4.  Dans le champ **Énumération de format**, sélectionnez **Liste des niveaux d’imposition**.

    Vous avez spécifié que, pour chaque règle qui est spécifiée dans cette source de données, un utilisateur professionnel doit sélectionner une des valeurs de l’énumération de format **Liste des niveaux d’imposition** comme une valeur retournée.
    
5.  Sélectionnez **Modifier la recherche**.
6.  Sélectionnez **Colonnes**.
7.  Développez l’article **Modèle**.
8.  Développez l’article **Données**.
9.  Développez l’article **Taxe**.
10. Sélectionnez l’article **Model.Data.Tax.Code**.
11. Sélectionnez le bouton **Ajouter** (la flèche droite).

    ![Menu coulissant de colonnes.](./media/RCS-AppSpecParms-ConfigureFormat-Lookup1.PNG)

    Vous venez de spécifier que, pour chaque règle qui est spécifiée dans cette source de données pour identifier le niveau d’imposition, un utilisateur professionnel doit sélectionner une des valeurs de l’énumération de format comme condition. La liste des codes taxe que l’utilisateur professionnel peut sélectionner sera renvoyée par la source de données **Model.Data.Tax**. Parce que cette source de données contient le champ **Nom**, le nom du code taxe est affiché pour chaque valeur de code taxe dans la recherche qui est présentée à l’utilisateur professionnel.
    
12. Cliquez sur **OK**.

    ![Page du concepteur de recherche.](./media/RCS-AppSpecParms-ConfigureFormat-Lookup2.PNG)

    Les utilisateurs professionnels peuvent ajouter plusieurs règles en tant qu’enregistrements de cette source de données. Chaque enregistrement sera calculé par un code de ligne. Les règles seront évaluées afin d’augmenter le numéro de ligne.

    Comme vous avez sélectionné le champ **Code taxe** comme condition pour les règles de cette source de données de recherche, et parce que le champ **Code taxe** est paramétré comme champ de type de données **Chaîne**, chaque règle sera évaluée au moment de l’exécution en comparant le code taxe transmis à la source de données au code taxe défini dans cet enregistrement de la source de données.

    Lorsqu’une règle qui répond à la condition configurée est détectée, cette source de données renvoie la valeur de recherche de la règle définie dans le champ **Résultat de la recherche**. Si aucune règle n’est détectée, une exception est levée pour informer l’utilisateur que la source de données actuelle ne peut pas renvoyer une valeur appropriée.

13. Sélectionnez **Enregistrer**.
14. Fermez la page **Concepteur de recherche**.
15. Cliquez sur **OK**.

    Notez que vous avez ajouté une nouvelle source de données qui renvoie le niveau d’imposition comme valeur de l’énumération de format **Liste des niveaux d’imposition** pour tout code taxe transmis à la source de données comme argument du paramètre **Code** du type de données **Chaîne**.
    
    ![Page du concepteur de format avec une nouvelle source de données.](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld.PNG)

    L’évaluation des règles configurées dépend du type de données des champs sélectionnés pour définir les conditions de ces règles. Lorsque vous sélectionnez un champ qui est configuré comme un champ de type **Numérique** ou **Date**, les critères différeront des critères qui ont été décrits plus tôt pour le type de données **Chaîne**. Pour les champs **Numérique** et **Date**, la règle doit être spécifiée comme plage de valeurs. La condition de la règle sera alors considérée remplie lorsqu’une valeur transmise à la source de données est comprise dans la plage de configuration.
    
    L’illustration suivante montre un exemple de ce type de configuration. Outre le champ **Model.Data.Tax.Code** du type de données **Chaîne**, le champ **Model.Tax.Summary.Base** du type de données **Réel** permet de spécifier des conditions pour une source de données de recherche.
    
    ![Page du concepteur de recherche avec des colonnes supplémentaires.](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld2.PNG)

    Parce que les champs **Model.Data.Tax.Code** et **Model.Tax.Summary.Base** sont sélectionnés pour cette source de données de recherche, chaque règle de cette source de données est configurée de la façon suivante :
    
    -   Dans la liste qui s’affiche, la valeur de l’énumération de format **Liste des niveaux d’imposition** doit être sélectionnée comme valeur renvoyée.
    -   Un code taxe doit être entré comme condition de cette règle. Seuls les codes taxe indiqués par la source de données **Model.Data.Tax** s’appliquent.
    -   Les valeurs minimale et maximale du montant de base de taxe doivent être entrées comme des conditions de cette règle.

    Voici la manière dont chaque règle de cette source de données est évaluée au moment de l’exécution :
    -   Le code du type de données **Chaîne** qui a été transmis à cette source de données est-il égal au code taxe d’une règle ?
    -   La valeur du type de données **Réel** transmise à cette source de données tombe-t-elle dans la plage de valeurs minimale et maximale spécifiques ?

    Une règle sera considérée comme applicable lorsque les deux conditions seront satisfaites.

### <a name="translate-the-label-of-the-lookup-data-source-that-was-added"></a>Traduire le libellé de la source de données de recherche qui a été ajouté

Comme les utilisateurs professionnels peuvent utiliser différentes langues pour spécifier les ensembles de codes taxe dépendant de l’entité juridique, nous vous recommandons de traduire le libellé de toute source de données de recherche que vous ajoutez, de telle sorte qu’il soit présenté dans chaque langue préférée de l’utilisateur sur la page correspondante.

1.  Sélectionnez la source de données **Model.Data.Selector**.
2.  Sélectionnez **Modifier**.
3.  Cliquez sur le champ **Libellé**.
4.  Sélectionnez **Traduire**.
5.  Dans le volet **Traduction de texte**, dans le champ **ID de libellé**, saisissez **LBL_SELECTOR_DS**.
6.  Dans le champ **Texte de la langue par défaut**, entrez **Sélectionner le niveau d’imposition par code taxe**.
7.  Dans le champ **Langue**, sélectionnez **DE**.
8.  Dans le champ **Texte traduit**, entrez **Steuerebene für Steuerkennzeichen auswählen**.
9.  Sélectionnez **Traduire**.
10. Cliquez sur **OK**.

    ![Menu coulissant de propriétés de la source de données.](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFldTranslate.PNG)

### <a name="add-a-new-field-to-consume-the-configured-lookup"></a>Ajouter un nouveau champ pour utiliser la recherche configurée

1.  Développez l’article **Modèle.Data**.
2.  Sélectionnez l’article **Model.Data.Summary**.
3.  Sélectionnez **Ajouter**.
4.  Sélectionnez **Fonctions/Champ calculé**.
5.  Dans le champ **Nom**, entrez **LevelByLookup**.
6.  Sélectionnez **Modifier la formule**.
7.  Dans le **champ Formule**, entrez **Model.Selector(Model.Data.Summary.Code)**.
8.  Sélectionnez **Enregistrer**.

    ![Ajout de Model.Selector (Model.Data.Summary.Code) à la page Concepteur de formule.](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld.PNG)

9.  Fermez la page **Éditeur de formule**.
10. Cliquez sur **OK**.

    ![Page du concepteur de format avec une nouvelle formule ajoutée.](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld2.PNG)

    Notez que le champ calculé **LevelByLookup** que vous avez ajouté renverra le niveau d’imposition comme valeur de l’énumération de format **Liste des niveaux d’imposition** pour chaque enregistrement résumé des transactions de taxe. Le code taxe de l’enregistrement sera transmis à la source de données de recherche **Model.Selector**, ainsi que l’ensemble de règles pour cette source de données sera utilisé pour sélectionner le niveau d’imposition approprié.

### <a name="add-a-new-format-enumeration-based-data-source"></a>Ajouter une nouvelle source de données basée sur l’énumération de format

Ensuite, vous ajouterez une nouvelle source de données qui fait référence à l’énumération de format que vous avez entrée précédemment. Les valeurs de cette source de données seront utilisées dans une expression de format de gestion des états électroniques ultérieurement.

1.  Sélectionnez **Ajoutez racine**.
2.  Sélectionnez **Énumérations de format\Énumération**.
3.  Dans le champ **Nom**, entrez **TaxationLevel**.
4.  Dans le champ **Énumération de format**, sélectionnez **Liste des niveaux d’imposition**.
5.  Sélectionnez **Enregistrer**.

### <a name="modify-an-existing-field-to-start-to-use-the-lookup"></a>Modifier un champ existant pour commencer à utiliser la recherche

Ensuite, vous modifierez le champ calculé existant afin qu’il utilise la source de données de recherche configurée pour qu’elle renvoie la bonne valeur de niveau d’imposition, selon le code taxe.

1.  Sélectionnez l’article **Model.Data.Summary.Level**.
2.  Sélectionnez **Modifier**.
3.  Sélectionnez **Modifier la formule**.

    Notez que l’expression actuelle du champ **Model.Data.Summary.Level** inclut les codes taxe codés en dur suivants :
    
    CASE (@.Code, "VAT19", "Regular", "InVAT19", "Regular", "VAT7", "Reduced", "InVAT7", "Reduced", "THIRD", "None", "InVAT0", "None", "Other")

4.  Dans le champ **Formule**, saisissez **CASE(@.LevelByLookup, TaxationLevel.’Regular taxation’, "Regular", TaxationLevel.’Reduced taxation’, "Reduced", TaxationLevel.’No taxation’, "None", "Other")**.

    ![Page Concepteur d’opération de gestion des états électroniques.](./media/RCS-AppSpecParms-ConfigureFormat-ChangeLookupFld.PNG)
    
    Notez que l’expression du champ **Model.Data.Summary.Level** renvoie à présent le niveau d’imposition, selon le code taxe de l’enregistrement actuel et l’ensemble des règles que l’utilisateur professionnel configure dans la source de données de recherche **Model.Data.Selector**.
    
5.  Sélectionnez **Enregistrer**.
6.  Fermez la page **Concepteur de formule**.
7.  Cliquez sur **OK**.
8.  Sélectionnez **Enregistrer**.
9.  Fermez la page **Concepteur de formats**.

## <a name="complete-the-draft-version-of-a-derived-format"></a>Terminer la version brouillon d’un format dérivé

1.  Dans le raccourci **Versions**, sélectionnez **Modifier le statut**.
2.  Sélectionnez **Terminer**.
3.  Cliquez sur **OK**.

## <a name="export-completed-version-of-modified-format"></a>Exporter la version terminée d’un format modifié

1.  Dans l’arborescence des configurations, sélectionnez l’élément **Format pour apprendre comment rechercher les données LE**.
2.  Dans le raccourci **Versions**, sélectionnez l’enregistrement ayant un statut **Terminé**.
3.  Sélectionnez **Exchange**.
4.  Sélectionnez **Exporter en tant que fichier XML**.
5.  Cliquez sur **OK**.
6.  Le navigateur Web télécharge un fichier **Format pour apprendre comment rechercher le fichier LE data.xml**. Enregistrez ce fichier localement.

Répétez les étapes de cette section pour les articles parents du format **Format pour apprendre comment rechercher les données LE**, et enregistrez les fichiers suivants localement :

-   Format pour apprendre les appels paramétrés.xml
-   Mise en correspondance pour apprendre les appels paramétrés.xml
-   Modèle pour apprendre les appels paramétrés.xml

Pour savoir comment utiliser le format de gestion des états électroniques **Format pour apprendre comment rechercher les données LE** configuré pour paramétrer les ensembles de codes taxe selon l’entité juridique pour filtrer les transactions en fonction des différents niveaux d’imposition, procédez comme suit dans l’article [Configurer les paramètres d’un format de gestion des états électroniques par entité juridique](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)

[Définir les paramètres d’un format de gestion des états électroniques par entité juridique](er-app-specific-parameters-set-up.md)

[Configurer les sources de données de Recherche pour utiliser les paramètres spécifiques à la fonction de gestion des états électroniques](er-lookup-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
