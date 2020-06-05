---
title: Créer une configuration pour générer des documents au format Excel
description: Cette rubrique fournit des informations sur la conception d'un format d'états électroniques (ER) pour renseigner un modèle Excel, puis générer des documents sortants au format Excel.
author: NickSelin
manager: AnnBe
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e889b08f10c5d0c95fed7c9e422340706bdd154a
ms.sourcegitcommit: 67ce81c57194afb26a04ae4c0b7509e0efa32afc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/14/2020
ms.locfileid: "3375811"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>Créer une configuration pour générer des documents au format Excel

[!include[banner](../includes/banner.md)]

Vous pouvez concevoir une configuration de format [états électroniques (ER)](general-electronic-reporting.md) ayant un [composant de format](general-electronic-reporting.md#FormatComponentOutbound) ER que vous pouvez configurer pour générer un document sortant dans un format de classeur Microsoft Excel. Des composants spécifiques au format ER doivent être utilisés à cet effet.

Pour en savoir plus sur cette fonctionnalité, suivez les étapes de la rubrique : [Concevoir une configuration pour générer des états au format OPENXML](tasks/er-design-reports-openxml-2016-11.md).

## <a name="add-a-new-er-format"></a>Ajouter un nouveau format ER

Lorsque vous ajoutez une nouvelle configuration de format ER pour générer un document sortant dans un format de classeur Excel, vous devez soit sélectionner la valeur **Excel** pour l'attribut **Type de format** du format ou laisser l'attribut **Type de format** vide.

- Si vous sélectionnez **Excel**, vous pouvez configurer le format pour générer un document sortant uniquement au format Excel.
- Si vous laissez l'attribut vide, vous pouvez configurer le format pour générer un document sortant dans n'importe quel format pris en charge par l'infrastructure ER.

Pour configurer le composant de format ER de la configuration, sélectionnez **Concepteur** dans le volet Actions et ouvrez le composant de format ER pour le modifier dans le concepteur d'opération de gestion des états électroniques.

![Page Configurations](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Composant de fichier Excel

### <a name="manual-entry"></a>Saisie manuelle

Vous devez ajouter un composant de **fichier\\Excel** au format ER configuré pour générer un document sortant au format Excel.

![Composant de fichier Excel](./media/er-excel-format-add-file-component.png)

Pour spécifier la mise en page du document sortant, attachez un classeur Excel doté de l'extension .xlsx au composant **Fichier\\Excel** comme modèle pour les documents sortants.

> [!NOTE]
> Lorsque vous joignez manuellement un modèle, vous devez utiliser un [type de document](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) configuré à cet effet dans les [Paramètres ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Ajout d'une pièce jointe au composant Fichier\Excel](./media/er-excel-format-add-file-component2.png)

Pour spécifier comment le modèle joint sera rempli lorsque vous exécuterez le format ER configuré, vous devez ajouter les composants **Feuille**, **Plage** et **Cellule** au composant **Fichier\\Excel**. Chaque composant imbriqué doit être associé à un élément nommé Excel.

### <a name="template-import"></a>Importation de modèles

Vous pouvez sélectionner **Importer à partir d'Excel** sur l'onglet **Importer** du volet Actions pour importer un nouvelle modèle dans un format ER vide. Dans cet exemple, un composant **Fichier\\Excel** sera créé automatiquement et le modèle importé y sera attaché. Tous les composants ER requis seront également créés automatiquement, en fonction de la liste des éléments nommés Excel découverts.

![Sélection de l'importation depuis Excel](./media/er-excel-format-import-template.png)

> [!NOTE]
> Définissez l'option **Créer un élément de format de feuille Excel** sur **Oui** pour créer l'élément **Feuille** facultatif au format ER modifiable.

## <a name="sheet-component"></a>Composant de feuille

Le composant **Feuille** indique une feuille de calcul du classeur Excel joint à remplir. Le nom de la feuille de calcul dans un modèle Excel est défini dans la propriété **Feuille** de ce composant.

> [!NOTE]
> Ce composant est facultatif pour les classeurs Excel qui contiennent une seule feuille de calcul.

Sur l'onglet **Mise en correspondance** du concepteur d'opération ER, vous pouvez configurer la propriété **Activé** pour un composant **Feuille** pour spécifier si le composant doit être placé dans un document généré :

- Si une expression de la propriété **Activé** est configurée pour renvoyer **Vrai** lors de l'exécution ou si aucune expression n'est configurée, la feuille de calcul appropriée sera placée dans le document généré.
- Si une expression de la propriété **Activé** est configurée pour renvoyer la valeur **Faux** au moment de l'exécution, le document généré ne contiendra pas de feuille de calcul.

![Exemple de composant feuille](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Composant de gamme

Le composant **Plage** indique une plage Excel qui doit être contrôlée par ce composant ER. Le nom de la plage est défini dans la propriété **Plage Excel** de ce composant.

La propriété **Direction de la réplication** spécifie si et comment la plage sera répétée dans un document généré :

- Si la propriété **Direction de la réplication** est définie sur **Pas de réplication**, la plage Excel appropriée ne sera pas répétée dans le document généré.
- Si la propriété **Direction de la réplication** est définie sur **Vertical**, la plage Excel appropriée sera répétée dans le document généré. Chaque plage répliquée est placée sous la plage d'origine dans un modèle Excel. Le nombre de répétitions est défini par le nombre d'enregistrements dans une source de données du type **Liste d'enregistrements** lié à ce composant ER.
- Si la propriété **Direction de la réplication** est définie sur **Horizontal**, la plage Excel appropriée sera répétée dans le document généré. Chaque plage répliquée est placée à droite de la plage d'origine dans un modèle Excel. Le nombre de répétitions est défini par le nombre d'enregistrements dans une source de données du type **Liste d'enregistrements** lié à ce composant ER.

Pour en savoir plus sur la réplication horizontale, suivez les étapes de la rubrique [Utiliser des plages extensibles horizontalement pour ajouter dynamiquement des colonnes dans les états Excel](tasks/er-horizontal-1.md).

Le composant **Plage** peut avoir d'autres composants ER imbriqués qui sont utilisés pour entrer des valeurs dans les plages nommées Excel appropriées.

- Si l'un des composants du groupe **Texte** est utilisé pour entrer des valeurs, la valeur est entrée dans une plage Excel en tant que valeur de texte.

    > [!NOTE]
    > Utilisez ce modèle pour formater les valeurs entrées en fonction des paramètres régionaux définis dans l'application.

- Si le composant **Cellule** du groupe **Excel** est utilisé pour entrer des valeurs, la valeur est entrée dans une plage Excel en tant que valeur du type de données défini par la liaison de ce composant **Cellule**(par exemple, **Chaîne**, **Réel**, ou **Entier**).

    > [!NOTE]
    > Utilisez ce modèle pour permettre à l'application Excel de formater les valeurs entrées en fonction des paramètres régionaux de l'ordinateur local qui ouvre le document sortant.

Sur l'onglet **Mise en correspondance** du concepteur d'opération ER, vous pouvez configurer la propriété **Activé** pour un composant **Plage** pour spécifier si le composant doit être placé dans un document généré :

- Si une expression de la propriété **Activé** est configurée pour renvoyer **Vrai** lors de l'exécution ou si aucune expression n'est configurée, la plage appropriée sera renseignée dans le document généré.
- Si une expression de la propriété **Activé** est configurée pour renvoyer la valeur **Faux** lors de l'exécution et si la plage ne représente pas les lignes et les colonnes entières, la plage appropriée ne sera pas renseignée dans le document généré.
- Si une expression de la propriété **Activé** est configurée pour renvoyer la valeur **Faux** lors de l'exécution et si cette plage représente les lignes et les colonnes entières, celles-ci seront masquées dans le document.

## <a name="cell-component"></a>Composant Cellule

Le composant **Cellule** est utilisé pour remplir des cellules, des formes et des images nommées Excel. Pour indiquer un objet nommé Excel qui doit être rempli par un composant **Cellule** ER, vous devez spécifier le nom de cet objet dans la propriété **Plage Excel** du composant **Cellule**.

Sur l'onglet **Mise en correspondance** du concepteur d'opération ER, vous pouvez configurer la propriété **Activé** pour un composant **Cellule** pour spécifier si l'objet doit être renseigné dans un document généré :

- Si une expression de la propriété **Activé** est configurée pour renvoyer **Vrai** lors de l'exécution ou si aucune expression n'est configurée, l'objet approprié sera renseigné dans le document généré. La liaison de ce composant **Cellule** spécifie une valeur qui est placée dans l'objet approprié.
- Si une expression de la propriété **Activé** est configurée pour renvoyer **Faux** au moment de l'exécution, l'objet approprié ne sera pas renseigné dans le document généré.

Lorsqu'un composant **Cellule** est configuré pour entrer une valeur dans une cellule, il peut être lié à une source de données qui renvoie la valeur d'un type de données primitif (par exemple, **Chaîne**, **Réel**, ou **Entier**). Dans ce cas, la valeur est entrée dans la cellule en tant que valeur du même type de données.

Lorsqu'un composant **Cellule** est configuré pour entrer une valeur dans un format Excel, il peut être lié à une source de données qui renvoie une valeur d'un type de données primitif (par exemple, **Chaîne**, **Réel**, ou **Entier**). Dans ce cas, la valeur est entrée au format Excel en tant que texte. Pour les valeurs de types de données qui ne sont pas définies en tant que **Chaîne**, la conversion en texte se fait automatiquement.

> [!NOTE]
> Vous pouvez configurer un composant **Cellule** pour remplir une forme uniquement dans les cas où une propriété de texte est prise en charge.

Lorsqu'un composant **Cellule** est configuré pour entrer une valeur dans une image Excel, il peut être lié à une source de données qui renvoie la valeur d'un type de données **Conteneur** qui représente une image au format binaire. Dans ce cas, la valeur est entrée dans l'image Excel sous forme d'image.

> [!NOTE]
> Chaque image et forme Excel est considérée comme étant ancrée par son coin supérieur gauche à une cellule ou une plage Excel spécifique. Si vous souhaitez répliquer une image ou une forme Excel, vous devez configurer la cellule ou la plage à laquelle il est ancré en tant que cellule ou plage répliquée.

Pour en savoir plus sur l'incorporation d'images et de formes, consultez [Intégrer des images et des formes dans les documents que vous générez ER à l'aide de la gestion des états électroniques (ER)](electronic-reporting-embed-images-shapes.md).

## <a name="page-break-component"></a>Composant Saut de page

Le composant **Saut de page** oblige Excel à démarrer une nouvelle page. Ce composant n'est pas requis lorsque vous souhaitez utiliser la pagination par défaut d'Excel, mais vous devez l'utiliser lorsque vous souhaitez qu'Excel suive votre format ER pour structurer la pagination.

## <a name="edit-an-added-er-format"></a>Modifier un format ER ajouté

### <a name="update-a-template"></a>Mettre à jour un modèle

Vous pouvez sélectionner **Mettre à jour à partir d'Excel** sur l'onglet **Importer** du volet Actions pour importer un modèle mis à jour dans un format ER modifiable. Au cours de ce processus, un modèle du composant **Fichier\\Excel** sera remplacé par un nouveau modèle. Le contenu du format ER modifiable sera synchronisé avec le contenu du modèle ER mis à jour.

- Un nouveau composant au format ER sera automatiquement créé pour chaque nom Excel si le composant au format ER n'est pas trouvé dans le format modifiable.
- Chaque composant au format ER sera supprimé du format ER modifiable si aucun nom Excel approprié n'est trouvé.

> [!NOTE]
> Définissez l'option **Créer un élément de format de feuille Excel** sur **Oui** pour créer l'élément **Feuille** facultatif au format ER modifiable.
>
> Si le format ER modifiable contenait à l'origine des éléments **Feuille**, nous vous recommandons de définir l'option **Créer un élément de format de feuille Excel** sur **Oui** lorsque vous importez un modèle mis à jour. Sinon, tous les éléments imbriqués de l'élément **Feuille** original seront créés de toutes pièces. Par conséquent, toutes les liaisons des éléments de format recréés seront perdues dans le format ER mis à jour.

![Option Créer un élément de format de feuille Excel dans la boîte de dialogue Mettre à jour à partir d'Excel](./media/er-excel-format-update-template.png)

Pour en savoir plus sur cette fonctionnalité, suivez les étapes de rubrique [Modifier des formats de gestion des états électroniques en réappliquant des modèles Excel](modify-electronic-reporting-format-reapply-excel-template.md).

## <a name="validate-an-er-format"></a>Valider un format ER

Lorsque vous validez un format ER qui peut être modifié, une vérification de cohérence est effectuée pour vous assurer que le nom Excel est présent dans le modèle Excel actuellement utilisé. Vous serez informé de toute incohérence. Pour certaines incohérences, l'option de résolution automatique des problèmes sera proposée.

![Validation et message d'erreur](./media/er-excel-format-validate.png)


## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des États électroniques](general-electronic-reporting.md)

[Concevoir une configuration pour générer des états au format OPENXML](tasks\er-design-reports-openxml-2016-11.md)

[Modifier des formats de gestion des états électroniques en réappliquant des modèles Excel](modify-electronic-reporting-format-reapply-excel-template.md)

[Utiliser des plages extensibles horizontalement pour ajouter dynamiquement des colonnes dans les états Excel](tasks/er-horizontal-1.md)

[Intégrer des images et des formes dans les documents que vous générez ER à l'aide de la gestion des états électroniques (ER)](electronic-reporting-embed-images-shapes.md)

[Configurer la gestion des états électroniques (ER) pour extraire les données dans Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)
