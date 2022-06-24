---
title: Utiliser des réglages de style prédéfinis
description: Cet article décrit l’utilisation des styles prédéfinie dans le générateur de site Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0a06052ab29502c57a2ad5a25e5bec870585ef4a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900358"
---
# <a name="work-with-style-presets"></a>Utiliser des réglages de style prédéfinis

[!include [banner](includes/banner.md)]

Cet article décrit l’utilisation des styles prédéfinie dans le générateur de site Microsoft Dynamics 365 Commerce.

Un style prédéfini est un ensemble stocké de toutes les valeurs de style utilisables dans le thème d’un site. Il peut être utilisé pour changer immédiatement l’apparence d’un site à partir du générateur de site. Les styles prédéfinis permettent aux créateurs du générateur de site de Commerce de modifier, prévisualiser et activer rapidement un ensemble de valeurs de style sur tout leur site, sans avoir à utiliser des feuilles de style en cascade (CSS) ou à déployer des thèmes. Les styles de police et de bouton et les couleurs de site sont des exemples typiques de variables de style qui peuvent être gérées via les styles prédéfinis.

L’ensemble des variables de style disponibles dans un site est déterminé par la bibliothèque de modules et de thèmes déployée sur le locataire d’un site. Le kit de développement logiciel en ligne Dynamics 365 Commerce permet aux développeurs d’implémenter autant (ou aussi peu) de variables de style utilisables qu’il leur faut pour un thème donné. En activant davantage de variables de style, un développeur de thème peut mettre le choix final des styles du site entre les mains des créateurs de site. Par conséquent, les non-développeurs peuvent mettre à jour et prévisualiser les styles de site à l’aide du jeu d’outils. Cette fonctionnalité est également utile dans tout scénario où la modification directe des thèmes ou du CSS est une source de tracas inutile.

Les thèmes où les variables de style utilisables sont activées nécessitent un style prédéfini par défaut. Ils peuvent éventuellement inclure des options prédéfinies supplémentaires dans le cadre d’un package de thème déployé. Par exemple, un thème peut être déployé avec un seul style prédéfini par défaut, « modern light ». Il peut aussi inclure des options de style prédéfini supplémentaires en plus de la prédéfinition par défaut, telles que « modern dark », « vintage light » ou « vintage dark ». Ces thèmes prédéfinis intégrés sont créés par les développeurs et peuvent être utilisés comme points de départ pour de nouvelles conceptions de site.

Dans le générateur de site, les créateurs peuvent faire un choix parmi les réglages prédéfinis intégrés d’un thème, ou ils peuvent créer leurs propres réglages de style prédéfinis en utilisant les variables de style activées. Un style prédéfini peut être prévisualisé dans le générateur de site avant d’être activé sur le site en ligne. Une fois les modifications de style d’un créateur vérifiées, le style prédéfini peut être défini sur « actif » pour le site en ligne.

## <a name="preview-a-style-preset"></a>Prévisualiser un style prédéfini

Pour prévisualiser un style prédéfini sur votre site dans le générateur de site, procédez comme suit.

1. Dans le volet de navigation de gauche de votre site, accédez à **Paramètres du site \> Conception**.
1. Dans l’onglet **Styles prédéfinis** en haut de l’éditeur de conception, dans la liste **Réglages prédéfinis disponibles**, sélectionnez un réglage prédéfini, puis sélectionnez **Afficher** pour accéder à l’éditeur de réglages prédéfinis.

    Si la liste **Réglages prédéfinis disponibles** ne comporte actuellement aucun réglage prédéfini, voir [Créer un réglage de style prédéfini personnalisé](#create-a-custom-style-preset) pour plus d’informations sur la création d’un réglage de style prédéfini personnalisé.

    > [!NOTE]
    > Les réglages prédéfinis inclus avec le thème sont indiqués par un badge **Intégré**. Ces réglages prédéfinis intégrés sont en lecture seule. Pour copier un réglage prédéfini intégré en tant que nouveau réglage prédéfini personnalisable, sélectionnez le bouton représentant des points de suspension (**...**) pour le réglage prédéfini, puis sélectionnez **Enregistrer sous**.

1. Dans la barre de commande, sélectionnez **Aperçu**.
1. Sélectionnez une URL de votre site à utiliser pour prévisualiser le style prédéfini, puis sélectionnez **OK**.
1. Sélectionnez la variante d’URL spécifique au canal et aux paramètres régionaux à prévisualiser en sélectionnant le nom de la variante. Une nouvelle fenêtre de navigateur d’aperçu s’ouvre, où le style prédéfini sélectionné est appliqué à la page spécifiée.

> [!NOTE]
> L’URL d’aperçu est persistante et authentifiée. Par conséquent, vous pouvez la copier, la coller et l’envoyer à d’autres collègues authentifiés pour vérification avant de la définir comme « active » sur votre site en ligne. L’URL de prévisualisation est également utile pour vérifier les styles sur différents appareils, dans différents navigateurs et sur différents écrans.

> [!TIP]
> Pendant que vous modifiez un style prédéfini, il peut être utile de laisser la fenêtre de prévisualisation du navigateur ouverte dans une fenêtre distincte, afin de pouvoir valider rapidement vos modifications. Après avoir enregistré vos modifications dans un réglage prédéfini, actualisez la fenêtre du navigateur d’aperçu ouverte pour valider l’expérience utilisateur.

## <a name="create-a-custom-style-preset"></a>Créer un réglage de style prédéfini personnalisé

Pour créer un style prédéfini personnalisé dans le générateur de site, procédez comme suit.

1. Dans le volet de navigation de gauche de votre site, accédez à **Paramètres du site \> Conception**.
1. Dans l’onglet **Styles prédéfinis** en haut de l’éditeur de conception, dans la barre de commandes, sélectionnez **Nouveau réglage prédéfini**.
1. Entrez un nom et une description pour le nouveau réglage prédéfini et sélectionnez **Enregistrer**. Un nouveau réglage prédéfini personnalisable est créé, qui utilise les valeurs par défaut du thème comme point de départ.

> [!NOTE]
> Vous pouvez également créer un nouveau style prédéfini personnalisé à partir de n’importe quel style prédéfini existant en sélectionnant le bouton représentant des points de suspension (**...**) pour ce style prédéfini, puis en sélectionnant **Enregistrer sous**. Vous pouvez également sélectionner **Enregistrer sous** dans la barre de commandes de l’éditeur des styles prédéfinis.

## <a name="modify-global-and-module-type-style-values"></a>Modifier les valeurs de style de type global et module

Certaines variables de style d’un thème sont partagées entre plusieurs types de modules. Ces variables de style sont appelées variables de style *globales*. Les exemples incluent les couleurs principales du site, les styles de police par défaut et les styles de bouton. En définissant des variables globales, vous pouvez changer l’apparence de nombreux types de modules différents.

Certaines valeurs de style peuvent être exclusives à un type de module, ou elles peuvent éventuellement remplacer une valeur globale par défaut. Si le thème d’un site a implémenté des variables de style de type module, les créateurs du générateur de site peuvent personnaliser le style d’un type de module indépendamment des paramètres globaux. Les variables de type module peuvent augmenter ou remplacer les variables de style globales d’un thème.

> [!NOTE]
> La hiérarchie des valeurs de style d’un site se comporte de la manière suivante. Les valeurs de style qui apparaissent le plus à droite remplacent les valeurs de style qui sont à leur gauche.
>
> Valeurs par défaut du thème \< Valeurs de style globales \< Valeurs de style de type module \< remplacement CSS

Pour modifier les valeurs globales ou de type module d’un style prédéfini dans le générateur de site, procédez comme suit.

1. Dans le volet de navigation de gauche de votre site, accédez à **Paramètres du site \> Conception**.
1. Dans l’onglet **Styles prédéfinis** en haut de l’éditeur de conception, sélectionnez **Afficher** pour que tout style prédéfini passe à l’éditeur des réglages prédéfinis.
1. Sélectionnez **Aperçu**, puis suivez les étapes de sélection d’URL pour ouvrir un aperçu de votre style prédéfini dans une fenêtre de navigateur. Laissez cette fenêtre de navigateur d’aperçu ouverte.
1. Dans l’éditeur des réglages prédéfinis, sélectionnez **Modifier** en haut à droite.
1. Utilisez les contrôles des variables de style dans l’éditeur pour modifier certaines valeurs de style globales.
1. En haut de l’éditeur, dans l’onglet **Modules** à droite de l’onglet **Global**, sélectionnez un type de module dont le style doit être modifié.
1. Utilisez les commandes de style pour modifier certaines valeurs de type module.
1. Lorsque vous êtes prêt à prévisualiser vos modifications, sélectionnez **Enregistrer** dans la barre de commandes.
1. Revenez à la fenêtre d’aperçu du navigateur ouverte et actualisez-la. L’aperçu dans une fenêtre de navigateur est utile pour vérifier les modifications du style à différents points d’arrêt, dans différents navigateurs et sur différentes plateformes d’appareils.
1. Une fois toutes les modifications terminées et validées, sélectionnez **Terminer la modification** en haut à droite de l’éditeur.

> [!NOTE]
> Si vous modifiez le style prédéfini actuellement actif sur votre site, vous verrez un badge bleu **Actif** dans l’éditeur. Ce badge indique que le réglage prédéfini est actuellement en ligne sur votre site web. Si vous modifiez le réglage prédéfini actif, sélectionnez **Publier** pour appliquer ces modifications à votre site en ligne.

## <a name="make-a-new-style-preset-active-on-your-live-site"></a>Rendre un nouveau style prédéfini actif sur votre site en ligne

Pour définir un style prédéfini comme le nouveau réglage prédéfini actif sur votre site, procédez comme suit.

- Sélectionnez le bouton **Définir comme actif** dans l’un de ces endroits :

    - La barre de commandes dans l’éditeur de styles prédéfinis
    - Le menu représentant des points de suspension (**...**) pour tout réglage prédéfini disponible dans la vue principale de l’onglet **Styles prédéfinis** dans **Paramètres du site \> Conception**

Les valeurs de style du réglage prédéfini sont activées sur votre site web présenté au public.

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajouter un logo](add-logo.md)

[Sélectionner un thème pour le site](select-site-theme.md)

[Utilisation de fichiers de remplacement CSS](css-override-files.md)

[Ajouter une icône de favori](add-favicon.md)

[Ajouter un avis de droits d’auteur](add-copyright-notice.md)

[Ajouter des langues à votre site](add-languages-to-site.md)

[Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie](add-telemetry.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
