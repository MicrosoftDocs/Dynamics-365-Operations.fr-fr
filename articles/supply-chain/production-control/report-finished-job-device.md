---
title: Déclarer comme terminé à partir du périphérique de bon de travail
description: Cette rubrique décrit comment configurer le système afin que les utilisateurs d’un périphérique de bon de travail puissent déclarer les produits finis depuis un ordre de fabrication vers le stock.
author: johanhoffmann
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 5da18ff1013f0e767ca64b090eb1559bf05cb056
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350520"
---
# <a name="report-as-finished-from-the-job-card-device"></a>Déclarer comme terminé à partir du périphérique de bon de travail

[!include [banner](../includes/banner.md)]

Les collaborateurs utilisent la page **Connaître l’état de progression** sur le périphérique de bon de travail pour signaler les quantités terminées pour une tâche de production. Cette rubrique décrit comment configurer diverses options qui déterminent comment les collaborateurs peuvent signaler comme ayant terminé à l’aide de cette page et ce qui se passe ensuite. Options possibles :

- Contrôlez si et comment les quantités déclarées comme terminées sont ajoutées au stock.
- Contrôlez si et comment les numéros de lot sont générés et appliqués lorsque le rapport est terminé.
- Contrôlez si et comment les numéros de série sont générés et appliqués lorsque le rapport est terminé.
- Contrôle si et comment déclarer comme terminé dans un contenant.

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a>Contrôlez si les quantités déclarées comme terminées sont ajoutées au stock

Pour contrôler si et comment les quantités déclarées comme terminées lors de la dernière opération doivent être ajoutées au stock, procédez comme suit.

1. Accédez à **Contrôle produit \> Paramétrage \> Contrôle et suivi de la production \> Valeurs par défaut de l’ordre de fabrication**.
1. Dans l’onglet **Déclarer comme terminé**, définissez le champ **Mettre à jour déclaration de fin en ligne** sur l’une des valeurs suivantes :

    - **Non** – Aucune quantité ne sera ajoutée au stock lorsque des quantités sont déclarées lors de la dernière opération. Le statut de l’ordre de fabrication ne changera jamais.
    - **Statut + Quantité** – Le statut de l’ordre de fabrication passera à *Déclarer comme terminé* et la quantité sera signalée comme terminée dans le stock.
    - **Quantité** – La quantité sera déclarée comme terminée dans le stock, mais le statut de l’ordre de fabrication ne changera jamais.
    - **Statut** – Seul le statut de l’ordre de fabrication change. Aucune quantité ne sera ajoutée au stock lorsque des quantités sont déclarées lors de la dernière opération.

> [!NOTE]
> Les quantités ne sont pas suivies dans le stock si les opérations sur lesquelles elles sont signalées comme terminées ne sont pas définies comme la dernière opération. Cependant, ces quantités peuvent être utilisées pour visualiser la progression. Elles peuvent également être incluses dans les règles qui contrôlent si les collaborateurs peuvent lancer l’opération suivante avant qu’un seuil défini de quantités déclarées sur l’opération précédente soit atteint. Vous pouvez définir ces règles dans l’onglet **Validation des quantités** sur la page **Valeurs par défaut des ordres de fabrication**.

Pour plus d’informations sur l’utilisation de la page **Valeurs par défaut des ordres de fabrication**, voir [Paramètres de production dans Contrôle et suivi de la production](production-parameters-manufacturing-execution.md).

## <a name="report-batch-controlled-items-as-finished"></a>Déclarer les articles contrôlés par lot comme terminés

Le périphérique de bon de travail prend en charge trois scénarios pour la déclaration des articles par lot. Ces scénarios s’appliquent à la fois aux articles activés pour les processus d’entrepôt avancés et aux articles qui ne sont pas activés pour les processus d’entrepôt avancés.

- **Numéros de lot attribués manuellement** - Les collaborateurs entrent un numéro de lot personnalisé. Ce numéro de lot peut provenir d’une source externe inconnue du système.
- **Numéros de lots prédéfinis** - Les collaborateurs sélectionnent un numéro de lot dans une liste de numéros de lot que le système génère automatiquement avant que l’ordre de fabrication ne soit envoyé au périphérique de bon de travail.
- **Numéros de lot fixes** - Les collaborateurs n’entrent ni ne sélectionnent de numéro de lot. Au lieu de cela, le système attribue automatiquement un numéro de lot à l’ordre de fabrication avant son lancement.


### <a name="enable-the-feature-on-your-system"></a>Activer la fonctionnalité sur votre système

Pour permettre aux périphériques de bon de travail d’accepter un numéro de lot lors de la déclaration de fin, vous devez utiliser la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer les fonctionnalités suivantes (dans cet ordre) :

1. Amélioration de l’expérience utilisateur pour la boîte de dialogue Connaître l’état de progression dans le périphérique des bons de travail
1. Ce bouton permet d’entrer des numéros de lot et de série lors de la déclaration de fin à partir du périphérique de bons de travail

### <a name="configure-products-that-require-batch-number-reporting"></a>Configurer les produits qui nécessitent un rapport de numéro de lot

Pour permettre à un produit de prendre en charge l’un des scénarios contrôlés par lots disponibles, procédez comme suit :

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez le produit à configurer.
1. Dans le raccourci **Gérer le stock**, dans le champ **Groupe de numéros de lot**, sélectionnez le groupe de numéros de suivi configuré pour prendre en charge votre scénario.

> [!NOTE]
> Par défaut, si aucun groupe de numéros de lot n’est affecté à un produit contrôlé par lot, le périphérique de bon de travail fournit une entrée manuelle pour le numéro de lot lors de la génération du rapport.

Les sections suivantes décrivent comment configurer les groupes de numéros de suivi pour prendre en charge chacun des trois scénarios de génération de rapports sur les articles par lot.

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a>Configurer un groupe de numéros de suivi qui permet aux employés d’attribuer manuellement un numéro de lot

Pour permettre l’attribution manuelle de numéros de lot, procédez comme suit pour configurer un groupe de numéros de suivi.

1. Accédez à **Gestion des stocks \> Paramétrage \> Dimensions \> Groupes de numéros de suivi**.
1. Créez ou sélectionnez le groupe de numéros de suivi à configurer.
1. Dans le raccourci **Général**, définissez l’option **Manuel** sur **Oui**.

    ![Groupe de numéros de suivi pour les numéros de lots manuels.](media/tracking-number-group-manual.png "Groupe de numéros de suivi pour les numéros de lots manuels")

1. Définissez les autres valeurs selon vos besoins, puis sélectionnez ce groupe de numéros de suivi comme groupe de numéros de lot pour les produits lancés pour lesquels vous souhaitez utiliser ce scénario.

Lorsque vous utilisez ce scénario, le champ **Numéro de lot** fourni par la page **Connaître l’état de progression** du périphérique de bon de travail est une zone de texte où les collaborateurs peuvent entrer n’importe quelle valeur.

![Page Connaître l’état de progression avec un champ pour les numéros de lot manuels.](media/job-card-device-batch-manual.png "Page Connaître l’état de progression avec un champ pour les numéros de lot manuels")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a>Configurer un groupe de numéros de suivi qui fournit une liste de numéros de lots prédéfinis

Pour fournir une liste de numéros de lot prédéfinis, procédez comme suit pour configurer un groupe de numéros de suivi.

1. Accédez à **Gestion des stocks \> Paramétrage > Dimensions \> Groupes de numéros de suivi**.
1. Créez ou sélectionnez le groupe de numéros de suivi à configurer.
1. Dans le raccourci **Général**, définissez l’option **Mouvements de stock uniquement** sur **Oui**.
1. Utilisez le champ **Par qté** pour fractionner les numéros de lot par quantité, en fonction de la valeur que vous entrez. Par exemple, vous avez un ordre de fabrication pour dix pièces et le champ **Par qté** est défini sur *2*. Dans ce cas, cinq numéros de lot seront affectés à l’ordre de fabrication lors de sa création.

    ![Groupe de numéros de suivi pour les numéros de lots prédéfinis.](media/tracking-number-group-predefined.png "Groupe de numéros de suivi pour les numéros de lots prédéfinis")

1. Définissez les autres valeurs selon vos besoins, puis sélectionnez ce groupe de numéros de suivi comme groupe de numéros de lot pour les produits lancés pour lesquels vous souhaitez utiliser ce scénario.

Lorsque vous utilisez ce scénario, le champ **Numéro de lot** fourni par la page **Connaître l’état de progression** du périphérique de bon de travail est une liste déroulante où les collaborateurs doivent sélectionner une valeur prédéfinie.

![Page Connaître l’état de progression avec une liste de numéros de lot prédéfinis.](media/job-card-device-batch-predefined.png "Page Connaître l’état de progression avec une liste de numéros de lot prédéfinis")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a>Configurer un groupe de numéros de suivi qui attribue automatiquement les numéros de lot

Si des numéros de lot doivent être attribués automatiquement, sans saisie d’un collaborateur, procédez comme suit pour configurer un groupe de numéros de suivi.

1. Accédez à **Gestion des stocks \> Paramétrage \> Dimensions \> Groupes de numéros de suivi**.
1. Créez ou sélectionnez le groupe de numéros de suivi à configurer.
1. Dans le raccourci **Général**, définissez l’option **Mouvements de stock uniquement** sur **No**.
1. Définissez l’option **Manuel** sur **Non**.

    ![Groupe de numéros de suivi pour les numéros de lots fixes.](media/tracking-number-group-fixed.png "Groupe de numéros de suivi pour les numéros de lots fixes")

1. Définissez les autres valeurs selon vos besoins, puis sélectionnez ce groupe de numéros de suivi comme groupe de numéros de lot pour les produits lancés pour lesquels vous souhaitez utiliser ce scénario.

Lorsque vous utilisez ce scénario, le champ **Numéro de lot** fourni par la page **Connaître l’état de progression** du périphérique de bon de travail affiche une valeur que les collaborateurs ne peuvent pas modifier.

![Page Connaître l’état de progression avec un numéro de lot fixe.](media/job-card-device-batch-fixed.png "Page Connaître l’état de progression avec un numéro de lot fixe")

## <a name="report-serial-controlled-items-as-finished"></a>Déclarer les articles contrôlés par série comme terminés

Le périphérique de bon de travail prend en charge trois scénarios pour la déclaration des articles contrôlés par série. Ces scénarios s’appliquent à la fois aux articles activés pour les processus d’entrepôt avancés et aux articles qui ne sont pas activés pour les processus d’entrepôt avancés.

- **Numéros de série attribués manuellement** - Les collaborateurs entrent un numéro de série personnalisé. Ce numéro de série peut provenir d’une source externe inconnue du système.
- **Numéros de série prédéfinis** - Les collaborateurs sélectionnent un numéro de série dans une liste de numéros de série que le système génère automatiquement avant que l’ordre de fabrication ne soit envoyé au périphérique de bon de travail.
- **Numéros de série fixes** - Les collaborateurs n’entrent ni ne sélectionnent de numéro de série. Au lieu de cela, le système attribue automatiquement un numéro de série à l’ordre de fabrication avant son lancement.

### <a name="enable-the-feature-on-your-system"></a>Activer la fonctionnalité sur votre système

Pour permettre aux périphériques de bon de travail d’accepter un numéro de série lors de la déclaration de fin, vous devez utiliser la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer les fonctionnalités suivantes (dans cet ordre) :

1. Amélioration de l’expérience utilisateur pour la boîte de dialogue Connaître l’état de progression dans le périphérique des bons de travail
1. Ce bouton permet d’entrer des numéros de lot et de série lors de la déclaration de fin à partir du périphérique de bons de travail

### <a name="configure-products-that-require-serial-number-reporting"></a>Configurer les produits qui nécessitent un rapport de numéro de série

Pour permettre à un produit de prendre en charge l’un des scénarios contrôlés par série disponibles, procédez comme suit :

Pour activer chaque scénario, procédez comme suit :

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez le produit à configurer.
1. Dans le raccourci **Gérer le stock**, dans le champ **Groupe de numéros de série**, sélectionnez le groupe de numéros de suivi configuré pour prendre en charge votre scénario.

> [!NOTE]
> Par défaut, si aucun groupe de numéros de série n’est affecté à un produit contrôlé par série, le périphérique des bons de travail fournit une entrée manuelle pour le numéro de série lors de la génération du rapport.

Les sections suivantes décrivent comment configurer les groupes de numéros de suivi pour prendre en charge chacun des trois scénarios de génération de rapports sur les articles contrôlés par série.

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-serial-number"></a>Configurer un groupe de numéros de suivi qui permet aux employés d’attribuer manuellement un numéro de série

Pour permettre l’attribution manuelle de numéros de série, procédez comme suit pour configurer un groupe de numéros de suivi.

1. Accédez à **Gestion des stocks \> Paramétrage \> Dimensions \> Groupes de numéros de suivi**.
1. Créez ou sélectionnez le groupe de numéros de suivi à configurer.
1. Dans le raccourci **Général**, définissez l’option **Manuel** sur **Oui**.

    ![Page des groupes de numéros de suivi, numéros de série.](media/tracking-number-group-manual-serial.png "Page des groupes de numéros de suivi, numéros de série")

1. Définissez les autres valeurs selon vos besoins, puis sélectionnez ce groupe de numéros de suivi comme groupe de numéros de série pour les produits lancés pour lesquels vous souhaitez utiliser ce scénario.

Lorsque vous utilisez ce scénario, le champ **Numéro de série** fourni par la page **Connaître l’état de progression** du périphérique de bon de travail est une zone de texte où les collaborateurs peuvent entrer n’importe quelle valeur pour le numéro de série. Lors de la saisie d’une valeur, elle est ajoutée à la liste des numéros de série. Pour ce faire, les collaborateurs peuvent utiliser l’une des méthodes suivantes :

- Pour marquer un numéro de série comme mis au rebut, sélectionnez le bouton **Rebut** pour la ligne appropriée. Le collaborateur sera invité à fournir une **Cause de l’erreur**.
- Pour supprimer un numéro de série, sélectionnez le bouton **Supprimer** pour la ligne appropriée.

![Page Connaître l’état de progression avec un champ pour les numéros de série manuels.](media/job-card-device-serial-manual.png "Page Connaître l’état de progression avec un champ pour les numéros de série manuels")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-serial-numbers"></a>Configurer un groupe de numéros de suivi qui fournit une liste de numéros de série prédéfinis

Pour fournir une liste de numéros de série prédéfinis, procédez comme suit pour configurer un groupe de numéros de suivi.

1. Accédez à **Gestion des stocks \> Paramétrage \> Dimensions \> Groupes de numéros de suivi**.
1. Créez ou sélectionnez le groupe de numéros de suivi à configurer.
1. Dans le raccourci **Général**, définissez l’option **Mouvements de stock uniquement** sur **Oui**.
1. Utilisez le champ **Par quantité** pour fractionner les numéros de série par quantité d’un.

    ![Groupe de numéros de suivi pour les numéros de série prédéfinis.](media/tracking-number-group-predefined-sn.png "Groupe de numéros de suivi pour les numéros de série prédéfinis")

1. Définissez les autres valeurs selon vos besoins, puis sélectionnez ce groupe de numéros de suivi comme groupe de numéros de série pour les produits lancés pour lesquels vous souhaitez utiliser ce scénario.

Lorsque vous utilisez ce scénario, le champ **Numéro de série** fourni par la page **Connaître l’état de progression** du périphérique de bon de travail est une liste déroulante où les collaborateurs doivent sélectionner une valeur prédéfinie.

![Page Connaître l’état de progression avec une liste de numéros de série prédéfinis.](media/job-card-device-serial-predefined.png "Page Connaître l’état de progression avec une liste de numéros de série prédéfinis")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-serial-numbers"></a>Configurer un groupe de numéros de suivi qui attribue automatiquement les numéros de série

Si un numéro de série doit être attribué automatiquement, sans saisie d’un collaborateur, procédez comme suit pour configurer un groupe de numéros de suivi.

1. Accédez à **Gestion des stocks \> Paramétrage \> Dimensions \> Groupes de numéros de suivi**.
1. Créez ou sélectionnez le groupe de numéros de suivi à configurer.
1. Dans le raccourci **Général**, définissez l’option **Mouvements de stock uniquement** sur **No**.
1. Définissez l’option **Manuel** sur **Non**.

    ![Groupe de numéros de suivi pour les numéros de série fixes.](media/tracking-number-group-fixed-sn.png "Groupe de numéros de suivi pour les numéros de série fixes")

1. Définissez les autres valeurs selon vos besoins, puis sélectionnez ce groupe de numéros de suivi comme groupe de numéros de série pour les produits lancés pour lesquels vous souhaitez utiliser ce scénario.

Lorsque vous utilisez ce scénario, le champ **Numéro de série** fourni par la page **Connaître l’état de progression** du périphérique de bon de travail affiche une valeur que les collaborateurs ne peuvent pas modifier. Ce scénario n’est pertinent que lorsqu’un ordre de fabrication est créé pour une quantité d’une pièce d’un article contrôlé par numéro de série.

![Page Connaître l’état de progression avec un numéro de série fixe.](media/job-card-device-serial-fixed.png "Page Connaître l’état de progression avec des numéros de série fixes")

## <a name="report-as-finished-to-a-license-plate"></a>Déclarer comme terminé à un contenant

Les processus d’entrepôt avancés peuvent utiliser la dimension de contenant pour suivre le stocke sur les sites d’entrepôt qui ont été configurés à cet effet. Dans ce cas, le numéro de contenant est requis lorsqu’un collaborateur déclare des quantités comme terminées.

### <a name="enable-license-plate-reporting-and-label-printing"></a>Activer la déclaration et l’impression d’étiquette de contenant

Pour utiliser les fonctionnalités décrites dans cette section, vous devez utiliser la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer les fonctionnalités suivantes (dans cet ordre) :

1. Contenant pour la déclaration ajouté comme finalisé au périphérique pour bons de travail
1. Activer la génération automatique du numéro de contenant lors de la déclaration de fin dans le périphérique de bon de travail
1. Imprimer une étiquette à partir d’un périphérique de bons de travail

### <a name="set-up-reporting-as-finished-to-a-license-plate"></a>Configurer la déclaration de fin à un contenant

Pour contrôler si les collaborateurs doivent réutiliser un contenant existant ou en générer un nouveau lorsqu’ils déclarent des quantités comme terminées, procédez comme suit.

1. Accédez à **Contrôle de la production \> Paramétrage \> Contrôle et suivi de la production \> Configurer le bon de travail pour les périphériques**.
2. Définissez les options suivantes pour chaque périphérique :

    - **Générer un contenant** – Définissez cette option sur **Oui** pour générer un nouveau contenant pour chaque déclaration de fin. Définissez-la sur **Non** s’il faut utiliser un contenant existant pour chaque déclaration de fin.
    - **Imprimer l’étiquette** – Définissez cette option sur **Oui** si le collaborateur doit imprimer une étiquette de contenant pour chaque déclaration de fin. Définissez-la sur **Non** si aucune étiquette n’est requise. 

![Page Configurer le bon de travail pour les périphériques.](media/config-job-card-raf.png "Page Configurer le bon de travail pour les périphériques")

> [!NOTE]
> Pour configurer l’étiquette, accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Acheminement de document**. Pour plus d’informations, voir [Activer l’impression d’étiquette de contenant](../warehousing/tasks/license-plate-label-printing.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]