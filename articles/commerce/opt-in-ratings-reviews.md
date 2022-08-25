---
title: Choix d’utilisation des évaluations et avis
description: Cet article explique comment adhérer à l’utilisation des classements et des évaluations de votre site Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 00fd30ded916cc6b587ceff67728e7d964714716
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269160"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>Choix d’utilisation des évaluations et avis

[!include [banner](includes/banner.md)]

Cet article explique comment adhérer à l’utilisation des classements et des évaluations de votre site Microsoft Dynamics 365 Commerce.

La solution de classements et d’évaluations est une solution omnicanale que vous pouvez rendre disponible dans Dynamics 365 Commerce en utilisant Microsoft Dynamics Lifecycle Services (LCS). LCS est un portail d’administration que les détaillants utilisent pour gérer leurs environnements de la mise en service jusqu’à la mise hors service.

Pour utiliser la solution de classements et d’évaluations sur votre site web Commerce, activez les classements et les évaluations lors du déploiement de votre site de commerce électronique sur Dynamics 365 Commerce.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Choix d’utilisation des évaluations et avis

Pour adhérer à l’utilisation des classements et évaluations sur votre site, procédez comme suit.

1. Suivez les étapes dans [Déployer un nouveau site de commerce électronique](deploy-ecommerce-site.md).
1. Lorsque vous êtes toujours dans LCS, accédez à **Paramétrage du déploiement de la vente au détail \> Autres paramètres**.
1. Définissez l’option **Activer le service de classements et évaluations** sur **Activé**.
1. Dans le champ **Groupe de sécurité AAD pour le modérateur de classements et d’évaluations**, entrez l’ID du groupe de sécurité Microsoft Azure Active Directory (Azure AD) qui inclut les modérateurs des classements et évaluations.

    ![Choix d’utilisation des évaluations et avis.](media/LCS_RnR_Preference_2.png)

1. Terminez le processus d’initialisation de commerce électronique.

> [!NOTE] 
> Si vous êtes un client Dynamics 365 Commerce existant, qui a déjà déployé un site de commerce électronique sans choisir les classements et les évaluations, mais que vous souhaitez maintenant les utiliser à partir du progiciel Dynamics 365 Commerce, veuillez envoyer une demande de service. Pour des informations sur l’envoi d’une demande de service, voir [Soumettre des demandes de service](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json). 

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des évaluations et avis](ratings-reviews-overview.md)

[Gestion des évaluations et avis](manage-reviews.md)

[Configuration des évaluations et avis](configure-ratings-reviews.md)

[Synchronisation des évaluations de produit dans Dynamics 365 Commerce](sync-product-ratings.md)

[Activer la publication manuelle des évaluations et des avis par un modérateur](manual-publish-rating-reviews.md)

[Importation et exportation des évaluations et des avis](import-export-reviews.md)

[Configurer l’authentification service à service](service-to-service-auth.md)

[FAQ sur les évaluations et avis](ratings-reviews-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
