---
title: Regulatory Configuration Service (RCS) – Abandon du stockage Lifecycle Services (LCS)
description: Cette rubrique fournit des informations sur l’obsolescence du stockage Microsoft Dynamics Lifecycle Services (LCS) prévu dans le cadre du déploiement du référentiel global Regulatory Configuration Service (RCS).
author: JaneA07
ms.date: 05/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, LCS storage, LCS storage deprecation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.19
ms.openlocfilehash: abaeb34db1d209fa8e5cc83a98c333f42e91f2d2
ms.sourcegitcommit: 7cda434becd198c1cd405e001289777ae7a24fe1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6127917"
---
# <a name="regulatory-configuration-service-rcs--lifecycle-services-lcs-storage-deprecation"></a>Regulatory Configuration Service (RCS) – Abandon du stockage Lifecycle Services (LCS)

[!include [banner](../includes/banner.md)]

L’utilisation de Microsoft Dynamics Lifecycle Services (LCS) comme référentiel de stockage pour les configurations de rapports électroniques (ER) est obsolète. Cet abandon entraînera les modifications suivantes :

- Les configurations produites par Microsoft qui sont utilisées dans les applications Microsoft Dynamics 365 ne seront plus publiées dans la bibliothèque de biens partagés dans LCS. Au lieu de cela, elles seront publiés uniquement via le référentiel global RCS. Cependant, les configurations pour Dynamics AX 2012 continueront d’être publiées dans la bibliothèque de biens partagés dans LCS jusqu’à la fin du cycle de vie du support d’AX 2012.
- La fonctionnalité qui vous permet de charger des configurations vers la bibliothèque de biens de projet dans LCS à partir des applications Finance and Operations et de RCS sera désactivée. Cependant, vous pourrez toujours utiliser le navigateur dans LCS pour charger des configurations dans la bibliothèque de biens du projet. Par conséquent, vous pourrez toujours ajouter des configurations à LCS afin qu’elles puissent être incluses dans des packages de solutions.
- L’importation de configurations depuis LCS continuera d’être disponible et prise en charge dans les applications Finance and Operations et dans RCS pendant un certain temps. Cependant, la fonctionnalité finira par être abandonnées. (La date exacte de l’obsolescence sera annoncée ultérieurement.)

## <a name="deprecation-notice"></a>Avis d′obsolescence

L’abandon de l’utilisation de LCS comme stockage a été communiqué dans [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Finance - Avis d’obsolescence de LCS](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). La date d’abandon prévue est le 1er avril 2022.

## <a name="key-features"></a>Fonctions principales

- Vous pouvez utiliser RCS pour créer et modifier des configurations. Vous pouvez ensuite envoyer ces configurations directement du concepteur vers une application connectée. Ainsi, vous pouvez rapidement modifier et tester vos configurations.
- Le référentiel global est le stockage centralisé de toutes les configurations de génération d’états électroniques.

## <a name="guidance-for-one-time-and-ongoing-actions"></a>Conseils pour les actions ponctuelles et continues

Cette section décrit un ensemble d’étapes qui doivent être effectuées une seule fois. Elle décrit également les étapes à réaliser de façon continue par la suite.

### <a name="one-time-action"></a>Action ponctuelle

Importez toutes les configurations requises de LCS vers RCS, puis publiez-les de RCS vers le référentiel global. Si vous utilisez des bibliothèques de biens spécifiques à un projet pour stocker des configurations dérivées dans LCS, vous devez procéder aux étapes suivantes pendant que LCS est toujours accessible.

1. Si une instance RCS n’est pas déjà disponible, provisionnez-en une. Pour plus d’informations, voir [Vue d’ensemble de RCS](rcs-overview.md).
2. Dans l’instance RCS provisionnée, pour chaque projet LCS de la bibliothèque de biens contenant des configurations ER dérivées, enregistrez le référentiel LCS approprié.
3. Importez les configurations ER des référentiels LCS vers RCS. Pour plus d’informations, voir [Importer des configurations depuis LCS](../../dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services.md).
4. Si le référentiel global n’est pas fourni automatiquement, enregistrez-le dans RCS.
5. Chargez toutes les configurations dérivées de l’instance RCS actuelle vers le référentiel global. Utilisez la fonction **Packages de configuration qui permettent à l’utilisateur de charger toutes les configurations vers le référentiel global en une seule opération** pour faciliter le chargement. Pour plus d’informations, voir [Chargement dans le référentiel global RCS](rcs-global-repo-upload.md).

### <a name="going-forward"></a>À l’avenir

Utilisez les concepteurs visuels de RCS pour créer toutes les nouvelles configurations. Chargez ensuite les configurations dans le référentiel global pour le stockage. Pour plus d’informations, voir [Créer une configuration ER dans RCS et la charger dans le référentiel global](rcs-global-repo-upload.md).

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a>Ce changement signifie-t-il que LCS ne pourra plus être utilisé comme stockage central pour les configurations ?

Oui. La fonctionnalité qui vous permet de charger des configurations vers la bibliothèque de biens de projet dans LCS à partir des applications Finance and Operations sera obsolète. Cependant, vous pouvez toujours utiliser le navigateur dans LCS pour charger des configurations dans la bibliothèque de biens du projet, selon vos besoins.

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a>Je pensais que RCS était un référentiel de remplacement pour l’importation de fichiers de modèles globaux. Je ne pensais pas qu’il était utilisé pour stocker des configurations. Lequel des deux est vrai ?

RCS est un service de conception pour la création et la modification de configurations ER. RCS possède son propre référentiel appelé Référentiel global. Ce référentiel est utilisé pour stocker les configurations créées dans RCS. Une fois l’utilisation de LCS comme stockage obsolète, le référentiel global sera la source unique pour les configurations Microsoft. Vous devez effectuer une action unique pour importer toutes les configurations dont vous avez besoin de LCS vers RCS, puis les publier de RCS vers le référentiel global.

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a>Sans LCS, quelle est la méthode suggérée pour stocker les configurations afin de gérer et transférer facilement les configurations « test » et « production » ?

RCS utilise le concept d’*application connectée*. Une application connectée établit une connexion entre RCS et toute instance des applications Finance and Operations. Étant donné que RCS peut être utilisé pour éditer des configurations, l’application connectée peut être utilisée pour envoyer les configurations directement du concepteur vers les environnements des applications Finance and Operations. Par conséquent, vous pouvez rapidement modifier et tester vos configurations au lieu de devoir passer par le stockage au niveau du projet LCS.

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a>Existe-t-il des exemples illustrant la configuration et la gestion ?

Il n’y a pas d’exemples, mais vous pouvez suivre les étapes décrites plus haut dans cette rubrique pour migrer vos configurations vers le référentiel RCS Global.
