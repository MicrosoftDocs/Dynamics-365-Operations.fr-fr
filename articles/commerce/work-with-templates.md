---
title: Utiliser des modèles
description: Cette rubrique décrit comment utiliser des modèles dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 04/14/2020
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
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a3fc4259a76f6edcfaa0b8f6e08292477c6c0835
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269864"
---
# <a name="work-with-templates"></a>Utiliser des modèles


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment utiliser des modèles dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Comme discuté dans [Vue d'ensemble des modèles et dispositions](templates-layouts-overview.md), les modèles définissent le jeu d'options disponible pour les auteurs en aval. Les modèles sont utiles l'équipe de création web d'une entreprise pour plusieurs raisons, et les modèles bien structurés peuvent vous aider dans tous les objectifs suivants :

- Simplifiez l'expérience de création des rôles d'éditeur de contenu quotidien.

    - Des options du module de filtre afin que seuls les modules appropriés soient affichés pour une section spécifique de page. (Par exemple, une section de marketing d'un modèle peut être configurée pour filtrer les modules inutiles qui ne devraient jamais être utilisés dans ce contexte, et qui compliqueront les tâches de création de contenu s'ils sont affichés.)
    - Configurez le paramètre par défaut du module pour améliorer l'efficacité de la création.
    - Définissez des fragments de page par défaut pour améliorer l'efficacité de la création. (Par exemple, les fragments d'en-tête et de pied de page dans un modèle s'affichent automatiquement sur chaque page en aval.)

- Conservez les sites de votre entreprise basés sur la marque en définissant un ensemble approuvé d'options de disposition et de configuration du module.

    > [!TIP] 
    > Les sites de commerce électronique ayant du succès fournissent aux clients des modèles conviviaux, renouvelables et des schémas de conception d'expérience utilisateur (UX) basée sur la marque. Grâce aux modèles, vous aidez à contrôler la cohérence de votre site.

- Améliorez les scores d'optimisation du moteur de recherche (SEO) en garantissant des définitions et des métadonnées de page définies par programme et reproductibles.

> [!NOTE]
> Bien que les modèles soient conçus pour contrôler la cohérence d'un site, ils peuvent théoriquement être configurés pour ne pas entraîner d'incohérence. Les administrateurs de la marque et du site peuvent définir tous les niveaux de variabilité pour les pages sur son site. Par exemple, un modèle peut être laissé entièrement ouvert, de sorte que les créateurs de contenu puissent créer n'importe quelle conception de page de leur choix. Dans ce cas, aucun des avantages dans la liste précédente ne s'applique.

## <a name="modify-a-template"></a>Modification d'un modèle

Les modèles sont modifiés à l'aide de l'éditeur de modèle.

Pour ouvrir l'éditeur de modèle, suivez l'une des étapes suivantes :

- Dans le volet de navigation de votre site, sélectionnez **Modèles**, puis sélectionnez le modèle à modifier.
- Dans l'éditeur de page pour une page existante, sélectionnez le nœud supérieur dans l'arborescence d'ensemble à gauche. Dans le volet de propriétés de droite, sélectionnez la propriété **Modifier le modèle**.

L'arborescence de contour à gauche affiche les options et les structures de module disponibles pour les dispositions enfants et pages. Lorsque vous sélectionnez un module dans l'arborescence de contour, vous pouvez afficher les propriétés de modèle pour le module sélectionné dans le volet de propriété à droite. Certaines de ces propriétés sont spécifiques à la modification du modèle. Le tableau suivant décrit ces propriétés.

| Nom de la propriété | Description |
|---|---|
| Nombre minimal d'exécutions | Cette propriété définit le nombre minimal d'occurrences pour le module sélectionné. Par exemple, si la valeur est définie **1**, le module est requis pour les auteurs en aval, tandis que si la valeur est définie **0** (zéro), le module est facultatif. |
| Nombre maximal d'exécutions | Cette propriété définit le nombre maximal d'occurrences pour le module sélectionné. Par exemple, si la valeur est définie **1**, le module peut être ajouté une seule fois. |
| Modules mini. (conteneurs) | Pour les modules qui contiennent d'autres modules (c'est-à-dire, pour les *modules de conteneur*), cette propriété définit le nombre minimal total de modules qui doivent être ajouté en tant qu'enfants. Par exemple, pour un module de carrousel, la valeur peut être définie comme un numéro qui est supérieur à 1. |
| Modules maxi. (conteneurs) | Pour les modules de conteneur, cette propriété définit le nombre maximal total de modules qui doivent être ajoutés en tant qu'enfants. Par exemple, pour un module de carrousel, la valeur peut être définie comme un numéro qui est inférieur à 10. |
| Verrouillé | Un contrôle booléen **Verrouillé** apparaît en regard de toutes les propriétés du module de base. Il permet à l'auteur du modèle de verrouiller un paramètre de module dans le modèle. Un paramètre de module qui est verrouillé ne peut pas être remplacé par des dispositions ou page enfants. Il devient une valeur de propriété centralement modifiable pour toutes les dispositions et pages qui utilisent le modèle. |

## <a name="create-a-new-template"></a>Créer un modèle

Pour créer un modèle, procédez comme suit.

1. Dans le volet de navigation de votre site, sélectionnez **Modèles**, pour ouvrir le modèle de vue d'inspecteur.
1. Sélectionnez **Nouveau modèle**.
1. Dans la boîte de dialogue de création de modèle, entrez un nom et une description pour le modèle. Les valeurs entrées sont affichées aux auteurs lorsqu'ils créent des pages. Entrez donc des métadonnées qui sont utiles pour les auteurs de pages. Par exemple, entrez **Utiliser ce modèle pour créer des pages marketing générales** comme description. Ces métadonnées peuvent être modifiées plus tard.
1. Sélectionnez **OK** pour créer un modèle et ouvrir l'éditeur de modèle. L'éditeur de modèle affiche une arborescence de contour à gauche et un volet de propriété à droite.
1. Dans l'arborescence de contour, développez les nœuds, puis sélectionnez l'emplacement **En-tête HTML**.
1. S'il n'existe pas encore de module à cet emplacement, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Synthèse de la page par défaut**, puis sélectionnez **OK**.
1. Dans l'arborescence de contour, sélectionnez le nouveau module, puis, dans le volet de propriété, entrez tous les paramètres par défaut qui doivent être automatiquement configurés pour toutes les pages enfants du modèle. Si vous ne souhaitez pas de paramètres par défaut, laissez le champ vide de valeurs.
1. Dans l'arborescence de contour, sélectionnez l'emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (...), puis le sélectionnez **Ajouter un module**.
1. Sélectionnez un module de conteneur de page (il ne peut y avoir qu'une option), puis sélectionnez **OK**.

Sous le nouveau module de conteneur de page, un nouvel ensemble d'emplacements (**En-tête**, **Principal**, etc.). Ici, vous pouvez ajouter et configurer les options de module qui seront accessibles des auteurs lorsqu'ils créent des pages de ce modèle. Par défaut, si vous n'ajoutez pas module à un emplacement, tous les types de modules disponibles sont pris en charge pour cet emplacement.

Le modèle est désormais techniquement valide, et peut être enregistré, archivé et utilisé pour créer des pages. Toutefois, les trois sections suivantes décrivent certains autres paramètres par défaut que vous souhaitez peut-être pour configurer en premier.

## <a name="add-a-header-and-a-footer"></a>Ajouter un en-tête et un pied de page

Si votre site a déjà un fragment d'en-tête, procédez comme suit pour ajouter un en-tête ou un pied de page à un modèle.

1. Dans l'arborescence de contour, développez l'emplacement **Corps** et le module enfant de page.
1. Sélectionnez l'emplacement **En-tête**.
1. Sélectionnez le bouton représentant des points de suspension pour l'emplacement **Pied de page**, et sélectionnez **Ajouter un fragment**.
1. Recherchez, puis sélectionnez le fragment de l'en-tête de votre site, puis sélectionnez **OK**.

Toutes les pages qui utilisent le modèle hériteront désormais automatiquement de ce fragment d'en-tête.

Si votre site n'est pas encore un fragment d'en-tête, voir [Créer un fragment](work-with-fragments.md#create-a-fragment) pour plus d'informations sur la procédure de création, puis d'exécution de la procédure précédente.

## <a name="change-the-template-theme"></a>Modifier le modèle de thème

Pour définir un thème par défaut pour toutes les pages qui utilisent un modèle, procédez comme suit.

1. Dans l'arborescence de contour à gauche, développez l'emplacement **Corps**.
1. À l'emplacement **Corps**, sélectionnez le module de conteneur de page (par exemple, **Page par défaut**).
1. Dans le volet de propriété de droite, dans le champ **Thème**, sélectionnez un thème.

Par défaut, toutes les nouvelles pages utiliseront désormais un thème sélectionné. Pour éviter que des pages de remplacer ce paramètre au niveau de la disposition ou des pages, définissez le contrôle booléen **Verrouillé** sur **Vrai**.

## <a name="add-a-script-to-a-template"></a>Ajout d'un script à un modèle

Vous pouvez ajouter des éléments de **&lt;script&gt;** HTML contenant du Javascript à votre modèle. De cette manière, vous pouvez fournir des comportements par défaut du script pour l'en tête HTML, les sections de début et de fin du corps de vos pages.

Pour ajouter un script à un modèle, procédez comme suit.

1. Dans l'arborescence de contour à gauche, sélectionnez l'emplacement où vous souhaitez ajouter l'élément **&lt;script&gt;** (par exemple, le l'en-tête, le début ou la fin du corps HTML).
1. Sélectionnez le bouton représentant des points de suspension pour l'emplacement, et sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez un module de script (par exemple, **Script externe** ou **Script intégré**).
1. Dans le volet de propriété de droite, dans le contrôle approprié de propriété du script (par exemple, **Script intégré** ou **Balises de script**), entrez le script.
1. Dans le volet de propriété, entrez tous les autres paramètres facultatifs à configurer.

> [!TIP]
> Si vous souhaitez réutiliser l'un de vos modules de script pour d'autres modèles, vous pouvez les convertir des fragments. Ainsi, vous aidez à rendre le processus de création plus efficace, et vous centralisez le processus de mise à jour. Pour plus d'informations sur la conversion d'un module de script en un fragment, voir [Enregistrer une configuration de module existante en fragment](work-with-fragments.md#save-an-existing-module-configuration-as-a-fragment).

## <a name="save-check-in-preview-and-publish-a-template"></a>Enregistrer, archiver, afficher un aperçu et publier un modèle

Pour enregistrer et archiver dans un modèle, procédez comme suit.

1. Sélectionnez **Enregistrer** en haut de l'éditeur de modèle. Les modifications enregistrées n'affectent pas les pages en aval tant qu'elles ne sont pas archivées.
1. Sélectionnez **Terminer la modification**. Vos modifications sont désormais découvrables pour les workflows en aval.

Pour afficher les modifications en aperçu, ouvrez une page existante qui utilise le modèle ou créez une page du modèle.

Après avoir prévisualisé les modifications de votre modèle, suivez l'une de ces étapes pour publier le modèle à votre site en direct :

* Accédez à **Modèles**, sélectionnez le modèle, puis sélectionnez **Publier**.
* Sélectionnez le nom de la disposition pour ouvrir l'éditeur de disposition, puis cliquez sur **Publier**.
* Publiez une page qui référence le modèle non publié. Le modèle est publié automatiquement.

> [!WARNING]
> Lorsqu'un modèle, ou tout autre élément du système de gestion de contenu (CMS), est publié, il est découvrable sur Internet. Ne publiez pas des documents ou des actifs tant que vous n'êtes pas prêt à les rendre publics. Les versions de documents enregistrées et archivées, mais qui n'ont pas été publiées, sont découvrables qu'aux utilisateurs système authentifiés.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des modèles et dispositions](templates-layouts-overview.md)

[Utilisation des mises en page prédéfinies](work-with-layouts.md)
