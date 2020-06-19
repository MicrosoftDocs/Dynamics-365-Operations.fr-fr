---
title: Déclarer comme terminé à partir du périphérique de bon de travail
description: Cette rubrique décrit comment configurer le système afin que les utilisateurs d'un périphérique de bon de travail puissent déclarer les produits finis depuis un ordre de fabrication vers le stock.
author: johanhoffmann
manager: tfehr
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f5d34893ddc8adc3785ec50dbd72438cf8f68c5d
ms.sourcegitcommit: 52ba8d3e6af72df5dab6c04b9684a61454d353ad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/26/2020
ms.locfileid: "3403260"
---
# <a name="report-as-finished-from-the-job-card-device"></a>Déclarer comme terminé à partir du périphérique de bon de travail

[!include [banner](../includes/banner.md)]

Les collaborateurs utilisent la page **Connaître l'état de progression** sur le périphérique de bon de travail pour signaler les quantités terminées pour une tâche de production.

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a>Contrôlez si les quantités déclarées comme terminées sont ajoutées au stock

Pour contrôler si et comment les quantités déclarées comme terminées lors de la dernière opération doivent être ajoutées au stock, procédez comme suit.

1. Accédez à **Contrôle produit \> Paramétrage \> Contrôle et suivi de la production \> Valeurs par défaut de l'ordre de fabrication**.
1. Dans l'onglet **Déclarer comme terminé**, définissez le champ **Mettre à jour déclaration de fin en ligne** sur l'une des valeurs suivantes :

    - **Non** – Aucune quantité ne sera ajoutée au stock lorsque des quantités sont déclarées lors de la dernière opération. Le statut de l'ordre de fabrication ne changera jamais.
    - **Statut + Quantité** – Le statut de l'ordre de fabrication passera à *Déclarer comme terminé* et la quantité sera signalée comme terminée dans le stock.
    - **Quantité** – La quantité sera déclarée comme terminée dans le stock, mais le statut de l'ordre de fabrication ne changera jamais.
    - **Statut** – Seul le statut de l'ordre de fabrication change. Aucune quantité ne sera ajoutée au stock lorsque des quantités sont déclarées lors de la dernière opération.

> [!NOTE]
> Les quantités ne sont pas suivies dans le stock si les opérations sur lesquelles elles sont signalées comme terminées ne sont pas définies comme la dernière opération. Cependant, ces quantités peuvent être utilisées pour visualiser la progression. Elles peuvent également être incluses dans les règles qui contrôlent si les collaborateurs peuvent lancer l'opération suivante avant qu'un seuil défini de quantités déclarées sur l'opération précédente soit atteint. Vous pouvez définir ces règles dans l'onglet **Validation des quantités** de la page **Valeurs par défaut des ordres de fabrication**.

Pour plus d'informations sur l'utilisation de la page **Valeurs par défaut des ordres de fabrication**, voir [Paramètres de production dans Contrôle et suivi de la production](production-parameters-manufacturing-execution.md).

## <a name="report-batch-controlled-items-as-finished"></a>Déclarer les articles contrôlés par lot comme terminés

Le périphérique de bon de travail prend en charge trois scénarios pour la déclaration des articles par lot. Ces scénarios s'appliquent à la fois aux articles activés pour les processus d'entrepôt avancés et aux articles qui ne sont pas activés pour les processus d'entrepôt avancés.

- **Numéros de lot attribués manuellement :** Les collaborateurs entrent un numéro de lot personnalisé. Ce numéro de lot peut provenir d'une source externe inconnue du système.
- **Numéros de lots prédéfinis :** Les collaborateurs sélectionnent un numéro de lot dans une liste de numéros de lot que le système génère automatiquement avant que l'ordre de fabrication ne soit envoyé au périphérique de bon de travail.
- **Numéros de lot fixes :** Les collaborateurs n'entrent ni ne sélectionnent de numéro de lot. Au lieu de cela, le système attribue automatiquement un numéro de lot à l'ordre de fabrication avant son lancement.

Pour activer chaque scénario, procédez comme suit :

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez le produit à configurer.
1. Dans le raccourci **Gérer le stock**, dans le champ **Groupe de numéros de lot**, sélectionnez le groupe de numéros de suivi configuré pour prendre en charge votre scénario.

> [!NOTE]
> Par défaut, si aucun groupe de numéros de lot n'est affecté à un produit contrôlé par lot, le périphérique de bon de travail fournit une entrée manuelle pour le numéro de lot lors de la génération du rapport.

Les sous-sections suivantes décrivent comment configurer les groupes de numéros de suivi pour prendre en charge chacun des trois scénarios de génération de rapports sur les articles par lot.

### <a name="enable-batch-number-reporting-on-the-job-card-device"></a>Activer la déclaration de numéro de lot sur le périphérique de bon de travail

Pour permettre aux périphériques de bon de travail d'accepter un numéro de lot lors de la déclaration de fin, vous devez utiliser la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer les fonctionnalités suivantes (dans cet ordre) :

1. Amélioration de l'expérience utilisateur pour la boîte de dialogue Connaître l'état de progression dans le périphérique des bons de travail
1. Permet d'entrer des numéros de lot et de série lors de la déclaration de fin à partir du périphérique de bons de travail (version préliminaire)

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a>Configurer un groupe de numéros de suivi qui permet aux employés d'attribuer manuellement un numéro de lot

Pour permettre l'attribution manuelle de numéros de lot, procédez comme suit pour configurer un groupe de numéros de suivi.

1. Accédez à **Gestion des stocks \> Paramétrage \> Dimensions \> Groupes de numéros de suivi**.
1. Créez ou sélectionnez le groupe de numéros de suivi à configurer.
1. Dans le raccourci **Général**, définissez l'option **Manuel** sur **Oui**.

    ![Page Groupes de numéros de suivi](media/tracking-number-group-manual.png "Page Groupes de numéros de suivi")

1. Définissez les autres valeurs selon vos besoins, puis sélectionnez ce groupe de numéros de suivi comme groupe de numéros de lot pour les produits lancés pour lesquels vous souhaitez utiliser ce scénario.

Lorsque vous utilisez ce scénario, le champ **Numéro de lot** fourni par la page **Connaître l'état de progression** du périphérique de bon de travail est une zone de texte où les collaborateurs peuvent entrer n'importe quelle valeur.

![Page Connaître l'état de progression avec un champ pour les numéros de lot manuels](media/job-card-device-batch-manual.png "Page Connaître l'état de progression avec un champ pour les numéros de lot manuels")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a>Configurer un groupe de numéros de suivi qui fournit une liste de numéros de lots prédéfinis

Pour fournir une liste de numéros de lot prédéfinis, procédez comme suit pour configurer un groupe de numéros de suivi.

1. Accédez à **Gestion des stocks \> Paramétrage > Dimensions \> Groupes de numéros de suivi**.
1. Créez ou sélectionnez le groupe de numéros de suivi à configurer.
1. Dans le raccourci **Général**, définissez l'option **Mouvements de stock uniquement** sur **Oui**.
1. Utilisez le champ **Par qté** pour fractionner les numéros de lot par quantité, en fonction de la valeur que vous entrez. Par exemple, vous avez un ordre de fabrication pour dix pièces et le champ **Par qté** est défini sur *2*. Dans ce cas, cinq numéros de lot seront affectés à l'ordre de fabrication lors de sa création.

    ![Page Groupes de numéros de suivi](media/tracking-number-group-predefined.png "Page Groupes de numéros de suivi")

1. Définissez les autres valeurs selon vos besoins, puis sélectionnez ce groupe de numéros de suivi comme groupe de numéros de lot pour les produits lancés pour lesquels vous souhaitez utiliser ce scénario.

Lorsque vous utilisez ce scénario, le champ **Numéro de lot** fourni par la page **Connaître l'état de progression** du périphérique de bon de travail est une liste déroulante où les collaborateurs doivent sélectionner une valeur prédéfinie.

![Page Connaître l'état de progression avec une liste de numéros de lot prédéfinis](media/job-card-device-batch-predefined.png "Page Connaître l'état de progression avec une liste de numéros de lot prédéfinis")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a>Configurer un groupe de numéros de suivi qui attribue automatiquement les numéros de lot

Si des numéros de lot doivent être attribués automatiquement, sans saisie d'un collaborateur, procédez comme suit pour configurer un groupe de numéros de suivi.

1. Accédez à **Gestion des stocks \> Paramétrage \> Dimensions \> Groupes de numéros de suivi**.
1. Créez ou sélectionnez le groupe de numéros de suivi à configurer.
1. Dans le raccourci **Général**, définissez l'option **Mouvements de stock uniquement** sur **No**.
1. Définissez l'option **Manuel** sur **Non**.

    ![Page Groupes de numéros de suivi](media/tracking-number-group-fixed.png "Page Groupes de numéros de suivi")

1. Définissez les autres valeurs selon vos besoins, puis sélectionnez ce groupe de numéros de suivi comme groupe de numéros de lot pour les produits lancés pour lesquels vous souhaitez utiliser ce scénario.

Lorsque vous utilisez ce scénario, le champ **Numéro de lot** fourni par la page **Connaître l'état de progression** du périphérique de bon de travail affiche une valeur que les collaborateurs ne peuvent pas modifier.

![Page Connaître l'état de progression avec un numéro de lot fixe](media/job-card-device-batch-fixed.png "Page Connaître l'état de progression avec un numéro de lot fixe")

## <a name="report-as-finished-to-a-license-plate"></a>Déclarer comme terminé à un contenant

Les processus d'entrepôt avancés peuvent utiliser la dimension de contenant pour suivre le stocke sur les sites d'entrepôt qui ont été configurés à cet effet. Dans ce cas, le numéro de contenant est requis lorsqu'un collaborateur déclare des quantités comme terminées.

### <a name="enable-license-plate-reporting-and-label-printing"></a>Activer la déclaration et l'impression d'étiquette de contenant

Pour utiliser les fonctionnalités décrites dans cette section, vous devez utiliser la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer les fonctionnalités suivantes (dans cet ordre) :

1. Contenant pour la déclaration ajouté comme finalisé au périphérique pour bons de travail
1. Activer la génération automatique du numéro de contenant lors de la déclaration de fin dans le périphérique de bon de travail
1. Imprimer une étiquette à partir d'un périphérique de bons de travail

### <a name="set-up-reporting-as-finished-to-a-license-plate"></a>Configurer la déclaration de fin à un contenant

Pour contrôler si les collaborateurs doivent réutiliser un contenant existant ou en générer un nouveau lorsqu'ils déclarent des quantités comme terminées, procédez comme suit.

1. Accédez à **Contrôle de la production \> Paramétrage \> Contrôle et suivi de la production \> Configurer le bon de travail pour les périphériques**.
2. Définissez les options suivantes pour chaque périphérique :

    - **Générer un contenant** – Définissez cette option sur **Oui** pour générer un nouveau contenant pour chaque déclaration de fin. Définissez-la sur **Non** s'il faut utiliser un contenant existant pour chaque déclaration de fin.
    - **Imprimer l'étiquette** – Définissez cette option sur **Oui** si le collaborateur doit imprimer une étiquette de contenant pour chaque déclaration de fin. Définissez-la sur **Non** si aucune étiquette n'est requise. 

![Page Configurer le bon de travail pour les périphériques](media/config-job-card-raf.png "Page Configurer le bon de travail pour les périphériques")

> [!NOTE]
> Pour configurer l'étiquette, accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Acheminement de document**. Pour plus d'informations, voir [Activer l'impression d'étiquette de contenant](../warehousing/tasks/license-plate-label-printing.md).
