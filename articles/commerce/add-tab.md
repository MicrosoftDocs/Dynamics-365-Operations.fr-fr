---
title: Module Onglet
description: Cet article couvre les modules d’onglet et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 91c79ca1b70a776352ef99d854397ada34c548e3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276971"
---
# <a name="tab-module"></a>Module Onglet

[!include [banner](includes/banner.md)]

Cet article couvre les modules d’onglet et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Les modules d’onglets sont des modules de type conteneur utilisés pour organiser les informations d’une page de site dans des onglets. Ils peuvent être utilisés sur n’importe quelle page où les informations doivent être présentées dans des onglets.

Dans chaque module d’onglet, un ou plusieurs modules d’élément d’onglet peuvent être ajoutés. Chaque module d’élément d’onglet représente un onglet unique. Dans chaque module d’élément d’onglet, un ou plusieurs modules peuvent être ajoutés. Il n’y a aucune restriction quant aux types de modules qui peuvent être ajoutés à un module d’élément d’onglet.

L’image suivante montre un exemple de module d’onglet sur une page de site. Dans cet exemple, l’onglet **Livraison** est sélectionné.

![Exemple d’un module d’onglet.](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a>Propriétés du module d’onglet

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| Titre | Détails | Cette propriété spécifie un en-tête de texte facultatif pour le module d’onglet. |
| Index des onglets actifs | Nombre | Cette propriété spécifie l’onglet qui doit être actif par défaut au chargement d’une page. Si aucune valeur n’est fournie, le premier élément d’onglet est activé par défaut. |

## <a name="tab-item-module-properties"></a>Propriétés du module d’élément d’onglet

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| Titre | Détails | Cette propriété spécifie le texte du titre du module d’élément d’onglet. |

## <a name="add-a-tab-module-to-a-page"></a>Ajouter un module d’onglet à une page

Pour ajouter un module d’onglet à une page et définir les propriétés requises, procédez comme suit.

1. Utilisez le modèle de marketing Fabrikam (ou tout modèle dénué de restriction) pour créer une nouvelle page nommée **Page des politiques du magasin**.
1. Dans l’emplacement **Principal** de la **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner les modules**, sélectionnez le module **Onglet**, puis cliquez sur **OK**.
1. Dans le volet des propriétés du module d’onglet, sélectionnez **En-tête** à côté du symbole du crayon.
1. Dans la boîte de dialogue **En-tête**, sous **Texte d’en-tête**, saisissez le texte de l’en-tête (par exemple, **Politiques**). Puis sélectionnez **OK**.
1. Dans l’emplacement **Onglet**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Élément d’onglet**, puis cliquez sur **OK**.
1. Dans le volet des propriétés du module d’élément d’onglet, sous **Titre**, saisissez le texte du titre (par exemple, **Livraison**).
1. Dans l’emplacement **Élément d’onglet**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Bloc de texte**, puis cliquez sur **OK**.
1. Dans le volet des propriétés du module de bloc de texte, sous **Texte enrichi**, entrez un paragraphe de texte.
1. Dans l’emplacement **Onglet**, ajoutez quelques autres modules d’élément d’onglet portant un titre. Dans chaque module d’élément d’onglet, ajoutez un module de bloc de texte portant du contenu.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page. La page affichera un module d’onglet contenant les modules d’élément d’onglet ayant le contenu que vous avez ajouté.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Conteneur](add-container-module.md)

[Module Accordéon](add-accordion.md)

[Module de bloc de texte](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
