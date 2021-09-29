---
title: Créer une configuration pour générer des documents au format Excel
description: Cette rubrique décrit comment concevoir un format pour la gestion des états électroniques pour renseigner un modèle Excel, puis générer des documents sortants au format Excel.
author: NickSelin
ms.date: 09/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd3171ad24f9c06f04372b30f2682b6da516bcb6
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7488136"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>Créer une configuration pour générer des documents au format Excel

[!include[banner](../includes/banner.md)]

Vous pouvez concevoir une configuration de format [états électroniques (ER)](general-electronic-reporting.md) ayant un [composant de format](general-electronic-reporting.md#FormatComponentOutbound) ER que vous pouvez configurer pour générer un document sortant dans un format de classeur Microsoft Excel. Des composants spécifiques au format ER doivent être utilisés à cet effet.

Pour en savoir plus sur cette fonctionnalité, suivez les étapes de la rubrique : [Concevoir une configuration pour générer des états au format OPENXML](tasks/er-design-reports-openxml-2016-11.md).

## <a name="add-a-new-er-format"></a>Ajouter un nouveau format ER

Lorsque vous ajoutez une nouvelle configuration de format ER pour générer un document sortant dans un format de classeur Excel, vous devez soit sélectionner la valeur **Excel** pour l’attribut **Type de format** du format ou laisser l’attribut **Type de format** vide.

- Si vous sélectionnez **Excel**, vous pouvez configurer le format pour générer un document sortant uniquement au format Excel.
- Si vous laissez l’attribut vide, vous pouvez configurer le format pour générer un document sortant dans n’importe quel format pris en charge par l’infrastructure ER.

Pour configurer le composant de format ER de la configuration, sélectionnez **Concepteur** dans le volet Actions et ouvrez le composant de format ER pour le modifier dans le concepteur d’opération de gestion des états électroniques.

![Page Configurations.](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Composant de fichier Excel

### <a name="manual-entry"></a>Saisie manuelle

Vous devez ajouter un composant de **fichier\\Excel** au format ER configuré pour générer un document sortant au format Excel.

![Composant de fichier Excel.](./media/er-excel-format-add-file-component.png)

Pour spécifier la mise en page du document sortant, attachez un classeur Excel doté de l’extension .xlsx au composant **Fichier\\Excel** comme modèle pour les documents sortants.

> [!NOTE]
> Lorsque vous joignez manuellement un modèle, vous devez utiliser un [type de document](../../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md#configure-document-types) configuré à cet effet dans les [Paramètres ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Ajout d’une pièce jointe au composant Fichier\Excel.](./media/er-excel-format-add-file-component2.png)

Pour spécifier comment le modèle joint sera rempli lorsque vous exécuterez le format ER configuré, vous devez ajouter les composants **Feuille**, **Plage** et **Cellule** au composant **Fichier\\Excel**. Chaque composant imbriqué doit être associé à un élément nommé Excel.

### <a name="template-import"></a>Importation de modèles

Vous pouvez sélectionner **Importer à partir d’Excel** sur l’onglet **Importer** du volet Actions pour importer un nouvelle modèle dans un format ER vide. Dans cet exemple, un composant **Fichier\\Excel** sera créé automatiquement et le modèle importé y sera attaché. Tous les composants ER requis seront également créés automatiquement, en fonction de la liste des éléments nommés Excel découverts.

![Sélection de l’importation depuis Excel.](./media/er-excel-format-import-template.png)

> [!NOTE]
> Définissez l’option **Créer un élément de format de feuille Excel** sur **Oui** pour créer l’élément **Feuille** facultatif au format ER modifiable.

## <a name="sheet-component"></a>Composant de feuille

Le composant **Feuille** indique une feuille de calcul du classeur Excel joint à remplir. Le nom de la feuille de calcul dans un modèle Excel est défini dans la propriété **Feuille** de ce composant.

> [!NOTE]
> Ce composant est facultatif pour les classeurs Excel qui contiennent une seule feuille de calcul.

Sur l’onglet **Mise en correspondance** du concepteur d’opération ER, vous pouvez configurer la propriété **Activé** pour un composant **Feuille** pour spécifier si le composant doit être placé dans un document généré :

- Si une expression de la propriété **Activé** est configurée pour renvoyer **Vrai** lors de l’exécution ou si aucune expression n’est configurée, la feuille de calcul appropriée sera placée dans le document généré.
- Si une expression de la propriété **Activé** est configurée pour renvoyer la valeur **Faux** au moment de l’exécution, le document généré ne contiendra pas de feuille de calcul.

![Exemple de composant feuille.](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Composant de gamme

Le composant **Plage** indique une plage Excel qui doit être contrôlée par ce composant ER. Le nom de la plage est défini dans la propriété **Plage Excel** de ce composant.

La propriété **Direction de la réplication** spécifie si et comment la plage sera répétée dans un document généré :

- Si la propriété **Direction de la réplication** est définie sur **Pas de réplication**, la plage Excel appropriée ne sera pas répétée dans le document généré.
- Si la propriété **Direction de la réplication** est définie sur **Vertical**, la plage Excel appropriée sera répétée dans le document généré. Chaque plage répliquée est placée sous la plage d’origine dans un modèle Excel. Le nombre de répétitions est défini par le nombre d’enregistrements dans une source de données du type **Liste d’enregistrements** lié à ce composant ER.
- Si la propriété **Direction de la réplication** est définie sur **Horizontal**, la plage Excel appropriée sera répétée dans le document généré. Chaque plage répliquée est placée à droite de la plage d’origine dans un modèle Excel. Le nombre de répétitions est défini par le nombre d’enregistrements dans une source de données du type **Liste d’enregistrements** lié à ce composant ER.

Pour en savoir plus sur la réplication horizontale, suivez les étapes de la rubrique [Utiliser des plages extensibles horizontalement pour ajouter dynamiquement des colonnes dans les états Excel](tasks/er-horizontal-1.md).

Le composant **Plage** peut avoir d’autres composants ER imbriqués qui sont utilisés pour entrer des valeurs dans les plages nommées Excel appropriées.

- Si l’un des composants du groupe **Texte** est utilisé pour entrer des valeurs, la valeur est entrée dans une plage Excel en tant que valeur de texte.

    > [!NOTE]
    > Utilisez ce modèle pour formater les valeurs entrées en fonction des paramètres régionaux définis dans l’application.

- Si le composant **Cellule** du groupe **Excel** est utilisé pour entrer des valeurs, la valeur est entrée dans une plage Excel en tant que valeur du type de données défini par la liaison de ce composant **Cellule**(par exemple, **Chaîne**, **Réel**, ou **Entier**).

    > [!NOTE]
    > Utilisez ce modèle pour permettre à l’application Excel de formater les valeurs entrées en fonction des paramètres régionaux de l’ordinateur local qui ouvre le document sortant.

Sur l’onglet **Mise en correspondance** du concepteur d’opération ER, vous pouvez configurer la propriété **Activé** pour un composant **Plage** pour spécifier si le composant doit être placé dans un document généré :

- Si une expression de la propriété **Activé** est configurée pour renvoyer **Vrai** lors de l’exécution ou si aucune expression n’est configurée, la plage appropriée sera renseignée dans le document généré.
- Si une expression de la propriété **Activé** est configurée pour renvoyer la valeur **Faux** lors de l’exécution et si la plage ne représente pas les lignes et les colonnes entières, la plage appropriée ne sera pas renseignée dans le document généré.
- Si une expression de la propriété **Activé** est configurée pour renvoyer la valeur **Faux** lors de l’exécution et si cette plage représente les lignes et les colonnes entières, celles-ci seront masquées dans le document.

## <a name="cell-component"></a>Composant Cellule

Le composant **Cellule** est utilisé pour remplir des cellules, des formes et des images nommées Excel. Pour indiquer un objet nommé Excel qui doit être rempli par un composant **Cellule** ER, vous devez spécifier le nom de cet objet dans la propriété **Plage Excel** du composant **Cellule**.

Sur l’onglet **Mise en correspondance** du concepteur d’opération ER, vous pouvez configurer la propriété **Activé** pour un composant **Cellule** pour spécifier si l’objet doit être renseigné dans un document généré :

- Si une expression de la propriété **Activé** est configurée pour renvoyer **Vrai** lors de l’exécution ou si aucune expression n’est configurée, l’objet approprié sera renseigné dans le document généré. La liaison de ce composant **Cellule** spécifie une valeur qui est placée dans l’objet approprié.
- Si une expression de la propriété **Activé** est configurée pour renvoyer **Faux** au moment de l’exécution, l’objet approprié ne sera pas renseigné dans le document généré.

Lorsqu’un composant **Cellule** est configuré pour entrer une valeur dans une cellule, il peut être lié à une source de données qui renvoie la valeur d’un type de données primitif (par exemple, **Chaîne**, **Réel**, ou **Entier**). Dans ce cas, la valeur est entrée dans la cellule en tant que valeur du même type de données.

Lorsqu’un composant **Cellule** est configuré pour entrer une valeur dans un format Excel, il peut être lié à une source de données qui renvoie une valeur d’un type de données primitif (par exemple, **Chaîne**, **Réel**, ou **Entier**). Dans ce cas, la valeur est entrée au format Excel en tant que texte. Pour les valeurs de types de données qui ne sont pas définies en tant que **Chaîne**, la conversion en texte se fait automatiquement.

> [!NOTE]
> Vous pouvez configurer un composant **Cellule** pour remplir une forme uniquement dans les cas où une propriété de texte est prise en charge.

Lorsqu’un composant **Cellule** est configuré pour entrer une valeur dans une image Excel, il peut être lié à une source de données qui renvoie la valeur d’un type de données **Conteneur** qui représente une image au format binaire. Dans ce cas, la valeur est entrée dans l’image Excel sous forme d’image.

> [!NOTE]
> Chaque image et forme Excel est considérée comme étant ancrée par son coin supérieur gauche à une cellule ou une plage Excel spécifique. Si vous souhaitez répliquer une image ou une forme Excel, vous devez configurer la cellule ou la plage à laquelle il est ancré en tant que cellule ou plage répliquée.

Pour en savoir plus sur l’incorporation d’images et de formes, consultez [Intégrer des images et des formes dans les documents que vous générez ER à l’aide de la gestion des états électroniques (ER)](electronic-reporting-embed-images-shapes.md).

## <a name="page-break-component"></a>Composant Saut de page

Le composant **Saut de page** oblige Excel à démarrer une nouvelle page. Ce composant n’est pas requis lorsque vous souhaitez utiliser la pagination par défaut d’Excel, mais vous devez l’utiliser lorsque vous souhaitez qu’Excel suive votre format ER pour structurer la pagination.

## <a name="page-component"></a><a name="page-component"></a>Composant de page

### <a name="overview"></a>Vue d’ensemble

Vous pouvez utiliser le composant **Page** lorsque vous souhaitez qu’Excel suive votre format ER et structure la pagination dans un document sortant généré. Lorsqu’un format ER exécute des composants qui sont sous le composant **Page**, les sauts de page requis sont automatiquement ajoutés. Au cours de ce processus, la taille du contenu généré, la mise en page du modèle Excel et le format de papier sélectionné dans le modèle Excel sont pris en compte.

Si vous devez diviser un document généré en différentes sections, chacune ayant une pagination différente, vous pouvez configurer plusieurs composants **Page** dans chaque composant [Feuille](er-fillable-excel.md#sheet-component).

### <a name="structure"></a><a name="page-component-structure"></a>Structure

Si le premier composant sous le composant **Page** est un composant [Plage](er-fillable-excel.md#range-component) où la propriété **Direction de réplication** est définie sur **Pas de réplication**, cette plage est considérée comme l’en-tête de page pour la pagination basée sur les paramètres du composant **Page**. La plage Excel associée à ce composant de format est répétée en haut de chaque page générée à l’aide des paramètres du composant **Page** actuel.

> [!NOTE]
> Pour une pagination correcte, si la plage [Lignes à répéter en haut](https://support.microsoft.com/office/repeat-specific-rows-or-columns-on-every-printed-page-0d6dac43-7ee7-4f34-8b08-ffcc8b022409) est configurée dans votre modèle Excel, l’adresse de cette plage Excel doit être identique à l’adresse de la plage Excel associée au composant **Plage** précédemment décrit.

Si le dernier composant sous le composant **Page** est un composant **Plage** où la propriété **Direction de réplication** est définie sur **Pas de réplication**, cette plage est considérée comme le pied de page pour la pagination basée sur les paramètres du composant **Page**. La plage Excel associée à ce composant de format est répétée en bas de chaque page générée à l’aide des paramètres du composant **Page** actuel.

> [!NOTE]
> Pour une pagination correcte, les plages Excel associées aux composants **Plage** ne doivent pas être redimensionnées lors de l’exécution. Nous vous déconseillons de formater les cellules de cette plage en utilisant les options **Ajuster le texte dans une cellule** et **Ajuster automatiquement la hauteur de ligne** Excel [options](https://support.microsoft.com/office/wrap-text-in-a-cell-2a18cff5-ccc1-4bce-95e4-f0d4f3ff4e84).

Vous pouvez ajouter plusieurs autres composants **Plage** entre les composants **Plage** en option pour spécifier comment un document généré est rempli.

Si l’ensemble des composants **Plage** imbriqués sous le composant **Page** n’est pas conforme à la structure décrite précédemment, une [erreur](er-components-inspections.md#i17) de validation se produit au moment de la conception dans le concepteur de format ER. Le message d’erreur vous informe que le problème peut causer des problèmes lors de l’exécution.

> [!NOTE]
> Pour générer une sortie correcte, ne spécifiez pas de liaison pour tout composant **Plage** sous le composant **Page** si la propriété **Direction de réplication** pour ce composant **Plage** est défini sur **Pas de réplication**, et la plage est configurée pour générer des en-têtes ou des pieds de page.

Si vous souhaitez que la somme associée à pagination et le décompte des totaux cumulés et des totaux par page, nous vous recommandons de configurer les sources de données [Collecte de données](er-data-collection-data-sources.md) requises. Pour découvrir comment utiliser le composant **Page** pour paginer un document Excel généré, exécutez les procédures dans [Concevoir un format ER pour paginer un document généré au format Excel](er-paginate-excel-reports.md).

### <a name="limitations"></a><a name="page-component-limitations"></a>Limitations

Lorsque vous utilisez le composant **Page** pour la pagination Excel, vous ne connaîtrez pas le nombre final de pages dans un document généré tant que la pagination n’est pas terminée. Par conséquent, vous ne pouvez pas calculer le nombre total de pages en utilisant des formules ER et imprimer le nombre correct de pages d’un document généré sur n’importe quelle page avant la dernière page.

> [!TIP]
> Pour obtenir ce résultat dans un en-tête ou un pied de page Excel en utilisant la [mise en page](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) Excel spéciale pour les en-têtes et les pieds de page.

Les composants de **Page** configurés ne sont pas pris en compte lorsque vous mettez à jour un modèle Excel au format modifiable dans Dynamics 365 Finance version 10.0.22. Cette fonctionnalité est prise en compte pour les versions ultérieures de Finance.

Si vous configurez votre modèle Excel pour utiliser la [mise en forme conditionnelle](/office/dev/add-ins/excel/excel-add-ins-conditional-formatting), cela peut ne pas fonctionner comme prévu dans certains cas.

### <a name="applicability"></a>Conditions d’application

Le composant **Page** fonctionne pour le composant au format de [fichier Excel](er-fillable-excel.md#excel-file-component) uniquement lorsque ce composant est configuré pour utiliser un modèle dans Excel. Si vous [remplacez](tasks/er-design-configuration-word-2016-11.md) le modèle Excel avec un modèle Word, puis exécutez le format ER modifiable, le composant **Page** est ignoré.

Le composant **Page** ne fonctionne que lorsque la fonctionnalité **Activer l’utilisation de la bibliothèque EPPlus dans le cadre d’états électroniques** est activée. Une exception est levée au moment de l’exécution si les états électroniques essaient de traiter le composant **Page** lorsque cette fonctionnalité est désactivée.

> [!NOTE]
> Une exception est levée au moment de l’exécution si un format ER traite le composant **Page** pour un modèle Excel qui contient au moins une formule qui fait référence à une cellule qui n’est pas valide. Pour éviter les erreurs d’exécution, corrigez le modèle Excel comme décrit dans [Comment corriger une erreur #REF!](https://support.microsoft.com/office/how-to-correct-a-ref-error-822c8e46-e610-4d02-bf29-ec4b8c5ff4be).

## <a name="footer-component"></a>Composant Pied de page

Le composant **Pied de page** est utilisé pour remplir les pieds de page au bas d’une feuille de calcul générée dans un classeur Excel.

> [!NOTE]
> Vous pouvez ajouter ce composant pour chaque composant **Feuille** afin de spécifier différents pieds de page pour différentes feuilles de calcul dans un classeur Excel généré.

Lorsque vous configurez un composant **Pied de page** individuel, vous pouvez utiliser la propriété **Apparence en-tête/pied de page** pour spécifier les pages pour lesquelles le composant est utilisé. Les valeurs disponibles sont les suivantes :

- **Tout** – Exécutez le composant **Pied de page** configuré pour n’importe quelle page de la feuille de calcul Excel parente.
- **Premier** – Exécutez le composant **Pied de page** configuré uniquement pour la première page de la feuille de calcul Excel parente.
- **Pair** – Exécutez le composant **Pied de page** configuré uniquement pour les pages paires de la feuille de calcul Excel parente.
- **Impair** – Exécutez le composant **Pied de page** configuré uniquement pour les pages impaires de la feuille de calcul Excel parente.

Pour un même composant **Feuille**, vous pouvez ajouter plusieurs composants **Pied de page**, chacun ayant une valeur différente pour la propriété **Apparence en-tête/pied de page**. De cette façon, vous pouvez générer différents pieds de page pour différents types de pages dans une feuille de calcul Excel.

> [!NOTE]
> Assurez-vous que chaque composant **Pied de page** que vous ajoutez à un même composant **Feuille**, a une valeur différente pour la propriété **Apparence en-tête/pied de page**. Sinon, une [erreur de validation](er-components-inspections.md#i16) se produit. Le message d’erreur que vous recevez vous avertit de l’incohérence.

Sous le composant **Pied de page** ajouté, ajoutez les composants imbriqués requis de type **Texte\\Chaîne**, **Texte\\DateTime** ou d’un autre type. Configurez les liaisons de ces composants pour spécifier la manière dont votre pied de page est rempli.

Vous pouvez également utiliser des [codes de mise en forme](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) pour mettre en forme correctement le contenu d’un pied de page généré. Pour apprendre à utiliser cette approche, suivez les étapes de la section [Exemple 1](#example-1), plus loin dans cette rubrique.

> [!NOTE]
> Lorsque vous configurez des formats ER, assurez-vous de prendre en compte la [limite](https://support.microsoft.com/office/excel-specifications-and-limits-1672b34d-7043-467e-8e27-269d656771c3) Excel et le nombre maximum de caractères pour un seul en-tête ou pied de page.

## <a name="header-component"></a>Composant d’en-tête

Le composant **En-tête** est utilisé pour remplir les en-têtes en haut d’une feuille de calcul générée dans un classeur Excel. Il est utilisé de la même manière que le composant **Pied de page**.

## <a name="edit-an-added-er-format"></a>Modifier un format ER ajouté

### <a name="update-a-template"></a>Mettre à jour un modèle

Vous pouvez sélectionner **Mettre à jour à partir d’Excel** sur l’onglet **Importer** du volet Actions pour importer un modèle mis à jour dans un format ER modifiable. Au cours de ce processus, un modèle du composant **Fichier\\Excel** sera remplacé par un nouveau modèle. Le contenu du format ER modifiable sera synchronisé avec le contenu du modèle ER mis à jour.

- Un nouveau composant au format ER sera automatiquement créé pour chaque nom Excel si le composant au format ER n’est pas trouvé dans le format modifiable.
- Chaque composant au format ER sera supprimé du format ER modifiable si aucun nom Excel approprié n’est trouvé.

> [!NOTE]
> Définissez l’option **Créer un élément de format de feuille Excel** sur **Oui** pour créer l’élément **Feuille** facultatif au format ER modifiable.
>
> Si le format ER modifiable contenait à l’origine des éléments **Feuille**, nous vous recommandons de définir l’option **Créer un élément de format de feuille Excel** sur **Oui** lorsque vous importez un modèle mis à jour. Sinon, tous les éléments imbriqués de l’élément **Feuille** original seront créés de toutes pièces. Par conséquent, toutes les liaisons des éléments de format recréés seront perdues dans le format ER mis à jour.

![Option Créer un élément de format de feuille Excel dans la boîte de dialogue Mettre à jour à partir d’Excel.](./media/er-excel-format-update-template.png)

Pour en savoir plus sur cette fonctionnalité, suivez les étapes de rubrique [Modifier des formats de gestion des états électroniques en réappliquant des modèles Excel](modify-electronic-reporting-format-reapply-excel-template.md).

## <a name="validate-an-er-format"></a>Valider un format ER

Lorsque vous validez un format ER qui peut être modifié, une vérification de cohérence est effectuée pour vous assurer que le nom Excel est présent dans le modèle Excel actuellement utilisé. Vous serez informé de toute incohérence. Pour certaines incohérences, l’option de résolution automatique des problèmes sera proposée.

![Message d’erreur de validation.](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Contrôler le calcul des formules Excel

Lorsqu’un document sortant dans un format du classeur Microsoft Excel est généré, certaines cellules de ce document peuvent contenir des formules Excel. Quand la fonctionnalité **Activer l’utilisation de la bibliothèque EPPlus dans le cadre de reporting électronique** est activée, vous pouvez contrôler le moment où les formules sont calculées en modifiant la valeur du [paramètre](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows) **Options de calcul** dans le modèle Excel utilisé :

- Sélectionnez **Automatique** pour recalculer toutes les formules dépendantes chaque fois qu’un document généré est ajouté par de nouvelles plages, cellules, etc.

    >[!NOTE]
    > Cela peut entraîner un problème de performances pour les modèles Excel contenant plusieurs formules associées.

- Sélectionnez **Manuel** pour éviter le recalcul de formule lors de la génération d’un document.

    >[!NOTE]
    > Le recalcul de la formule est forcé manuellement lorsqu’un document généré est ouvert pour un aperçu à l’aide d’Excel.
    > N’utilisez pas cette option si vous configurez une destination ER qui suppose l’utilisation d’un document généré sans son aperçu dans Excel (conversion PDF, envoi par e-mail, etc.) car le document généré peut ne pas contenir de valeurs dans des cellules contenant des formules.

## <a name="example-1-format-footer-content"></a><a name="example-1"></a>Exemple 1 : Mettre en forme le contenu d’un pied de page

1. Utilisez les configurations ER fournies pour [générer](er-generate-printable-fti-forms.md) une facture financière imprimable.
2. Vérifiez le pied de page du document généré. Notez qu’il contient des informations sur le numéro de page actuel et le nombre total de pages dans le document.

    ![Vérifier le pied de page d’un document généré au format Excel.](./media/er-fillable-excel-footer-1.gif)

3. Dans le concepteur de format ER, [ouvrez](er-generate-printable-fti-forms.md#features-that-are-implemented-in-the-sample-er-format) l’exemple de format ER afin de le vérifier.

    Le pied de page de la feuille de calcul **Facture** est généré en fonction des paramètres de deux composants **Chaîne** qui se trouvent sous le composant **Pied de page** :

    - Le premier composant **Chaîne** remplit les codes de mise en forme spéciaux suivants pour forcer Excel à appliquer une mise en forme spécifique :

        - **&C** – Alignez le texte du pied de page au centre.
        - **&"Segoe UI,Regular"&8** – Présentez le texte du pied de page dans la police "Segoe UI Regular" en taille 8 points.

    - Le deuxième composant **Chaîne** remplit le texte contenant le numéro de page actuel et le nombre total de pages dans le document actuel.

    ![Vérifier le composant de format ER Pied de page sur la page Concepteur de format.](./media/er-fillable-excel-footer-2.png)

4. Personnalisez l’exemple de format ER pour modifier le pied de page actuel :

    1. [Créez](er-quick-start2-customize-report.md#DeriveProvidedFormat) un format ER **Facture financière (Excel) personnalisé** dérivé basé sur l’exemple de format ER.
    2. Ajoutez la première nouvelle paire de composants **Chaîne** pour le composant **Pied de page** de la feuille de calcul **Facture** :

        1. Ajoutez un composant **Chaîne** qui aligne le nom de l’entreprise sur la gauche et le présente en police "Segoe UI Regular" de taille 8 points (**"&L&"Segoe UI,Regular"&8**).
        2. Ajoutez un composant **Chaîne** qui remplit le nom de l’entreprise (**model.InvoiceBase.CompanyInfo.Name**).

    3. Ajoutez la seconde nouvelle paire de composants **Chaîne** pour le composant **Pied de page** de la feuille de calcul **Facture** :

        1. Ajoutez un composant **Chaîne** qui aligne la date de traitement sur la droite et la présente en police "Segoe UI Regular" de taille 8 points (**""&R&"Segoe UI,Regular"&8**).
        2. Ajouter un composant **Chaîne** qui remplit la date de traitement dans un format personnalisé (**"&nbsp;"&DATEFORMAT(SESSIONTODAY(), "yyyy-MM-dd")**).

        ![Vérification du composant de format ER Pied de page sur la page Concepteur de format.](./media/er-fillable-excel-footer-3.png)

    4. [Complétez](er-quick-start2-customize-report.md#CompleteDerivedFormat) la version brouillon du format ER **Facture financière (Excel) personnalisé** dérivé.

5. [Configurez](er-generate-printable-fti-forms.md#configure-print-management) la gestion de l’impression pour utiliser le format ER **Facture financière (Excel) personnalisé** dérivé au lieu de l’exemple de format ER.
6. Générez un document FTI imprimable et consultez le pied de page du document généré.

    ![Vérification du pied de page d’un document généré au format Excel.](./media/er-fillable-excel-footer-4.gif)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des États électroniques](general-electronic-reporting.md)

[Concevoir une configuration pour générer des états au format OPENXML](tasks\er-design-reports-openxml-2016-11.md)

[Modifier des formats de gestion des états électroniques en réappliquant des modèles Excel](modify-electronic-reporting-format-reapply-excel-template.md)

[Utiliser des plages extensibles horizontalement pour ajouter dynamiquement des colonnes dans les états Excel](tasks/er-horizontal-1.md)

[Intégrer des images et des formes dans les documents que vous générez ER à l’aide de la gestion des états électroniques (ER)](electronic-reporting-embed-images-shapes.md)

[Configurer la gestion des états électroniques (ER) pour extraire les données dans Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
