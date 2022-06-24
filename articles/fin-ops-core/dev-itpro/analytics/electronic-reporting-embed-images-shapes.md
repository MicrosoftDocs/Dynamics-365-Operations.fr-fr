---
title: Intégrer des images et des formes dans les documents que vous générez ER à l’aide de la gestion des états électroniques (ER)
description: Cet article explique comment utiliser l’outil États électroniques pour générer des documents commerciaux contenant des images et des formes incorporées.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: fe0e6d6def50670566f44cfb5cd6bb4abe5faf15
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851046"
---
# <a name="embed-images-and-shapes-in-documents-that-you-generate-by-using-er"></a>Intégrer des images et des formes dans les documents que vous générez ER à l’aide de la gestion des états électroniques (ER)

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser l’outil États électroniques (ER) pour concevoir des rapports que vous pouvez exécuter pour générer les documents électroniques requis. Vous pouvez utiliser des documents Microsoft Excel ou Microsoft Word pour spécifier la disposition d’un état. Le Concepteur d’opérations de gestion des états électroniques vous permet de joindre un document Excel ou Word en tant que modèle pour l’état. Les éléments nommés suivants dans le modèle joint sont associés aux éléments de format de l’état ER. Les éléments de format de l’état sont liés aux sources de données. Ces éléments spécifient les données qui seront entrées, lors de l’exécution, dans les documents générés.

Cette nouvelle fonctionnalité va au-delà des capacités ER existantes pour la création de documents au format Microsoft Office. Pour plus d’informations, consultez les guides de tâches suivants. Vous trouverez ces guides de tâches sous le processus métier 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677).

- ER Concevoir une configuration pour générer des états au format OPENXML
- ER Concevoir une configuration pour générer des états au format Microsoft WORD

## <a name="embed-an-image-in-an-excel-document"></a>Incorporer une image dans un document Excel

### <a name="embed-an-image-in-an-excel-worksheet"></a>Incorporer une image dans une feuille de calcul Excel

Tout d’abord, vous devez ajouter un espace réservé pour l’image dans un document Excel. Ouvrez un classeur Excel et ajoutez une image comme espace réservé pour l’image que vous ajouterez plus tard. Utilisez ensuite l’outil ER pour ajouter une nouvelle configuration de format ER afin d’inclure l’état que vous concevez. Joignez le classeur Excel en tant que modèle pour le format du rapport, puis importez le contenu du classeur au format ER. La définition de format sera créée automatiquement. L’espace réservé pour l’image que vous avez ajouté sera inclus dans la définition du format ER en tant qu’élément **CELLULE**.

> [!NOTE]
> Vous pouvez spécifier manuellement la définition de format au lieu de l’importer. Lorsque vous enregistrez vos modifications, le format est validé.

Ensuite, liez l’élément **CELLULE** du format ER au champ de la source de données du format qui fournit les données de l’image au format binaire au moment de l’exécution. Lorsqu’un modèle de données ER est utilisé comme source de données d’un format, le type de données du champ doit être [Conteneur](er-formula-supported-data-types-composite.md#container). Actuellement, un champ de modèle de données ER qui a le type de données [Conteneur](er-formula-supported-data-types-composite.md#container) peut être lié à plusieurs types de sources de données qui renvoient des images au format binaire. Vous pouvez accéder à un champ dans une table de données et à un fichier attaché à l’enregistrement de la table de données à l’aide de la structure de gestion de documents.

> [!IMPORTANT]
> - Si vous souhaitez remplir l’espace réservé à l’image dans le document que vous créez à l’aide du modèle Excel, le format ER doit contenir l’élément **CELLULE** qui fait référence à l’élément d’image nommé dans le modèle Excel. Sinon, aucun espace réservé pour l’image n’apparaîtra dans la sortie de l’état. Si la liaison d’un élément **CELLULE** ne renvoie aucune donnée au moment de l’exécution, le document généré affichera l’espace réservé à l’image du modèle. Pour masquer une image dans le document que vous générez, définissez un élément **CELLULE** et précisez que l’expression **Activation** doit renvoyer la valeur **FALSE**.
> - Dans le modèle Excel, utilisez un nom unique pour chaque élément. Ces éléments comprennent des images et des cellules. Si vous dupliquez un nom d’élément, le contenu de l’état généré sera ambigu et déroutant.

### <a name="embed-images-in-the-header-and-footer-of-an-excel-worksheet"></a>Incorporer des images à l’en-tête et au pied de page d’une feuille de calcul Excel

Utilisez le document de classeur Excel comme modèle pour spécifier la disposition d’un état. Le classeur peut contenir plusieurs feuilles de calcul, chacune pouvant être conçue de manière à comporter un en-tête et un pied de page. Excel prend en charge jusqu’à trois images dans l’en-tête et le pied de page de chaque feuille de calcul. Les images peuvent être alignées à gauche, à droite ou au centre.

Dans Finance version 10.0.21, vous pouvez gérer les images d’en-tête et de pied de page générées par une solution ER dotée d’un modèle Excel.

Si vous souhaitez qu’une image par défaut apparaisse dans l’en-tête ou le pied de page d’un document généré, vous pouvez ajouter une image à l’en-tête ou au pied de page d’une feuille de calcul d’un modèle ER. Pour accéder à cette image dans votre format ER, vous devez ajouter le composant **Photo** sous le composant [En-tête](er-fillable-excel.md#header-component) ou [Pied de page](er-fillable-excel.md#footer-component) du format. Configurez l’alignement du composant **Image**, le cas échéant. 

Vous pouvez également utiliser le composant **Image** pour placer une image dans l’en-tête ou le pied de page d’un document généré lors de l’exécution, même si le modèle ne contient aucune image par défaut. Pour spécifier le contenu multimédia qui doit être placé dans l’en-tête ou le pied de page d’un document généré en tant que nouvelle image ou en remplacement d’une image par défaut, vous devez lier le composant **Image** à une source de données du type [Conteneur](er-formula-supported-data-types-composite.md#container) qui représente une image au format binaire.

Chaque composant **En-tête** ou **Pied de page** peut contenir un composant **Image** pour chaque alignement pris en charge : **Gauche**, **Centre** et **Droite**.

La propriété **Mettre à l’échelle la hauteur** du composant **Image** vous permet d’utiliser la liaison configurée pour contrôler la taille d’une image :

- Sélectionnez **Original** pour conserver la taille initiale de l’image.
- Sélectionnez **Relatif** pour mettre à l’échelle la hauteur de l’image proportionnellement à la hauteur de l’en-tête ou du pied de page qui contient cette image.

    - Dans ce cas, la hauteur de l’image doit être définie en pourcentage de l’en-tête ou du pied de page parent.
    - Si la valeur de mise à l’échelle dépasse 100 pour cent, l’image peut chevaucher la zone de données de la feuille de calcul correspondante.
    - Si la hauteur de l’image est modifiée lorsque la mise à l’échelle est appliquée, la largeur est également modifiée pour conserver le rapport hauteur/largeur d’origine de l’image.

- Sélectionnez **Absolu** pour redimensionner l’image en fonction des valeurs de hauteur et de largeur (en pixels) fournies au moment de la conception.

    - Si la hauteur spécifiée dépasse la hauteur de l’en-tête ou du pied de page parent, l’image peut chevaucher la zone de données de la feuille de calcul correspondante.

Vous pouvez également utiliser la propriété **Activée** du composant **Image** pour contrôler la visibilité d’une image insérée dans un document généré à l’aide de ce composant.

> [!NOTE]
> Vous devez utiliser le concepteur de format ER pour ajouter un composant **Image** au format ER modifiable. Vous ne pouvez pas ajouter le composant lorsque vous utilisez l’espace de travail [Gestion des documents commerciaux](er-business-document-management.md) pour éditer le modèle d’un document commercial.

Pour en savoir plus sur cette fonctionnalité, suivez les étapes indiquées dans [Concevoir un format ER pour générer un état au format Excel avec des images incorporées aux en-têtes ou pieds de page](er-embed-images-header-footer-excel-reports.md).

## <a name="embed-a-shape-in-an-excel-document"></a>Incorporer une forme dans un document Excel

Tout d’abord, vous devez ajouter un espace réservé pour la forme dans un document Excel. Ouvrez un classeur Excel et sélectionnez **Forme**, **Zone de texte** ou **WordArt** comme espace réservé pour la forme. Utilisez ensuite l’outil ER pour ajouter une nouvelle configuration de format ER afin d’inclure l’état que vous concevez. Joignez le classeur Excel en tant que modèle pour le format du rapport, puis importez le contenu du classeur au format ER. La définition de format sera créée automatiquement. L’espace réservé de forme que vous avez ajouté sera inclus à définition du format ER en tant qu’élément **CELLULE** qui fait référence à l’élément de forme Excel nommé.

> [!NOTE]
> Vous pouvez spécifier manuellement la définition de format au lieu de l’importer. Lorsque vous enregistrez vos modifications, le format est validé.

Ensuite, liez l’élément **CELLULE** du format ER au champ de la source de données du format qui fournit les données au moment de l’exécution. Ces données peuvent être converties en une chaîne de texte. Quand l’élément **CELLULE** au format ER fait référence à un élément de forme dans le modèle Excel qui prend en charge le texte, le texte fourni via cette liaison au moment de l’exécution sera affiché dans une forme dans le document généré.

> [!IMPORTANT]
> - Si vous souhaitez utiliser le modèle Excel qui inclut l’espace réservé de forme pour générer un nouveau document, le format ER doit contenir un élément **CELLULE** qui fait référence à l’élément de forme Excel. Sinon, aucun espace réservé pour la forme n’apparaîtra dans la sortie de l’état. Si la liaison d’un élément **CELLULE** qui fait référence à l’élément de forme Excel nommé ne renvoie aucune donnée au moment de l’exécution, le document généré affichera le texte de l’espace réservé pour la forme provenant du modèle Excel. Pour masquer une forme dans le document que vous générez, définissez un élément **CELLULE** qui fait référence à l’élément de forme Excel nommé et précisez que l’expression **Activation** doit renvoyer la valeur **FALSE**.
> - Dans le modèle Excel, utilisez un nom unique pour chaque élément. Ces éléments comprennent des formes et des cellules. Si vous dupliquez un nom d’élément, le contenu de l’état généré sera ambigu et déroutant.

## <a name="embed-an-image-in-a-word-document"></a>Incorporer une image dans un document Word
> [!IMPORTANT]
> Vous pouvez réutiliser le format ER qui utilise un modèle Excel pour créer des documents qui incluent des images incorporées. Dans le format ER, assurez-vous qu’un nom est spécifié pour l’élément **CELLULE** qui fait référence à un élément d’image nommé dans Excel et qui est lié à une source de données qui renvoie une image au moment de l’exécution.

Tout d’abord, vous devez configurer la disposition du document Word. Utilisez le contrôle **Contenu de l’image** pour créer un espace réservé pour l’image incorporée. Pour accéder à ce contrôle, vous devez d’abord rendre visible l’onglet **Développeur** sur le ruban Word.

Ensuite, supprimez le modèle Excel du format ER et joignez le document de modèle Word. Mettez à jour la référence au modèle et enregistrez vos modifications. La structure du format ER actuel est enregistrée dans le modèle Word en tant que nouvelle partie XML personnalisée nommée **État**.

Ensuite, enregistrez le modèle Word pour le format ER actuel sur votre ordinateur local. Ouvrez le modèle, puis le volet **Mappage XML**. Localisez la partie XML personnalisée nommée **État**, puis pointez sur l’élément **CELLULE** du rapport ER lié à une source de données qui renvoie une image au format binaire. Mappez l’élément de cette partie XML au contrôle **Contenu de l’image** sélectionné et enregistrez vos modifications.

[![incorporer des images.](./media/embed-images-shapes-01.png)](./media/embed-images-shapes-01.png)

Enfin, supprimez le modèle Word du format ER et joignez le document Word qui inclut les parties XML personnalisées mappées. Mettez à jour la référence de format au modèle et enregistrez les modifications que vous avez apportées à ce format ER.

## <a name="more-information"></a>Informations supplémentaires
Pour vous familiariser avec les détails de cette fonctionnalité, lisez l’ensemble de guides de tâches, **ER Créer des états aux formats MS Office avec des images incorporées**. Ces guides de tâches montrent comment incorporer les images d’un logo de compagnie et la signature d’une personne autorisée aux chèques de paiement générés à l’aide de l’outil ER dans des documents Excel et Word.

Le tableau suivant répertorie les fichiers nécessaires pour compléter les guides de tâches **ER Créer des états aux formats MS Office avec des images incorporées**. Téléchargez et enregistrez les fichiers sur votre ordinateur local.

| Description                                          | Nom de fichier                   |
|------------------------------------------------------|-----------------------------|
| Configuration de modèle de données ER                          | [Modèle pour les chèques.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| Configuration de format ER                              | [Format d’impression des chèques.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Image du logo de l’entreprise                                   | [Logo de société au format .png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Image de signature                                      | [Image de signature au format .png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Image de signature alternative                          | [Signature image 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Modèle Microsoft Word pour l’impression des chèques de paiement  | [Cheque template Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |
| Modèle Microsoft Excel pour l’impression des chèques de paiement | [Modèle de chèque.xlsx](https://download.microsoft.com/download/1/f/6/1f671963-73aa-48d5-ae69-45f21fe7dfb4/Cheque%20template.xlsx)        |

Le graphique suivant fournit un exemple de test d’impression pour un chèque de paiement généré à partir du modèle Excel.

[![Test d’impression de chèque de paiement.](./media/embed-images-shapes-02.png)](./media/embed-images-shapes-02.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
