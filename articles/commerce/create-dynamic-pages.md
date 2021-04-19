---
title: Créer des pages e-commerce dynamiques basées sur des paramètres d’URL
description: Cette rubrique décrit comment configurer une page d’e-commerce Microsoft Dynamics 365 Commerce pouvant diffuser du contenu dynamique, en fonction des paramètres d’URL.
author: StuHarg
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8f59b80880e6947e1b45c110df0e78d4bdd57c5d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795809"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a>Créer des pages e-commerce dynamiques basées sur des paramètres d’URL

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment configurer une page d’e-commerce Microsoft Dynamics 365 Commerce pouvant diffuser du contenu dynamique, en fonction des paramètres d’URL.

Une page d’e-commerce peut être configurée pour diffuser un contenu différent, en fonction d’un segment dans le chemin de l’URL. Par conséquent, la page est appelée page dynamique. Le segment est utilisé comme paramètre pour récupérer le contenu de la page. Par exemple, une page nommée **blog\_observateur** est créée et associée à l’URL `https://fabrikam.com/blog`. Cette page peut ensuite être utilisée pour afficher un contenu différent, en fonction du dernier segment du chemin de l’URL. Par exemple, le dernier segment de l’URL `https://fabrikam.com/blog/article-1` est **article-1**.

Des pages personnalisées distinctes qui remplacent la page dynamique peuvent également être associées à des segments dans le chemin de l’URL. Par exemple, une page nommée **blog\_résumé** est créée et associée à l’URL `https://fabrikam.com/blog/about-this-blog`. Lorsque cette URL est demandée, la page **blog\_résumé** associée au paramètre **/about-this-blog** est renvoyée à la place de la page **blog\_observateur**.

> [!NOTE]
> La fonctionnalité d’hébergement, de récupération et d’affichage du contenu de page dynamique est implémentée à l’aide d’un module personnalisé. Pour plus d’informations, consultez [Extensibilité des canaux en ligne](e-commerce-extensibility/overview.md).

## <a name="set-up-a-dynamic-e-commerce-page"></a>Configurer une page d’e-commerce dynamique

Pour configurer une page d’e-commerce dynamique, vous devez créer la page dynamique, créer l’URL de base et configurer l’itinéraire vers la page dynamique.

### <a name="create-the-page-that-will-serve-dynamic-content"></a>Créer la page qui diffusera du contenu dynamique

Pour créer une page qui diffusera du contenu dynamique, suivez les étapes de la rubrique [Ajouter une nouvelle page de site](add-new-page.md). La page que vous créez nécessitera l’implémentation d’un module qui utilise le dernier segment du chemin d’URL pour récupérer le contenu d’une source de données externe. Pour plus d’informations sur le développement de modules personnalisés, consultez la rubrique [Extensibilité des canaux en ligne](e-commerce-extensibility/overview.md).

### <a name="create-the-base-url-for-the-dynamic-page"></a>Créer l’URL de base pour la page dynamique

Pour créer l’URL de base de la page dynamique dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **URL**, et sélectionnez **Nouveau \> Nouvelle URL**.
1. Dans la boîte de dialogue **Créer une nouvelle URL**, sélectionnez **Page interne**. Sous **Chemin de l’URL**, entrez le chemin qui servira de racine à la page dynamique (dans cet exemple, **/blog**). Sélectionnez ensuite **Suivant**.
1. Dans la boîte de dialogue **Sélectionner une page**, sélectionnez la page que vous avez créée pour servir de page dynamique, puis sélectionnez **Enregistrer**.
1. Sélectionnez **Publier**.

### <a name="configure-the-route-to-the-dynamic-page"></a>Configurer l’itinéraire vers la page dynamique

Pour configurer l’itinéraire vers la page dynamique dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **Paramètres du site \> Extensions**.
1. Sous **Chemins d’URL paramétrés**, sélectionnez **Ajouter**, puis entrez le chemin de l’URL que vous avez entré lors de la création de l’URL (dans cet exemple, **/blog**).
1. Sélectionnez **Enregistrer et publier**.

Une fois l’itinéraire configuré, toutes les demandes adressées au chemin d’URL paramétré renverront la page associée à cette URL. Si des demandes contiennent un segment supplémentaire, la page associée sera renvoyée et le contenu de la page sera récupéré en utilisant le segment comme paramètre. Par exemple, `https://fabrikam.com/blog/article-1` retournera la page **blog\_résumé**, et le contenu de la page sera récupéré en utilisant le paramètre **/article-1**.

## <a name="override-a-parameterized-url-with-a-custom-page"></a>Remplacer une URL paramétrée par une page personnalisée

Pour remplacer une URL paramétrée par une page personnalisée dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **URL**, et sélectionnez **Nouveau \> Nouvelle URL**.
1. Dans la boîte de dialogue **Créer une nouvelle URL**, sélectionnez **Page interne**. Sous **Chemin de l’URL**, entrez le chemin qui inclut le segment à remplacer (dans cet exemple, **/blog/about-this-blog**). Sélectionnez ensuite **Suivant**.
1. Dans la boîte de dialogue **Sélectionner une page**, sélectionnez la page personnalisée, puis sélectionnez **Enregistrer**.
1. Sélectionnez **Publier**.
1. Si la page personnalisée n’a pas encore été publiée, accédez à **Pages**, sélectionnez la page personnalisée, puis sélectionnez **Publier**.

Une fois la page personnalisée publiée, elle sera diffusée à la place de la page dynamique dont le contenu est paramétré.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier une page de site existante](modify-existing-page.md)

[Ajouter une nouvelle page de site](add-new-page.md)

[Sélectionner des dispositions de page](select-page-layouts.md)

[Gestion des métadonnées SEO](manage-seo-metadata.md)

[Enregistrer, afficher un aperçu et publier une page](save-preview-publish-page.md)

[Enrichir une page de produit](enrich-product-page.md)

[Enrichir une page d’arrivée de catégorie](enrich-category-page.md)

[Vérifier l’accessibilité du contenu de la page](verify-accessibility.md)

[Extensibilité des canaux en ligne](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
