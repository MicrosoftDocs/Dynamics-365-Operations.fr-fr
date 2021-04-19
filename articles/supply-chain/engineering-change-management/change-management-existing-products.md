---
title: Activer la gestion des changements sur les produits existants
description: Cette rubrique explique comment activer la gestion des modifications pour les produits existants. Il décrit également les cas où votre capacité à activer la gestion des changements est limitée.
author: t-benebo
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-02
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: be7b17c1049f60379764c5424422ff1ac6ee1770
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830098"
---
# <a name="enable-change-management-on-existing-products"></a>Activer la gestion des changements sur les produits existants

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment activer la gestion des modifications pour les produits existants. Il décrit également les cas où votre capacité à activer la gestion des changements est limitée.

Lorsque vous activez la gestion des modifications pour un produit existant, vous pouvez créer des versions de ce produit et suivre les modifications qui lui sont apportées tout au long de sa vie. Par conséquent, vous pouvez suivre ces modifications à l’aide des demandes de modification. Pour activer la gestion des modifications, vous devez convertir les produits concernés en *articles d’ingénierie* (également appelés produits d’ingénierie). Les produits d’ingénierie sont des produits versionnés et gérés via la gestion des changements. Un assistant est fourni pour vous guider tout au long du processus de conversion.

## <a name="turn-on-the-feature-in-your-system"></a>Activez la fonctionnalité dans votre système

Pour utiliser cette capacité, procédez comme suit :

1. Activez la fonctionnalité Gestion des modifications d’ingénierie et sa clé de configuration comme décrit dans [Gestion du changement d’ingénierie](product-engineering-overview.md).
1. Activez la fonctionnalité *Activer la gestion des modifications sur les produits existants* dans la gestion des fonctionnalités. Pour plus d’informations, voir [Vue d’ensemble de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="restrictions-and-limitations"></a>Restrictions et limitations

Tous les types de produits ne peuvent pas être convertis en tous les autres types. Les restrictions et limitations suivantes s’appliquent :

- Lorsque vous convertissez un produit en produit d’ingénierie, il reste un *produit*. Cela ne devient pas un *produit générique*.
- Lorsque vous convertissez une base de données produit qui a un ensemble spécifique de dimensions, ces dimensions sont conservées après la modification. Par exemple, si vous convertissez un produit générique qui a la dimension de taille, il conservera la dimension de taille.

Par conséquent, si vous avez un produit distinct, vous pouvez le modifier uniquement en un produit d’ingénierie qui ne suit pas la dimension de produit dans les transactions (c’est-à-dire que la dimension de version n’est pas utilisée). Pour plus d’informations sur ces problèmes, voir les section restantes de cette rubrique.

## <a name="prepare-for-conversion-by-creating-all-required-engineering-product-categories"></a>Préparez la conversion en créant toutes les catégories de produits d’ingénierie requises

Une *catégorie de produit d’ingénierie* doit être attribué à chaque produit d’ingénierie. Vous ferez cette tâche lorsque vous exécuterez l’Assistant **Convertir en produit d’ingénierie**. Des catégories de produits d’ingénierie doivent exister pour tous les produits standard pertinents *avant que* vous pouvez convertir ces produits.

La catégorie de produit d’ingénierie fournit une base pour la création d’un produit d’ingénierie et établit un ensemble de valeurs et de règles par défaut. La catégorie d’ingénierie doit correspondre au produit auquel vous l’affectez. Par exemple, le type de produit et le groupe de dimensions doivent correspondre à la fois au produit et à sa catégorie de produit d’ingénierie. Pour plus d’informations, voir [Versions d’ingénierie et catégories de produits d’ingénierie](engineering-versions-product-category.md).

> [!IMPORTANT]
> L’assistant **Convertir en produit d’ingénierie** ne peut convertir le produit qu’en produits d’ingénierie dont la version n’est pas suivie dans les transactions. Par conséquent, l’option **Suivre la version dans les transactions** doit être définie sur *Non* pour les catégories de produits d’ingénierie que vous créez pour convertir des produits existants.

Pour plus d’informations sur la création des catégories de produits d’ingénierie, voir [Versions d’ingénierie et catégories de produits d’ingénierie](engineering-versions-product-category.md).

## <a name="run-the-convert-to-engineering-product-wizard"></a>Exécutez l’assistant de conversion en produit d’ingénierie

L’assistant **Convertir en produit d’ingénierie** vous aide à convertir un ou plusieurs produits existants en produits d’ingénierie. Il convertit les produits en produits d’ingénierie (produits versionnés) dont la version n’est pas suivie dans les transactions (c’est-à-dire que la dimension de version n’est pas utilisée). Une fois la conversion terminée, vous pouvez gérer les produits à l’aide de la gestion des modifications d’ingénierie.

La conversion est permanente. Par conséquent, vous ne pourrez pas l’inverser plus tard. 

Chaque produit d’ingénierie converti continuera à être commercialisé dans les mêmes entreprises dans lesquelles le produit d’origine a été lancé. Cependant, la nomenclature technique et les itinéraires ne seront pas automatiquement transmis à ces sociétés.

Suivez ces étapes pour exécuter l’assistant **Convertir en produit d’ingénierie** et convertissez un produit en produit d’ingénierie.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Dans la grille, cochez la case de chaque produit à convertir.
1. Dans le volet Actions, sur l’onglet **Ingénieur**, dans le groupe **Gestion des modifications d’ingénierie**, sélectionnez **Convertir en produit d’ingénierie** pour ouvrir l’assistant.
1. La première page de l’assistant est la page de **Bienvenue**. Si vous n’êtes pas déjà familiarisé avec le processus de conversion, lisez attentivement les informations sur cette page. Lorsque vous êtes prêt à continuer, sélectionnez **Suivant**.
1. La page **Sélectionnez les détails des produits à convertir** affiche chaque produit que vous avez sélectionné avant d’ouvrir l’assistant. Inspectez la liste. Utilisez les boutons **Nouveau** et **supprimer** de la barre d’outils ou supprimez les produits selon vos besoins.
1. Utilisez les champs suivants en haut de la grille pour attribuer des valeurs par défaut à chaque produit répertorié. (Vous pourrez modifier ces valeurs pour des produits individuels une fois la conversion terminée.) Les valeurs par défaut ne seront pas attribuées aux produits pour lesquels une valeur pertinente a déjà été attribuée.

    - **Catégorie d’ingénierie par défaut** – Sélectionnez une catégorie de produit d’ingénierie initiale à attribuer à chaque produit répertorié. La catégorie que vous sélectionnez ne sera appliquée qu’aux produits compatibles avec elle.
    - **Version par défaut** – Saisissez la version initiale du produit à attribuer à chaque produit répertorié. Chaque produit d’ingénierie a au moins une version d’ingénierie.
    - **État du cycle de vie par défaut** – Sélectionnez l’état initial du cycle de vie du produit à attribuer à chaque produit répertorié.
    - **La nomenclature actuelle fera partie du produit d’ingénierie** – Cochez cette case si la nomenclature actuelle de chaque produit répertorié doit être utilisée comme nomenclature pour le produit d’ingénierie.

    Pour plus d’informations sur les paramétrages de produit, voir l’étape suivante.

1. Examinez chaque produit répertorié dans la grille et évaluez dans quelle mesure les valeurs par défaut que vous avez attribuées s’y appliquent. Pour chaque ligne, examinez les informations suivantes et définissez les champs appropriés :

    - **Numéro de produit** – numéro de produit.
    - **Nom du produit** – Nom du produit.
    - **Catégorie d’ingénierie** – Sélectionnez la catégorie de produit d’ingénierie à laquelle le produit doit appartenir après sa conversion. Une catégorie appropriée doit déjà exister pour chaque produit, comme expliqué dans la section précédente de cette rubrique. Vous devez attribuer une catégorie à chaque produit.
    - **Version** – Saisissez la version du produit à attribuer au produit une fois celui-ci converti. Par exemple, vous pouvez sélectionner un nombre qui correspond à la souche de numéros que votre catégorie utilise déjà. Chaque version d’ingénierie stocke les données d’ingénierie spécifiques à cette version. Pour plus d’informations, voir [Versions d’ingénierie et catégories de produits d’ingénierie](engineering-versions-product-category.md).
    - **État du cycle de vie du produit** – Sélectionnez l’état du cycle de vie du produit dans lequel le produit doit se trouver après sa conversion. L’état du cycle de vie du produit vous permet de contrôler les transactions autorisées pour une version d’ingénierie donnée. Pour plus d’informations, voir [États du cycle de vie du produit et transactions](product-lifecycle-state-transactions.md).
    - **A une nomenclature** – Une case cochée indique que le produit a une nomenclature. Le paramétrage de cette case à cocher peut vous aider à décider comment définir la case **La nomenclature actuelle fera partie du produit d’ingénierie**.
    - **La nomenclature actuelle fera partie du produit d’ingénierie** – Cochez cette case si la nomenclature actuelle du produit répertorié doit être utilisée comme nomenclature pour le produit d’ingénierie. Cette nomenclature sera ensuite gérée par la gestion du changement d’ingénierie. Si le produit n’a pas de nomenclature ou si vous préférez créer manuellement une nomenclature pour le produit converti ultérieurement, désactivez cette case à cocher.
    - **A des erreurs** – Une case à cocher activée indique que la configuration du produit comporte une ou plusieurs erreurs. Par exemple, le type de produit ou le groupe de dimensions peut ne pas correspondre dans la catégorie. Les produits comportant des erreurs seront ignorés et ne seront pas convertis.

1. Lorsque vous avez terminé, sélectionnez **Valider** dans la barre d’outils pour valider la configuration du produit. Pour chaque ligne, la case **A des erreurs** sera mise à jour pour indiquer l’état du produit. Ajustez les valeurs jusqu’à ce que la configuration de chaque produit soit exempte d’erreurs.
1. Lorsque tous les produits sont correctement configurés, sélectionnez **Suivant** pour continuer.
1. La page **Confirmer la sélection** affiche le nombre de produits qui n’ont pas d’erreurs dans leur configuration et sont donc prêts pour la conversion. Il indique également le nombre de produits qui seront ignorés en raison d’erreurs. Pour exécuter la conversion en tant que travail par lots, définissez l’option **Exécuter par lots** sur *Oui*.
1. Sélectionner **Terminer** pour appliquer vos paramètres et commencer à convertir les produits en produits d’ingénierie.

> [!NOTE]
> Si votre système est configuré pour accepter manuellement les produits avant leur lancement, vous devez accepter chaque produit converti en utilisant la page **Ouvrir les versions de produit** dans les entreprises appropriées. Pour plus d’informations, voir [Vérifiez et acceptez le produit avant de le commercialiser dans l’entreprise locale](engineering-scenarios.md#accept).
