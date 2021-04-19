---
title: Utilisation de fichiers de remplacement CSS
description: Cette rubrique décrit pourquoi, quand et comment utiliser les fichiers de remplacement de feuilles de style en cascade (CSS) dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ef96070fe77b46622667301c7c7c402909ee7dfc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799491"
---
# <a name="work-with-css-override-files"></a>Utiliser CSS pour remplacer les fichiers

[!include [banner](includes/banner.md)]

Cette rubrique décrit pourquoi, quand et comment utiliser les fichiers de remplacement de feuilles de style en cascade (CSS) dans Microsoft Dynamics 365 Commerce.

Les styles de sites permanents doivent généralement être gérés via le thème d’un site. Les thèmes fournissent les paramètres de CSS et de style de base pour les modules sur n’importe quelle page de votre site. Les thèmes sont créés à l’aide du kit de développement logiciel en ligne (SDK) Dynamics 365 Commerce, et ils sont déployés sur vos sites web via Microsoft Dynamics Lifecycle Services (LCS). Les capacités de débogage de thème et les configurations d’interface de module dans le kit de développement logiciel en ligne (SDK) aident les développeurs de sites à créer des packages de conception de site personnalisables et cohérents. Lorsque ces packages de conception sont déployés sur un site, les auteurs du site peuvent se concentrer sur la création, la modification et la publication de contenu au lieu du développement du site.

Étant donné le cycle de vie habituel d’un thème, la dépendance aux développeurs d’apporter des modifications de style via le pipeline de déploiement de Kit de développement logiciel (SDK) et LCS peut être prohibitive dans certains scénarios. Les prototypes de site ou les correctifs peuvent sembler encombrants si le Kit de développement logiciel (SDK) n’est pas configuré ou si vous n’avez pas le temps d’attendre un déploiement LCS.

Dans ces scénarios, les fichiers de remplacement CSS peuvent aider. Dans les outils de création Commerce, les utilisateurs authentifiés peuvent télécharger un fichier CSS, le prévisualiser, puis l’activer pour remplacer le thème d’un site. La surcharge du déploiement du Kit de développement logiciel (SDK) ou de LCS n’est pas requise. Les remplacements spécifiés dans un fichier de remplacement CSS peuvent être aussi petits qu’une modification d’un style de texte unique ou aussi étendus qu’une refonte complète de la marque.

Avant d’utiliser les fichiers de remplacement CSS, tenez compte des limitations suivantes :

- Seul un fichier de remplacement CSS peut être actif sur un site à la fois. Par conséquent, tous les remplacements actifs doivent être présents dans un seul fichier de remplacement.
- Bien que vous puissiez prévisualiser les remplacements dans les outils de création Commerce, il n’y a pas de fonctionnalités de débogage dédiées pour identifier les bogues que les remplacements introduisent. En d’autres termes, lorsque vous utilisez les fichiers de remplacement CSS, vous n’avez pas le même ensemble d’outils que le Kit de développement logiciel (SDK) fournit pour la validation du module et de la création.

Cependant, les fichiers de remplacement CSS fournissent un moyen rapide de prototyper une conception ou d’implémenter un correctif avant qu’une mise à jour complète du thème ne soit développée et déployée.

## <a name="create-a-css-override-file"></a>Créer un fichier de remplacement CSS

Pour créer un fichier de remplacement CSS, vous pouvez utiliser n’importe quel environnement de développement intégré (IDE), éditeur de texte ou éditeur de code source. Une approche typique consiste à utiliser des débogueurs web standard dans votre navigateur pour identifier les sélecteurs de style, les propriétés et les valeurs sur votre site existant. La plupart des navigateurs vous permettent de modifier des valeurs et de les prévisualiser dans le débogueur. Après avoir identifié les modifications que vous souhaitez apporter, vous pouvez les enregistrer dans votre propre fichier CSS.

## <a name="upload-a-css-override-file"></a>Charger un fichier de remplacement CSS

Pour télécharger un fichier CSS sur votre site dans Commerce, procédez comme suit.

1. Dans les outils de création, accédez à votre site.
1. Dans le volet de navigation sur la gauche, sélectionnez **Conception**.

    > [!NOTE]
    > Selon la version des outils de création Commerce que vous utilisez, vous devrez peut-être développer **Paramètres** dans le volet de navigation avant de pouvoir sélectionner **Conception**.

1. En haut du volet de conception principal, sélectionnez l’onglet **Remplacement par CSS**, s’il n’est pas déjà sélectionné.
1. En dessous de **Remplacements CSS disponibles**, sélectionnez **Télécharger un fichier CSS**. Une fenêtre de l’Explorateur de fichiers apparaît.
1. Dans l’Explorateur de fichiers, recherchez et sélectionnez un fichier CSS, puis sélectionnez **Ouvrir**. Le fichier CSS téléchargé apparaît maintenant sous **Remplacements CSS disponibles**.

## <a name="preview-a-css-override-file"></a>Aperçu d’un fichier de remplacement CSS

Pour prévisualiser un fichier de remplacement CSS avant de le rendre actif sur votre site en ligne, procédez comme suit.

1. Dans le volet de navigation de gauche, sélectionnez **Conception**, puis, sous l’onglet **Remplacement CSS**, sous **Remplacements CSS disponibles**, recherchez le fichier CSS que vous souhaitez prévisualiser.
1. À côté du nom du fichier CSS, sélectionnez **Aperçu du site**.
1. Dans la boîte de dialogue **Sélectionnez une URL**, sélectionnez l’URL du site auquel vous souhaitez voir la substitution appliquée, puis sélectionnez **OK**.
1. S’il existe plusieurs variantes pour l’URL sélectionnée, sélectionnez la variante souhaitée dans la boîte de dialogue **Aperçu des variations** qui apparaît.

Un nouvel onglet ou une nouvelle fenêtre de navigateur s’ouvre, où vous pouvez valider vos remplacements de style par rapport à votre site. Vous pouvez ensuite partager l’URL avec d’autres utilisateurs de Commerce authentifiés pour évaluation et commentaires.

## <a name="activate-a-css-override-file-on-your-live-site"></a>Activez un fichier de remplacement CSS sur votre site en ligne

Après avoir prévisualisé et approuvé le fichier de remplacement CSS, vous pouvez l’activer sur votre site en ligne.

> [!NOTE]
> Seul un fichier de remplacement CSS peut être actif sur votre site à la fois. Si vous activez un nouveau fichier de remplacement, le fichier de remplacement précédent est désactivé. Par conséquent, assurez-vous que tous les remplacements requis sont présents dans un seul fichier de remplacement CSS.

Pour activer un fichier de remplacement CSS, procédez comme suit.

1. Dans le volet de navigation de gauche, sélectionnez **Conception**, puis, sous l’onglet **Remplacement CSS**, sous **Remplacements CSS disponibles**, recherchez le fichier CSS que vous souhaitez activer.
1. Sous le nom du fichier CSS, sélectionnez **Activer**. Le fichier de remplacement devient immédiatement actif sur votre site en ligne.

## <a name="deactivate-a-css-override-file-on-your-live-site"></a>Désactivez un fichier de remplacement CSS sur votre site en ligne

Pour désactiver un fichier de remplacement CSS sur votre site, procédez comme suit.

1. Dans le volet de navigation de gauche, sélectionnez **Conception**, puis, sous l’onglet **Remplacement CSS**, sous **Remplacements CSS disponibles**, recherchez le fichier CSS que vous souhaitez désactiver.
1. Sous le nom du fichier CSS, sélectionnez **Désactiver**. Le fichier de remplacement devient immédiatement inactif sur votre site en ligne.

> [!TIP]
> Pour accéder à des options supplémentaires pour les fichiers de remplacement CSS, sélectionnez les points de suspension (**...**) à côté du nom de fichier CSS. Les options **Télécharger**, **Renommer** et **Remplacer** sont utiles pour des changements rapides à un fichier de remplacement CSS existant.

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajouter un logo](add-logo.md)

[Sélectionner un thème pour le site](select-site-theme.md)

[Utiliser des réglages de style prédéfinis](style-presets.md)

[Ajouter une icône de favori](add-favicon.md)

[Ajouter un message de bienvenue](add-welcome-message.md)

[Ajouter un avis de droits d’auteur](add-copyright-notice.md)

[Ajouter des langues à votre site](add-languages-to-site.md)

[Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie](add-telemetry.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
