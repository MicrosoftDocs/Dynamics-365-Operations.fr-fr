---
title: Module Conteneur
description: Cet article couvre les modules de conteneur et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 58fa222dfef9e559da00fef448c572800651bd63
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272905"
---
# <a name="container-module"></a>Module Conteneur

[!include [banner](includes/banner.md)]

Cet article couvre les modules de conteneur et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Un module de conteneur est un module qui héberge d’autres modules en son sein. Le principal objectif d’un module de conteneur est de définir, via les propriétés paramétrées pour ce dernier, la disposition des modules qu’il contient. Par exemple, ces modules peuvent s’afficher côte à côte dans une disposition à deux, trois, quatre voire six colonnes. Ils peuvent également être limités à la largeur du conteneur, ou ils peuvent remplir l’écran. Un en-tête peut également être ajouté à chaque module de conteneur.

Trois modules de conteneur sont pris en charge : conteneur, conteneur à 2 emplacements et conteneur à 3 emplacements. Tous types de modules peuvent être placés à l’intérieur de ces conteneurs. 

> [!NOTE] 
> Nous vous conseillons de toujours placer les modules dans un module de conteneur, de sorte qu’ils puissent être limités à la largeur du conteneur.

## <a name="examples-of-container-modules-in-e-commerce"></a>Exemples de modules de conteneur dans le commerce électronique

- Un auteur du site souhaite une disposition à trois colonnes, où trois modules apparaissent côte à côte. Par conséquent, l’auteur du site utilise un module de conteneur de type conteneur avec 3 emplacements.
- Un auteur du site souhaite une disposition à six colonnes, où six modules apparaissent côte à côte. Par conséquent, l’auteur du site utilise un conteneur de type conteneur avec six colonnes à l’intérieur de celui-ci.
- Un auteur du site souhaite mettre un module sur une page mais ne souhaite pas qu’il remplisse l’écran. Par conséquent, l’auteur du site ajoute le module à un module de conteneur et définit la propriété **Largeur** du conteneur sur **Adapter le conteneur**.

L’image suivante montre un exemple de module de conteneur contenant un module de carrousel dans le générateur de site Commerce. Dans cet exemple, la propriété **Largeur** du module de conteneur est définie sur **Remplir l’écran**.

![Exemple de module de conteneur.](./media/ecommerce-container.PNG)

## <a name="container-module-properties"></a>Propriétés du module de conteneur

| Nom de la propriété     | Valeurs | Description |
|-------------------|--------|-------------|
| En-tête           | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Un en-tête facultatif peut être fourni pour le conteneur. Par défaut, la balise d’en-tête **H2** sert pour l’en-tête. Toutefois, la balise peut être modifiée pour satisfaire aux exigences d’accessibilité. |
| Largeur             | **Adapter le conteneur** ou **Remplir l’écran** | Si la valeur est définie sur **Adapter le conteneur** (valeur par défaut), les modules à l’intérieur du conteneur sont limités à la largeur du conteneur. Si la valeur est définie **Plein écran**, les modules ne sont pas soumis à la largeur du conteneur mais peuvent remplir l’écran. |
| Nombre de colonnes | **1**, **2**, **3**, **4**, **6** ou **12** | Cette propriété définit le nombre de colonnes dans le conteneur. Conteneur peut comporter jusqu’à 12 colonnes. |

## <a name="container-with-2-slots"></a>Conteneur avec 2 emplacements

Le type de conteneur avec 2 emplacements est optimisé pour une disposition sur deux colonnes. Ce type de conteneur a deux emplacements pour autoriser une vue côte à côte des modules qui sont à l’intérieur.

Des propriétés supplémentaires peuvent être utilisées pour optimiser la disposition pour différents ports de vue (mobiles, tablettes, ordinateurs, etc.). Pour chaque port de vue, la largeur de chaque colonne peut être définie. Les paramètres de largeur de colonne disponibles sont les suivants :

- **75 %/25 %** – Le premier module possède une largeur de la colonne de 75 %, et le second module possède une largeur de la colonne de 25 %. Une option de **25 %/75 %** est également disponible.
- **50 %/50 %** – Les deux modules ont une largeur de colonne égale.
- **67 %/33 %** – Le premier module possède une largeur de la colonne de 67 %, et le second module possède une largeur de la colonne de 33 %. Une option de **33 %/67 %** est également disponible.
- **100 %** – Les deux modules ont une largeur de colonne totale. Par conséquent, les modules sont verticalement empilés en une seule colonne. Bien que cette disposition à une seule colonne soit contraire à l’objectif du conteneur de type à 2 emplacements, il peut être préférable pour certains ports de vue (par exemple, les ports de vue très petits, tels que des appareils mobiles).

### <a name="container-with-2-slots-properties"></a>Propriétés du conteneur à 2 emplacements

| Nom de la propriété                   | Valeurs | Description |
|---------------------------------|--------|-------------|
| En-tête                         | Texte d’en-tête et balise d’en-tête | Un en-tête facultatif peut être fourni pour le conteneur. |
| Configuration de port d’affichage extra-petit | **25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** ou **100 %** | Cette propriété définit la disposition des ports de vue extra-petits. |
| Configuration de petit port d’affichage   | **25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** ou **100 %** | Cette propriété définit la disposition des petits ports de vue, comme les appareils mobiles. |
| Configuration de port d’affichage moyen  | **25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** ou **100 %** | Cette propriété définit la disposition des ports de vue moyens, comme les tablettes. |
| Configuration de port d’affichage large   | **25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** ou **100 %** | Cette propriété définit la disposition des ports de vue larges, comme les ordinateurs. |

## <a name="container-with-3-slots"></a>Conteneur avec 3 emplacements

Le conteneur avec des types de modules à 3 emplacements est optimisé pour une disposition sur trois colonnes.

Des propriétés supplémentaires peuvent être utilisées pour optimiser la disposition pour différents ports de vue. Pour chaque port de vue, la largeur de chaque colonne peut être définie. Les paramètres de largeur de colonne disponibles sont les suivants :

- **33 %/33 %/33 %** – Les trois modules ont tous une largeur de colonne égale.
- **50 %/25 %/25 %** – Le premier module possède une largeur de colonne de 50 %, et chacun des deux autres modules a une largeur de colonne de 25 %. Les options **25 %/50 %/25 %** et **25 %/25 %/50 %** sont également disponibles.
- **16 %/16 %/67 %** – Chacun des deux premiers modules possède une largeur de colonne de 16 %, et le troisième module a une largeur de colonne de 67 %. Les options **16 %/67 %/16 %** et **67 %/16 %/16 %** sont également disponibles.

### <a name="container-with-3-slots-properties"></a>Propriétés du conteneur à 3 emplacements

| Nom de la propriété                   | Valeurs | Description |
|---------------------------------|--------|-------------|
| En-tête                         | Texte d’en-tête et balise d’en-tête | Un en-tête facultatif peut être ajouté au conteneur. |
| Configuration de port d’affichage extra-petit | **33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** ou **67 %/16 %/16 %** | Cette propriété définit la disposition des ports de vue extra-petits. |
| Configuration de petit port d’affichage   | **33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** ou **67 %/16 %/16 %** | Cette propriété définit la disposition des petits ports de vue, comme les appareils mobiles. |
| Configuration de port d’affichage moyen  | **33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** ou **67 %/16 %/16 %** | Cette propriété définit la disposition des ports de vue moyens, comme les tablettes. |
| Configuration de port d’affichage large   | **33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** ou **67 %/16 %/16 %** | Cette propriété définit la disposition des ports de vue larges, comme les ordinateurs. |

## <a name="add-a-container-module-to-a-page"></a>Ajouter un module de conteneur à une page

Pour ajouter un module de lecteur de conteneur à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de conteneur**, puis cliquez sur **OK**.
1. Dans l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Page par défaut**, puis cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier. 
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Créer une page**, sous **Nom de la page**, entrez **Page de conteneur**, puis cliquez sur **Suivant**.
1. Sous **Choisir un modèle**, sélectionnez le **Modèle de conteneur** que vous avez créé, puis sélectionnez **Suivant**.
1. Sous **Choisir une mise en page**, sélectionnez une mise en page (par exemple, **Disposition flexible**), puis sélectionnez **Suivant**.
1. Sous **Revoir et terminer**, vérifiez la configuration de la page. Si vous devez modifier les informations de la page, sélectionnez **Précédent**. Si les informations de la page sont correctes, sélectionnez **Créer une page**. 
1. Dans l’emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans le volet de propriétés du module de conteneur, définissez la propriété **Nombre de colonnes** sur **1** et la propriété **Largeur** sur **Remplir le conteneur**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Bloc de contenu**, puis cliquez sur **OK**.
1. Dans le volet de propriétés du module de bloc de contenu, configurez l’en-tête, l’image et la disposition.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page. Vous devez voir un module de fonctionnalité qui s’adapte à la largeur du module de conteneur.
1. Dans le volet de propriétés du module de conteneur, modifiez la valeur de la propriété **Nombre de colonnes** sur **3**.
1. Ajoutez au moins deux modules de bloc de contenu au module de conteneur et configurez-les.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page. Vous devriez à présent voir trois modules de bloc de contenu s’afficher côte à côte.
1. Une fois que vous avez obtenu la mise en page souhaitée, sélectionnez **Terminer la modification** pour archiver la page, puis sélectionnez **Publier** pour la publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Accordéon](add-accordion.md)

[Module Onglet](add-tab.md)

[Module Carrousel](add-carousel.md)

[Module de bloc de texte](add-content-rich-block.md)

[Module de zone d’achat](add-buy-box.md)

[Module de panier](add-cart-module.md)

[Module de validation](add-checkout-module.md)

[Module d’en-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
