---
title: Liste de produits tenant compte des stocks
description: Cet article décrit comment les organisations peuvent configurer des pages de liste de produits sur leur site Web Microsoft Dynamics 365 Commerce de commerce électronique afin qu’ils tiennent compte des stocks.
author: boycez
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-23
ms.openlocfilehash: e33a4dd8650ee2e371c51c5a19e955f2d2bdade2
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405551"
---
# <a name="inventory-aware-product-listing"></a>Liste de produits tenant compte des stocks

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Cet article décrit comment les organisations peuvent configurer des pages de liste de produits sur leur site Web Microsoft Dynamics 365 Commerce de commerce électronique afin qu’ils tiennent compte des stocks. Les pages de liste de produits incluent les pages de destination des catégories et les pages de résultats de recherche.

Les acheteurs s’attendent généralement à ce que la découverte d’un produit dans un site Web de e-commerce tienne compte des stocks, afin qu’ils puissent décider quoi faire s’il n’y a pas de stock pour un produit. La catégorie [Bibliothèque de modules Commerce](starter-kit-overview.md) et les modules de résultats de la recherche peuvent être configurés pour intégrer les données de stocks. De cette façon, ils peuvent fournir les expériences suivantes :

- Affichez les étiquettes de niveau d’inventaire à côté des produits.
- Masquer les produits en rupture de stock de la liste des produits.
- Déplacez les produits en rupture de stock en bas des pages de liste des produits.
- Prenez en charge le filtrage des produits basé sur les stocks.

Pour activer ces expériences, vous devez d’abord activer la fonctionnalité **Découverte améliorée des produits d’e-commerce pour tenir compte des stocks** dans Commerce headquarters.

> [!NOTE]
> Dans Commerce version 10.0.29 et versions ultérieures, la fonctionnalité **Découverte améliorée des produits de commerce électronique pour tenir compte des stocks** est activée par défaut.

## <a name="set-up-product-attribute-for-inventory-availability"></a>Configurer l’attribut de produit pour la disponibilité des stocks

La liste de produits prenant en charge les stocks utilise le cadre des attributs de produit. Au préalable, un attribut de produit dédié doit être créé pour capturer les données de disponibilité des stocks.

Pour configurer l’attribut de produit pour la disponibilité de stocks dans Commerce headquarters, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> IT vente au détail et commerce \> Produits et stock \> Remplir les attributs de produit avec le niveau de stock**.
1. Dans la boîte de dialogue **Remplir les attributs de produit avec le niveau de stock**, dans le champ **Nom de l’attribut de produit et du type**, entrez un nom personnalisé pour l’attribut de produit dédié qui sera créé pour capturer les données d’inventaire.
1. Dans le champ **Disponibilité des stocks en fonction de**, sélectionnez le type de quantité sur laquelle le calcul du niveau de stock doit être basé : **Physique disponible** ou **Total disponible**.
1. Définissez l’option **Traitement par lots** sur **Oui**.
1. Cliquez sur **OK**.

> [!NOTE]
> Pour un calcul cohérent du niveau de stock sur les pages de votre site web d’e-commerce, assurez-vous de sélectionner le même type de quantité pour **Disponibilité des stocks en fonction de** pour la tâche **Remplir les attributs de produit avec le niveau de stock** et le paramètre **Niveau de stock basé sur** dans le générateur de site Commerce.

Une fois l’attribut de produit dédié créé, l’étape suivante consiste à configurer l’attribut pour le canal en ligne.

Pour configurer l’attribut pour le canal en ligne dans Commerce headquarters, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Catégories de canal et attributs de produit**.
1. Sélectionnez le canal en ligne pour activer l’expérience de liste des produits tenant compte des stocks.
1. Sélectionnez et ouvrez un groupe d’attributs associé, puis ajoutez-y l’attribut de produit nouvellement créé.
1. Accédez à **Retail et Commerce \> Informatique Retail et Commerce \> Programme de distribution**, et exécutez la tâche **1150** (**Catalogue**). Nous vous recommandons de planifier cette tâche en tant que traitement par lots qui s’exécute à la même fréquence que la tâche **Remplir les attributs de produit avec le niveau de stock**.

> [!NOTE]
> Dans Commerce version 10.0.26 et antérieure, après avoir ajouté l’attribut de produit de disponibilité de l’inventaire à un groupe d’attributs, vous devez également sélectionner **Définir les métadonnées d’attribut**, puis activez les options **Afficher l’attribut sur le canal**, **Récupérable**, **Peut être affiné** et **Peut être interrogé** pour le nouvel attribut de produit.

## <a name="configure-the-display-behavior-for-out-of-stock-products-on-product-listing-pages"></a>Configurer le comportement d’affichage des produits en rupture de stock sur les pages de liste de produits

Une fois toutes les étapes de configuration précédentes terminées, les affinements des pages de catégories et de résultats de recherche disposeront d’une option de filtre basée sur l’inventaire. Une étiquette de niveau de stock sera affichée pour chaque vignette de produit qui apparaît sur la page.

La page de catégorie et de résultats de recherche affiche les produits au niveau principal, et non au niveau de la variante de produit. Le niveau de stock affiché à côté de chaque produit est un niveau de stock agrégé qui est déterminé par le niveau de stock de toutes les variantes d’un produit. Le niveau de stock d’une variante est calculé en fonction du stock disponible de cette variante dans l’entrepôt par défaut du canal en ligne dans Commerce headquarters. Le niveau de stock d’un produit principal a deux valeurs possibles qui représentent les états en stock et en rupture de stock. Un produit principal est considéré comme en rupture de stock quand toutes ses variantes sont en rupture de stock. Sinon, le produit est considéré comme en stock. L’étiquette de la valeur est extraite de la définition [Niveau de stock](inventory-buffers-levels.md). Si aucun niveau de stock n’est défini, les étiquettes par défaut (en anglais) sont **Disponible** et **Rupture de stock**.

Vous pouvez ensuite configurer le paramètre **Paramètres de stock pour les pages de liste de produits** dans le générateur de site Commerce pour contrôler la façon dont la catégorie et la page des résultats de recherche affichent les produits en rupture de stock. Pour plus d’informations, voir [Appliquer les paramètres de stock](inventory-settings.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
