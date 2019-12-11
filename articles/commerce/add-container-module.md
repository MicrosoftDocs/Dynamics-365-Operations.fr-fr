---
title: Module Container
description: Cette rubrique couvre les modules de conteneur et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 22a09b61fbe3bd1cca96011d3fb81a12ef1bc844
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697058"
---
# <a name="container-module"></a>Module Container

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de conteneur et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module de conteneur est un module qui héberge d'autres modules en son sein. Il s'agit du conteneur le plus générique utilisé dans Dynamics 365 Commerce. Le principal objectif d'un module de conteneur est de définir, via les propriétés définies pour celui-ci, la disposition des modules qui sont à l'intérieur. Par exemple, ces modules peuvent s'afficher côte à côte dans une disposition à deux, trois, quatre voire six colonnes. Ils peuvent également être limités à la largeur du conteneur, ou ils peuvent remplir l'écran. Un en-tête peut également être ajouté à chaque module de conteneur.

Il existe trois types standard de modules de conteneur : conteneur, conteneur à 2 emplacements, et conteneur à 3 emplacements. Tous types de modules peuvent être placés à l'intérieur de ces conteneurs. Il existe également des types spéciaux de modules de conteneur, tels que le carrousel, le bloc riche de contenu, le placement de contenu, le panier, la caisse, la zone d'achat, l'en-tête, et le pied de page. Ces conteneurs ont des usages spécifiques, et uniquement des types de modules pris en charge spécifiques peuvent être mis à l'intérieur de ceux-ci.

Nous vous conseillons de placer les modules dans un conteneur, de sorte qu'ils puissent être limités à la largeur du conteneur.

## <a name="examples-of-container-modules-in-e-commerce"></a>Exemples de modules de conteneur dans le commerce électronique

- Un auteur du site souhaite une disposition à trois colonnes, où trois modules apparaissent côte à côte. Par conséquent, l'auteur du site utilise un module de conteneur de type conteneur avec 3 emplacements.
- Un auteur du site souhaite une disposition à six colonnes, où six modules apparaissent côte à côte. Par conséquent, l'auteur du site utilise un conteneur de type conteneur avec six colonnes à l'intérieur de celui-ci.
- Un auteur du site souhaite mettre un module sur une page mais ne souhaite pas qu'il remplisse l'écran. Par conséquent, l'auteur du site ajoute le module à un module de conteneur et définit la propriété **Largeur** du conteneur sur **Adapter le conteneur**.

## <a name="container-module-properties"></a>Propriétés du module de conteneur

| Nom de la propriété     | Valeurs | Description |
|-------------------|--------|-------------|
| En-tête           | Texte d'en-tête et balise d'en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Un en-tête facultatif peut être fourni pour le conteneur. Par défaut, la balise d'en-tête **H2** sert pour l'en-tête. Toutefois, la balise peut être modifiée pour satisfaire aux exigences d'accessibilité. |
| Largeur             | **Adapter le conteneur** ou **Remplir l'écran** | Si la valeur est définie sur **Adapter le conteneur** (valeur par défaut), les modules à l'intérieur du conteneur sont limités à la largeur du conteneur. Si la valeur est définie **Plein écran**, les modules ne sont pas soumis à la largeur du conteneur mais peuvent remplir l'écran. |
| Nombre de colonnes | **1**, **2**, **3**, **4**, **6** ou **12** | Cette propriété définit le nombre de colonnes dans le conteneur. Conteneur peut comporter jusqu'à 12 colonnes. |

## <a name="container-with-2-slots"></a>Conteneur avec 2 emplacements

Le type de conteneur avec 2 emplacements est optimisé pour une disposition sur deux colonnes. Ce type de conteneur a deux emplacements pour autoriser une vue côte à côte des modules qui sont à l'intérieur.

Des propriétés supplémentaires peuvent être utilisées pour optimiser la disposition pour différents ports de vue (mobiles, tablettes, ordinateurs, etc.). Pour chaque port de vue, la largeur de chaque colonne peut être définie. Les paramètres de largeur de colonne disponibles sont les suivants :

- **75 %/25 %** – Le premier module possède une largeur de la colonne de 75 %, et le second module possède une largeur de la colonne de 25 %. Une option de **25 %/75 %** est également disponible.
- **50 %/50 %** – Les deux modules ont une largeur de colonne égale.
- **67 %/33 %** – Le premier module possède une largeur de la colonne de 67 %, et le second module possède une largeur de la colonne de 33 %. Une option de **33 %/67 %** est également disponible.
- **100 %** – Les deux modules ont une largeur de colonne totale. Par conséquent, les modules sont verticalement empilés en une seule colonne. Bien que cette disposition à une seule colonne soit contraire à l'objectif du conteneur de type à 2 emplacements, il peut être préférable pour certains ports de vue (par exemple, les ports de vue très petits, tels que des appareils mobiles).

### <a name="container-with-2-slots-properties"></a>Propriétés du conteneur à 2 emplacements

| Nom de la propriété                   | Valeurs | Description |
|---------------------------------|--------|-------------|
| En-tête                         | Texte d'en-tête et balise d'en-tête | Un en-tête facultatif peut être fourni pour le conteneur. |
| Configuration de port d'affichage extra-petit | **25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** ou **100 %** | Cette propriété définit la disposition des ports de vue extra-petits. |
| Configuration de petit port d'affichage   | **25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** ou **100 %** | Cette propriété définit la disposition des petits ports de vue, comme les appareils mobiles. |
| Configuration de port d'affichage moyen  | **25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** ou **100 %** | Cette propriété définit la disposition des ports de vue moyens, comme les tablettes. |
| Configuration de port d'affichage large   | **25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** ou **100 %** | Cette propriété définit la disposition des ports de vue larges, comme les ordinateurs. |

## <a name="container-with-3-slots"></a>Conteneur avec 3 emplacements

Le conteneur avec des types de modules à 3 emplacements est optimisé pour une disposition sur trois colonnes.

Des propriétés supplémentaires peuvent être utilisées pour optimiser la disposition pour différents ports de vue. Pour chaque port de vue, la largeur de chaque colonne peut être définie. Les paramètres de largeur de colonne disponibles sont les suivants :

- **33 %/33 %/33 %** – Les trois modules ont tous une largeur de colonne égale.
- **50 %/25 %/25 %** – Le premier module possède une largeur de colonne de 50 %, et chacun des deux autres modules a une largeur de colonne de 25 %. Les options **25 %/50 %/25 %** et **25 %/25 %/50 %** sont également disponibles.
- **16 %/16 %/67 %** – Chacun des deux premiers modules possède une largeur de colonne de 16 %, et le troisième module a une largeur de colonne de 67 %. Les options **16 %/67 %/16 %** et **67 %/16 %/16 %** sont également disponibles.

### <a name="container-with-3-slots-properties"></a>Propriétés du conteneur à 3 emplacements

| Nom de la propriété                   | Valeurs | Description |
|---------------------------------|--------|-------------|
| En-tête                         | Texte d'en-tête et balise d'en-tête | Un en-tête facultatif peut être ajouté au conteneur. |
| Configuration de port d'affichage extra-petit | **33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** ou **67 %/16 %/16 %** | Cette propriété définit la disposition des ports de vue extra-petits. |
| Configuration de petit port d'affichage   | **33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** ou **67 %/16 %/16 %** | Cette propriété définit la disposition des petits ports de vue, comme les appareils mobiles. |
| Configuration de port d'affichage moyen  | **33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** ou **67 %/16 %/16 %** | Cette propriété définit la disposition des ports de vue moyens, comme les tablettes. |
| Configuration de port d'affichage large   | **33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** ou **67 %/16 %/16 %** | Cette propriété définit la disposition des ports de vue larges, comme les ordinateurs. |

## <a name="add-a-container-module-to-a-page"></a>Ajouter un module de conteneur à une page

Pour ajouter un module de lecteur de conteneur à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Créez un modèle de page nommé **modèle de conteneur**.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un module de conteneur.
1. Dans le module de conteneur, ajoutez un module de fonctionnalité.
1. Archivez le modèle, et publiez-le.
1. Utilisez le modèle de conteneur que vous venez de créer pour créer une page qui s'appelle **page de conteneur**.
1. À l'emplacement **Principal** de la nouvelle page, ajoutez un module de conteneur.
1. Dans le volet de propriété du module de conteneur, définissez la propriété **Nombre de colonnes** sur **1** et la propriété **Largeur** sur **Adapter au conteneur**.
1. Dans le module de conteneur, ajoutez un module de fonctionnalité.
1. Dans le volet de propriété du module de fonctionnalité, configurez un en-tête.
1. Enregistrez et affichez un aperçu de la page. Vous devez voir un module de fonctionnalité qui s'adapte à la largeur du module de conteneur.
1. Dans le volet de propriété du module de conteneur, modifiez la valeur de la propriété **Nombre de colonnes** sur **3**.
1. Ajoutez un module de fonctionnalité au module de conteneur.
1. Enregistrez et affichez un aperçu de la page. Vous devez à présent voir trois modules de fonctionnalités qui apparaissent côte à côte.
1. Après avoir obtenu la disposition de votre choix, archivez la page, puis publiez-la.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Carrousel](add-carousel.md)

[Module de bloc de contenu riche](add-content-rich-block.md)

[Module Placement de contenu](add-content-placement-modules.md)

[Module Zone d'achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Paiement](add-checkout-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
