---
title: Impact de l’extensibilité des catalogues Commerce pour les personnalisations B2B
description: Cet article décrit l’impact sur l’extensibilité de la fonctionnalité Catalogues Commerce pour B2B dans Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 06d304226270c9c63c6907190dc1038a38f70e44
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136798"
---
# <a name="extensibility-impact-of-commerce-catalogs-for-b2b-customizations"></a>Impact de l’extensibilité des catalogues Commerce pour les personnalisations B2B

[!include [banner](includes/banner.md)]

Cet article décrit l’impact sur l’extensibilité de la fonctionnalité **Catalogues Commerce pour B2B** dans Microsoft Dynamics 365 Commerce.

Si vous souhaitez étendre le contexte du catalogue à des scénarios personnalisés, vos personnalisations devront peut-être être mises à jour. Cette mise à jour suit le processus standard que les clients doivent suivre, car leurs personnalisations peuvent ne pas prendre automatiquement en charge les dernières fonctionnalités une fois les mises à niveau effectuées. Si vos personnalisations incluent une nouvelle fonctionnalité ou des corrections de bogues dans leurs expériences, nous vous recommandons de mettre à jour le code de personnalisation en conséquence. Cette mise à jour ressemble aux modifications que Microsoft aurait pu apporter au code principal.

Passez en revue les cas de personnalisation qui suivent pour déterminer si vos personnalisations doivent être mises à jour.

> [!NOTE]
> - Toutes les interfaces de programmation d’application (API) de marchandisage doivent être sensibles au catalogue. Par conséquent, il est essentiel que vous transmettiez le paramètre **CatalogID**.
> - Le catalogue par défaut (**CatalogID**=**0**) n’est pas un catalogue valide pour les utilisateurs B2B connectés. Par conséquent, tous les appels d’API qui transmettent "0" ou utilisent une valeur par défaut échoueront, car les utilisateurs du site n’ont pas accès au catalogue 0. Pour obtenir l’expérience correcte, les appels d’API client doivent être mis à jour afin qu’ils transmettent l’ID de catalogue qui a été sélectionné dans le sélecteur de catalogue. Si vous utilisez une valeur par défaut et que l’utilisateur change de catalogue, le site Web doit fournir les données du catalogue sélectionné. Par conséquent, pour correspondre aux API exécutées à partir du code Commerce principal, les API personnalisées doivent transmettre le catalogue sélectionné.

Les cas de personnalisation suivants nécessitent des mises à jour de développement :

- **Cas 1 :** Un client présente sa propre [action de données](e-commerce-extensibility/data-actions.md) qui appelle une API ou une action de données liée au produit. Les étapes de mise à jour suivantes sont obligatoires :

    1. Si l’action de données utilise un appel d’API direct, mettez à jour l’action de données afin qu’elle transmette l’ID de catalogue, comme illustré dans l’exemple suivant.

        ![Action de données mise à jour qui transmet l’ID de catalogue.](./media/customization1_a.png)

    1. Si l’action de données appelle une autre action de données liée au produit dans la personnalisation, le code doit être mis à jour afin qu’il transmette certains nouveaux paramètres, tels que **requestContext**. Le paramètre **requestContext** est utilisé pour récupérer l’ID de catalogue actuel, comme illustré dans l’exemple suivant.

        ![Action de données mise à jour qui transmet le nouveau paramètre.](./media/customization1_b.png)

- **Cas 2 :** Un client a une [action de données remplacée](e-commerce-extensibility/data-action-overrides.md). L’étape de mise à jour suivante est obligatoire :

    - Mettez à jour l’action de données comme pour le cas 1.

- **Cas 3 :** Un client dispose d’une extension de vue, d’un module d’injection de script ou d’un [module cloné](e-commerce-extensibility/modules-overview.md#clone-a-module-library-module) qui inclut les appels aux API ou les actions de données. L’étape de mise à jour suivante est obligatoire :

    - Mettez à jour le code comme pour le cas 1, comme indiqué dans l’exemple d’illustration suivant.

       ![Code mis à jour qui transmet le nouveau paramètre.](./media/customization3.png)

- **Cas 4 :** Un client utilise un appel d’API **getById**. L’étape de mise à jour suivante est obligatoire :

    - Passez à l’appel d’API **getByIds** à la place, car l’appel d’APT **getById** a certaines limitations et ne prend pas en charge la reconnaissance du catalogue.

- **Cas 5 :** Un client a une action de données qui récupère des informations pour plusieurs produits qui peuvent provenir de différents catalogues. L’étape de mise à jour suivante est obligatoire :

    - Fractionnez les appels d’API par ID de catalogue. Par exemple, pour les API de panier, le panier peut contenir des produits de différents catalogues. Les lignes de produits doivent être regroupées par ID de catalogue, et elles doivent appeler l’API pour chaque catalogue séparément, comme illustré dans l’exemple suivant.

        ![Action de données mise à jour qui regroupe les gammes de produits par ID de catalogue.](./media/customization5.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer des catalogues Commerce pour les sites B2B](catalogs-b2b-sites.md)

[FAQ sur les catalogues Commerce pour le B2B](catalogs-b2b-sites-FAQ.md)

[Module de sélection de catalogue](catalog-picker.md)
