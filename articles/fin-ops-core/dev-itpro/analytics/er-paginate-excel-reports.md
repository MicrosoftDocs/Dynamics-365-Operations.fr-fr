---
title: Concevoir un format de gestion des états électroniques (ER) pour paginer les documents générés dans Excel
description: Cet article explique comment concevoir un document volumineux généré par un format de gestion des états électroniques (ER) dans Microsoft Excel.
author: kfend
ms.date: 09/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: Version 10.0.22
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.form: EROperationDesigner
ms.openlocfilehash: e4a34dffda9e9b95f5d6c7ee382723663817ec6b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284999"
---
# <a name="design-an-er-format-to-paginate-generated-documents-in-excel"></a>Concevoir un format de gestion des états électroniques (ER) pour paginer les documents générés dans Excel

[!include [banner](../includes/banner.md)]

Cet article explique comment un utilisateur ayant le rôle d’administrateur système ou de consultant fonctionnel des états électroniques peut configurer un format [de gestion des états électroniques (ER)](general-electronic-reporting.md) pour générer des documents sortants dans Microsoft Excel et gérer la pagination des documents.

Dans cet exemple, vous allez modifier le format de gestion des états électroniques (ER) fourni par Microsoft qui est utilisé pour imprimer l’état de contrôle lorsque la déclaration des échanges de biens est [générée](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md). Cet état vous permet d’observer les transactions d’échanges de biens déclarées. Vos modifications vous permettront de gérer la pagination des états de contrôle générés.

Les procédures de cet article peuvent être effectuées dans la compagnie **DEMF**. Aucun codage n’est requis. Avant de commencer, téléchargez et enregistrez les fichiers suivants.

| Description       | Nom de fichier |
|-------------------|-----------| 
| Modèle d’état 1 | [ERIntrastatReportDemo1.xlsx](https://download.microsoft.com/download/7/2/a/72ae292a-8bb2-4b9d-8397-9764218f6fa8/ERIntrastatReportDemo1%20.xlsx) |
| Modèle d’état 2 | [ERIntrastatReportDemo2.xlsx](https://download.microsoft.com/download/7/d/1/7d15858d-6260-4afa-9dda-d8b955e59b1a/ERIntrastatReportDemo2.xlsx) |

## <a name="configure-the-er-framework"></a>Configurer la structure de gestion des états électroniques

Procédez comme suit dans [Configurer la structure des états électroniques](er-quick-start2-customize-report.md#ConfigureFramework) pour configurer l’ensemble minimum de paramètres d’état électronique. Vous devez terminer cette configuration avant de commencer à utiliser la structure des états électroniques pour concevoir une version personnalisée d’un format de gestion des états électroniques standard.

## <a name="import-the-standard-er-format-configuration"></a>Importer la configuration du format de gestion des états électroniques standard

Suivez les étapes de l’action [Importer la configuration du format de gestion des états électroniques standard](er-quick-start2-customize-report.md#ImportERSolution1) pour ajouter les configurations des états électroniques standard à votre instance actuelle de Dynamics 365 Finance. Importer la version **1.9** de la configuration du format **de la déclaration d’échanges de biens**. La version de base 1 de la configuration **Modèle d’échanges de biens** de base est automatiquement importée du référentiel.

## <a name="customize-the-standard-er-format"></a>Personnaliser le format de gestion des états électroniques standard

### <a name="create-the-custom-er-format"></a>Créer le format de gestion des états électroniques personnalisé

Dans ce scénario, vous êtes le représentant de Litware, Inc., qui est actuellement sélectionné comme fournisseur de configuration des états électroniques actif. Vous devez créer une nouvelle configuration de format de gestion des états électroniques en utilisant la configuration **Déclaration des échanges de biens** comme base.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle d’échanges de biens**, puis sélectionnez **Déclaration d’échanges de biens**. Litware, Inc. utilisera la version 1.9 de cette configuration du format de gestion des états électroniques comme base pour la version personnalisée.
3. Sélectionnez **Créer une configuration** pour ouvrir la boîte de dialogue déroulante. Vous pouvez utiliser cette boîte de dialogue pour créer une configuration pour un format de paiement personnalisé.
4. Dans le groupe de champs **Nouveau**, sélectionnez l’option **Provenant du nom : déclaration des échanges de biens, Microsoft**.
5. Dans le champ **Nom**, entrez **État de déclaration d’échanges de biens Litware**.
6. Sélectionnez **Créer une configuration** pour créer le format.

La version 1.9.1 de la configuration du format de gestion des états électroniques **État de déclaration d’échanges de biens Litware** est créée. Cette version présente le statut **Brouillon** et peut être modifiée. Le contenu actuel de votre format de gestion des états électroniques personnalisé correspond au contenu du format fourni par Microsoft.

### <a name="make-the-custom-format-runnable"></a>Rendre le format personnalisé exécutable

Maintenant que la première version de votre format personnalisé a été créée et présente le statut **Brouillon**, vous pouvez l’exécuter à des fins de test. Pour exécuter l’état, traitez un paiement fournisseur en utilisant le mode de paiement qui fait référence à votre format de gestion des états électroniques personnalisé. Par défaut, lorsque vous appelez un format de gestion des états électroniques depuis l’application, seules les versions qui ont le statut **Terminé** ou **Partagé** sont prises en compte. Ce comportement permet de ne pas utiliser les formats de gestion des états électroniques dont les conceptions sont inachevées. Cependant, pour vos exécutions de test, vous pouvez forcer l’application à utiliser la version de votre format de gestion des états électroniques dont le statut est **Brouillon**. De cette façon, vous pouvez ajuster la version actuelle du format si des modifications sont nécessaires. Pour plus d’informations, voir [Applicabilité](electronic-reporting-destinations.md#applicability).

Pour utiliser la version provisoire d’un format de gestion des états électroniques, vous devez explicitement marquer le format de gestion des états électroniques.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Dans la boîte de dialogue **Paramètres utilisateur**, définissez l’option **Paramètres d’exécution** sur **Oui**, puis cliquez sur **OK**.
4. Sélectionnez **Modifier** pour rendre la page active modifiable, selon les besoins.
5. Dans l’arborescence de configuration du volet gauche, sélectionnez **État de déclaration d’échanges de biens Litware**.
6. Définissez l’option **Exécuter le brouillon** sur **Oui**, puis sélectionnez **Enregistrer**.

    ![Option Exécuter le brouillon de la page Configurations.](./media/er-paginate-excel-reports-derived-format-configuration.png)

## <a name="set-up-foreign-trade-parameters-to-use-the-custom-er-format"></a>Configurer les paramètres du commerce extérieur pour utiliser le format de gestion des états électroniques personnalisé

Suivez ces étapes pour configurer les paramètres du commerce extérieur afin que vous puissiez utiliser le format personnalisé.

1. Accédez à **Taxe** \> **Paramétrage** \> **Commerce extérieur** \> **Paramètres de commerce extérieur**.
2. Sur la page **Paramètres de commerce extérieur**, dans le raccourci **Gestion des états électroniques**, dans le champ **Mappage de format de fichier**, sélectionnez **État de déclaration d’échanges de biens Litware**.
3. Dans le champ **Mappage de format d’état**, sélectionnez **État de déclaration d’échanges de biens Litware**.
4. Sélectionnez **Enregistrer**.

## <a name="configure-the-custom-format-to-use-the-downloaded-report-template"></a>Configurer le format personnalisé pour utiliser le modèle d’état téléchargé

### <a name="review-the-first-downloaded-excel-template"></a>Passer en revue le premier modèle Excel téléchargé

1. Dans l’application de bureau Excel, ouvrez le fichier de modèle **ERIntrastatReportDemo1.docx** que vous avez téléchargé précédemment.
2. Veillez à ce que le modèle contienne des plages désignées afin de créer des sections d’en-tête d’état, de détails d’état et de pied de page d’état dans les documents générés.

    ![Disposition du modèle Excel 1 dans l’application de bureau.](./media/er-paginate-excel-reports-template1.gif)

### <a name="replace-the-current-excel-template-in-the-custom-er-format"></a><a id="replace-template"></a>Remplacer le modèle Excel actuel au format de gestion des états électroniques personnalisé

Vous devez ajouter un nouveau modèle Excel au format de gestion des états électroniques personnalisé.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle d’échanges de biens** \> **État de déclaration d’échanges de biens** et sélectionnez la configuration **État de déclaration d’échanges de biens Litware**.
3. Sélectionnez **Concepteur**.
4. Sur la page **Concepteur de formats**, sur le volet Actions, sélectionnez **Afficher les détails**.
5. Veillez à ce que le composant du format racine **Déclaration d’échanges de biens : Excel** soit sélectionné, puis, dans le volet Actions, sur l’onglet **Importer**, dans le groupe **Importer**, sélectionnez **Mettre à jour à partir d’Excel**.
6. Dans la boîte de dialogue **Mettre à jour à partir d’Excel**, sélectionnez **Mettre à jour le modèle**.
7. Dans la boîte de dialogue **Ouvrir**, accédez au fichier **ERIntrastatReportDemo1.xlsx** que vous avez téléchargé précédemment et sélectionnez-le, puis sélectionnez **Ouvrir**.
8. Cliquez sur **OK**.
9. Sélectionnez **Enregistrer**.

![Structure de format dans le concepteur de formats de gestion des états électroniques une fois le nouveau modèle Excel ajouté.](./media/er-paginate-excel-reports-format1.png)

## <a name="change-the-data-binding-to-show-the-item-description-on-a-generated-report"></a>Modifier la liaison de données pour afficher la description de l’article sur un état généré

1. Dans la page **Concepteur de formats**, sélectionnez l’onglet **Mise en correspondance**.
2. Développez **Déclaration d’échanges de biens** \> **Lignes d’état**, et sélectionnez le composant **Code marchandise**.
3. Sélectionnez **Modifier la formule**.
4. Changez la formule de liaison de `@.CommodityCode` vers `CONCATENATE(@.CommodityCode, " ", @.ProductName)`.
5. Sélectionnez **Enregistrer**.

![Liaison configurée pour afficher la description de l’élément dans le concepteur de formats de gestion des états électroniques.](./media/er-paginate-excel-reports-format1a.png)

## <a name="generate-an-intrastat-declaration-control-report"></a><a id="generate-intrastat-control-report"></a>Générer un fichier d’état de contrôle de déclaration d’échanges de biens

Tout d’abord, assurez-vous que vous disposez des transactions de déclaration d’échanges de biens pour la génération d’états sur la page **Déclaration d’échanges de biens**.

![Transactions sur la page de déclaration d’échanges de biens.](./media/er-paginate-excel-reports-transactions1.gif)

Utilisez ensuite le format de gestion des états électroniques (ER) personnalisé pour générer l’état de contrôle de la déclaration d’échanges de biens.

1. Accédez à **Taxes** \> **Déclarations** \> **Commerce extérieur** \> **Déclaration d’échanges de biens**.
2. Sur la page **Déclaration d’échanges de biens**, dans le volet Actions, sélectionnez **Sortie** \> **État**.
3. Dans la boîte de dialogue **État de déclaration d’échanges de biens**, procédez comme suit pour exécuter l’état :

    1. Définissez les champs **Date de début** et **Date de fin** pour inclure les transactions de la déclaration d’échanges de biens dans l’état.
    2. Définissez l’option **Générer un fichier** sur **Non**.
    3. Définissez l’option **Générer un état** sur **Oui**.
    4. Cliquez sur **OK**.

4. Téléchargez et enregistrez le document généré.
5. Ouvrez le document dans Excel, puis passez-le en revue.

    ![Document Excel généré dans l’application de bureau.](./media/er-paginate-excel-reports-document1.png)

## <a name="configure-the-custom-format-to-paginate-generated-documents"></a>Configurer le format personnalisé pour paginer les documents générés

### <a name="review-the-second-downloaded-excel-template"></a>Passer en revue le deuxième modèle Excel téléchargé

1. Dans Excel, ouvrez le fichier de modèle **ERIntrastatReportDemo2.xlsx** que vous avez téléchargé précédemment.
2. Comparez ce modèle avec le modèle **ERIntrastatReportDemo1.xlsx** et vérifiez qu’il contient plusieurs nouveaux noms Excel pour créer et remplir des sections spécifiques à la page dans les documents générés :

    - La plage **ReportPageHeader** est ajoutée pour créer des en-têtes de page.
    - La plage **ReportPageFooter** est ajoutée pour créer des pieds de page.
    - La cellule **ReportPageFooter\_PageLines** est configurée pour afficher le nombre de transactions par page.
    - La cellule **ReportPageFooter\_PageAmount** est configurée pour afficher le nombre total de transactions par page.
    - La cellule **ReportPageFooter\_PageWeight** est configurée pour afficher le poids total de transactions par page.
    - La cellule **ReportPageFooter\_RunningCounterLines** est configurée pour afficher le compteur de transactions en cours depuis le début du rapport jusqu’à la page en cours.
    - La cellule **ReportPageFooter\_RunningTotalAmount** est configurée pour afficher le nombre total de toutes les transactions en cours depuis le début du rapport jusqu’à la page en cours.
    - La cellule **ReportPageFooter\_RunningTotalWeight** est configurée pour afficher le poids total de toutes les transactions en cours depuis le début du rapport jusqu’à la page en cours.

    ![Disposition du modèle Excel 2 dans l’application de bureau.](./media/er-paginate-excel-reports-template2a.gif)

    La cellule **CommodityCode** de ce modèle est configurée pour envelopper le texte de la cellule. Étant donné que la ligne des détails de la transaction est configurée de manière à s’adapter automatiquement à la hauteur d’une ligne, la hauteur de la ligne entière doit changer automatiquement lorsque le texte dans la cellule **CommodityCode** est encapsulé.

    ![Cellule CommodityCode configurée pour encapsuler le texte de la cellule.](./media/er-paginate-excel-reports-template2b.gif)

### <a name="repeat-the-replacement-of-the-current-excel-template-in-the-custom-er-format"></a>Répéter le remplacement du modèle Excel actuel au format de gestion des états électroniques personnalisé

1. Suivez les étapes de la section [Remplacer le modèle Excel actuel au format de gestion des états électroniques (ER) personnalisé](#replace-template) de cet article. Cependant, à l’étape 7, sélectionnez le fichier **ERIntrastatReportDemo2.xlsx**.
2. Sur la page **Concepteur de formats**, développez **Déclaration d’échanges de biens**.
3. Désignez les composants de format [Plage](er-fillable-excel.md#range-component) qui ont été ajoutés au format de gestion des états électroniques (ER) modifiable pour synchroniser la structure avec la structure du modèle Excel appliqué :

    1. Sélectionnez le composant **Plage** associé au nom Excel **ReportPageHeader**.
    2. Sur l’onglet **Format**, dans le champ **Nom**, saisissez **En-tête de page de l’état**.
    3. Sélectionnez le composant **Plage** associé au nom Excel **ReportPageFooter**.
    4. Sur l’onglet **Format**, dans le champ **Nom**, saisissez **Pied de page de l’état**.

4. Sélectionnez **Enregistrer**.

![Structure de format dans le concepteur de formats de gestion des états électroniques une fois le modèle Excel remplacé.](./media/er-paginate-excel-reports-format2.png)

### <a name="change-the-format-structure-to-implement-document-pagination"></a>Modifier la structure de format pour implémenter la pagination du document

1. Sur la page **Concepteur de formats**, dans l’arborescence des formats du volet gauche, sélectionnez le composant racine **Déclaration d’échanges de biens**.
2. Sélectionnez **Ajouter**.
3. Dans la boîte de dialogue **Ajouter**, sélectionnez le composant [Page](er-fillable-excel.md#page-component) dans le groupe de composants **Excel**.
4. Dans la boîte de dialogue **Propriétés du composant**, dans le champ **Nom**, tapez **Page d’état**. Puis sélectionnez **OK**.
5. Pour utiliser le composant **En-tête de page d’état** comme en-tête de page sur chaque page générée, procédez comme suit :

    1. Sélectionnez le composant **En-tête de page d’état**, puis sélectionnez **Couper**.
    2. Sélectionnez le composant **Page d’état**, puis sélectionnez **Coller**.
    3. Développez **Page d’état**.
    4. Pour forcer le composant **Page** à [tenir compte de](er-fillable-excel.md#page-component-structure) cette plage comme d’un en-tête de page, sélectionnez **En-tête de page d’état**, puis, sur l’onglet **Format**, dans le champ **Direction de réplication**, sélectionnez **Pas de réplication**.

6. Pour paginer un document généré afin que le contenu des lignes d’état soit pris en compte, procédez comme suit :

    1. Sélectionnez le composant **Lignes d’état**, puis sélectionnez **Couper**.
    2. Sélectionnez le composant **Page d’état**, puis sélectionnez **Coller**.

7. Pour inclure le pied de page d’état après les lignes d’état, mais avant le pied de page final, procédez comme suit :

    1. Sélectionnez le composant **Pied de page d’état**, puis sélectionnez **Couper**.
    2. Sélectionnez le composant **Page d’état**, puis sélectionnez **Coller**.

8. Pour utiliser le composant **Pied de page d’état** comme pied de page sur chaque page générée, procédez comme suit :

    1. Sélectionnez le composant **Pied de page d’état**, puis sélectionnez **Couper**.
    2. Sélectionnez le composant **Page d’état**, puis sélectionnez **Coller**.
    3. Pour forcer le composant **Page** à [tenir compte de](er-fillable-excel.md#page-component-structure) cette plage comme d’un pied de page, sélectionnez **Pied de page d’état**, puis, sur l’onglet **Format**, dans le champ **Direction de réplication**, sélectionnez **Pas de réplication**.

![Structure de format dans le concepteur de formats de gestion des états électroniques une fois la pagination du document implémentée.](./media/er-paginate-excel-reports-format3.png)

### <a name="add-data-sources-to-calculate-page-footer-totals"></a>Ajouter des sources de données pour calculer les totaux du pied de page

Vous devez configurer de nouvelles sources de données pour calculer le total de pages, le compteur en cours et les valeurs de total en cours, et pour les afficher dans la section de pied de page. Nous vous recommandons d’utiliser les sources de données [Collection de données](er-data-collection-data-sources.md) à cet effet.

1. Dans la page **Concepteur de formats**, sélectionnez l’onglet **Mise en correspondance**.
2. Sélectionnez **Ajouter une racine**, puis procédez comme suit :

    1. Dans la boîte de dialogue **Ajouter une source de données**, dans la section **Général**, sélectionnez **Conteneur vide**.
    2. Dans la boîte de dialogue **Propriétés de la source de données « Conteneur vide »**, dans le champ **Nom**, saisissez **Total**.
    3. Cliquez sur **OK**.

3. Sélectionnez la source données **Total**, sélectionnez **Ajouter**, puis procédez comme suit :

    1. Dans la boîte de dialogue **Ajouter une source de données**, dans la section **Général**, sélectionnez **Conteneur vide**.
    2. Dans la boîte de dialogue **Propriétés de la source de données « Conteneur vide »**, dans le champ **Nom**, saisissez **Page**.
    3. Cliquez sur **OK**.

4. Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :

    1. Dans la boîte de dialogue **Ajouter une source de données**, dans la section **Général**, sélectionnez **Conteneur vide**.
    2. Dans la boîte de dialogue **Propriétés de la source de données « Conteneur vide »**, dans le champ **Nom**, saisissez **Exécution**.
    3. Cliquez sur **OK**.

5. Sélectionnez la source données **Total.Page**, sélectionnez **Ajouter**, puis procédez comme suit :

    1. Dans la boîte de dialogue **Ajouter une source de données**, dans la section **Fonctions**, sélectionnez **Collection de données**.
    2. Dans la boîte de dialogue **Propriétés de la source de données « Collection de données »**, dans le champ **Nom**, saisissez **Montant**.
    3. Dans le champ **Type d’article**, sélectionnez **Réel**.
    4. Définissez l’option **Collecter toutes les valeurs** sur **Oui**.
    5. Cliquez sur **OK**.

6. Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :

    1. Dans la boîte de dialogue **Ajouter une source de données**, dans la section **Fonctions**, sélectionnez **Collection de données**.
    2. Dans la boîte de dialogue **Propriétés de la source de données « Collection de données »**, dans le champ **Nom**, saisissez **Poids**.
    3. Dans le champ **Type d’article**, sélectionnez **Réel**.
    4. Définissez l’option **Collecter toutes les valeurs** sur **Oui**.
    5. Cliquez sur **OK**.

7. Sélectionnez la source données **Total.Running**, sélectionnez **Ajouter**, puis procédez comme suit :

    1. Dans la boîte de dialogue **Ajouter une source de données**, dans la section **Fonctions**, sélectionnez **Collection de données**.
    2. Dans la boîte de dialogue **Propriétés de la source de données « Collection de données »**, dans le champ **Nom**, saisissez **Montant**.
    3. Dans le champ **Type d’article**, sélectionnez **Réel**.
    4. Définissez le champ **Collecter toutes les valeurs** sur **Oui**.
    5. Cliquez sur **OK**.

8. Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :

    1. Dans la boîte de dialogue **Ajouter une source de données**, dans la section **Fonctions**, sélectionnez **Collection de données**.
    2. Dans la boîte de dialogue **Propriétés de la source de données « Collection de données »**, dans le champ **Nom**, saisissez **Poids**.
    3. Dans le champ **Type d’article**, sélectionnez **Réel**.
    4. Définissez le champ **Collecter toutes les valeurs** sur **Oui**.
    5. Cliquez sur **OK**.

9. Sélectionnez à nouveau **Ajouter**, puis procédez comme suit :

    1. Dans la boîte de dialogue **Ajouter une source de données**, dans la section **Fonctions**, sélectionnez **Collection de données**.
    2. Dans la boîte de dialogue **Propriétés de la source de données « Collection de données »**, dans le champ **Nom**, saisissez **Lignes**.
    3. Dans le champ **Type d’article**, sélectionnez **Entier**.
    4. Définissez le champ **Collecter toutes les valeurs** sur **Oui**.
    5. Cliquez sur **OK**.

10. Sélectionnez **Enregistrer**.

### <a name="add-data-sources-to-control-page-footer-visibility"></a>Ajouter des sources de données pour contrôler la visibilité du pied de page

Si vous envisagez de contrôler la visibilité du pied de page et que vous ne prévoyez pas d’inclure le pied de page sur la dernière page si elle contient des transactions, configurez une nouvelle source de données pour calculer le compteur courant requis.

1. Dans la page **Concepteur de formats**, sélectionnez l’onglet **Mise en correspondance**.
2. Sélectionnez la source de données **Total.Running**, sélectionnez **Ajouter**.
3. Dans la boîte de dialogue **Ajouter une source de données**, dans la section **Fonctions**, sélectionnez **Collection de données**.
4. Dans la boîte de dialogue **Propriétés de la source de données « Collection de données »**, dans le champ **Nom**, saisissez **Lines2**.
5. Dans le champ **Type d’article**, sélectionnez **Entier**.
6. Définissez l’option **Collecter toutes les valeurs** sur **Oui**.
7. Cliquez sur **OK**.
8. Sélectionnez **Enregistrer**.

![Ajout de sources de données dans le concepteur de formats de gestion des états électroniques.](./media/er-paginate-excel-reports-format4.png)

### <a name="configure-bindings-to-collect-total-values"></a>Configurer des liaisons pour collecter des valeurs totales

1. Sur la page **Concepteur de formats**, dans l’arborescence des formats, développez le composant **Lignes d’état** et sélectionnez le composant **Valeur de la facture**.
2. Sélectionnez **Modifier la formule**.
3. Changez la formule de liaison de `NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", "")` vers `Total.Page.Amount.Collect(NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", ""))`.

    > [!NOTE]
    > En plus de mettre la valeur du montant dans une cellule Excel pour chaque transaction itérée, cette liaison collecte la valeur dans la source de données **Total.Page.Amount** de la collection de données.

4. Sélectionnez le composant imbriqué **Poids**.
5. Sélectionnez **Modifier la formule**.
6. Changez la formule de liaison de `@.'$RoundedWeight'` vers `Total.Page.Weight.Collect(@.'$RoundedWeight')`.

    > [!NOTE]
    > En plus de mettre la valeur du poids dans une cellule Excel pour chaque transaction itérée, cette liaison collecte la valeur dans la source de données **Total.Page.Weight** de la collection de données.

![Liaisons configurées pour collecter les valeurs totales dans le concepteur de format de gestion des états électroniques (ER).](./media/er-paginate-excel-reports-format5.png)

### <a name="configure-bindings-to-fill-in-page-footer-totals"></a>Configurer des liaisons pour remplir les totaux de pied de page

1. Sur la page **Concepteur de formats**, dans l’arborescence des formats, développez le composant **Pied de page de l’état**, sélectionnez le composant **Plage** qui fait référence à la cellule **ReportPageFooter\_PageAmount**, puis procédez comme suit :

    1. Dans l’arborescence des sources de données dans le volet de droite, sélectionnez l’élément **Total.Page.Amount.Sum()**.
    2. Sélectionnez **Lier**.
    3. Sélectionnez **Modifier la formule**.
    4. Mettez à jour la formule pour `Total.Page.Amount.Sum(false)`.

    > [!NOTE]
    > Vous devez spécifier l’argument de cette fonction comme **False** pour conserver les données collectées pour la page en cours, car ces données sont nécessaires pour calculer le total cumulé, le nombre total de lignes par page et le compteur cumulé de lignes.

2. Dans l’arborescence des formats, sélectionnez le composant **Plage** qui fait référence à la cellule **ReportPageFooter\_PageWeight** Excel, puis procédez comme suit :

    1. Dans l’arborescence des sources de données dans le volet de droite, sélectionnez l’élément **Total.Page.Weight.Sum()**.
    2. Sélectionnez **Lier**.
    3. Sélectionnez **Modifier la formule**.
    4. Mettez à jour la formule pour `Total.Page.Weight.Sum(false)`.

### <a name="configure-bindings-to-fill-in-page-running-totals"></a>Configurer des liaisons pour remplir les totaux en cours de page

1. Sur la page **Concepteur de formats**, dans l’arborescence des formats, développez le composant **Pied de page de l’état**, sélectionnez le composant **Plage** qui fait référence à la cellule **ReportPageFooter\_RunningTotalAmount**, puis procédez comme suit :

    1. Dans l’arborescence des sources de données dans le volet de droite, sélectionnez l’élément **Total.Running.Amount.Collect()**.
    2. Sélectionnez **Lier**.
    3. Sélectionnez **Modifier la formule**.
    4. Mettez à jour la formule pour `Total.Running.Amount.Sum(false)+Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))`.

    > [!NOTE]
    > L’opérande `Total.Running.Amount.Sum(false)` renvoie le total en cours du montant précédemment collecté. L’opérande `Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))` renvoie le montant total de la page en cours. Vous devez spécifier l’argument de la fonction imbriquée de la deuxième opérande sur **True** pour réinitialiser la collection de données `Total.Page.Amount` dès que cette valeur est mise dans la collection totale en cours `Total.Running.Amount`. L’argument spécifié doit commencer à collecter le total de pages suivant à partir d’une valeur 0 (zéro).
    >
    > La fonction `Total.Running.Amount.Sum(false)` est appelée pour entrer le montant total cumulé dans la cellule **ReportPageFooter\_RunningTotalAmount** Excel sur la page en cours.

2. Dans l’arborescence des formats, sélectionnez le composant **Plage** qui fait référence à la cellule **ReportPageFooter\_RunningTotalWeight** Excel, puis procédez comme suit :

    1. Dans l’arborescence des sources de données dans le volet de droite, sélectionnez l’élément **Total.Running.Weight.Collect()**.
    2. Sélectionnez **Lier**.
    3. Sélectionnez **Modifier la formule**.
    4. Mettez à jour la formule pour `Total.Running.Weight.Sum(false)+Total.Running.Weight.Collect(Total.Page.Weight.Sum(true))`.

### <a name="configure-bindings-to-fill-in-the-page-running-counter"></a>Configurer des liaisons à remplir dans le compteur de pages en cours

1. Sur la page **Concepteur de formats**, dans l’arborescence des formats, développez le composant **Pied de page de l’état**, sélectionnez le composant **Plage** qui fait référence à la cellule **ReportPageFooter\_RunningCounterLines**, puis procédez comme suit :
2. Sélectionnez **Modifier la formule**.
3. Ajoutez la formule `Total.Running.Lines.Collect(COUNT(Total.Page.Amount.Result))`.

    > [!NOTE]
    > Cette formule renvoie le nombre des valeurs du montant collecté pour l’ensemble de l’état. Ce nombre est égal au nombre de transactions qui ont été itérées à l’instant présent. En même temps, la formule collecte la valeur renvoyée dans la collection **Total.Running.Lines**.

### <a name="configure-bindings-to-fill-in-the-page-footer-counter"></a>Configurer des liaisons à remplir dans le compteur de pieds de page en cours

1. Sur la page **Concepteur de formats**, dans l’arborescence des formats, développez le composant **Pied de page de l’état**, sélectionnez le composant **Plage** qui fait référence à la cellule **ReportPageFooter\_PageLines**, puis procédez comme suit :
2. Sélectionnez **Modifier la formule**.
3. Ajoutez la formule `COUNT(Total.Page.Amount.Result)-Total.Running.Lines.Sum(false)`.

    > [!NOTE]
    > Cette formule calcule le nombre de transactions sur la page actuelle comme la différence entre le nombre de transactions qui ont été collectées dans **Total.Page.Amount.Result** pour l’ensemble du rapport et le nombre de transactions qui ont été stockées à ce stade dans **Total.Running.Lines.Sum**. Parce que le nombre de transactions pour la page actuelle est stocké dans **Total.Running.Lines** dans la liaison du composant **Plage** qui fait référence à la cellule **ReportPageFooter\_RunningCounterLines** Excel, le nombre de transactions sur la page en cours n’est pas encore inclus. Par conséquent, cette différence est égale au nombre de transactions sur la page en cours.

![Liaisons configurées pour le remplissage du compteur de pieds de page dans le concepteur de formats de gestion des états électroniques.](./media/er-paginate-excel-reports-format6.png)

### <a name="configure-component-visibility"></a>Configurer la visibilité du composant

Vous pouvez modifier la visibilité de l’en-tête et du pied de page sur une page spécifique d’un document généré pour masquer les éléments suivants :

- L’en-tête de page sur la première page, car l’en-tête de l’état contient déjà des titres de colonne
- L’en-tête de page sur toute page qui n’a pas de transactions pouvant se produire pour la dernière page
- Le pied de page sur toute page qui n’a pas de transactions pouvant se produire pour la dernière page

Pour modifier la visibilité, mettez à jour la propriété **Activé** des composants **En-tête de page d’état** et **Pied de page d’état**.

1. Sur la page **Concepteur de formats**, dans l’arborescence des formats, développez le composant **Page d’état** et sélectionnez le composant **En-tête de page d’état** et procédez comme suit :

    1. Sélectionnez **Modifier** pour le champ **Activé**.
    2. Sur la page **Concepteur de formule**, dans le champ **Formule**, saisissez l’expression suivante :

        `AND(`<br>
        `COUNT(Total.Page.Amount.Result)<>0,`<br>
        `COUNT(Total.Page.Amount.Result)<>COUNT(model.CommodityRecord)`<br>
        `)`

2. Dans l’arborescence des formats, sélectionnez le composant **Pied de page d’état**, puis procédez comme suit :

    1. Sélectionnez **Modifier** pour le champ **Activé**.
    2. Sur la page **Concepteur de formule**, dans le champ **Formule**, saisissez l’expression suivante :

        `(`<br>
        `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)+`<br>
        `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result))`<br>
        `)<>0`

    > [!NOTE]
    > La construction `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)` est utilisée pour calculer le nombre de transactions sur la page en cours. La construction `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result)` permet d’ajouter le nombre de transactions sur la page actuelle à la collection, pour gérer correctement la visibilité du pied de page suivant.
    >
    > La collection `Total.Running.Lines` ne peut pas être réutilisée ici, car la propriété **Activé** d’un composant de base est traitée **après** que les liaisons des composants imbriqués ont été traitées. Quand la propriété **Activé** est traitée, la collection `Total.Running.Lines` est déjà incrémentée par le nombre de transactions sur la page en cours.

3. Sélectionnez **Enregistrer**.

## <a name="generate-an-intrastat-declaration-control-report-updated"></a>Générer un fichier d’état de contrôle de déclaration d’échanges de biens (mis à jour)

1. Veillez à ce que vous disposiez de 24 transactions sur la page **Déclaration d’échanges de biens**. Répétez les étapes de la section [Générer un état de contrôle de la déclaration d’échanges de biens](#generate-intrastat-control-report) de cet article pour générer et examiner l’état de contrôle.

    Toutes les transactions sont présentées sur la première page. Les totaux et les compteurs de pages sont égaux aux totaux et aux compteurs d’états. La plage d’en-tête de page est masquée sur la première page, car l’en-tête de l’état contient déjà des titres de colonne. L’en-tête et le pied de page sont masqués sur la deuxième page, car cette page ne contient aucune transaction.

    ![Document Excel généré dans l’application de bureau.](./media/er-paginate-excel-reports-document2.gif)

2. Mettez à jour deux transactions sur la page **Déclaration d’échanges de biens** en changeant le code **Numéro d’article** de **D00006** vers **L0010**. Notez que le nom de produit du nouvel article, **Paire d’enceintes stéréo actives**, est plus long que le nom de produit de l’article d’origine, **Haut-parleur standard**. Cette situation force l’ajustement du texte dans la cellule correspondante du document généré. La pagination des documents, ainsi que la somme et le comptage de pages, doivent maintenant être mis à jour. Répétez les étapes de la section [Générer un état de contrôle de la déclaration d’échanges de biens](#generate-intrastat-control-report) pour générer et examiner l’état de contrôle.

    Actuellement, les transactions sont présentées sur deux pages, et les totaux et les compteurs des pages sont correctement calculés. La plage d’en-tête de page est correctement masquée sur la première page et visible sur la deuxième page. Le pied de page est visible sur les deux pages, car elles contiennent des transactions.

    ![Document Excel généré mis à jour dans l’application de bureau.](./media/er-paginate-excel-reports-document3.gif)

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="is-there-any-way-to-recognize-when-the-final-page-is-processed-by-the-page-format-component"></a>Existe-t-il un moyen de reconnaître le moment où la page finale est traitée par le composant du format de page ?

Le composant **Page** [n’expose pas](er-fillable-excel.md#page-component-limitations) d’informations sur le numéro de la page traitée et le nombre total de pages dans un document généré. Néanmoins, vous pouvez configurer des [formules](er-formula-language.md) de gestion des états électroniques pour reconnaître la dernière page. Voici un exemple :

- Calculez le nombre total de transactions qui ont déjà été traitées en utilisant le composant **Page d’état**. Pour procéder à ce calcul, utilisez la formule `COUNT(Total.Page.Amount.Result)`. 
- Calculez le nombre total de transactions qui doivent être traitées en fonction de la liaison `model.CommodityRecord` configurée pour le composant **Lignes d’état**. Pour procéder à ce calcul, utilisez la formule `COUNT(model.CommodityRecord)`.
- Comparez deux nombres pour reconnaître la dernière page. Lorsque les deux valeurs sont égales, la page finale est générée.

> [!NOTE]
> Nous vous recommandons d’utiliser cette approche uniquement lorsque la propriété **Activé** du composant **Lignes d’état** ne contient aucune formule susceptible de renvoyer la valeur [False](er-formula-supported-data-types-primitive.md#boolean) au moment de l’exécution de certains [enregistrements](er-formula-supported-data-types-composite.md#record) itérés de la [Liste des enregistrements](er-formula-supported-data-types-composite.md#record-list) liée.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Créer une configuration pour générer des documents au format Excel](er-fillable-excel.md)
- [Utiliser les sources de données COLLECTION DE DONNÉES dans des formats de gestion d’états électroniques (ER)](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
