---
title: Modules de comparaison de produits
description: Cet article décrit les modules de comparaison de produits et comment les mettre en œuvre afin que les clients puissent effectuer des comparaisons de produits sur les sites e-commerce de Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 08/09/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: ced471dd7e3e4c3e9be938b295edaad626a890a3
ms.sourcegitcommit: 92c4506be7dc14078e3c4f1d182edd895d64ffe0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9247651"
---
# <a name="product-comparison-modules"></a>Modules de comparaison de produits

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Cet article décrit les modules de comparaison de produits et comment les mettre en œuvre afin que les clients puissent effectuer des comparaisons de produits sur les sites e-commerce de Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Les modules de comparaison de produits et de bouton de comparaison de produits sont disponibles à partir de la mise en production de la version 10.0.29 de Dynamics 365 Commerce. Ils peuvent être utilisés à la fois pour les sites Web d’entreprise à consommateur (B2C) et d'interentreprises (B2B).

La fonctionnalité de comparaison de produits permet aux acheteurs de comparer les détails des produits sur une page de comparaison de produits pour les aider à prendre de meilleures décisions d’achat. Cette fonctionnalité est configurée dans le constructeur de sites Commerce à l’aide du module de comparaison de produits. Sur les pages de liste de produits (PLP), telles que les résultats de catégorie, les résultats de recherche et les pages de collections de produits, vous pouvez configurer un bouton de comparaison de produits qui permet aux acheteurs d’ajouter des produits à un plateau de comparaison. Cette fonctionnalité est configurée dans le constructeur de site en utilisant le module de bouton de comparaison de produits, qui fonctionne comme le [module de vue rapide](quick-view-module.md).

Lorsque les utilisateurs du site ajoutent des produits pour la comparaison en les sélectionnant sur des vignettes de produits, un plateau de comparaison apparaît en bas de la page. Le plateau de comparaison montre les produits que l’acheteur compare actuellement, ainsi que de brefs aperçus des produits. Les utilisateurs du site peuvent également ajouter des produits à partir des pages de détails des produits (PDP), et ils peuvent ajouter des variantes de produits spécifiques à comparer avec les produits génériques.

Une fois que les clients ont ajouté quelques produits au plateau de comparaison, ils peuvent sélectionner **Comparer** pour être redirigé vers une page de comparaison de produits. La page de comparaison de produits affiche les détails du produit pour chaque produit sélectionné afin que les clients puissent comparer les images, les prix, les dimensions du produit (taille, style et couleur), les informations de notation agrégées et d’autres attributs du produit.

L’illustration suivante montre des exemples de bouton de comparaison de produits, de bouton de suppression de la comparaison, de plateau de comparaison et de page de comparaison de produits.

![Vue d'ensemble de la comparaison des produits montre le bouton comparateur de produits, le bouton de suppression de la comparaison, le panneau du plateau de comparaison et la page de comparaison de produits.](./media/Product-Comparison-Overview.png)

> [!NOTE]
> - La page de comparaison de produits compare un ensemble par défaut de propriétés de produit et tous les attributs pouvant être affichés sur un PDP pour un produit donné.
> - Les propriétés telles que le mode de livraison, l’inventaire disponible et l’unité de mesure ne peuvent pas être affichées sur une page de comparaison de produits.
> - Les clients peuvent ajouter des produits de différentes catégories au plateau de comparaison, à condition que les produits soient du même catalogue.
> - La fonctionnalité de comparaison de produits est actuellement limitée à la comparaison de produits dans un catalogue individuel. Les utilisateurs du site ne peuvent pas effectuer de comparaisons entre catalogues.
> - Vous devez vous assurer que la propriété **Module de rendu côté client** est effacée pour tous les modules de comparaison de produits.
> - Vous devez vous assurer que la mise en cache au niveau de la page est désactivée pour toutes les pages où le module de comparaison de produits est utilisé. Ces pages incluent des PDP, des PLP et des pages de comparaison de produits. Pour plus d’informations, voir [Configurer la mise en cache de page](e-commerce-extensibility/page-caching.md).

L’illustration suivante présente un exemple de page de comparaison de produits.

![Page de comparaison de produits.](./media/Product-Comparison-Page.png)

## <a name="add-the-product-comparison-module-to-a-new-product-comparison-page"></a>Ajouter le module de comparaison de produits à une nouvelle page de comparaison de produits

Vous pouvez créer une page de comparaison de produits dédiée en ajoutant un module de comparaison de produits au corps d’une page. En plus de permettre aux clients de comparer les détails des produits de différents produits, vous pouvez configurer le module de comparaison de produits pour donner aux clients la possibilité de finaliser rapidement leur achat après avoir comparé les produits. Le module de comparaison de produits contient également un emplacement **Comparaison vide**, où vous pouvez ajouter un module de bloc de contenu qui décrit l’état vide (par exemple « Votre comparaison de produits est vide »).

Pour ajouter un module de comparaison de produits à une nouvelle page de comparaison de produits, suivez ces étapes.

1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Créer une nouvelle page**, sous **Nom de la page**, entrez un nom de page approprié (for example, **Comparaison de produits**), puis sélectionnez **Suivant**.
1. Sous **Choisir un modèle**, sélectionnez le modèle approprié (par exemple, le modèle qui est utilisé par votre page de catégorie par défaut), puis sélectionnez **Suivant**.
1. Sous **Choisir une mise en page**, sélectionnez une mise en page (par exemple, **Disposition flexible**), puis sélectionnez **Suivant**.
1. Sous **Revoir et terminer**, vérifiez la configuration de la page. Si vous devez modifier les informations de la page, sélectionnez **Précédent**. Si les informations de la page sont correctes, sélectionnez **Créer une page**.
1. Dans l’**Emplacement principal**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Comparaison de produits**, puis sélectionnez **OK**.
1. Dans l’emplacement **Bouton de vue rapide**, sélectionnez les points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Visualisation rapide de produit**, puis sélectionnez **OK**.
1. Dans le volet des propriétés sur la droite, configurez les propriétés du module **Visualisation rapide de produit**.
1. Dans l’emplacement **Comparaison vide**, sélectionnez les points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Bloc de contenu**, puis cliquez sur **OK**.
1. Dans le volet des propriétés sur la droite, configurez les propriétés du module **Bloc de contenu**. 
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

L’illustration suivante montre un exemple d'une page de comparaison vide dans le générateur de site.

![Module de comparaison de produits.](./media/Product-comparison-module.png)

## <a name="add-a-product-comparison-button-to-product-tiles-on-search-and-category-results-pages"></a>Ajouter un bouton de comparaison de produits aux vignettes de produits sur les pages de résultats de recherche et de catégorie

Le bouton de comparaison de produits permet aux utilisateurs d’ajouter rapidement un produit au plateau de comparaison lorsqu’ils parcourent les produits sur une page de liste. Ils peuvent ajouter un ou plusieurs produits au plateau de comparaison depuis une page de liste sans avoir à passer par un PDP.

Le bouton de comparaison de produits est pris en charge par les modules de collecte de produits, de résultats de recherche, et de boîte d'achat PDP.

Pour ajouter un bouton de comparaison de produits aux vignettes de produits sur les pages de résultats de recherche et de catégorie, suivez ces étapes.

1. Dans le constructeur de site, accédez à **Pages**, et ouvrez la page de catégorie à laquelle vous souhaitez ajouter un bouton de comparaison de produits.
1. Dans l’**Emplacement principal**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Résultats de la recherche**, puis cliquez sur **OK**.
1. Dans l’emplacement **Bouton de comparaison de produits** du module **Résultats de la recherche**, sélectionnez les points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Bouton de comparaison de produits**, puis sélectionnez **OK**.
1. Dans le volet des propriétés sur la droite, configurez les propriétés du module **Bouton de comparaison de produit**.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="specify-the-maximum-number-of-products-to-show-in-the-comparison-tray"></a>Spécifiez le nombre maximum de produits à afficher dans le plateau de comparaison

Vous pouvez spécifier le nombre maximum de produits à afficher dans le plateau de comparaison en allant sur **Paramètres du site \> Extensions** dans le constructeur de site. Vous pouvez configurer des limites maximales distinctes pour les vues sur ordinateur et sur mobile/tablette. Par défaut, aucune limite ne sera appliquée si aucune limite maximale n’est définie.

> [!NOTE]
> Pour une expérience de navigation optimale, nous vous recommandons de définir le nombre maximum de produits dans le plateau de comparaison à **2** pour la fenêtre d'affichage mobile et à **4** pour la fenêtre d'affichage de bureau afin de réduire la quantité de défilement horizontal nécessaire.

Pour spécifier le nombre maximum de produits dans le plateau de comparaison, suivez ces étapes.

1. Dans le constructeur de site, accédez à **Paramètres du site \> Extensions**.
1. Pour la propriété **Produits dans la limite de comparaison - appareils de bureau**, entrez le nombre maximum de produits qui doivent être affichés dans le plateau de comparaison pour les fenêtres d'affichage de bureau.
1. Pour la propriété **Produits dans la limite de comparaison - appareils mobiles et tablettes**, entrez le nombre maximum de produits qui doivent être affichés dans le plateau de comparaison pour les fenêtres d'affichage de mobile et de tablette.
1. Dans la barre de commande, sélectionnez **Enregistrer et publier**.

![Paramètres du site pour limiter les produits dans le plateau de comparaison.](./media/Site-settings-to-limit-products-in-comparison-tray.png)
