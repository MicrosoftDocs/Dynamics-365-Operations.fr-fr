---
title: Présentation de la gestion des modifications d’ingénierie
description: Cette rubrique fournit une vue d'ensemble de la gestion des modifications techniques, qui vous aide à planifier et à gérer la gestion des versions des produits et à gérer les cycles de vie des produits et les modifications techniques.
author: t-benebo
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: f1aa04b472eaef7ed398f08a05d46bac2d589561
ms.sourcegitcommit: 9f32389715b226c11e74c53547527e0a8b51e300
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/12/2020
ms.locfileid: "4514348"
---
# <a name="engineering-change-management-overview"></a>Présentation de la gestion des modifications d’ingénierie

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Résumé de la fonction

Les fabricants d'aujourd'hui ont besoin d'une solide gestion des données produit, d'un contrôle de version et d'une gestion des changements d'ingénierie pour réussir dans un monde où les cycles de vie des produits diminuent constamment, les exigences de qualité et de fiabilité accrues et une attention accrue à la sécurité des produits.

La gestion des changements d'ingénierie apporte structure et discipline au processus de gestion des données produit et permet aux produits d'être définis, publiés et révisés de manière contrôlée et prise en charge par des workflows. Grâce aux versions de produit et à la gestion des modifications techniques, vous pouvez documenter, évaluer l'impact et appliquer les modifications techniques tout au long du cycle de vie d'un produit.

La gestion des modifications techniques, qui vous aide à planifier et à gérer la gestion des versions des produits et à gérer les cycles de vie des produits et les modifications techniques. Voici une liste de ses principales caractéristiques :

- Gestion des versions du produit
- Fonctionnalité de lancement de produit améliorée qui vous permet de conserver les données de base du produit dans une seule entité juridique (la société d'ingénierie) et de publier le produit lancé entièrement configuré dans d'autres entités juridiques
- Règles de validation de la saisie des informations requises avant l'activation d'une version de produit (contrôles de disponibilité)
- Gestion améliorée du cycle de vie des produits grâce à un contrôle précis du moment où un produit lancé peut être utilisé dans des processus d'entreprise spécifiques
- Demandes de modification technique prises en charge par les workflows
- Ordres de modification technique pris en charge par les workflows

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

La vidéo précédente ([Capacités de gestion du changement dans Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) est incluse dans la [playlist Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.

## <a name="turn-on-engineering-change-management-for-your-system"></a>Activez la gestion des modifications techniques pour votre système

Commencez par activer la gestion des modifications techniques en suivant ces étapes.

1. Accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Rechercher des mises à jour.
1. Activez la fonctionnalité nommée **Gestion des modifications d’ingénierie**.

Ensuite, activez la clé de configuration **Gestion du changement d'ingénierie** en suivant ces étapes.

1. Mettez votre système en mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Accédez à **Administration système \> Paramétrage \> Configuration des licences**.
1. Développez le nœud **Commerce**, et cochez la case **Gestion du changement d'ingénierie**.
1. Désactiver le mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]