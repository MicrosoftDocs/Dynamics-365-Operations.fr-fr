---
title: Activer la publication manuelle des évaluations et des avis par un modérateur
description: Cette rubrique explique comment activer la publication manuelle des évaluations et des avis par un modérateur dans Microsoft Dynamics 365 Commerce, et comment publier manuellement des évaluations et des avis.
author: gvrmohanreddy
manager: annbe
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 2b4ba835ff4540b63f6fe49cc847286f8c2a3bcf
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407816"
---
# <a name="enable-manual-publishing-of-ratings-and-reviews-by-a-moderator"></a>Activer la publication manuelle des évaluations et des avis par un modérateur

[!include [banner](includes/banner.md)]

Cette rubrique explique comment activer la publication manuelle des évaluations et des avis par un modérateur dans Microsoft Dynamics 365 Commerce, et comment publier manuellement des évaluations et des avis.

La solution d’évaluations et d’avis de Dynamics 365 Commerce utilise Azure Cognitive Services pour supprimer automatiquement les grossièretés dans les titres et le contenu des avis, et pour publier les évaluations et les avis. Par conséquent, aucune intervention manuelle n’est requise pour examiner et publier les évaluations et les avis sur votre site de commerce électronique.

Cependant, certaines entreprises peuvent préférer que des modérateurs examinent et approuvent manuellement les avis avant qu’ils ne soient publiés. Pour activer la publication manuelle des évaluations et des avis par un modérateur, vous devez activer la fonction **Exiger un modérateur pour les évaluations et les avis** dans le générateur de site de Commerce.

## <a name="enable-the-require-moderator-for-ratings-and-reviews-feature-in-commerce-site-builder"></a>Activer la fonctionnalité Exiger un modérateur pour les évaluations et les avis dans le générateur de site de Commerce

Pour activer la fonction **Exiger un modérateur pour les évaluations et les avis** ans le générateur de site de Commerce, procédez comme suit.

1. Accédez à **Accueil \> Évaluations \> Paramètres**.
1. Définissez l’option **Exiger un modérateur pour les évaluations et les avis** sur **Activé**.

> [!NOTE]
> En activant la fonction **Exiger un modérateur pour les évaluations et les avis**, vous arrêtez la publication automatique des évaluations et des avis, de sorte que la publication manuelle est désormais requise. Cependant, Azure Cognitive Services continuera de relever les grossièretés dans les titres et le contenu des avis.

<!--![Require moderator for ratings and reviews setting in Commerce site builder.](media/Ratings-reviews-settings-human-moderation.png)-->

## <a name="publish-ratings-and-reviews"></a>Publier les évaluations et les avis

Lorsque vous activez la fonction **Exiger un modérateur pour les évaluations et les avis**, un modérateur doit manuellement examiner et publier les évaluations et les avis pour qu’ils s’affichent dans votre site de commerce électronique.

Pour examiner et publier les évaluations et les avis dans le générateur de site de Commerce, procédez comme suit.

1. Accédez à **Avis \> Modération**.
1. Dans la grille, si le champ **Statut** d’une ligne est défini sur **Non publié**, l’évaluation et l’avis de cette ligne n’ont pas encore été publiés. Pour afficher uniquement les évaluations et avis non publiés, sélectionnez **Statut : examen nécessaire** dans le filtre de statut au-dessus de la grille.
1. Sélectionnez un ou plusieurs évaluations et avis dont le statut est **Non publié**, puis sélectionnez **Publier** sur la barre de commandes. Les évaluations et avis sélectionnés sont ajoutés à la file d’attente de publication et apparaîtront sur le site de commerce électronique après leur publication.

> [!NOTE]
> - Après la publication d’une évaluation et d’un avis, la valeur du statut passe de **Non publié** à une valeur null (champ vide).
> - Si vous sélectionnez plusieurs évaluations et avis qui ont des statuts mixtes, puis sélectionnez **Publier**, les évaluations et les avis qui n’ont pas encore été publiés seront publiés. Cependant, les évaluations et avis qui ont déjà été publiés ne seront pas publiés à nouveau.

L’illustration suivante montre un exemple où trois évaluations et avis non publiés sont sélectionnés sur la page **Modération** dans le générateur de site de Commerce.

![Trois évaluations et avis non publiés sélectionnés sur la page Modération dans le générateur de site de Commerce.](media/Ratings-reviews-publishing-reviews.png)

<!--![Dynamics 365 Commerce - Ratings and Review configuration 2](media/Ratings-reviews-published-reviews.png)-->
<!--![Status filter](media/Ratings-reviews-published-reviews-status-filter.png)-->

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des évaluations et avis](ratings-reviews-overview.md)

[Choix d’utilisation des évaluations et avis](opt-in-ratings-reviews.md)

[Gestion des évaluations et avis](manage-reviews.md)

[Configuration des évaluations et avis](configure-ratings-reviews.md)

[Synchronisation des évaluations de produit](sync-product-ratings.md)

[Importation et exportation des évaluations et des avis](import-export-reviews.md)

[Configurer l’authentification service à service](service-to-service-auth.md)

[FAQ sur les évaluations et avis](ratings-reviews-faq.md)
