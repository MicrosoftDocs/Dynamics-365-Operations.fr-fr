---
title: Réimpression et annulation d'étiquettes de vague
description: Cette rubrique explique comment annuler et réimprimer des étiquettes de vague existantes.
author: GarmMSFT
manager: PJacobse
ms.date: 07/09/2020
ms.topic: article
ms.service: dynamics-ax-applications
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSWaveTableListPage, WHSWorkException, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelLayout, WHSWaveLabelType, WHSWaveLabelTemplateGroup
audience: Application User
ms.reviewer: PJacobse
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-07-09
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: cc76a3915d6a1e58a71eb997b5af58941905e879
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996046"
---
# <a name="reprint-and-void-wave-labels"></a>Réimpression et annulation d'étiquettes de vague

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment gérer les étiquettes générées par le traitement de vague. (Pour une description détaillée et des instructions de configuration, voir [Configurer l'impression des étiquettes de vague](../warehousing/configure-wave-label-printing.md) .)

Vous pouvez réimprimer les étiquettes de vague à tout moment. Par exemple, vous pouvez être dans l'obligation d'imprimer une seule étiquette si une étiquette existante a été perdue ou endommagée. Dans un autre cas, un magasinier ou un superviseur peut avoir à réimprimer tout un rouleau d'étiquettes si le nombre et/ou la composition de toute une série d'étiquettes de vague a changé (par exemple, en raison d'une pénurie de stock ou pour d'autres raisons). Souvent, même si seul le nombre de cartons a changé, le rouleau entier doit être réimprimé pour que le nombre total demeure exact dans la section « Carton X sur Y » de chaque étiquette.

La fonction de réimpression des étiquettes de vague prend en charge les fonctionnalités suivantes :

- Réimpression d'étiquettes à partir de l'application d'entreposage et du Rich Client.
- Annulation d'étiquettes et réimpression simultanée. (La possibilité d'annuler des étiquettes est intégrée dans les scénarios de prélèvement partiel, par exemple.)
- Nettoyage de l'historique des étiquettes de vague.

Cette rubrique présente une collection de scénarios qui montrent, à travers des exemples, comment utiliser la fonction de réimpression des étiquettes de vague.

> [!IMPORTANT]
> Pour travailler sur les scénarios présentés dans cette rubrique, vous devez d'abord activer et configurer les fonctionnalités d'impression de vague appropriées, comme décrit dans [Configurer l'impression des étiquettes de vague](../warehousing/configure-wave-label-printing.md). Plusieurs des scénarios de cette rubrique nécessitent également que vous travailliez d'abord sur les scénarios de cette rubrique pour générer les exemples de données prérequis.

## <a name="scenario-1-reprint-labels-from-the-web-client"></a>Scénario 1 : réimprimer des étiquettes à partir du client Web

Vous pouvez afficher et réimprimer des étiquettes de vague à partir des pages suivantes. Dans le volet Actions de chaque page, sous l'onglet **Expéditions**, dans le groupe **Informations associées**, sélectionnez **Étiquettes de vague**.

- Toutes les expéditions \>Détails de l'expédition
- Tous les chargements \>Charger du chargement
- Toutes les vagues
- Étiquettes de vague
- Historique des étiquettes de la vague

Pour réimprimer une étiquette de vague à partir du client Web, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.
1. Sélectionnez la vague à partir de laquelle réimprimer les étiquettes.
1. Dans le volet Actions, sous l'onglet **Vague**, dans le groupe **Imprimer**, sélectionnez **Étiquettes de vague**.
1. Suivez une ou les deux étapes suivantes :

    - Pour réimprimer l'étiquette, sélectionnez l'imprimante dans le champ **Nom d'imprimante**. (Laissez ce champ vide si vous souhaitez simplement mettre à jour les détails de l'étiquette de vague sans la réimprimer.)
    - Pour mettre à jour l'étiquette, cochez la case **Mettre à jour les détails de l'étiquette de vague**. (Laissez cette case décochée si vous souhaitez simplement réimprimer l'étiquette précédente.)

    > [!NOTE]
    > Chaque fois qu'une étiquette de vague est imprimée ou réimprimée, ses données sont converties en utilisant la mise en page d'étiquette de vague appropriée, et tous les espaces réservés sont remplacés par des valeurs réelles. La chaîne résultante est stockée sous forme d'enregistrement dans l'historique des étiquettes de vague. Si la case **Mettre à jour les détails de l'étiquette de vague** est décochée, les données stockées du langage de programmation Zebra (ZPL) sont utilisées lorsqu'une étiquette est réimprimée. Si la case **Mettre à jour les détails de l'étiquette de vague** est cochée, une nouvelle chaîne est générée. Les étiquettes de vague existantes sont également recalculées et toutes les étiquettes en excès (par exemple, si les lignes de travail associées ont été annulées ou modifiées) sont marquées comme **Annulées** et ne sont pas réimprimées.

1. Sélectionnez **OK** pour confirmer votre sélection.

## <a name="scenario-2-reprint-labels-from-the-warehousing-app"></a>Scénario 2 : réimprimer des étiquettes à partir de l'application d'entreposage

Ce scénario s'applique généralement si un rouleau d'étiquettes a été perdu ou endommagé. Il illustre comment configurer les éléments de menu de l'appareil mobile qui permettront aux employés de réimprimer une ou plusieurs étiquettes. Il montre ensuite comment utiliser ces nouveaux éléments de menu pendant le travail sur un appareil mobile.

### <a name="set-up-the-required-menu-items-and-menu-for-the-mobile-device"></a>Configurer les éléments de menu et le menu requis pour l'appareil mobile

Avant que les employés puissent réimprimer des étiquettes à partir d'un appareil mobile, vous devez configurer des éléments de menu pour fournir cette fonctionnalité, puis ajouter ces éléments au menu de l'application d'entreposage.

#### <a name="create-new-mobile-device-menu-items"></a>Créer des options de menu d'appareil mobile

Suivez ces étapes pour créer une nouvelle collection d'éléments de menu pour la réimpression d'étiquettes à partir de l'application d'entreposage.

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d'appareil mobile**.
1. Créez une option de menu et définissez les valeurs suivantes pour elle :

    - **Nom de l'élément de menu :** *Réimprimer une seule étiquette de vague*
    - **Titre :** *Réimprimer une seule étiquette de vague*
    - **Mode :** *Indirect*
    - **Code d'activité :** *Réimprimer une seule étiquette de vague*

1. Créez une deuxième option de menu et définissez les valeurs suivantes pour elle :

    - **Nom de l'élément de menu :** *Réimprimer des étiquettes (article)*
    - **Titre :** *Réimprimer des étiquettes (article)*
    - **Mode :** *Indirect*
    - **Code d'activité :** *Réimprimer plusieurs étiquettes de vague*
    - **Afficher le filtre de regroupement de liste de travail :** *Oui*
    - **Champ de regroupement système :** *ShipmentID*
    - **Étiquette de regroupement système :** *ShipmentID*
    - **Mode d'impression :** *Produit*

1. Dans le volet Actions, sélectionnez **Liste de champs** pour ouvrir une page où vous pouvez sélectionner les champs qui seront affichés pour aider les employés à identifier le bon rouleau d'étiquettes.
1. Vous pouvez afficher jusqu'à sept champs. Utilisez les listes déroulantes pour sélectionner le champ qui s'affiche dans chaque position disponible. Laissez vides tous les champs dont vous n'avez pas besoin. 

    Voici un exemple :

    - **Champ affiché :** *LabelItemId*
    - **Champ affiché 2 :** *LabelItemName*
    - **Champ affiché 3 :** *InventQty*
    - **Champ affiché 4 :** *LabelUnitId*

1. Fermez la page.
1. Créez une troisième option de menu et définissez les valeurs suivantes pour elle :

    - **Nom de l'élément de menu :** *Réimprimer des étiquettes (Énumération)*
    - **Titre :** *Réimprimer des étiquettes de vague (Énumération)*
    - **Mode :** *Indirect**
    - **Code d'activité :** *Réimprimer plusieurs étiquettes de vague*
    - **Afficher le filtre de regroupement de liste de travail :** *Oui*
    - **Champ de regroupement système :** *ShipmentID*
    - **Étiquette de regroupement système :** *ShipmentID*
    - **Mode d'impression :** *Énumération*

1. Dans le volet Actions, sélectionnez **Liste de champs**, puis utilisez les listes déroulantes pour sélectionner les champs qui seront affichés pour aider les employés à identifier le bon rouleau d'étiquettes (par exemple, *LabelItemId*, *LabelItemName*, *InventQty*, *LabelUnitId* et *NumberOfLabels*).
1. Fermez la page.
1. Créez une quatrième option de menu et définissez les valeurs suivantes pour elle :

    - **Nom de l'élément de menu :** *Réimprimer des étiquettes (à partir de la dernière)*
    - **Titre :** *Réimprimer des étiquettes de vague (à partir de la dernière)*
    - **Mode :** *Indirect*
    - **Code d'activité :** *Réimprimer plusieurs étiquettes de vague*
    - **Afficher le filtre de regroupement de liste de travail :** *Oui*
    - **Champ de regroupement système :** *ShipmentID*
    - **Étiquette de regroupement système :** *ShipmentID*
    - **Mode d'impression :** *ID de la dernière bonne étiquette de vague*

1. Dans le volet Actions, sélectionnez **Liste de champs**, puis utilisez les listes déroulantes pour sélectionner les champs qui seront affichés pour aider les employés à identifier le bon rouleau d'étiquettes (par exemple, *LabelItemId*, *LabelItemName*, *InventQty*, *LabelUnitId* et *NumberOfLabels*).
1. Fermez la page.

#### <a name="set-up-the-mobile-device-menu"></a>Configurer le menu de l’appareil mobile

Suivez ces étapes pour ajouter vos nouveaux éléments de menu au menu de l'application d'entreposage.

1. Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d'appareil mobile**.
1. Sélectionnez un menu **Sortant** existant.
1. Dans la liste de gauche, recherchez les éléments du menu de réimpression que vous venez de créer, puis utilisez le bouton avec la flèche vers la droite pour les ajouter à la liste de droite.
1. Fermez la page.

### <a name="use-cases"></a>Cas d'utilisation

Les cas d'utilisation indiqués ici sont des illustrations de l'utilisation des divers éléments de menu de l'appareil mobile que vous avez configurés pour permettre aux employés de réimprimer des étiquettes de vague.

Avant de travailler sur ces cas d'utilisation, les conditions préalables suivantes doivent être en place :

- Les données de démonstration doivent être installées et vous devez sélectionner l'entité juridique **USMF**.
- L'impression d'étiquettes de vague doit être configurée et certaines étiquettes doivent être générées, comme décrit dans [Configurer l'impression d'étiquettes de vague](../warehousing/configure-wave-label-printing.md).

#### <a name="use-case-21-a-single-wave-label-is-scratched-and-must-be-reprinted"></a>Cas d'utilisation 2.1 : une seule étiquette de vague est rayée et doit être réimprimée.

1. Connectez-vous à l’application d’entreposage en tant qu’utilisateur ayant accès à l’entrepôt *62*. (Dans les données de démonstration standard, vous pouvez vous connecter en utilisant *62* comme ID d'utilisateur et *1* comme mot de passe.)
1. Accédez à **Sortant \> Réimprimer une seule étiquette de vague**.
1. Saisissez ou scannez l'ID d'étiquette de vague.
1. Sélectionnez l'imprimante sur laquelle réimprimer.
1. Sélectionnez **OK** pour confirmer l'action.

#### <a name="use-case-22-several-labels-for-boxes-of-the-same-item-were-damaged-and-must-be-reprinted-each-label-has-a-product-bar-code-but-no-enumeration-or-sscc-number"></a>Cas d'utilisation 2.2 : plusieurs étiquettes pour des boîtes d'un même article ont été endommagées et doivent être réimprimées. Chaque étiquette comporte un code-barres de produit, mais pas d'énumération ni de numéro SSCC.

1. Connectez-vous à l’application d’entreposage en tant qu’utilisateur ayant accès à l’entrepôt *62*. (Dans les données de démonstration standard, vous pouvez vous connecter en utilisant *62* comme ID d'utilisateur et *1* comme mot de passe.)
1. Accédez à **Sortant \> Réimprimer des étiquettes (article)**.
1. Saisissez ou scannez l'ID d'expédition.
1. Sélectionnez la vignette contenant le bon rouleau d'étiquettes à partir duquel réalisation la réimpression.
1. Scannez le code-barres du produit à partir d'une étiquette existante pour vérifier que la ligne correcte a été sélectionnée.
1. Entrez le nombre d'étiquettes à réimprimer.
1. Sélectionnez l'imprimante sur laquelle réimprimer.
1. Sélectionnez **OK** pour confirmer l'action.

#### <a name="use-case-23-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-because-the-labels-have-enumeration-you-can-define-the-carton-range-to-reprint"></a>Cas d'utilisation 2.3 : plusieurs étiquettes de boîtes n'ont pas été imprimées à cause d'un bourrage dans l'imprimante. Étant donné que les étiquettes ont une énumération, vous pouvez définir la plage de cartons à réimprimer.

1. Connectez-vous à l’application d’entreposage en tant qu’utilisateur ayant accès à l’entrepôt *62*. (Dans les données de démonstration standard, vous pouvez vous connecter en utilisant *62* comme ID d'utilisateur et *1* comme mot de passe.)
1. Accédez à **Sortant \> Réimprimer des étiquettes (Énumération)**.
1. Saisissez ou scannez l'ID d'expédition.
1. Sélectionnez la vignette contenant le bon rouleau d'étiquettes à partir duquel réalisation la réimpression.
1. Entrez le premier carton pour lequel réimprimer une étiquette.
1. Entrez le dernier carton pour lequel réimprimer une étiquette. Vous pouvez également laisser ce champ vide pour réimprimer les étiquettes de tous les cartons après le premier carton spécifié.
1. Sélectionnez l'imprimante sur laquelle réimprimer.
1. Sélectionnez **OK** pour confirmer l'action.

#### <a name="use-case-24-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-the-last-good-label-has-a-wave-label-id-that-is-printed-as-a-bar-code"></a>Cas d'utilisation 2.4 : plusieurs étiquettes de boîtes n'ont pas été imprimées à cause d'un bourrage dans l'imprimante. La dernière bonne étiquette a un ID d'étiquette de vague qui est imprimé sous forme de code-barres.

1. Connectez-vous à l’application d’entreposage en tant qu’utilisateur ayant accès à l’entrepôt *62*. (Dans les données de démonstration standard, vous pouvez vous connecter en utilisant *62* comme ID d'utilisateur et *1* comme mot de passe.)
1. Accédez à **Sortant \> Réimprimer des étiquettes (à partir de la dernière)**.
1. Saisissez ou scannez l'ID d'expédition.
1. Sélectionnez la vignette contenant le bon rouleau d'étiquettes à partir duquel réalisation la réimpression.
1. Saisissez ou scannez l'ID d'étiquette de vague de la dernière bonne étiquette de vague. L'application identifie l'étiquette suivante de la séquence comme le premier carton pour lequel une étiquette sera réimprimée.
1. Entrez le dernier carton pour lequel réimprimer une étiquette. Vous pouvez également laisser ce champ vide pour réimprimer les étiquettes de tous les cartons après le premier carton spécifié.
1. Sélectionnez l'imprimante sur laquelle réimprimer.
1. Sélectionnez **OK** pour confirmer l'action.

## <a name="scenario-3-short-pick-and-reprint"></a>Scénario 3 : prélèvement partiel et réimpression

Avant de travailler sur ce scénario, les conditions préalables suivantes doivent être en place :

- Les données de démonstration doivent être installées et vous devez sélectionner l'entité juridique **USMF**.
- L'impression d'étiquettes de vague doit être configurée et certaines étiquettes doivent être générées, comme décrit dans [Configurer l'impression d'étiquettes de vague](../warehousing/configure-wave-label-printing.md).

### <a name="set-up-work-exceptions"></a>Définir des exceptions de travail

Les exceptions de travail contrôlent le comportement du prélèvement partiel. Procédez comme suit pour configurer une exception de travail :

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Travail \> Exceptions de travail**.
1. Créez un enregistrement possédant les paramètres suivants :

    - **Code d'exception de travail :** *Prélèvement partiel et impression*
    - **Type d'exception :** *Prélèvement partiel*
    - **Suggérer la réimpression des étiquettes de vague :** *Oui*

### <a name="void-and-reprint-after-a-short-pick"></a>Annulation et réimpression après un prélèvement partiel

1. Connectez-vous à l’application d’entreposage en tant qu’utilisateur ayant accès à l’entrepôt *62*. (Dans les données de démonstration standard, vous pouvez vous connecter en utilisant *62* comme ID d'utilisateur et *1* comme mot de passe.)
1. Ouvrez un flux de traitement pour le travail de commande client qui a été créé lors de l'impression initiale des étiquettes de vague.
1. Sélectionnez **Prélèvement partiel**.
1. Sélectionnez le code d'exception de travail que vous avez créé pour ce scénario.
1. Si vous avez sélectionné l'exception correcte, la case à cocher **Annulation et réimpression** doit être disponible. Cochez cette case et confirmez. Une fois l'opération confirmée, la séquence de rouleau d'étiquettes identifiée par le champ **ID de build d'étiquette** est recalculée en fonction de la quantité de la ligne de travail modifiée. Elle est ensuite réimprimée sur l'imprimante spécifiée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]