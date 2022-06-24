---
title: Activer les recommandations « acheter des descriptions similaires »
description: Cet article décrit comment activer la fonctionnalité de recommandations de produits « acheter des descriptions similaires » dans Microsoft Dynamics 365 Commerce.
author: bsokolov
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b935731b24f96753c814e3b496ffeeb7a92d9cc1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852006"
---
# <a name="enable-shop-similar-description-recommendations"></a>Activer les recommandations « acheter des descriptions similaires »

[!include [banner](includes/banner.md)]

Cet article décrit comment activer la fonctionnalité de recommandations de produits « acheter des descriptions similaires » dans Microsoft Dynamics 365 Commerce.

La fonctionnalité de recommandations « Acheter des description similaires » dans Dynamics 365 Commerce utilise l’intelligence artificielle et le Machine Learning (IA-ML) pour recommander des produits dont les descriptions correspondent à ce que recherchent les clients. En mettant à disposition des recommandations de type « acheter des descriptions similaires » pour tous les canaux de vente au détail dans Commerce, les détaillants peuvent aider leurs clients à trouver facilement ce qu’ils veulent.

La fonctionnalité de recommandations « acheter des descriptions similaires » utilise le nom et la description de produits initiaux pour rechercher et recommander des produits similaires dans le catalogue de produits d’un détaillant.

Les recommandations « acheter des descriptions similaires » sont disponibles dans les expériences de point de vente (PDV) et d’e-commerce.

## <a name="example-scenarios"></a>Exemple de scénarios

Les exemples de scénarios suivants illustrent les types de recommandations que la fonctionnalité « acheter des descriptions similaires » peut fournir :

- Un client regarde une paire de lunettes à monture rétro et reçoit un ensemble de recommandations pour d’autres lunettes avec un design similaire, dans le contexte du secteur du détaillant.
- Un client utilise les recommandations de la fonctionnalité « acheter des descriptions similaires » pour découvrir des saveurs de café similaires à une saveur qu’il avait précédemment achetée chez le détaillant.

## <a name="set-up-shop-similar-description-recommendations"></a>Définir les recommandations « acheter des descriptions similaires »

Les recommandations de produit sont uniquement prises en charge pour les utilisateurs de Commerce qui ont migré leur stockage vers Azure Data Lake Storage Gen2.

### <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir montrer aux clients des recommandations de type « acheter des descriptions similaires », vous devez remplir les conditions préalables suivantes :

- [Activer les recommandations de produits](enable-product-recommendations.md) au siège Commerce.
- Confirmez que le serveur multimédia prend en charge les appels HTTPS.

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a>Activer la fonctionnalité de recommandations « acheter des descriptions similaires »

Pour activer la fonctionnalité de recommandations « acheter des descriptions similaires » dans Commerce Headquarters, procédez comme suit.

1. Dans l’espace de travail **Gestion des fonctionnalités**, dans la liste des fonctionnalités disponibles, recherchez et sélectionnez **Acheter des descriptions similaires**.
1. Dans le volet droit, sélectionnez **Activer**.

> [!NOTE]
> Une fois la fonctionnalité activée, le système commence à générer des listes de recommandations de produits. Il peut falloir jusqu’à une journée avant que les listes soient disponibles et visibles en ligne et sur les terminaux de PDV.
>
> Si vous désactivez cette fonctionnalité, les autres types de recommandations de produits ne sont pas affectés. Pour plus d’informations sur les recommandations de produit, voir [Vue d’ensemble des recommandations de produits](product-recommendations.md).

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a>Ajouter un bouton Acheter des descriptions similaires aux pages de détails du produit

Une fois que vous avez activé la fonctionnalité de recommandations « acheter des descriptions similaires » dans Commerce Headquarters, vous pouvez ajouter un bouton **Acheter des descriptions similaires** dans la zone d’achat de n’importe quelle page de détails de produit (PDP). Un client qui clique sur ce bouton est redirigé vers une page dédiée **Acheter des descriptions similaires** qui affiche des produits visuellement similaires. Le client peut ensuite utiliser des sélecteurs pour filtrer davantage les produits.

Pour ajouter un bouton **Acheter des descriptions similaires** à une PDP à l’aide du générateur de site Commerce, procédez comme suit.

1. Ouvrez une page de générateur de site existante qui contient un module de zone d’achat.
1. Dans le volet de navigation de gauche, sélectionnez le module de zone d’achat.
1. Dans le volet de navigation de droite, cochez la case **Activer le lien Acheter des descriptions similaires**.
1. Sélectionnez **Enregistrer**.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier. Une fois la page publiée, la PDP comprendra un bouton **Achetez des descriptions similaires**.

L’illustration suivante montre la case à cocher **Activer le lien Acheter des descriptions similaires** et le bouton **Acheter des descriptions similaires** sur un exemple de PDP dans le générateur de site.

![Case à cocher Activer le lien Acheter des descriptions similaires et bouton Acheter des descriptions similaires sur une PDP dans le générateur de site.](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des recommandations produit](product-recommendations.md)

[Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce](enable-adls-environment.md)

[Activer les recommandations de produit](enable-product-recommendations.md)

[Activer les recommandations « acheter des aspects similaires »](shop-similar-looks.md)

[Ajuster des résultats des recommandations AI-ML](modify-product-recommendation-results.md)

[Créer manuellement des recommandations sélectionnées](create-editorial-recommendation-lists.md)

[FAQ sur les recommandations de produit](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]