---
title: Module de sélection de site
description: Cette rubrique couvre le module de sélecteur de sites et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: a1954f6b2fea35d5138218e6a2a23ab1fd04c8fc
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710301"
---
# <a name="site-picker-module"></a>Module de sélection de site

[!include [banner](includes/banner.md)]

Cette rubrique couvre le module de sélecteur de sites et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Lorsqu’une entreprise possède différents sites sur des marchés, des régions et des paramètres régionaux, les utilisateurs des sites ont besoin d’un moyen simple de basculer entre les sites et de sélectionner leur site d’achat préféré. Pour s’adapter à ce scénario, le module de sélecteur de sites permet aux utilisateurs de parcourir plusieurs sites. Un sélecteur de site est également recommandé lorsque la [géodétection et la redirection](geo-detection-redirection.md) ont été implémentés pour votre site de commerce électronique, afin que les clients aient un moyen de remplacer la préférence de site qu'ils indiquent en utilisant le module [sélecteur de pays/région](country-region-picker-module.md). 

Le module de sélecteur de sites doit être configuré avec la liste des sites (marchés, régions ou paramètres régionaux) que les utilisateurs des sites peuvent parcourir. L’illustration suivante montre un exemple de module de sélecteur de sites qui figure dans l’en-tête d’une page de site.

![Exemple de module de sélecteur de sites dans l’en-tête d’une page de site.](./media/ecommerce-sitepicker.PNG)

## <a name="site-picker-module-properties"></a>Propriétés du module de sélecteur de sites

| Nom de la propriété | Valeur                 | Description |
|---------------|-----------------------|-------------|
| Titre       | Détails                  | En-tête du module. |
| Options de site  | Nom, image, URL      | Cette propriété spécifie un nom, un lien vers la page d’accueil du site et une image facultative à afficher pour chaque site inclus dans le module. L’image peut être un drapeau ou une représentation d’un marché, d’une région ou d’un lieu. |

## <a name="add-a-site-picker-module-to-a-page"></a>Ajouter un module de sélecteur de sites à une page

Le module de sélecteur de sites peut être ajouté à l’emplacement **Sélecteur de sites** du [module d’en-tête](author-header-module.md). Une le module de sélection de sites ajouté, vous pouvez définir l’en-tête du module et les options du site. Généralement, un module d’en-tête est contenu dans un fragment d’en-tête qui peut être partagé entre les pages e-commerce d’un site. 

Pour ajouter le module de sélection de site à un module d'en-tête, procédez comme suit.

1. Dans l’emplacement **Sélecteur de sites** du module En-tête du fragment d'en-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner les modules**, ajoutez un module **Sélecteur de sites**, puis sélectionnez **OK**.
1. Dans le volet des propriétés **Sélecteur de site**, sélectionnez **Ajouter une liste d'options de site**. Une option **Liste des options du site** modifiable s'affiche.
1. Sélectionnez **Liste des options de site**. La boîte de dialogue **Liste des options du site** apparaît.
1. Sous **Nom du site**, saisissez le texte du nom du site qui s'affichera dans la liste déroulante du sélecteur de site.
1. Sous **URL de redirection du site**, sélectionnez **Ajouter un lien**. Le volet volant **Ajouter un lien** s'affiche.
1. Dans le volet volant **Ajouter un lien**, sélectionnez **Page personnalisée**, puis sélectionnez **Suivant**.
1. Dans la liste des URL du site, sélectionnez l'URL avec le chemin que vous avez créé lors de l'ajout de la chaîne au site (par exemple, `www.adventure-works.com/fr-ca`), puis sélectionnez **Appliquer**.
1. Cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Sélectionnez **Publier** pour publier la page.

Dans l’exemple suivant, le module de sélection de site a été ajouté à l’emplacement **Sélecteur de site** d’un module d’en-tête contenu dans un fragment d’en-tête nommé **HeaderContainer**.

![Exemple de module de sélecteur de sites dans un fragment d’en-tête.](./media/ecommerce-sitepicker-2.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module d’en-tête](author-header-module.md)

[Module de barre de navigation](add-breadcrumb.md)

[Module du menu de navigation](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
