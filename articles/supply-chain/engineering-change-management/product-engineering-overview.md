---
title: Présentation de la gestion des modifications d’ingénierie
description: Cette rubrique fournit une vue d’ensemble de la gestion des modifications techniques, qui vous aide à planifier et à gérer la gestion des versions des produits et à gérer les cycles de vie des produits et les modifications techniques.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d9430fe02abe58f37d2bfd1431b4da61527d0834
ms.sourcegitcommit: 588f8343aaa654309d2ff735fd437dba6acd9d46
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115047"
---
# <a name="engineering-change-management-overview"></a>Présentation de la gestion des modifications d’ingénierie

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Résumé de la fonction

Les fabricants d’aujourd’hui ont besoin d’une solide gestion des données produit, d’un contrôle de version et d’une gestion des changements d’ingénierie pour réussir dans un monde où les cycles de vie des produits diminuent constamment, les exigences de qualité et de fiabilité accrues et une attention accrue à la sécurité des produits.

La gestion des changements d’ingénierie apporte structure et discipline au processus de gestion des données produit et permet aux produits d’être définis, publiés et révisés de manière contrôlée et prise en charge par des workflows. Grâce aux versions de produit et à la gestion des modifications techniques, vous pouvez documenter, évaluer l’impact et appliquer les modifications techniques tout au long du cycle de vie d’un produit.

La gestion des modifications techniques, qui vous aide à planifier et à gérer la gestion des versions des produits et à gérer les cycles de vie des produits et les modifications techniques. Voici une liste de ses principales caractéristiques :

- Gestion des versions du produit
- Fonctionnalité de lancement de produit améliorée qui vous permet de conserver les données de base du produit dans une seule entité juridique (la société d’ingénierie) et de publier le produit lancé entièrement configuré dans d’autres entités juridiques
- Règles de validation de la saisie des informations requises avant l’activation d’une version de produit (contrôles de disponibilité)
- Gestion améliorée du cycle de vie des produits grâce à un contrôle précis du moment où un produit lancé peut être utilisé dans des processus d’entreprise spécifiques
- Demandes de modification technique prises en charge par les workflows
- Ordres de modification technique pris en charge par les workflows

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

La vidéo précédente ([Capacités de gestion du changement dans Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) est incluse dans la [playlist Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a>Activez la gestion des modifications techniques et les fonctionnalités de dimension de version pour votre système

Avant de pouvoir utiliser la gestion des modifications techniques, vous devez activer la fonctionnalité *Gestion du changement d’ingénierie* et sa clé de configuration. Si vous souhaitez également suivre la dimension de version des produits dans les transactions (facultatif), vous devez également activer la fonctionnalité *Dimension de la version du produit* et sa clé de configuration.

Commencez par activer les fonctionnalités en suivant ces étapes.

1. Accédez à l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Rechercher des mises à jour.
1. Activez la fonctionnalité nommée *Gestion des modifications d’ingénierie*.
1. Si vous souhaitez l’utiliser, activez également la fonctionnalité nommée *Version de dimension de produit*.

Ensuite, activez les clés de configuration en suivant ces étapes.

1. Mettez votre système en mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Accédez à **Administration système \> Paramétrage \> Configuration des licences**.
1. Développez le nœud **Commerce**.
1. Activez la clé de configuration de la fonction principale en activant la case à cocher **Gestion des modifications d’ingénierie**.
1. Développez le nœud **Gestion des modifications d’ingénierie** et cochez ou décochez les cases suivantes si nécessaire (selon les fonctionnalités que vous souhaitez utiliser) :

    - **Recherche d’attributs** : cochez cette case pour activer la [fonction de recherche d’attributs](engineering-attributes-and-search.md). Nous vous recommandons d’activer cette fonctionnalité, mais vous pouvez décocher cette case si vous ne l’utilisez pas.
    - **Gestion des modifications pour la fabrication par processus** : cochez cette case si vous souhaitez utiliser les fonctionnalités de gestion des modifications d’ingénierie pour gérer les changements de formules pour la fabrication par processus. Si vous n’avez pas à gérer les formules, vous pouvez décocher cette case. Pour plus d’informations, consultez [Gérer les changements de formules et de leurs composants](manage-formula-changes.md).

1. Si vous souhaitez également utiliser la dimension de la version, cochez **Dimension du produit – Version**. (Cette case à cocher se trouve plus bas dans la liste, elle n’est pas imbriquée sous le nœud **Gestion des modifications d’ingénierie**.)
1. Désactiver le mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

> [!IMPORTANT]
> À partir d'avril 2022, les clés de licence pour **Gestion du changement technologique** et **Dimension du produit – Version** seront activées par défaut pour toutes les nouvelles installations, mais vous pourrez toujours les désactiver si nécessaire.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
