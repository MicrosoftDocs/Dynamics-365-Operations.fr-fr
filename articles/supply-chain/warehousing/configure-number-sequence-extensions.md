---
title: Configurer des séquences de numéros pour les flux d’entrepôt
description: Cette rubrique présente la fonctionnalité qui fournit des extensions de séquence numérique pour les ID de contenant, les ID d’étiquette de vague, les ID de conteneur et les ID de feuille de chargement.
author: Mirzaab
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSNumberSequenceExt
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 20438ed3e34775a6312508595bcd32b16a37a81d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669553"
---
# <a name="configure-number-sequences-for-warehouse-flows"></a>Configurer des séquences de numéros pour les flux d’entrepôt

[!include [banner](../includes/banner.md)]

La fonction *Extensions de séquence numérique* ajoute une nouvelle page de configuration pour la configuration des séquences de numéros. Elle permet une configuration flexible des ID réglementés par la norme GS1, y compris les préfixes GS1 et les chiffres de contrôle (modulo 10) ; elle applique une limite de longueur aux séquences de numéros existantes.

Les segments de séquence de numéros standard ne conviennent pas à la mise en œuvre de la norme GS1, car aucun chiffre de contrôle n’est calculé et le préfixe GS1 de la société doit être mis à jour manuellement.

Cette fonction apporte les fonctionnalités suivantes :

- Les ID de feuille de chargement (BOL) peuvent être générés à l’avance.
- Une séquence de numéros unique peut être générée pour les numéros de code de conteneur d’expédition en série (SSCC).
- Des séquences de numéros conformes à la norme GS1 peuvent être créées pour les numéros BOL et SSCC. La fonctionnalité ajoute une prise en charge prête à l’emploi pour les ID de contenant, les ID de conteneur, les ID d’étiquette de vague et les ID de BOL.
- La configuration des numéros d’identification de contenant est flexible. Par exemple, vous pouvez inclure ou exclure les identificateurs d’application (IA), comme les zéros non significatifs (00).

Cette fonctionnalité rend plus efficace l’étiquetage des cartons et l’ajustement des nouveaux numéros générés par le système.

## <a name="turn-on-the-number-sequence-extensions-feature"></a>Activer la fonction Extensions de séquence numérique

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Extensions de séquence numérique*

## <a name="set-up-the-feature"></a>Paramétrage de la fonctionnalité

Pour configurer des extensions de séquence numérique dans votre système, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.
1. Dans l’onglet **Général**, dans le champ **Préfixe GS1 de la société**, entrez le préfixe GS1 de votre entreprise. Cette valeur affectera toutes les séquences de numéros dans lesquelles le préfixe GS1 est inclus en tant que segment.
1. Si vous souhaitez générer des numéros BOL pour des étiquettes de vague, dans l’onglet **Rapports**, cochez la case **Générer le numéro BOL lors de l’impression d’étiquettes de vague**.

    > [!NOTE]
    > Cette case à cocher n’est disponible que si la fonctionnalité d’[impression d’étiquettes de vague](configure-wave-label-printing.md) est activée.

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Extensions de séquence de nombres**
1. Dans le volet Actions, sélectionnez **Créer une configuration par défaut**. Une séquence de numéros BOL conforme à la norme GS1 et trois types de séquences de numéros SSCC sont créés. Toutes ces séquences de numéros tiennent compte de la longueur du préfixe GS1 de votre entreprise.

    Pour plus d’informations sur la personnalisation de ces séquences de numéros par défaut et/ou l’ajout de nouvelles séquences, reportez-vous à la section suivante. Vous pouvez également supprimer l’une de ces séquences si vous n’en avez pas besoin.

1. Revenez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.
1. Dans l’onglet **Séquences de numéros**, sélectionnez une extension de séquence numérique appropriée à utiliser pour générer des numéros pour vos identificateurs de contenant, identificateurs d’étiquette de vague, identificateurs de conteneur (dans ce cas, sélectionnez la séquence **Numéro SSCC-18** appropriée) et/ou identificateurs BOL (dans ce cas, sélectionnez la séquence **BOL**). Par défaut, les extensions de séquence numérique ne sont prises en charge que pour ces quatre types d’ID.

La prochaine fois qu’un nouveau numéro sera généré pour l’une de ces séquences de numéros, la nouvelle logique sera utilisée.

> [!NOTE]
> Si vous ne sélectionnez pas d’extension de séquence numérique pour les ID de contenant, les règles actuelles de génération d’ID de contenant seront utilisées. Sinon, la séquence de numéros sélectionnée sera utilisée. Les autres identificateurs utiliseront une séquence numérique simple jusqu’à ce que vous leur appliquiez une extension de séquence numérique.

## <a name="create-and-edit-number-sequences"></a>Créer et modifier des séquences numériques

Dans la section précédente, vous avez généré un ensemble par défaut de séquences numériques. Cette section explique comment chaque séquence numérique est définie. Elle explique également comment créer des séquences personnalisées et comment modifier les séquences par défaut ou personnalisées.

Pour créer et modifier des séquences numériques, procédez comme suit.

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Extensions de séquence numériques**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Extension de séquence numérique**, entrez un nom pour la nouvelle séquence. Entrez une description dans le champ **Description**.
1. Dans l’organisateur **Segments**, utilisez les boutons de la barre d’outils pour assembler votre format numérique en ajoutant, supprimant et organisant des segments. Dans le champ **Segment** de chaque ligne, attribuez un type de segment pour définir l’objectif et le contenu de ce segment. Le tableau suivant décrit les types de segments disponibles.

    | Type de segment | Description |
    |---|---|
    | Constante | Ce type de segment ajoute le même texte constant pour chaque numéro généré dans la séquence. Entrez le texte requis dans le champ **Valeur**. Le champ **Longueur** est automatiquement mis à jour à la longueur du texte que vous avez entré dans le champ **Valeur**. |
    | Souche de numéros | Dans le champ **Valeur**, entrez un signe dièse (*\#*) pour chaque caractère à afficher dans la séquence générée. La séquence numérique elle-même peut générer des nombres plus longs, mais seuls les caractères les plus à droite seront affichés. Le champ **Longueur** est automatiquement mis à jour au nombre de symboles numériques que vous avez entrés dans le champ **Valeur**.<p>Pour vous conformer aux exigences GS1 pour les numéros SSCC-18, assurez-vous que la longueur de ce segment est 16, moins la longueur de votre préfixe GS1.</p> |
    | Préfixe GS1 | Ce type de segment ajoute la valeur définie dans le champ **Préfixe GS1 de la société** de la page **Paramètres de gestion des entrepôts**. Le champ **Valeur** affiche la valeur définie sur la page **Paramètres de gestion des entrepôts** et le champ **Longueur** indique le nombre de caractères de la valeur. Les deux champs **Valeur** et **Longueur** sont en lecture seule. |
    | Identificateur d’application | Dans le champ **Valeur**, saisissez un identificateur d’application, comme spécifié par la stratégie GS1 pertinente pour ce type de séquence numérique. Par exemple, entrez *00* pour SSCC ou *420* pour BOL. Le champ **Longueur** est automatiquement mis à jour à la longueur de l’identificateur que vous avez entré dans le champ **Valeur**. |
    | Type d’emballage | Pour les articles qui peuvent être clairement identifiés, ce type de segment ajoute une valeur de champ provenant du groupe de séquence d’unités concerné (de la page **Groupes de séquences d’unités**). (Ce comportement correspond à la logique existante pour les ID de contenant.) Pour les contenants qui incluent plusieurs unités de gestion des stocks (SKU), ce type de segment ajoute *0* (zéro) par défaut. Pour ce type de segment, le champ **Valeur** est toujours défini sur *P*, et le champ **Longueur** est toujours défini sur *1*.|
    | Chiffre de contrôle | Ce type de segment ajoute un chiffre de contrôle, qui est un calcul modulo 10. (Ce comportement correspond à la logique existante pour les ID de contenant.) Pour ce type de segment, le champ **Valeur** est toujours défini sur un symbole caret (*^*), et le champ **Longueur** est toujours défini sur *1*. |

1. Pour voir un exemple de votre format de nombre final, inspectez le champ **Format** au bas de l’organisateur **Segments**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]