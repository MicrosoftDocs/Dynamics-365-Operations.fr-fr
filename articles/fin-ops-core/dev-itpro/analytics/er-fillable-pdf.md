---
title: Concevoir des configurations des états électroniques (ER) pour renseigner des modèles PDF
description: Cette rubrique fournit des informations sur la procédure pour concevoir un format d’états électroniques (ER) pour renseigner un modèle PDF.
author: NickSelin
manager: AnnBe
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: de31469e79addfb82b3b57e647ff82e4d254881a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688123"
---
# <a name="design-er-configurations-to-fill-in-pdf-templates"></a>Concevoir des configurations des états électroniques (ER) pour renseigner des modèles PDF

[!include[banner](../includes/banner.md)]

Les procédures de cette rubrique sont des exemples qui indiquent la manière dont le rôle **Administrateur système** ou le rôle **Développeur d’états électroniques** peut configurer un format d’états électroniques (ER) qui génère des états sous forme de fichiers PDF à l’aide de documents PDF pouvant être renseignés comme modèles d’états. Ces étapes peuvent être effectuées dans n’importe quelle société Dynamics 365 Finance ou Regulatory Configuration Service (RCS).

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer, vous devez avoir l’un des types d’accès suivants, selon le service que vous utilisez pour effectuer les procédures de cette rubrique :

- Accès à Finance pour un des rôles suivants :

    - Développeur d’états électroniques
    - Consultant fonctionnel des états électroniques
    - Administrateur système

- L’accès à RCS pour l’un des rôles suivants :

    - Développeur d’états électroniques
    - Consultant fonctionnel des états électroniques
    - Administrateur système

Vous devez également exécuter la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).

Enfin, vous devez télécharger les fichiers suivants depuis [CustomerSource](https://go.microsoft.com/fwlink/?linkid=874111).

| Description du contenu                       | Nom de fichier                                     |
|-------------------------------------------|-----------------------------------------------|
| Modèle de la première page de l’état | [IntrastatReportTemplate1.pdf](https://mbs.microsoft.com/Files/public/CS)                  |
| Modèle des autres pages de l’état    | [IntrastatReportTemplate2.pdf](https://mbs.microsoft.com/Files/public/CS/AX/IntrastatReportTemplate2.pdf)                  |
| Exemple de format d’ER - PDF                          | [État de déclaration d’échanges de biens (PDF).version.1.1.xml](https://mbs.microsoft.com/Files/public/CS/AX/IntrastatreportPDFversion11.xml)        |
| Exemple de format d’ER - Excel                          | [Déclaration d’échanges de biens (importation depuis Excel).version.1.1.xml](https://mbs.microsoft.com/Files/public/CS/AX/IntrastatimportfromExcelversion11.xml) |
| Exemple de jeu de données                            | [Exemple de données de déclaration d’échanges de biens.xlsx](https://mbs.microsoft.com/Files/public/CS/AX/Intrastatsampledata.xlsx)                    |

## <a name="design-the-format-configuration"></a>Concevoir la configuration du format

### <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Accéder à la liste des configurations fournies par Microsoft

1. Allez dans **Administration d’organisation \> Espaces de travail \> États électroniques**.
2. Assurez-vous que le fournisseur **Litware, Inc.** est disponible et marqué comme actif.
3. Sur la vignette du fournisseur **Microsoft**, sélectionnez **Référentiels**.

    > [!NOTE]
    > Si un référentiel de type **LCS** existe déjà, ignorez les étapes restantes de cette procédure.

4. Sélectionnez **Ajouter**.
5. Dans la boîte de dialogue déroulante, dans le groupe de champs **Type de référentiel de configuration**, sélectionnez l’option **LCS**.
6. Sélectionnez **Créer un référentiel**.
7. Cliquez sur **OK**.

### <a name="get-the-model-configurations-provided-by-microsoft"></a>Obtenir les configurations de modèle fournies par Microsoft

1. À gauche de la page **Référentiels de configuration**, sélectionnez le bouton **Afficher les filtres** (icône conique).
2. Ajoutez un filtre pour la valeur de **LCS** dans le champ **Type**, puis utilisez l’opérateur **commence par**.
3. Sélectionnez **Appliquer**.
4. Cliquez sur **Ouvrir**.
5. Dans l’arborescence, sélectionnez **Modèle de déclaration d’échanges de biens**.
6. Dans l’organisateur **Versions**, sélectionnez la version **1**.

    > [!NOTE]
    > Si le bouton **Importer** sur l’organisateur **Versions** n’est pas disponible, ignorez les étapes restantes de cette procédure.

7. Sélectionnez **Importer**.
8. Sélectionnez **Oui** pour confirmer l’importation de la version sélectionnée de la configuration du modèle **Modèle de déclaration d’échanges de biens**.

### <a name="create-a-new-format-configuration"></a>Créer une configuration de format

1. Dans l’espace de travail **Génération des états électronique**, sélectionnez la vignette **Configurations des états**.
2. Dans l’arborescence, sélectionnez **Modèle de déclaration d’échanges de biens**.
3. Sélectionnez **Créer une configuration**.

    > [!NOTE]
    > Si le bouton **Créer une configuration** n’est pas disponible, vous devez activer le mode de conception de la page **Paramètres de la gestion des états électroniques** qui peut être ouverte dans l’espace de travail **Génération des états électronique**.

4. Dans la boîte de dialogue déroulante, dans le groupe de champs **Nouveau**, sélectionnez l’option **Format basé sur le modèle de données de la déclaration d’échanges de biens**.
5. Dans le champ **Nom**, entrez **État de déclaration d’échanges de biens (PDF)**.
6. Dans le champ **Description**, entrez **État de déclaration d’échanges de biens au format PDF**.

    > [!NOTE]
    > Le fournisseur de configuration actif est automatiquement entré. Ce fournisseur pourra mettre à jour cette configuration. Bien que d’autres fournisseurs puissent utiliser cette configuration, ils ne pourront pas la mettre à jour.

7. Facultatif : Dans le champ **Type de format**, vous pouvez sélectionner un format spécifique de document électronique. Si vous sélectionnez **PDF**, au moment de la conception, le concepteur des opérations ER proposera seulement les éléments de format qui s’appliquent uniquement aux documents générés au format PDF (**PDF\Fichier**, **Fusion PDF\PDF**, et ainsi de suite.). Si vous laissez ce champ vide, un format de document électronique sera spécifié au moment de la conception dans le concepteur des opérations ER lorsqu’un premier élément de format sera ajouté. Par exemple, si vous ajoutez **Excel\Fichier** comme premier élément de format, le concepteur des opérations ER vous proposera juste les éléments de format qui s’appliquent uniquement aux documents générés au format Excel (**Excel\Cellule**, **Excel\Plage**, et ainsi de suite.). format.
8. Sélectionnez **Créer une configuration**.

Une configuration de format ER est créée. Vous pouvez utiliser la version temporaire de cette configuration pour stocker le composant de format ER conçu pour générer des documents électroniques au format PDF.

### <a name="design-the-format-of-an-electronic-document"></a>Créer le format d’un document électronique

Ensuite, dans la configuration de format ER créée, vous concevrez le format ER qui génère l’état **Contrôle pour la déclaration d’échanges de biens** au format PDF. La première page de cet état doit afficher un résumé de l’état et les détails des transactions de commerce extérieur déclarées. Les autres pages doivent afficher uniquement les détails des transactions de commerce extérieur déclarées. Comme les pages de l’état générées doivent avoir différentes mises en page, deux modèles distincts au format PDF seront utilisés dans le format ER.

Dans une visionneuse de PDF, ouvrez les modèles de documents PDF que vous avez téléchargés. Notez que chaque modèle contient plusieurs champs qui doivent être remplis. Dans chaque modèle, les détails des transactions de commerce extérieur sont présentés en 42 lignes, contenant chacune neuf champs. Le numéro de ligne apparaît à la fin du nom de chaque champ (par exemple, **Date 1**...**Date 42** et **Marchandise 1**...**Marchandise 42**).

L’illustration suivante présente le modèle PDF de la première page de l’état.

![Modèle 1](media/rcs-ger-filloutpdf-template1.png)

L’illustration suivante présente le modèle PDF des autres pages de l’état.

![Modèle 2](media/rcs-ger-filloutpdf-template2.png)

1. Dans la page **Configurations**, sélectionnez **Concepteur**.
2. Sélectionnez **Ajoutez racine**.
3. Dans la boîte de dialogue déroulante, dans l’arborescence, sélectionnez **PDF \> Fusion PDF**.

    Lorsque vous sélectionnez l’élément **Fusion PDF** comme l’élément racine du format, tous les documents PDF générés au moment de l’exécution seront fusionnés en un document PDF final unique. Si vous n’avez besoin que d’un modèle PDF pour générer tous les documents requis à l’aide du format ER que vous concevez, vous pouvez sélectionner **Fichier PDF** comme élément racine.

4. Dans le champ **Nom**, entrez **Production**.
5. Dans le champ **Préférences linguistiques**, sélectionnez **Préférences utilisateur**. L’état sera généré dans la langue favorite de l’utilisateur qui l’exécute.
6. Dans le champ **Préférences culturelles**, sélectionnez **Préférences utilisateur**. Les valeurs et les dates présentées sur les pages de l’état seront mises en page selon les paramètres régionaux préférés de l’utilisateur qui exécute l’état.
7. Cliquez sur **OK**.
8. Dans le volet Actions, sous l’onglet **Importer**, sélectionnez **Importer à partir du PDF**.

    Lorsqu’un document PDF pouvant être renseigné est importé comme modèle pour ce format ER, tous les éléments nécessaires au format ER (éléments **Fichier PDF**, **Groupe de champs** et **Champ**) sont automatiquement créés au format défini, selon la structure du document PDF importé.

9. Sélectionnez **Parcourir**. Accédez au fichier **IntrastatReportTemplate1.pdf** que vous avez téléchargé précédemment comme condition préalable et sélectionnez-le.
10. Cliquez sur **OK**.

    Le fichier sélectionné est chargé, et le champ **Modèle** dans la boîte de dialogue **Importer à partir du PDF** est renseigné.

11. Définissez l’option **Champs de groupe** sur **Oui**. Si le document PDF sélectionné contient tous les groupes de champs, ils seront utilisés pour regrouper les éléments de format ER créés. Un élément de format **Groupe de champs** sera créé à cet effet.

    Si cette option est définie sur **Non**, les éléments de format ER nécessaires seront créés comme liste plate des éléments imbriqués sous l’élément de format **Fichier PDF** créé.

12. Cliquez sur **OK**.

    ![Importer à partir de la boîte de dialogue PDF](media/rcs-ger-filloutpdf-importtemplate.png)

13. Dans l’arborescence, développer **Production**.

    Notez que le composant **Fichier PDF** a été créé automatiquement pour gérer la création de la première page de l’état généré au moment de l’exécution.

14. Dans l’arborescence, développez **Production \> Fichier PDF**.

    Notez que la liste structurée des éléments de format a été créée automatiquement dans ce format ER, selon la structure du document PDF pouvant être renseigné que vous avez importé précédemment.

15. Dans l’arborescence, sélectionnez **Production \> Fichier PDF**.
16. Dans le champ **Nom**, entrez **Page 1**.

    Cet élément de format sera utilisé pour générer la première page de l’état **Contrôle pour la déclaration d’échanges de biens**. Cette page affiche une synthèse de l’état et les détails des transactions de commerce extérieur.

    Si vous laissez le champ **Préférences linguistiques** vide, le paramètre **Préférences linguistiques** de l’élément **Fusion PDF** parent déterminera la langue de l’état généré à l’aide de cet élément de format. Vous pouvez sélectionner une autre valeur pour remplacer le paramétrage de l’élément parent.

    Si vous laissez le champ **Préférences culturelles** vide, le paramètre **Préférences culturelles** de l’élément **Fusion PDF** parent déterminera les paramètres régionaux de l’état généré à l’aide de cet élément de format. Les paramètres régionaux déterminent le format des valeurs et des dates sur les pages de l’état. Vous pouvez sélectionner une autre valeur pour remplacer le paramétrage de l’élément parent.

17. Dans le volet Actions, sélectionnez l’onglet **Importer**. Notez que le bouton **Mettre à jour à partir du PDF** est devenu disponible pour l’élément de format sélectionné, **Fichier PDF**.

    Vous pouvez utiliser ce bouton pour importer le modèle PDF mis à jour au format modifié. Lorsque le modèle PDF mis à jour est importé, la liste des éléments de format sera modifiée en fonction :

    - Pour les nouveaux champs dans le modèle PDF mis à jour, de nouveaux éléments de format sont créés au format ER modifié.
    - Si le modèle PDF mis à jour ne comprend plus des champs qui correspondent à tous les éléments de format existants dans le format ER modifié, ces éléments de format sont supprimés du format ER.

18. Dans l’onglet **Format**, sélectionnez **Pièces jointes**.

    Notez que le document PDF importé est associé au format ER modifié.

    ![Aperçu de la pièce jointe PDF](media/rcs-ger-filloutpdf-attachedtemplate.png)

19. Continuez à concevoir ce format en important le deuxième modèle PDF, en ajoutant les liaisons nécessaires aux sources de données, et ainsi de suite.
20. Sélectionnez **Enregistrer**.
21. Fermez la page.
22. Sélectionnez **Supprimer**.
23. Cliquez sur **Oui**.

Pour connaître la procédure d’utilisation des nouveaux éléments de format **Fusion PDF**, **Fichier PDF**, **Groupe de champs** et **Champ** pour générer des documents au format PDF, vous pouvez importer et analyser l’’exemple de format ER.

### <a name="import-the-format-configuration"></a>Importer la configuration du format

Ensuite, vous importerez l’exemple de format ER que vous avez précédemment téléchargé pour générer l’état **Contrôle pour la déclaration d’échanges de biens** au format PDF. La première page de l’état doit afficher un résumé de l’état et les détails des transactions de commerce extérieur déclarées. Les autres pages doivent afficher uniquement les détails des transactions de commerce extérieur déclarées.

1. Sur la page **Configurations**, sélectionnez **Échanger \> Charger depuis le fichier XML**.
2. Sélectionnez **Parcourir**. Accédez au fichier **État de déclaration d’échanges de biens (PDF).version.1.1.xml** que vous avez téléchargé précédemment comme condition préalable et sélectionnez-le.
3. Cliquez sur **OK**.

## <a name="analyze-the-format-configuration"></a>Analyser la configuration du format

### <a name="format-layout"></a>Mise en page du format

1. Dans la page **Configurations**, dans l’arborescence, sélectionnez **Modèle de déclaration d’échanges de biens \> État de déclaration d’échanges de biens (PDF)**.
2. Sélectionnez **Concepteur**.
3. Sélectionnez **Afficher les détails**.
4. Dans l’arborescence, développez **Production : Fusion PDF**.

    Notez que ce format ER contient deux éléments **Fichier PDF**, qui utilisent chacun un modèle PDF distinct. Un modèle est utilisé pour générer la première page de l’état au format PDF, et l’autre modèle est utilisé pour générer les autres pages.

5. Dans l’arborescence, développez **Production : Fusion PDF \> Page 1 : Fichier PDF (IntrastatReportTemplate1)**.
6. Dans l’arborescence, développez **Production : Fusion PDF \> Page N : Fichier PDF (IntrastatReportTemplate2)**.

    Notez que, du fait que le contenu des deux modèles PDF diffère, la structure des éléments de format imbriqués des deux éléments **Fichier PDF** diffère également.

### <a name="format-mapping"></a>Mise en correspondance des formats

1. Dans la page **Concepteur de formats**, sélectionnez l’onglet **Mise en correspondance**.
2. Dans l’arborescence, développez **Pagination \> Pages**.

    ![Page de concepteur de formule où le modèle d’arborescence est développé](media/rcs-ger-filloutpdf-reviewformat.png)

    Notez les informations suivantes :

    - L’élément de format **Production \> Page 1** du type **Fichier PDF** n’est associé à aucune source de données, et l’expression **Activé** de cet élément de format est vide. Par conséquent, au moment de l’exécution, le modèle PDF **IntrastatReportTemplate1** ne sera rempli qu’une fois lorsqu’un document PDF individuel sera généré.
    - L’élément de format **Production \> Page N** du type **Fichier PDF** est lié à la source de données **Paging.PageN** du type **Liste d’enregistrements**, et l’expression **Activé** de cet élément de format est vide. Par conséquent, au moment de l’exécution, le modèle PDF **IntrastatReportTemplate2** sera rempli pour chaque enregistrement à partir de la liste des enregistrements associés lorsqu’un document PDF individuel sera généré.
    - Comme les éléments de format **Page 1: Fichier PDF** et **Page N : Fichier PDF** sont les enfants de l’élément de format **Production : Fusion PDF**, tous les documents PDF renseignés sont fusionnés en un document PDF unique final.
    - Les sources de données **Paging.Page1** et **Paging.PageN** sont configurées en tant que filtres d’enregistrements dans la source de données **Paging.Pages**. Cette source de données est configurée pour fractionner l’ensemble complet des transactions de commerce extérieur en lots. Chaque lot contient jusqu’à 42 enregistrements. L’expression ER suivante permet de fractionner les transactions en lots :

        SPLITLIST(Totals.CommodityRecord,42)

    - La source de données **Paging.Pages** contient l’élément **Paging.Pages.Enumerated** qui renvoie les détails de chaque enregistrement inclus dans un lot. Ces détails incluent la séquence de l’enregistrement dans le lot actuel (le champ **Paging.Pages.Enumerated.Number**). Le champ **Paging.Pages.Enumerated.Number** est utilisé dans l’expression **Nom** des éléments de format **Champ PDF** pour générer de façon dynamique un nom de champ basé sur le nombre de transactions dans un lot. Le nom de champ qui est généré est ensuite utilisé pour renseigner le champ PDF approprié dans le modèle PDF utilisé.
    - L’élément de format **Production \> Page N \> Détails 2** du type **Groupe PDF** est lié à la source de données **Paging.PageN.Enumerated** (ou **\@.Enumerated** si le mode d’affichage **Chemin d’accès relatif** est utilisé) du type **Liste d’enregistrements**. Par conséquent, au moment de l’exécution, les éléments imbriqués de ce groupe PDF seront renseignés pour chaque enregistrement de la liste d’enregistrements associés. Ainsi, chaque ligne PDF individuelle est virtuellement générée lorsque chaque nième de 42 enregistrements de la liste **Paging.PageN.Enumerated** les champs PDF suivants sont remplis : Date N, Sens N, Marchandise N, et ainsi de suite. Par conséquent, à cet égard, le comportement de cet élément de format **Groupe de champs** s’apparente au comportement des éléments de format **XML \> Séquence** et **Texte \> Séquence**.

3. Dans l’arborescence, développez **Production \> Page N \> Details2**.
4. Dans l’arborescence, sélectionnez **Production \> Page N \> Details2 \> PageFooter**.

    Notez que l’attribut **Nom** de cet élément de format est défini sur **PageFooter**. Notez également que l’expression **Nom** de l’élément de format est vide.

5. Dans l’arborescence, sélectionnez **Production \> Page N \> Details2 \> Correction 1**.

    Notez que l’attribut **Nom** de cet élément de format est défini sur **Correction 1**. Notez également que l’expression **Nom** de l’élément de format est définie comme **Paging.FldName("Correction",\@.Number)**.

![Concepteur de formats dans lequel une mise en correspondance est sélectionnée](media/rcs-ger-filloutpdf-reviewformat2.png)

Notez que l’élément de format **Champ** permet de remplir un champ individuel d’un document PDF pouvant être renseigné défini comme modèle de l’élément de format parent **Fichier PDF**. La liaison de l’élément de format **Fichier PDF** ou de ses éléments imbriqués, s’il comporte des éléments imbriqués, spécifie la valeur entrée dans les champs PDF correspondants. Différentes propriétés de l’élément de format **Champ** permettent de spécifier quel champ PDF est renseigné par un élément de format individuel :

- Dans l’onglet **Format**, l’attribut **Nom** de l’élément de format
- Dans l’onglet **Mise en correspondance**, l’expression **Nom** de l’élément de format

Comme les deux propriétés sont facultatives pour un élément de format **Champ**, les règles suivantes sont appliquées pour spécifier le champ PDF cible :

- Si l’attribut **Nom** est vide, et que l’expression **Nom** renvoie une chaîne vide au moment de l’exécution, une exception est levée au moment de l’exécution pour informer l’utilisateur qu’un champ PDF est introuvable dans le modèle PDF utilisé pour renseigner le document PDF.
- Si l’attribut **Nom** est défini, et que l’expression **Nom** est vide, le champ PDF ayant le même nom que l’attribut **Nom** de l’élément de format est renseigné.
- Si l’attribut **Nom** est défini, et que l’expression **Nom** est configurée, le champ PDF ayant le même nom que la valeur renvoyée par l’expression **Nom** de l’élément de format est renseigné.

> [!NOTE]
> Une case à cocher PDF peut être renseignée comme activée comme suit :
>
> - Lorsque l’élément de format **Champ** correspondant est lié à un champ de source de données de type de donnée **Booléenne** ayant la valeur **True**
> - Lorsque l’élément de format **Champ** correspondant contient un élément de format **Chaîne** imbriqué associé à un champ de source de données ayant une valeur de texte **1**, **True** ou **Oui**

## <a name="run-the-format-configuration"></a>Exécuter la configuration du format

### <a name="import-the-format-configuration"></a>Importer la configuration du format

Ensuite, vous chargerez l’exemple de format ER **Déclaration d’échanges de biens (importation depuis Excel)**. Ce format est conçu pour analyser un classeur Microsoft Excel sélectionné par l’utilisateur qui simule des transactions de commerce extérieur.

1. Sur la page **Configurations**, sélectionnez **Échanger \> Charger depuis le fichier XML**.
2. Sélectionnez **Parcourir**. Accédez au fichier **État de déclaration d’échanges de biens (importation depuis Excel).version.1.1.xml** que vous avez téléchargé précédemment comme condition préalable et sélectionnez-le.
3. Cliquez sur **OK**.
4. Dans l’arborescence, sélectionnez **Modèle de déclaration d’échanges de biens \> Déclaration d’échanges de biens (importation depuis Excel)**.
5. Sélectionnez **Modifier**.
6. Définissez l’option **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.

    > [!NOTE]
    > Si vous avez défini précédemment l’option **Valeur par défaut de la mise en correspondance des modèles** sur **Oui** pour la configuration du **Modèle de déclaration d’échanges de biens** ou une autre configuration imbriquée sous la configuration **Modèle de déclaration d’échanges de biens**, définissez cette option sur **Non**.

    Lorsque l’option **Valeur par défaut de la mise en correspondance des modèles** est définie sur **Oui**, le format ER **Déclaration d’échanges de biens (importation depuis Excel)** importé est attribué comme source de données par défaut de la configuration du format **État de déclaration d’échanges de biens (PDF)**. Puis, lorsque la configuration de format **État de déclaration d’échanges de biens (PDF)** est exécutée, le contenu du classeur Excel analysé par le format ER **Déclaration d’échanges de biens (importation depuis Excel)** simulera les transactions de commerce extérieur devant être déclarées. L’illustration suivante présente un exemple de classeur Excel.

    ![Classeur Excel contenant des exemples de données](media/rcs-ger-filloutpdf-excelworkbook.png)

### <a name="run-the-format-configuration"></a>Exécuter la configuration du format

1. Dans la page **Configurations**, dans l’arborescence, sélectionnez **Modèle de déclaration d’échanges de biens \> État de déclaration d’échanges de biens (PDF)**.
2. Sélectionnez **Exécuter**.
3. Sélectionnez **Parcourir**. Accédez au fichier **Exemple de données de déclaration d’échanges de biens.xlsx** que vous avez téléchargé précédemment comme condition préalable et sélectionnez-le.
4. Cliquez sur **OK**.
5. Dans le champ **Sens de l’état**, sélectionnez **Les deux** pour renseigner toutes les transactions du classeur Excel importé dans l’état PDF généré.
6. Cliquez sur **OK**.
7. Vérifiez le document PDF généré.

L’illustration suivante présente un exemple de la première page de l’état généré.

![Première page de l’état généré](media/rcs-ger-filloutpdf-generatedreport.png)

L’illustration suivante présente un exemple d’une autre page de l’état généré.

![Autre page de l’état généré](media/rcs-ger-filloutpdf-generatedreport2.png)

## <a name="additional-resources"></a>Ressources supplémentaires

- [ER Concevoir une configuration pour générer des états au format OPENXML (novembre 2016)](tasks/er-design-reports-openxml-2016-11.md)
- [Créer des configurations de gestion d’états électroniques pour générer des états au format Word](tasks/er-design-configuration-word-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]