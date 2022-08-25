---
title: Import et export des évaluations et des avis
description: Cet article décrit comment importer et exporter des évaluations et des avis de produits dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: f369e3cd208cdfba816f817ead75374ee6982912
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271933"
---
# <a name="import-and-export-ratings-and-reviews"></a>Import et export des évaluations et des avis

[!include [banner](includes/banner.md)]

Cet article décrit comment importer et exporter des évaluations et des avis de produits dans Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce offre les [évaluations et avis](ratings-reviews-overview.md) en tant que solution omnicanal. Lorsque vous passerez à la solution d’évaluations et d’avis de Dynamics 365 Commerce, vous souhaiterez peut-être transférer vos données d’évaluations et d’avis existantes vers la plateforme Commerce. Vous pouvez également exporter les données d’évaluations et d’avis de Commerce, en fonction des besoins de votre entreprise. Un connecteur Power Automate vous permet d’importer des évaluations et des avis dans Commerce et de les exporter depuis Commerce.

> [!NOTE]
> Pour plus d’informations sur la prise en main des flux logiques dans Power Automate, consultez [Créer un flux cloud dans Power Automate](/power-automate/get-started-logic-flow).

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir importer et exporter des évaluations et des avis, vous devez remplir les conditions préalables suivantes :

- La solution d’évaluations et d’avis doit être activée pour votre site d’e-commerce sur la plateforme Commerce. Pour plus d’informations, voir [Choix d’utilisation des évaluations et avis](opt-in-ratings-reviews.md).
- Le connecteur Power App Ratings and Reviews de Dynamics 365 doit être configuré pour activer les actions « soumettre des avis » ou « exporter des avis » dans Power Automate. Pour plus d’informations, voir [Dynamics 365 Commerce - Évaluations et avis (version préliminaire)](/connectors/dynamics365ratingsre/).
- L’authentification de service à service (S2S) doit être configurée pour appeler en toute sécurité l’interface de programmation d’application (API) des évaluations et des avis depuis l’extérieur de Commerce. Pour plus d’informations, voir [Configurer l’authentification de service à service](service-to-service-auth.md).

## <a name="import-ratings-and-reviews"></a>Importer des évaluations et des avis

Pour importer les données d’évaluations et d’avis de votre système existant dans Commerce, vous devez ajouter le connecteur Power Automate Ratings and Review de Dynamics 365 à un flux Power Automate existant ou nouveau. Pour plus d’informations, voir [Dynamics 365 Commerce - Évaluations et avis (version préliminaire)](/connectors/dynamics365ratingsre/).

> [!IMPORTANT]
> Pour pouvoir effectuer cette procédure, vous devez [configurer l’authentification S2S](service-to-service-auth.md).

Pour importer des évaluations et des avis dans Commerce à l’aide du connecteur Power Automate Ratings and Review de Dynamics 365, procédez comme suit.

1. Sélectionnez l’action **Soumettre un avis utilisateur**.
1. Établissez une connexion en utilisant les informations d’application Azure Active Directory (Azure AD) qui ont été créées lorsque vous avez configuré l’authentification S2S. Pour plus d’informations, voir [Configurer l’authentification de service à service](service-to-service-auth.md).
1. L’action **Soumettre un avis utilisateur** prend un avis la fois. Par conséquent, répétez l’action. Utilisez les avis source sous forme de liste pour soumettre des avis groupés.
    
## <a name="export-ratings-and-reviews"></a>Exporter des évaluations et des avis

Pour exporter les données d’évaluations et d’avis depuis Commerce, vous devez ajouter le connecteur Power Automate Ratings and Review de Dynamics 365 à un flux Power Automate existant ou nouveau. Pour plus d’informations, voir [Dynamics 365 Commerce - Évaluations et avis (version préliminaire)](/connectors/dynamics365ratingsre/).

Pour exporter des évaluations et des avis depuis Commerce à l’aide du connecteur Power Automate Ratings and Review de Dynamics 365, procédez comme suit.

1. Sélectionnez l’action **Exporter tous les avis**.
1. Terminez l’action. 

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des évaluations et avis](ratings-reviews-overview.md)

[Choix d’utilisation des évaluations et avis](opt-in-ratings-reviews.md)

[Gestion des évaluations et avis](manage-reviews.md)

[Configuration des évaluations et avis](configure-ratings-reviews.md)

[Synchronisation des évaluations de produit](sync-product-ratings.md)

[Activer la publication manuelle des évaluations et des avis par un modérateur](manual-publish-rating-reviews.md)

[Configurer l’authentification service à service](service-to-service-auth.md)

[FAQ sur les évaluations et avis](ratings-reviews-faq.md)
