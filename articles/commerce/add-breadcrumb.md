---
title: Module de barre de navigation
description: Cet article couvre les modules de piste de navigation et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: fe5dfea7e579d54d11be35eb657a1c1f617a5724
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277083"
---
# <a name="breadcrumb-module"></a>Module de barre de navigation

[!include [banner](includes/banner.md)]

Cet article couvre les modules de piste de navigation et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Les modules de piste de navigation sont utilisés pour offrir une navigation secondaire sur les pages du site. Ils sont généralement affichés en haut d’une page, sous l’en-tête. Bien que des modules de piste de navigation puissent être ajoutés à n’importe quelle page, ils sont le plus souvent utilisés sur les pages de détails du produit (PDP), pour afficher la hiérarchie de catégories de produits et fournir un moyen rapide de se déplacer sur un site. Un module de piste de navigation peut également être utilisé pour afficher un lien « Retour aux résultats » lorsque les utilisateurs ouvrent une page PDP à partir d’une page de recherche ou de liste. De cette façon, les utilisateurs peuvent retourner rapidement à leur page de liste filtrée pour continuer leurs achats.

Sur les pages qui présentent un contexte de catégorie de produit, telles que les pages PDP et les pages de catégorie, les modules de piste de navigation affichent la hiérarchie de catégories. Sur les pages qui ne présentent pas de contexte de catégorie, les modules de piste de navigation affichent **&lt;Racine du site&gt; / &lt;Page en cours&gt;** par défaut. Les modules de piste de navigation peuvent également être configurés manuellement sur d’autres types de pages du site pour afficher des liens vers des pages spécifiques du site.

> [!NOTE]
> Le module de piste de navigation est disponible dans la version 10.0.12 de Dynamics 365 Commerce.

L’image suivante montre un exemple de module de piste de navigation qui montre la hiérarchie des catégories sur une page PDP.

![Exemple de module de piste de navigation.](./media/ecommerce-breadcrumb.PNG)

## <a name="breadcrumb-module-settings"></a>Paramètres du module de piste de navigation

Le module de piste de navigation repose sur le **Type d’affichage de la piste de navigation sur la PDP**, qui est défini dans **Paramètres du site \> Extensions** dans le générateur de site. Ce paramètre a trois valeurs possibles :

- **Afficher la hiérarchie de catégories** – Lorsque cette valeur est sélectionnée, le module de piste de navigation affichera la hiérarchie complète des catégories du produit affiché sur la page PDP.
- **Afficher Retour aux résultats** – Lorsque cette valeur est sélectionnée, le module de piste de navigation affiche un lien « Retour aux résultats » sur une PDP si l’utilisateur a ouvert la PDP à partir d’un module qui autorise un lien « Retour aux résultats ». Cette fonctionnalité est disponible lorsque les utilisateurs naviguent à partir des pages de catégorie, de recherche, de liste et de liste de recommandations. Pour prendre en charge cette fonctionnalité, les modules de collection de produits et de résultats de recherche ont une propriété nommée **Autoriser le retour aux résultats sur les PDP**. Cette propriété vous donne la flexibilité de définir quels modules doivent prendre en charge la fonctionnalité de lien « Retour aux résultats » sur la PDP. Par exemple, lorsque **Retour aux résultats** est sélectionné pour le paramètre **Type d’affichage de la piste de navigation sur la PDP** du module de piste de navigation, et que **Autoriser le retour aux résultats sur la PDP** est sélectionné pour le module de résultats de recherche de la page de recherche, un lien « Retour aux résultats » est affiché lorsque les utilisateurs naviguent de la page de recherche vers une page PDP.
- **Afficher la hiérarchie de catégories et retour aux résultats** – Cette valeur est une combinaison des deux précédentes. Lorsque cette valeur est sélectionnée, le module de piste de navigation affiche à la fois la hiérarchie complète des catégories et un lien « Retour aux résultats » (s’il est configuré) sur une PDP.

> [!IMPORTANT]
> Ces paramètres sont disponibles dans la version 10.0.12 de Dynamics 365 Commerce. Si vous effectuez une mise à jour à partir d’une ancienne version de Dynamics 365 Commerce, vous devez mettre à jour manuellement le fichier appsettings.json. Pour obtenir des instructions de mise à jour du fichier appsettings.json, consultez [Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="breadcrumb-module-properties"></a>Propriétés du module de piste de navigation

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| Racine | Texte ou lien| Cette propriété facultative spécifie le texte du lien et une cible de lien pour la racine du site de la piste de navigation. Si cette propriété n’est pas configurée, aucune racine n’est définie. |
| Lien de piste de navigation | Lien | Cette propriété facultative spécifie des liens pour une piste de navigation configurée manuellement, si ces liens sont requis. Les liens apparaissent dans l’ordre dans lequel ils sont répertoriés. |

## <a name="add-a-breadcrumb-module-to-a-new-page"></a>Ajouter un module de piste de navigation à une nouvelle page

Pour ajouter un module de piste de navigation à une page PDP et définir les propriétés requises, procédez comme suit.

1. Accédez à **Paramètres du site \> Extensions** puis, pour le paramètre **Type d’affichage de la piste de navigation sur la PDP**, sélectionnez **Afficher la hiérarchie de catégories**.
1. Accédez à **Modèles** et sélectionnez le modèle PDP.
1. Dans l’emplacement **Conteneur** qui contient le module de zone d’achat, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Barre de navigation**, puis cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages** et ouvrez une page PDP qui utilise le modèle PDP. Si aucune page PDP n’existe encore, créez-en une.
1. Dans l’emplacement **Conteneur** qui contient le module de zone d’achat, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Barre de navigation**, puis cliquez sur **OK**.
1. Dans le volet des propriétés de l’emplacement **Piste de navigation**, sous **Racine**, sélectionnez **Texte du lien**.
1. Dans la boîte de dialogue **Texte du lien**, entrez **Accueil** puis, sous **Cible du lien**, sélectionnez **Ajouter un lien**.
1. Dans la boîte de dialogue **Ajouter un lien**, sélectionnez un lien pour la racine de la piste de navigation, puis sélectionnez **OK**.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module du menu de navigation](nav-menu-module.md)

[Module de sélection de site](site-selector.md)

[Vue d’ensemble de la page d’arrivée de la catégorie par défaut et de la page des résultats de la recherche](category-search-page-overview.md)

[Modules de collecte de produits](product-collection-module-overview.md)

[Module Zone d’achat](add-buy-box.md)

[Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
