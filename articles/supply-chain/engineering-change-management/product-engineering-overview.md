---
title: Vue d’ensemble de la gestion des modifications techniques (contient une vidéo)
description: Cet article fournit une vue d’ensemble de la gestion des modifications techniques, qui vous aide à planifier et à gérer la gestion des versions des produits et à gérer les cycles de vie des produits et les modifications techniques.
author: t-benebo
ms.date: 01/11/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 3a27548fff9728c74814fb92438da1d0c17b5e2b
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067390"
---
# <a name="engineering-change-management-overview"></a>Présentation de la gestion des modifications d’ingénierie

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Résumé de la fonction

Les fabricants d’aujourd’hui ont besoin d’une solide gestion des données produit, d’un contrôle de version et d’une gestion des changements d’ingénierie pour réussir dans un monde où les cycles de vie des produits diminuent constamment, les exigences de qualité et de fiabilité accrues et une attention accrue à la sécurité des produits.

La gestion des changements d’ingénierie apporte structure et discipline au processus de gestion des données produit et permet aux produits d’être définis, publiés et révisés de manière contrôlée et prise en charge par des workflows. Grâce aux versions de produit et à la gestion des modifications techniques, vous pouvez documenter, évaluer l’impact et appliquer les modifications techniques tout au long du cycle de vie d’un produit.

La gestion des modifications techniques, qui vous aide à planifier et à gérer la gestion des versions des produits et à gérer les cycles de vie des produits et les modifications techniques. Voici une liste de ses principales caractéristiques :

- Gestion des versions du produit
- Fonctionnalité de lancement de produit améliorée qui vous permet de conserver les données de base du produit dans une seule entité juridique (la société d’ingénierie) et de publier le produit lancé entièrement configuré dans d’autres entités juridiques
- Règles de validation de la saisie des informations requises avant l’activation d’une version de produit (contrôles de disponibilité)
- Gestion améliorée du cycle de vie des produits grâce à un contrôle précis du moment où un produit lancé peut être utilisé dans des processus d’entreprise spécifiques
- Demandes de modification technique prises en charge par les workflows
- Ordres de modification technique pris en charge par les workflows

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HE6B]

La vidéo précédente ([Capacités de gestion du changement dans Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) est incluse dans la [liste des lectures de applications de finances et d’opérations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.

## <a name="turn-on-the-engineering-change-management-features-for-your-system"></a>Activer les fonctions de gestion des modifications techniques pour votre système

Avant de pouvoir utiliser la gestion des modifications techniques, vous devez activer la fonctionnalité *Gestion du changement d’ingénierie* et sa clé de configuration. Si vous souhaitez également suivre la dimension de version des produits dans les transactions (facultatif), vous devez également activer la fonctionnalité *Dimension de la version du produit* et sa clé de configuration. Une fois ces conditions préalables configurées, vous pourrez activer des fonctionnalités facultatives supplémentaires pour la gestion des modifications techniques.

### <a name="turn-the-basic-engineering-change-management-features-on-or-off"></a>Activer ou désactiver les fonctions de base de gestion des modifications techniques

Pour activer ou désactiver les fonctions de base de gestion des modifications techniques, procédez comme suit : Depuis la version 10.0.25 de Supply Chain Management, la fonctionnalité *Gestion des modifications d’ingénierie* est activée par défaut.

1. Accédez à l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Rechercher des mises à jour.
1. Activez ou désactivez la fonctionnalité nommée *Gestion des modifications d’ingénierie*, si nécessaire.
1. Si vous souhaitez également suivre la dimension de version des produits dans les transactions (facultatif), activez la fonctionnalité nommée *Version de dimension du produit*.

### <a name="turn-the-required-configuration-keys-on-or-off"></a>Activer ou désactiver les clés de configuration requises

Ensuite, activez les clés de configuration en suivant ces étapes. Elles ne sont pas activées par défaut.

1. Mettez votre système en mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Accédez à **Administration système \> Paramétrage \> Configuration des licences**.
1. Développez le nœud **Commerce**.
1. Activez ou désactivez la clé de configuration de la fonction principale à l’aide de la case à cocher **Gestion du changement technologique**.
1. Développez le nœud **Gestion des modifications d’ingénierie** et cochez ou décochez les cases suivantes si nécessaire (selon les fonctionnalités que vous souhaitez utiliser) :

    - **Recherche d’attributs** : cochez cette case pour activer la [fonction de recherche d’attributs](engineering-attributes-and-search.md). Nous vous recommandons d’activer cette fonctionnalité, mais vous pouvez décocher cette case si vous ne l’utilisez pas.
    - **Gestion des modifications pour la fabrication par processus** : cochez cette case si vous souhaitez utiliser les fonctionnalités de gestion des modifications d’ingénierie pour gérer les changements de formules pour la fabrication par processus. Si vous n’avez pas à gérer les formules, vous pouvez décocher cette case. Pour plus d’informations, consultez [Gérer les changements de formules et de leurs composants](manage-formula-changes.md).

1. Si vous souhaitez également utiliser la dimension de la version, cochez **Dimension du produit – Version**. (Cette case à cocher est plus bas dans la liste, pas imbriquée sous le nœud **Gestion des modifications techniques**.) Vous pouvez décocher cette case si vous n’avez pas besoin de cette fonctionnalité.
1. Désactiver le mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. La base de données doit être synchronisée pour s’assurer que les clés de configuration sont correctement mises à jour pour refléter vos modifications. Effectuez l’une des étapes suivantes, selon le type d’environnement sur lequel vous travaillez :
    - **Pour les environnements de niveau 1 (développement)**  : ouvrez votre projet dans Microsoft Visual Studio, puis sélectionnez **Dynamics 365 \> Synchroniser la base de données \> Synchroniser**.
    - **Pour les environnements de niveau 2 (et supérieur)**  : la base de données se synchronise automatiquement une fois que vous avez mis l’environnement en mode de maintenance ou l’en avez sorti, vous pouvez donc ignorer cette étape.

### <a name="turn-on-additional-engineering-change-management-features"></a>Activer les fonctions supplémentaires de gestion des modifications techniques

Une fois que vous avez activé les fonctionnalités de gestion des modifications techniques de base et activé leurs clés de configuration, plusieurs fonctionnalités de gestion des modifications techniques supplémentaires et facultatives sont ajoutées à la gestion des fonctionnalités. Chacune de ces fonctions est répertoriée sous le module **Gestion des modifications techniques**. Le tableau suivant décrit chaque fonction facultative et fournit des liens pour plus d’informations. À partir de la version 10.0.25 de Supply Chain Management, toutes ces fonctionnalités sont activées par défaut, mais vous pouvez toujours choisir de les désactiver.

| Nom de la fonction dans la Gestion des fonctionnalités | Description | État de la fonctionnalité |
|---|---|---|
| Activer la gestion des changements sur les produits existants | <p>Cette fonctionnalité vous permet de convertir des produits existants en produits d’ingénierie afin que vous puissiez commencer à les gérer en utilisant la gestion des modifications techniques.</p><p>Pour plus d’informations, consultez [Activer la gestion des changements sur les produits existants](change-management-existing-products.md).</p> |
| Notifications d’ingénierie pour la production | <p>Lorsqu’un produit est modifié en ingénierie, il peut être important d’informer la production de ces changements. De cette façon, les collaborateurs de la production peuvent prendre les mesures appropriées, telles que la substitution de composants, le remplacement de la nomenclature (BOM) ou le remplacement de la gamme. Cette fonctionnalité vous permet d’informer la production des modifications apportées aux produits en cours de production.</p><p>Pour plus d’informations, voir [Gérer modifications des produits techniques](engineering-change-management.md).</p> |
| Amélioration de l’héritage des attributs pour la gestion des changements d’ingénierie | <p>Cette fonctionnalité simplifie la gestion des attributs pour les produits finis ou les articles intermédiaires. Lorsque cette fonctionnalité est activée, il est plus facile d’identifier tous les attributs qui appartiennent à un article et vous pouvez sélectionner les attributs qui doivent être propagés de cet article à son article parent. Cette fonctionnalité est utile lorsque, par exemple, un composant d’un produit fini est fragile, toxique ou inflammable, car vous pouvez facilement identifier l’attribut fragile, toxique ou inflammable et le propager au produit fini.</p><p>Pour plus d’informations, voir [Attributs d’ingénierie et recherche d’attributs d’ingénierie](engineering-attributes-and-search.md).</p> |
| Vérifications de la disponibilité du produit | <p>Cette fonction vous permet de configurer des contrôles de préparation pour les produits standard (autres que des produits d’ingénierie). Utilisez des contrôles de préparation des produits pour vous assurer que chaque produit est entièrement défini et que toutes les stratégies requises sont configurées avant que le produit ne soit mis à disposition et utilisé dans les transactions. Si vous désactivez cette fonctionnalité après l’avoir utilisée pendant un certain temps, tous les contrôles de préparation existants pour les produits standard seront supprimés.</p><p>Pour plus d’informations, voir [Disponibilité du produit](product-readiness.md).</p> |
| Gérer les modifications apportées aux formules et à leurs ingrédients | <p>Cette fonctionnalité vous permet de suivre les modifications apportées aux ingrédients de la formule, aux co-produits et aux sous-produits.</p><p>Pour plus d’informations, consultez [Gérer les changements de formules et de leurs composants](manage-formula-changes.md).</p> |
| Générer des variantes pour les produits d’ingénierie | <p>Cette fonctionnalité vous permet de générer des variantes pour les produits d’ingénierie, en fonction des valeurs de dimension disponibles.</p><p>Pour plus d’informations, voir [Générer des variantes pour les produits d’ingénierie](engineering-variants.md).</p> |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

