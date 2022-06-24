---
title: Appliquer un style à l’interface d’exécution de l’atelier de production
description: L'article explique comment configurer les contrôles de formulaire afin que les styles d’exécution d’atelier de production par défaut leur soient appliqués.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: ad6ecd591353fe8ddc1a5b9049d65491fb58e98a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859138"
---
# <a name="style-the-production-floor-execution-interface"></a>Appliquer un style à l’interface d’exécution de l’atelier de production

[!include [banner](../includes/banner.md)]

L'article explique comment configurer les contrôles de formulaire afin que les styles d’exécution d’atelier de production par défaut leur soient appliqués.

## <a name="forms-and-dialogs"></a>Formulaires et boîtes de dialogue

Les styles peuvent être appliqués à un formulaire ou à une boîte de dialogue uniquement si les conditions suivantes sont remplies :

- Si le formulaire doit ressembler au formulaire de progression du rapport existant, le nom de votre formulaire ou de votre boîte de dialogue doit commencer par `JmgProductionFloorExecutionCustomInputDialog`.
- Le formulaire ou la boîte de dialogue peut contenir une partie de formulaire détaillée. Pour lui appliquer des styles, le nom de la partie de formulaire de détail doit commencer par `JmgProductionFloorExecutionCustomDetailsDialog`.
- Si le formulaire ou la boîte de dialogue doit avoir une vue simple, le nom de la vue simple doit commencer par `JmgProductionFloorExecutionCustomDialog`. Des exemples de formulaires qui ont une vue simple incluent le formulaire de démarrage et le formulaire d’activité indirecte.
- Tous les contrôles de la boîte de dialogue doivent être configurés comme décrit dans cet article.

> [!IMPORTANT]
> Les fonctionnalités mentionnées dans les deux premiers points de cette liste nécessitent Supply Chain Management version 10.0.19 ou ultérieure.

Les styles peuvent être appliqués au bouton **OK** dans une boîte de dialogue uniquement si les conditions suivantes sont remplies :

- Le bouton est contenu dans un groupe de formulaires.
- Le nom du groupe commence par `OkButtonGroup`.

Les styles peuvent être appliqués au bouton **Annuler** dans une boîte de dialogue uniquement si les conditions suivantes sont remplies :

- Le bouton est contenu dans un groupe de formulaires.
- Le nom du groupe commence par `CancelButtonGroup`.

### <a name="header"></a>En-tête

L’illustration suivante montre un en-tête de formulaire ou de boîte de dialogue type.

![En-tête de formulaire ou de boîte de dialogue typique.](media/pfe-styles-header.png "En-tête de formulaire ou de boîte de dialogue typique")

Dans Visual Studio, les en-têtes sont créés à l’aide d’une structure telle que celle illustrée dans l’illustration suivante.

![Structure de code typique pour créer un en-tête.](media/pfe-styles-header-code-structure.png "Structure de code typique pour créer un en-tête")

Pour ajouter du texte à votre en-tête, utilisez un code tel que l’exemple suivant.

```xpp
private void setCaption()
{
    HeaderFieldWithSeparatorText1.text("Report Progress");
    HeaderFieldWithSeparatorText2.text(ProdId);

    …

    HeaderFieldText.text(OprNum);
}
```

Lorsque vous écrivez votre code d’en-tête, appliquez les règles suivantes :

- Le nom du groupe principal doit être `TableRowHeaderGroup`.
- Chaque bloc de texte (séparé par des puces) doit commencer par `HeaderFieldWithSeparatorText`.
- Le dernier nom de texte doit commencer par `HeaderFieldText`.
- `CaptionImage` peut être ignoré.

### <a name="progress-indicator"></a>Indicateur de progression

Vous pouvez inclure un indicateur de progression, qui s’affiche à droite de l’en-tête. L’illustration suivante montre un indicateur de progression.

![Indicateur de progression typique.](media/pfe-styles-header-progress.png "Indicateur de progression typique")

Pour afficher l’indicateur de progression, le champ de texte doit être nommé `ShowProgress`.

## <a name="grid"></a>Grille

Les styles sont automatiquement appliqués. Aucune configuration spécifique n’est requise.

La grille doit avoir un style `TabularView`, et la méthode `run()` sur le formulaire personnalisé doit être remplacée, car une nouvelle grille n’est pas encore prise en charge. Ajoutez le code suivant.

```xpp
public void run()
{
    super();
    // To opt out a page from the new grid
    this.forceLegacyGrid();
}
```

Pour actualiser les données dans une vue principale, vous pouvez utiliser quelque chose comme `this.parmParentForm().updateLayout();` dans une méthode `click` de votre action. (Par un exemple, regardez la classe `JmgProductionFloorExecutionReportFeedbackAction`.) Assurez-vous simplement que `parmDataSource` est défini dans la méthode `init` de votre nouveau formulaire (`formCaller.parmDataSource(this.dataSource(1));`). Pour un exemple, regardez le formulaire `JmgProductionFloorExecutionMainGrid`.

## <a name="card-view"></a>Vue Carte

Les styles ne peuvent être appliqués aux commandes d’affichage des cartes que si les conditions suivantes sont remplies :

- Chaque vue de carte est contenue dans un groupe de formulaires.
- Le nom du groupe commence par `CardGroup` (par exemple, `CardGroupJobsView`).

L’illustration suivante montre une vue de carte qui n’a aucun contrôle à l’intérieur.

![Vue carte sans éléments.](media/pfe-styles-empty-card.png)

Les illustrations suivantes montrent des vues de carte contenant des commandes.

![Carte avec des éléments qui affichent Hz.](media/pfe-styles-elements.png)

![Fiche avec éléments pour une demande de maintenance.](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>Carte de visite

Les styles ne peuvent être appliqués aux commandes d’affichage des cartes de visite que si les conditions suivantes sont remplies :

- Chaque carte de visite est contenue dans un groupe de formulaires.
- Le nom du groupe commence par `BusinessCardGroup` (par exemple, `BusinessCardGroupJobsList`).

Définissez les propriétés suivantes sur la carte de visite :

- **Style :** *liste*
- **Style étendu :** *cardList*
- **Sélection multiple :** *Non*
- **Afficher étiquettes col. :** *Non*

![Carte de visite.](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>Case d’option

Les styles ne peuvent être appliqués aux cases d’options que si les conditions suivantes sont remplies :

- Chaque case d’option est contenue dans un groupe de formulaires.
- Le nom du groupe commence par `RadioTextBelow` ou `RadioTextRight`, selon l’endroit où vous souhaitez que le texte apparaisse.

Définissez les propriétés suivantes sur la case d’option :

- **Bouton bascule :** *Vérifier*
- **Activer la valeur :** *Activé* si la case d’option doit être sélectionnée ; autrement, *Désactivé*

L’illustration suivante montre un exemple où le texte apparaît sous les cases d’option.

![Cases d’option avec texte ci-dessous.](media/pfe-styles-radio-text-below.png)

L’illustration suivante montre un exemple où le texte apparaît à droite des cases d’option.

![Cases d’option avec texte à droite.](media/pfe-styles-radio-text-right.png)

### <a name="radio-buttons-in-internet-explorer"></a>Cases d’option dans Internet Explorer

Les styles de cases d’option ne sont pas pris en charge dans Internet Explorer. L’illustration suivante montre à quoi les cases d’option ressemblent dans Internet Explorer.

![Cases d’option dans Internet Explorer.](media/pfe-styles-browser.png)

## <a name="buttons"></a>Boutons

Les styles ne peuvent être appliqués aux boutons que si les conditions suivantes sont remplies :

- Chaque groupe de boutons est contenu dans un groupe de formulaires. Tous les boutons du groupe auront le même style.
- Il n’y a aucune exigence concernant le nom du groupe.

Définissez les propriétés suivantes sur les boutons :

- **Affichage bouton :** *TextWithImageLeft*
- **Image normale :** cette propriété ne peut pas être vide. Pour cet exemple, utilisez *CoffeeScript*.
- **Texte :** cette propriété ne peut pas être vide. Pour cet exemple, utilisez *Démarrer la pause*.
- **Largeur :** *Auto* ou *SizeToContent*
- **Hauteur :** *Auto* ou *SizeToContent*

### <a name="primary-button"></a>Bouton principal

Les styles ne peuvent être appliqués à un bouton principal que si les conditions suivantes sont remplies :

- Le bouton est contenu dans un groupe de formulaires.
- Le nom du groupe commence par `DefaultButtonGroup` ou `PrimaryButtonGroup` (par exemple, `DefaultButtonGroup10`).

![Bouton principal.](media/pfe-styles-first.png)

### <a name="secondary-button"></a>Bouton secondaire

Les styles ne peuvent être appliqués à un bouton secondaire que si les conditions suivantes sont remplies :

- Le bouton est contenu dans un groupe de formulaires.
- Le groupe s’appelle **Volet droit**, ou le nom du groupe commence par `SecondaryButtonGroup`.

![Bouton secondaire.](media/pfe-styles-second.png)

### <a name="third-group-button"></a>Bouton du troisième groupe

Les styles ne peuvent être appliqués à un bouton du troisième groupe que si les conditions suivantes sont remplies :

- Le bouton est contenu dans un groupe de formulaires.
- Le groupe s’appelle **Volet gauche**, ou le nom du groupe commence par `ThirdButtonGroup`.

![Bouton du troisième groupe.](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>Bouton du quatrième groupe

Les styles ne peuvent être appliqués à un bouton du quatrième groupe que si les conditions suivantes sont remplies :

- Le bouton est contenu dans un groupe de formulaires.
- Le nom du groupe commence par `FourthButtonGroup`.

Définissez les propriétés suivantes sur le bouton :

- **Affichage bouton :** *TextOnly*
- **Image normale :** cette propriété doit être vide.
- **Texte :** cette propriété ne peut pas être vide. Par exemple, utilisez *Visualiser* ou *Modifier*.
- **Largeur :** *Auto*
- **Hauteur :** *Auto*

![Bouton du quatrième groupe.](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>Bouton Fixe

Les styles ne peuvent être appliqués à un bouton fixe que si les conditions suivantes sont remplies :

- Le bouton est contenu dans un groupe de formulaires.
- Le nom du groupe commence par `FlatButtonGroup`.

Définissez les propriétés suivantes sur le bouton :

- **Bouton Afficher :** *ImageOnly*
- **Image normale :** cette propriété ne peut pas être vide. Pour cet exemple, utilisez *CoffeeScript*.
- **Texte :** cette propriété doit être vide.
- **Largeur :** *Auto* ou *SizeToContent*
- **Hauteur :** *Auto* ou *SizeToContent*

![Bouton Fixe.](media/pfe-styles-flat-button.png)

### <a name="continue-button"></a>Bouton Continuer

Les styles ne peuvent être appliqués à un bouton Continuer que si les conditions suivantes sont remplies :

- Le bouton est contenu dans un groupe de formulaires.
- Le nom du groupe commence par `ContinueButtonGroup`.

Définissez les propriétés suivantes sur le bouton :

- **Bouton Afficher :** *ImageOnly*
- **Image normale :** *En avant*
- **Texte :** cette propriété doit être vide.
- **Largeur :** *Auto* ou *SizeToContent*
- **Hauteur :** *Auto* ou *SizeToContent*

![Bouton Continuer.](media/pfe-styles-continue-button.png)

## <a name="combo-box"></a>Zone de liste modifiable

Une zone de liste déroulante est une combinaison de trois contrôles : un contrôle de saisie, un bouton qui efface le contrôle de saisie et un bouton qui exécute une recherche.

Les styles ne peuvent être appliqués à une zone de liste que si les conditions suivantes sont remplies :

- La zone de liste est contenue dans un groupe de formulaires.
- Le nom du groupe commence par `Combobox`.
- A l’intérieur du groupe, le premier contrôle est un contrôle `AxFormStringControl`. Ce contrôle affiche la valeur actuelle et c’est là que l’utilisateur entre la valeur requise.
- Le deuxième contrôle est un contrôle `CommonButton`, et son nom commence par `ClearButton`. Ce bouton doit contenir du code qui utilise la propriété `enable` pour afficher ou masquer le bouton. Par exemple, pour afficher ou masquer le bouton **Effacer** pendant que l’utilisateur tape des informations dans le contrôle de saisie, vous pouvez utiliser le code suivant.

    ```xpp
    public void textChange()
    {
        super();
        ClearButtonSerial.enabled(this.text()? true : false);
    }
    ```

    Vous devriez avoir une méthode où les données sont définies dans le contrôle d’entrée. Activez le bouton **Effacer** dans cette méthode. Voici un exemple :

    ```xpp
    public void setSerialId(str _serialId)
    {
        JmgTmpJobBundleProdFeedback.InventSerial = _serialId;
        ClearButtonSerial.enabled(_serialId? true : false);

        if (_serialId)
        {
            this.addSerialNumber();
        }
    }
    ```

    Utilisez le code suivant pour la méthode `clicked` du bouton **Effacer**.

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    Définissez la valeur du contrôle d’entrée, `AxFormStringControl`, lorsque le formulaire est initialisé en utilisant la méthode `init`. Si la valeur n’est pas vide, activez le bouton **Effacer**. Si la valeur est vide, désactivez le bouton **Effacer**.

- Le troisième contrôle est un contrôle `CommonButton`, et son nom commence par `SearchButton`.

L’illustration suivante montre deux contrôles de zone de liste déroulante. La zone de liste déroulante sur la gauche a une zone de textEffacere, et le bouton **Effacer** est désactivé. La zone de liste déroulante sur la droite contient du texte dans la zone de texte, et le bouton **Effacer** est activé.

![Zones de liste déroulante avec et sans bouton Effacer.](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>Filtre rapide

Le contrôle de filtre rapide ajoute un champ de recherche à la page. Vous pouvez appliquer des styles à un filtre rapide à condition que les conditions suivantes soient remplies :

- Le filtre rapide est contenu dans un groupe de formulaires.
- Le nom du groupe commence par `SearchInputGroup`.
- À l’intérieur du groupe, le premier contrôle est un contrôle `QuickFilter`. (Ce contrôle est où l’utilisateur entre la chaîne de recherche.)
- Le deuxième contrôle est un `FormStaticTextControl` qui s’appelle `NumberOfResults`. (Ce contrôle est facultatif. S’il est inclus, il indique le nombre d’éléments trouvés.)
- Le troisième contrôle est un contrôle `CommonButton`, et son nom commence par `ClearButton`.

L’illustration suivante montre deux contrôles de filtre rapide. Le filtre rapide sur la gauche a un filtre rapide vide et le nombre de résultats n’est pas visible. Le filtre rapide à droite contient une chaîne de recherche et affiche le nombre de résultats.

![Exemples de contrôle de filtre rapide avec et sans chaîne de recherche.](media/pfe-styles-quick-filter.png "Exemples de contrôle de filtre rapide avec et sans chaîne de recherche")

## <a name="center-align-elements-on-a-tab"></a>Centrer les éléments sur un onglet

Pour aligner des éléments au centre d’un onglet, le nom du groupe doit commencer par `TabContentGroup`, et le groupe doit avoir les propriétés suivantes :

- **Mode largeur :** `SizeToAvailable`
- **Mode hauteur :** `SizeToAvailable`

## <a name="align-a-grid-detail-part-and-quick-filter"></a>Aligner une grille, une pièce de détail et un filtre rapide

Pour organiser une grille personnalisée, une partie détaillée et un filtre rapide de manière à ce qu’ils ressemblent à la conception standard, gardez les points suivants à l’esprit lorsque vous les assemblez :

- Si la grille a un filtre rapide, la grille et le filtre rapide doivent être à l’intérieur du groupe dont le nom commence par `GridGroup`.
- Pour lui appliquer des styles à une partie de détail, le nom du groupe doit commencer par `DetailInformationGroup`,

L’illustration suivante montre une grille typique qui comprend un filtre rapide et une partie détaillée sur la droite.

![Grille typique qui inclut un filtre rapide et une pièce de détail.](media/pfe-styles-align-grid.png "Grille typique qui inclut un filtre rapide et une pièce de détail")

Dans Visual Studio, une grille, ne partie de détail et un filtre rapide peuvent être créés à l’aide d’une structure telle que celle illustrée dans l’illustration suivante.

![Structure de code typique qui s’aligne sur une grille, un filtre rapide et une pièce de détail.](media/pfe-styles-header-code-structure2.png "Structure de code typique qui s’aligne sur une grille, un filtre rapide et une pièce de détail")

## <a name="additional-resources"></a>Ressources supplémentaires

- [Personnaliser l’interface d’exécution de l’atelier de production](production-floor-execution-customize.md)
- [Concevoir l’interface d’exécution de l’atelier de production](production-floor-execution-tabs.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
