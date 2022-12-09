---
title: Définitions de ligne dans le générateur d’états financiers
description: Une définition de ligne est un composant de l’état, ou un bloc élémentaire, qui spécifie le contenu de chaque ligne d’un état financier.
author: aprilolson
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.form: FinancialReports
ms.openlocfilehash: 3325f76f991ea6d2a1b6131f299460e529d63d38
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802443"
---
# <a name="row-definitions-in-financial-report-designer"></a>Définitions de ligne dans le générateur d’états financiers

[!include [banner](../includes/banner.md)]

Une définition de ligne est un composant de l’état, ou un bloc élémentaire, qui spécifie le contenu de chaque ligne d’un état financier. Une définition de ligne peut être combinée avec les définitions de colonne, les définitions d’arborescence de génération d’état et les définitions d’état pour créer un groupe de blocs élémentaires pouvant être utilisé par plusieurs sociétés.

## <a name="create-a-row-definition"></a>Création d’une définition de ligne

1. Dans Report Designer, dans le volet de navigation, cliquez sur **Définitions de ligne**.
2. Dans le menu **Fichier**, cliquez sur **Nouveau**, puis cliquez sur **Définition de ligne**. Pour plus d’informations sur le contenu de chaque cellule, voir [Modifier les cellules de définition de ligne](modify-row-definition-cells-financial-reporting.md).

## <a name="open-a-row-definition"></a>Ouvrir une définition de ligne
1. Dans Report Designer, dans le volet de navigation, cliquez sur **Définitions de ligne**.
2. Double-cliquez sur le nom de la définition de ligne à ouvrir.
3. Pour afficher tous blocs élémentaires associés à la définition de ligne, cliquez avec le bouton droit sur la définition de ligne, puis sélectionnez **Associations**.

## <a name="contents-of-a-row-definition"></a>Contenu d’une définition de ligne
Une définition de ligne peut contenir jusqu’à 20 000 lignes de dimensions financières et peut inclure les informations suivantes :

- Texte descriptif précisant le rapport en créant des titres de section, des lignes et des espaces tels que **Espèces** ou **Produit total**
- Liens vers des données financières, qui peuvent inclure des valeurs de dimension dans Microsoft Dynamics 365 Finance

    > [!NOTE]
    > Vous pouvez configurer une définition de ligne de manière à extraire les données du système des dimensions financières chaque fois que le rapport est généré.

- Totaux de ligne et formules basés sur les données financières associées

Généralement, chaque ligne d’une définition de ligne inclut un des types d’informations suivants :

- Références au système de dimensions financières
- Totaux ou calculs selon les données
- Mise en forme

Il existe deux méthodes pour entrer des informations dans une définition de ligne :

- Entrez les informations de ligne manuellement dans une nouvelle définition de ligne. Pour plus d’informations, voir [Modifier les cellules de définition de ligne](modify-row-definition-cells-financial-reporting.md).
- Le générateur d’états permet d’extraire des informations en ligne directement à partir des dimensions financières. Pour plus d’informations, reportez-vous à la section « Formules/lignes/unités associées » dans [Modifier les cellules de définition de ligne](modify-row-definition-cells-financial-reporting.md).

## <a name="add-dimensions-in-a-row-definition"></a>Ajout de dimensions à une définition de ligne
Une dimension est une intersection de données et de valeurs. Vous pouvez regrouper les données et les valeurs dans le générateur d’états. Vous pouvez ensuite classer et analyser les transactions plus en détail. Vous pouvez utiliser la boîte de dialogue **Insérer des lignes à partir de dimensions** pour ajouter plusieurs lignes à une définition de ligne en même temps. La boîte de dialogue affiche la colonne pour chaque dimension. Le tableau suivant décrit les informations que vous pouvez spécifier pour chaque dimension.

| Option                | Description |
|-----------------------|-------------|
| Dimension             | Le motif qui identifie la dimension à ajouter à la définition de ligne. Ce motif contient une esperluette (&) ou symbole dièse (\#) pour chaque position dans les dimensions. En général, utilisez les esperluettes pour la dimension Compte principal et tous les signes de numéros pour d’autres dimensions. |
| Début de la plage de dimensions | Première valeur de cette dimension à ajouter à la définition de ligne. |
| Fin de la plage de dimensions   | La dernière valeur pour cette dimension à ajouter à la définition de ligne. |

Pour ajouter des dimensions à une définition de ligne, procédez comme suit.

1. Dans Report Designer, cliquez sur **Définitions de ligne**, puis ouvrez ensuite la définition de ligne à modifier.
2. Dans le menu **Édition**, cliquez sur **Insérer des lignes à partir des dimensions**.
3. Dans la boîte de dialogue **Insérer des lignes à partir de dimensions**, dans la ligne **Dimensions**, sélectionnez la cellule pour que la dimension soit transférée vers la définition de ligne, puis cliquez sur **Tout &&&**.
4. Pour limiter la définition de ligne à une plage spécifique de valeurs de dimension, saisissez la valeur de dimension de début dans la cellule **Début de la plage de dimensions**, puis saisissez la valeur de dimension de fin dans la cellule **Fin de la plage de dimensions**. Pour inclure toutes les valeurs pour la dimension sélectionnée, laissez ces cellules vides.

    > [!NOTE]
    > Il se peut que les caractères génériques (\* ou ?) dans les plages de dimensions ne renvoient pas tous les résultats souhaités en fonction du mode d’assemblage des données de la base de données ERP.

5. Dans le champ **Code ligne de début**, spécifiez le code de ligne pour la première valeur de dimension à ajouter à la définition de ligne.
6. Dans le champ **Incrémenter chaque ligne de**, spécifiez l’intervalle entre les codes de ligne consécutifs. Par exemple, si le premier code ligne est 100 et que la valeur d’incrément est 30, les premières lignes possèdent les codes 100, 130, 160, 190 et 220. Utilisez une valeur d’incrément qui laisse un espace suffisant pour insérer de nouvelles lignes de format et de formule.
7. Cliquez sur **OK**. Pour chaque valeur de dimension sélectionnée, une ligne est ajoutée à la définition de ligne.

## <a name="adjust-rounding-in-a-row-definition"></a>Ajustement de l’arrondi dans une définition de ligne
Si vous avez un bilan dans lequel les montants sont arrondis, les totaux peuvent être déséquilibrés. Ce problème peut se produire si, par exemple, vous utilisez l’option d’arrondissement sur un état Bilan et que la définition d’état spécifie également l’arrondi. Vous pouvez utiliser l’option **Ajustement d’arrondi** dans la définition de ligne afin d’équilibrer les montants dans les bilans. L’arrondi est désactivé ou modifié sur l’onglet **Paramètres** de la définition d’état. Le tableau suivant indique les montants validés arrondis. Dans ce tableau, les totaux des lignes 100 et 200 diffèrent lorsque l’arrondi est activé.

| Code de ligne | Montants sans arrondi | Montant avec arrondi au millier entier |
|----------|--------------------------|-----------------------------------------|
| 100      | 3,600                    | 4                                       |
| 200      | 3,700                    | 4                                       |
| Total    | 7,300                    | 8                                       |

Pour ajuster l’arrondi dans un bilan, procédez comme suit.

1. Dans Report Designer, cliquez sur **Définitions de ligne**, puis ouvrez ensuite la définition de ligne à modifier.
2. Dans le menu **Edition**, cliquez sur **Ajustement d’arrondi**.
3. Dans la boîte de dialogue **Ajustements d’arrondi**, saisissez les valeurs suivantes :

    - **Ligne d’ajustement d’arrondi** – Le code de ligne pour la ligne qui doit être ajusté au solde du bilan.
    - **Ligne Total de l’actif** – Le code de ligne pour la ligne du bilan contenant le total de l’actif.
    - **Ligne Total du passif et des capitaux propres** – Le code de ligne pour la ligne du bilan contenant le total du passif et des capitaux propres.
    - **Limite du montant d’ajustement** – Entier positif qui spécifie la limite des ajustements automatiques. Ce montant est comparé à la valeur absolue de l’erreur d’arrondi réelle.

    > [!NOTE]
    > Ces codes ligne doivent être liés à vos données financières. En d’autres termes, la ligne doit posséder une valeur de dimension dans sa cellule **Lien vers les dimensions financières**. Ne fait **pas** référence à une description (**DESC**), à une ligne calculée (**CALC**) ou totalisée (**TOT**).

Les montants de votre bilan s’équilibreront de manière équitable lorsque l’arrondi est activé.

> [!NOTE]
> La limite d’ajustement est appliquée en fonction de l’option **Précision de l’arrondi** spécifiée pour la définition de rapport. Par exemple, si vous choisissez d’arrondir votre rapport au millier et de saisir **2** dans le champ **Limite du montant d’ajustement**, vous recevez un message d’avertissement lorsque la valeur identifiée dans le champ **Ligne d’ajustement d’arrondi** augmente ou diminue de plus de 2 000 EUR.

## <a name="format-row-and-column-text"></a>Mise en forme du texte de ligne et de colonne
Vous pouvez personnaliser l’apparence de vos rapports en modifiant les polices et en mettant le texte en forme. Les sections suivantes expliquent comment mettre en forme l’apparence des lignes et colonnes des états.

### <a name="manage-font-styles"></a>Gestion des styles de police

Vous pouvez créer et modifier des styles de police pour l’état. Vous pouvez ensuite appliquer ces styles dans le document, ou à une ligne ou une colonne sur un état.

<table>
<tbody>
<tr>
<td><strong>Créer un style de police</strong></td>
<td>
<ol>
<li>Dans Report Designer, dans le menu <strong>Format</strong>, cliquez sur <strong>Styles et mise en forme</strong>.</li>
<li>Cliquez sur <strong>Nouveau</strong> dans la boîte de dialogue <strong>Styles et mise en forme</strong>, puis entrez un nom unique pour le nouveau style.</li>
<li>Sélectionnez vos polices, puis cliquez sur <strong>OK</strong>.</li>
</ol>
</td>
</tr>
<tr>
<td><strong>Modification d’un style de police</strong></td>
<td>
<ol>
<li>Dans Report Designer, dans le menu <strong>Format</strong>, cliquez sur <strong>Styles et mise en forme</strong>.</li>
<li>Dans la boîte de dialogue <strong>Styles et mise en forme</strong>, sélectionnez un style à modifier puis cliquez sur <strong>Modifier</strong>.</li>
<li>Sélectionnez vos polices, puis cliquez sur <strong>OK</strong>.</li>
</ol>
</td>
</tr>
<tr>
<td><strong>Application d’un style de police</strong></td>
<td>
<ol>
<li>Dans le Report Designer, dans une définition ou une définition de colonne, ou dans les en-têtes et les pieds de page, sélectionnez une ou plusieurs cellules.</li>
<li>Dans la liste <strong>Style</strong> de la barre d’outils, sélectionnez un style de police.</li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a>Mise en forme du texte de ligne

Cette mise en forme spécifiée dans la définition de colonne remplace la mise en forme spécifiée dans la définition de colonne et la définition d’état. Vous pouvez modifier le format du texte à l’aide des contrôles de la barre d’outils Mise en forme. Ces commandes sont des commandes Microsoft Windows standard.

1. Dans Report Designer, ouvrez la définition de ligne à modifier.
2. Sélectionnez les cellules à mettre en forme. Pour sélectionner plusieurs cellules, maintenez la touche CTRL enfoncée tout en sélectionnant les cellules souhaitées.
3. Cliquez sur le bouton de format à appliquer. Par exemple, pour mettre en retrait une ligne, sélectionnez la ligne, puis cliquez sur **Augmenter le retrait** ![Augmenter le retrait](media/indent.gif "Augmenter le retrait") sur la barre d’outils.

### <a name="adjust-columns-while-you-design-reports"></a>Ajustement des colonnes durant la création des rapports

Pour faciliter l’affichage des colonnes sur lesquelles vous travaillez dans la définition de ligne, vous pouvez ajuster la largeur d’une colonne et réduire (minimiser) ou afficher les colonnes dans le volet d’affichage. Les modifications que vous apportez affectent uniquement l’apparence à l’écran des colonnes. Elles n’affectent pas la mise en forme de colonne dans les états.

### <a name="change-the-width-of-a-column-in-the-view-pane"></a>Modifier la largeur d’une colonne dans le volet d’affichage

1. Dans Report Designer, ouvrez la définition de ligne à modifier.
2. Dans le menu **Format**, sélectionnez **Largeur de colonne**.
3. Dans la boîte de dialogue **Largeur de colonne**, entrez une valeur, puis cliquez sur **OK**. Sinon, vous pouvez faire glisser la limite droite d’une cellule d’en-tête de colonne pour modifier la largeur de la colonne.

### <a name="hide-columns-in-the-view-pane"></a>Masquer les colonnes dans le volet d’affichage

1. Dans Report Designer, ouvrez la définition de ligne à modifier.
2. Sélectionnez les colonnes à réduire.
3. Cliquez avec le bouton droit, puis cliquez sur **Masquer**.

### <a name="show-all-hidden-columns-in-the-view-pane"></a>Permet d’afficher toutes les colonnes masquées dans le volet d’affichage

1. Dans Report Designer, ouvrez la définition de ligne à modifier.
2. Cliquez avec le bouton droit sur la colonne réduite à afficher, puis cliquez sur **Afficher**.


## <a name="additional-resources"></a>Ressources supplémentaires

[États financiers](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
