---
title: Personnaliser les titres d’étapes et les instructions pour l’application mobile Warehouse Management
description: Cet article explique comment créer et afficher des instructions personnalisées pour chaque étape de chaque flux de tâches que vous configurez pour l'application mobile Warehouse Management.
author: Mirzaab
ms.date: 08/11/2021
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-11
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 40b2115126aae28a41feaec4d3aabd73595107cd
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220147"
---
# <a name="customize-step-titles-and-instructions-for-the-warehouse-management-mobile-app"></a>Personnaliser les titres d’étapes et les instructions pour l’application mobile Warehouse Management

> [!IMPORTANT]
> Les fonctionnalités décrites dans cet article s’appliquent uniquement à la nouvelle application mobile Warehouse Management. Elles n'affectent pas l'ancienne application d'entrepôt, qui est désormais obsolète.

Cet article explique comment créer et afficher des instructions personnalisées pour chaque étape de chaque flux de tâches que vous configurez pour l'application mobile Warehouse Management. Lorsque les magasiniers reçoivent des instructions bien écrites, ils peuvent immédiatement commencer à utiliser de nouveaux flux sans avoir besoin de formation préalable. Cette fonctionnalité offre les avantages suivants :

- **Améliorer l'efficacité des travailleurs plus rapidement en leur permettant de suivre des instructions simples pour chaque étape de la tâche.** Chaque étape d'un flux fournit des instructions qui permettent aux travailleurs de première ligne de comprendre la tâche.
- **Fournir des instructions qui correspondent à vos propres processus.** Rédigez vos propres instructions pour qu'elles correspondent aux processus de votre entreprise et de votre entrepôt. Par exemple, vous pouvez adapter la terminologie à votre espace physique et aux abréviations locales.

## <a name="turn-on-the-warehouse-app-step-instructions-feature"></a>Activer la fonctionnalité d'instructions d'étape de l'application d'entrepôt

Pour pouvoir utiliser cette fonctionnalité, vous devez l’activer dans le système. À compter de la version 10.0.29 de Supply Chain Management, cette fonctionnalité sera activée par défaut. Les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Instructions par étape du Warehouse app* dans l'espace de traveil [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="step-titles-and-step-instructions-in-the-app"></a>Titres d'étape et instructions d'étape dans l'application

Chaque étape dans un flux de tâches sur le Warehouse Management mobile app est identifiée par un ID d'étape. De plus, chaque étape a un titre, une icône et une instruction. (Pour plus d’informations, voir [Affecter des icônes et des titres d’étape pour le Warehouse Management mobile app](step-icons-titles.md).)

### <a name="step-titles"></a>Titres des étapes

Un *titre d'étape* est une brève description de ce qu'un collaborateur doit faire pendant une étape. Il apparaît sous forme de gros texte en haut de l'écran, comme le montre l'illustration suivante.

![Exemple d’un titre d’étape dans le Warehouse Management mobile app](media/wma-step-title.png "Exemple d’un titre d’étape dans le Warehouse Management mobile app")

> [!TIP]
> En raison de la grande taille du texte, vous devriez essayer de garder les titres des étapes aussi courts que possible. Sinon, le texte pourrait être coupé. Cependant, pour les titres longs, les collaborateurs peuvent toujours appuyer sur le titre et le maintenir enfoncé pour ouvrir une boîte de dialogue qui affiche le texte intégral.

### <a name="step-instructions"></a>Instructions des étapes

Une *instruction d'étape* est une description plus longue qui fournit plus d'informations sur ce qu'un collaborateur doit faire au cours d'une étape. Elle apparaît dans une boîte de dialogue contextuelle, comme le montre l'illustration suivante.

![Exemple d’une instruction d’étape dans le Warehouse Management mobile app](media/wma-step-instructions.png "Exemple d’une instruction d’étape dans le Warehouse Management mobile app")

L'instruction d'étape s'affiche automatiquement lorsqu'une étape est ouverte. Les collaborateurs peuvent la masquer en appuyant n'importe où en dehors de la boîte de dialogue contextuelle. De plus, la boîte de dialogue comprend une case à cocher **Ne plus afficher** que les collaborateurs peuvent sélectionner pour éviter que l'instruction n'apparaisse la prochaine fois qu'ils effectueront la même tâche.

## <a name="load-the-default-setup"></a>Charger la configuration par défaut

Lorsque vous activez pour la première fois la fonctionnalité *Instructions d'étape du Warehouse app*, votre système ne contiendra aucun titre ou instruction d'étape personnalisable. Par conséquent, la première chose à faire est de charger la configuration par défaut. La configuration par défaut fournit des textes pour tous les ID d'étape disponibles dans toutes les langues prises en charge. Pour charger la configuration par défaut, suivez ces étapes.

1. Accédez à **Warehouse management \> Configuration \> Appareil mobile \> Étapes d’appareil mobile**.
1. Dans le volet Action, sélectionnez **Créer configuration par défaut**. La page est remplie avec les étapes standard.

## <a name="customize-step-titles-and-instructions"></a>Personnaliser les titres et les instructions des étapes

Pour personnaliser le titre et/ou l'instruction pour une étape dans un certain nombre de langues, suivez ces étapes.

1. Accédez à **Warehouse management \> Configuration \> Appareil mobile \> Étapes d’appareil mobile**.

    La page **Étapes d'appareil mobile** répertorie toutes les étapes disponibles pour votre système. Chaque ID d'étape peut être partagé entre n'importe quel nombre d'éléments de menu d'appareil mobile. Si un ID d'étape est partagé entre plusieurs éléments de menu, le même titre et la même instruction sont affichés pour tous ces éléments de menu. Cependant, vous pouvez créer des remplacements pour personnaliser le titre et l'instruction pour des éléments de menu spécifiques. (Pour plus d’informations, voir la section suivante.)

    La grille comprend les colonnes suivantes :

    - **Nom de l'élément de menu** – Les lignes où cette colonne est vide utilisent le titre et l'instruction d'étape par défaut qui s'appliquent à tous les éléments de menu d'appareil mobile pour lesquels aucun remplacement n'est défini. Les lignes où cette colonne est définie sur le nom d'un élément de menu ont des remplacements qui s'appliquent uniquement à l'élément de menu spécifié.
    - **ID de l'étape** – L'identifiant unique de l'étape.
    - **Titre pour entrée** – Le titre qui s'affiche lorsque l'application demande de nouvelles informations. En règle générale, les champs sur la page sont vides (c'est-à-dire qu'ils n'ont pas de valeurs prédéfinies).
    - **Titre pour confirmation** – Le titre qui s'affiche lorsque l'application demande la confirmation d'une valeur déjà stockée dans le système. En règle générale, les champs sur la page ont des valeurs prédéfinies.

1. Trouvez la combinaison de valeurs **ID de l'étape** et **Nom de l'élément de menu** que vous souhaitez modifier et sélectionnez la valeur dans la colonne **ID de l'étape**. La page qui s'ouvre liste toutes les traductions disponibles pour le titre et l'instruction de l'étape sélectionnée.
1. Suivez l'une de ces étapes pour personnaliser le texte pour n'importe quelle langue. Les deux options vous permettent de modifier les textes pour les langues existantes. Cependant, seule la première option vous permet d'ajouter des textes pour de nouvelles langues, alors que seule la deuxième option vous permet d'afficher et de modifier des textes pour tous les remplacements existants spécifiques au menu de la langue sélectionnée.

    - Dans la barre d'outils, sélectionnez **Ajouter** pour ouvrir une boîte de dialogue dans laquelle vous pouvez ajouter ou modifier des textes pour n'importe quelle langue prise en charge. Définissez le champ **Langue de référence** sur la langue pour laquelle vous souhaitez afficher les valeurs. Les valeurs sont affichées dans la colonne de gauche. Définissez le champ **Langue des traductions** sur la langue que vous souhaitez ajouter ou personnaliser. Dans la colonne de droite, modifiez les valeurs des champs **Titre pour entrée**, **Instruction pour entrée**, **Titre pour confirmation** et **Instruction pour confirmation** selon vos besoins. Puis sélectionnez **OK**.
    - Dans la grille, recherchez et sélectionnez la ligne où le champ **Langue** est défini sur la langue que vous souhaitez modifier. Dans la barre d'outils, sélectionnez **Afficher &lt;traductions&gt; dans la langue de cette étape** pour ouvrir une boîte de dialogue dans laquelle vous pouvez modifier les textes de tous les remplacements disponibles pour la langue sélectionnée. La boîte de dialogue comprend une grille comportant des lignes pour à la fois les textes standard (où le champ **Nom de l'élément de menu** est vide) et pour chaque texte de remplacement disponible (où le champ **Nom de l'élément de menu** est défini sur le nom de l'élément de menu auquel le remplacement s'applique). Modifiez les valeurs des champs **Titre pour entrée**, **Instruction pour entrée**, **Titre pour confirmation** et **Instruction pour confirmation** selon vos besoins. Puis sélectionnez **OK**.

1. Continuez à travailler jusqu'à ce que vous ayez défini chaque titre et instruction requis pour chaque langue requise.

## <a name="add-menu-specific-overrides"></a>Ajouter des remplacements spécifiques au menu

Comme mentionné dans la section précédente, vous pouvez créer n'importe quel nombre de remplacements spécifiques au menu pour chaque ID d'étape. Vous pouvez utiliser cette fonctionnalité pour éditer et modifier l'instruction afin qu'elle corresponde mieux à votre processus métier local pour un élément de menu spécifique. Par exemple, pour le prélèvenement des ventes, si votre entreprise fournit généralement des ID de travail aux collaborateurs sur un document imprimé, vous pouvez indiquer que les collaborateur doivent commencer par scanner un ID de travail.

Chaque remplacement s'applique à un élément de menu d'appareil mobile spécifique et peut contenir n’importe quel nombre de traductions. S'il n'existe aucun remplacement pour un élément de menu, l'élément de menu utilise les textes standard. Si aucune traduction de remplacement n'est définie pour une langue, les textes standard sont utilisés, même pour les éléments de menu où un remplacement est défini pour d'autres langues.

Pour créer et configurer un remplacement, suivez ces étapes.

1. Accéder à **Warehouse management \> Configuration \> Appareil mobile \> Étapes d’appareil mobile**.
1. Dans la grille, recherchez et sélectionnez la ligne pour laquelle créer un remplacement.
1. Sur le volet Action, sélectionnez **Ajouter une configuration d'étape**.
1. Dans la boîte de dialogue déroulante **Ajouter une configuration d'étape**, définissez le champ **Élément de menu** sur le nom de l'élément de menu d'appareil mobile auquel votre remplacement s'applique. Puis sélectionnez **OK**.
1. La page qui apparaît affiche tous les textes disponibles pour le nouveau remplacement. Initialement, une seule langue est créée. Toutes les autres langues continueront d'utiliser les textes standard à moins que vous n'ajoutiez ces langues ici. Modifiez les textes et ajoutez de nouvelles langues selon vos besoins, comme décrit dans la section précédente.
