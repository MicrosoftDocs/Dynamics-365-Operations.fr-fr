---
title: Codes-barres GS1 et codes QR
description: Cette rubrique décrit comment configurer les codes-barres GS1 et les codes QR afin que les étiquettes puissent être scannées dans un entrepôt.
author: Mirzaab
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ef28fcaf308225a78bcbac42f591e6b24b21b1b1
ms.sourcegitcommit: 2b04b5a5c883d216072bb91123f9c7709a41f69a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2021
ms.locfileid: "7384535"
---
# <a name="gs1-bar-codes-and-qr-codes"></a>Codes-barres GS1 et codes QR

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Les employés d'entrepôt doivent souvent effectuer plusieurs tâches lorsqu'ils utilisent un lecteur d'appareil mobile pour enregistrer les mouvements d'un article, d'une palette ou d'un conteneur. Ces tâches peuvent inclure à la fois la lecture de codes-barres et la saisie manuelle d'informations sur l'appareil mobile. Les codes-barres utilisent un format spécifique à l'entreprise que vous définissez et gérez à l'aide de Microsoft Dynamics 365 Supply Chain Management.

Les formats de codes-barres GS1 et de codes QR pour les étiquettes d'expédition ont été développés pour fournir une norme mondiale pour l'échange de données entre les entreprises. Les formats GS1 encodent non seulement les données, mais vous permettent également d'utiliser une liste prédéfinie d'*identificateurs d'application* pour définir la signification des données. La norme GS1 définit le format des données et les différents types de données qui peuvent être utilisés pour encoder. Contrairement aux anciens codes-barres, les codes-barres GS1 peuvent avoir plusieurs éléments de données. Par conséquent, une seule lecture de code-barres peut capturer plusieurs types d'informations sur le produit, telles que le lot et la date d'expiration.

La prise en charge de GS1 dans Supply Chain Management simplifie considérablement le processus de lecture dans les entrepôts où les palettes et les conteneurs sont étiquetés à l'aide de codes au format GS1. Les employés d'entrepôt peuvent extraire toutes les informations requises grâce à une simple lecture d'un code-barres GS1. En éliminant le besoin de faire plusieurs lectures et/ou de saisir manuellement des informations, les codes-barres GS1 aident à réduire le temps associé aux tâches. Dans le même temps, ils contribuent également à améliorer la précision.

Les responsables logistiques doivent configurer la liste requise d'identificateurs d'application et associer chacun d'eux aux éléments de menu appropriés de l'appareil mobile. Les identificateurs d'application peuvent ensuite être utilisés dans les entrepôts en tant que paramètre global à des fins de déplacement et d'emballage. Par conséquent, toutes les étiquettes d'expédition prendront une forme unifiée.

Sauf indication contraire, cette rubrique utilise le terme *code-barres* pour faire référence à la fois aux codes à barres et aux codes QR.

## <a name="turn-on-the-gs1-feature"></a>Activer la fonctionnalité GS1

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Scanner les codes-barres GS1*

## <a name="set-up-global-gs1-options"></a>Configurer les options GS1 globales

La page **Paramètres de gestion des entrepôts** fournit quelques paramètres qui établissent les options GS1 globales.

Pour paramétrer les options GS1 globales, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Paramètres de gestion des entrepôts**.
1. Dans le raccourci **Codes-barres**, définissez les champs suivants :

    - **Caractère FNC1** – Spécifiez les caractères qui doivent être interprétés comme préfixe lors de l'analyse d'un code-barres.
    - **Caractère Datamatrix** – Spécifiez les caractères qui doivent être interprétés comme préfixe lors de l'analyse d'une matrice de données.
    - **Caractère Code QR** – Spécifiez les caractères qui doivent être interprétés comme préfixe lors de l'analyse d'un code QR.
    - **Séparateur de groupe** – Spécifiez le caractère qui identifie les parties distinctes d'un code-barres ou d'un code QR.
    - **Longueur maximale de l'identificateur** – Spécifiez le nombre maximal de caractères autorisé pour l'identificateur de l'application.

> [!NOTE]
> Les préfixes indiquent au système qu'un code-barres est crypté selon la norme GS1. Jusqu'à trois préfixes (**Caractère FNC1**, **Caractère Datamatrix** et **Caractère Code QR**) peuvent être utilisés simultanément et à diverses fins.

## <a name="gs1-application-identifiers"></a>Identificateurs d’application de GS1

Les formats GS1 encodent non seulement les données, mais vous permettent également d'utiliser une liste prédéfinie d'identificateurs d'application pour définir la signification des données. Les responsables logistiques doivent configurer la liste requise d'identificateurs d'application et associer chacun d'eux aux éléments de menu appropriés de l'appareil mobile. Les identificateurs peuvent ensuite être utilisés dans les entrepôts en tant que paramètre global à des fins de déplacement et d'emballage. Par conséquent, toutes les étiquettes d'expédition prendront une forme unifiée.

Le système utilise les données, en particulier les identificateurs d'application prédéfinis, pour établir les règles qui doivent être appliquées à l'information scannée pertinente.

Chaque identificateur d'application signale au système que les caractères suivants dans le code-barres scanné doivent être considérés comme un bloc d'informations cryptées. La configuration des identificateurs d'application définit comment le système doit interpréter un code-barres et l'enregistrer en tant que valeur dans le système.

Les responsables logistiques peuvent utiliser les identificateurs d'application internationaux standard et/ou créer les leurs.

### <a name="load-the-standard-application-identifiers"></a>Charger les identificateurs d'application standard

Pour démarrer rapidement, vous pouvez charger une liste d'identificateurs d'applications internationaux courants. Vous pouvez ensuite étendre ou modifier la liste ultérieurement, selon vos besoins.

Pour charger les identificateurs d'application standard, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> GS1 \> Identificateurs d'application GS1**.
1. Dans le volet Actions, sélectionnez **Créer une configuration par défaut**.

> [!WARNING]
> La commande **Créer une configuration par défaut** supprime tous les identificateurs d'application actuellement définis et les remplace par la liste standard. Cependant, après avoir chargé la configuration par défaut, vous pouvez personnaliser la liste selon vos besoins.

### <a name="set-up-custom-application-identifiers"></a>Configurer des identificateurs d'application personnalisés

Si certains ou tous les identificateurs d'application utilisés par votre entreprise diffèrent de l'ensemble standard, vous pouvez créer vos propres codes à partir de zéro ou personnaliser l'ensemble standard selon vos besoins.

Pour configurer et personnaliser vos propres identificateurs d'application GS1, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> GS1 \> Identificateurs d'application GS1**.
1. Utilisez l’une des procédures suivantes :

    - Pour créer un identificateur, dans le volet Action, sélectionnez **Nouveau**.
    - Pour modifier un identificateur existant : Sélectionnez l'identificateur, puis, dans le volet Actions, sélectionnez **Modifier**.

1. Définissez les champs suivants pour le nouvel identificateur ou l'identificateur sélectionné :

    - **Identificateur d'application** – Saisissez le code d'identification de l'identificateur d'application. Typiquement, ce code est un entier à deux chiffres, mais il peut être plus long. Pour les valeurs décimales, le dernier chiffre indique le nombre de décimales. Pour plus d'informations, consultez la description de la case à cocher **Décimale** plus loin dans cette liste.
    - **Description** – Permet d'entrer une brève description de l'identificateur.
    - **Longueur fixe** – Cochez cette case si les valeurs analysées à l'aide de cet identificateur d'application ont un nombre fixe de caractères. Décochez cette case si la longueur des valeurs est variable. Dans ce cas, vous devez indiquer la fin de la valeur en utilisant le caractère séparateur de groupe que vous avez spécifié sur la page **Paramètres de gestion des entrepôts**.
    - **Longueur** – Saisissez le nombre maximal de caractères pouvant apparaître dans les valeurs analysées à l'aide de cet identificateur d'application. Si la case **Longueur fixe** est cochée, exactement ce nombre de caractères est attendu.
    - **Type** – Sélectionnez le type de valeur qui est scanné à l'aide de cet identificateur d'application (*Numérique*, *Alphanumérique* ou *Date*). Pour les dates, le format attendu est AAMMJJ (sans espaces ni tirets).
    - **Décimale** – Cochez cette case si la valeur comprend un point décimal implicite. Si cette case est cochée, le système utilisera le dernier chiffre de l'identificateur de l'application pour déterminer le nombre de décimales. Par exemple, si l'identificateur de l'application est *3205*, les cinq chiffres les plus à droite de la valeur seront interprétés comme venant après la virgule.

> [!NOTE]
> Le séparateur de groupe qui est spécifié sur la page **Paramètres de gestion des entrepôts** est facultatif si une valeur suivie d'un identificateur d'application a une longueur fixe, ou si sa longueur est maximisée (c'est-à-dire si la longueur est égale à la valeur **Longueur** définie pour l'identificateur de l'application).

## <a name="establish-the-generic-gs1-setup"></a>Établir la configuration GS1 générique

La configuration GS1 générique établit une collection de mappages communs. Ces mappages font correspondre chaque champ de saisie pertinent de l'application mobile à l'identificateur d'application qui contrôle la manière dont les valeurs des codes-barres scannés doivent être interprétées et stockées dans ce champ. Par défaut, ces paramètres s'appliquent à tous les scans pour tous les éléments de menu de l'appareil mobile. Cependant, ils peuvent être écrasés pour un ou plusieurs champs spécifiques par une stratégie GS1 affectée à un élément de menu spécifique.

La configuration GS1 générique ne permet de scanner qu'une seule valeur à la fois. Par conséquent, si vous souhaitez charger plusieurs valeurs de champ à partir d'un seul scan, vous devez configurer une stratégie GS1 pour les éléments de menu pertinents.

Pour plus d'informations sur les stratégies GS1, consultez la section suivante.

### <a name="load-the-standard-generic-gs1-setup"></a>Charger la configuration GS1 générique standard

La page **Configuration GS1 générique** vous permet de charger un ensemble standard de mappages entre les champs d'appareil mobile et les identifiants d'application standard créés par la configuration par défaut.

Pour établir la configuration GS1 générique, allez dans **Gestion des entrepôts \> Paramétrage \> GS1 \> Configuration générique GS1**. Sélectionnez ensuite **Créer une configuration par défaut** pour attribuer automatiquement un identificateur d'application approprié à chaque champ généralement utilisé par les éléments de menu de l'appareil mobile.

> [!WARNING]
> Si une configuration GS1 générique existe déjà, la commande **Créer une configuration par défaut** la supprime complètement et charge la configuration standard.

### <a name="customize-the-standard-generic-gs1-setup"></a>Personnaliser la configuration GS1 générique standard

Pour personnaliser la configuration GS1 générique, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> GS1 \> Configuration générique GS1**.
1. Utilisez l’une des procédures suivantes :

    - Pour créer un mappage : dans le volet Actions, sélectionnez **Nouveau**.
    - Pour modifier un mappage existant : Sélectionnez le mappage, puis, dans le volet Actions, sélectionnez **Modifier**.

1. Définissez les champs suivants pour le nouveau mappage ou le mappage sélectionné :

    - **Champ** – Sélectionnez ou entrez le champ de saisie de l'application mobile auquel la valeur entrante doit être affectée. La valeur n'est pas le nom d'affichage que les travailleurs voient. Au lieu de cela, c'est le nom de clé qui est attribué au champ dans le code sous-jacent. La configuration par défaut fournit une collection de champs susceptibles d'être utiles et comprend des noms de clé intuitifs pour chaque champ et la fonctionnalité programmée correspondante. Cependant, vous devrez peut-être parler à vos partenaires de développement pour trouver les bonnes sélections pour votre implémentation.
    - **Identificateur d'application** – Sélectionnez l'identificateur d'application applicable, tel que défini sur la page **Identificateurs d'application GS1**. L'identificateur établit comment le code-barres sera interprété et stocké en tant que valeur pour le champ nommé. Une fois que vous avez sélectionné un identificateur d'application, le champ **Description** affiche la description de celui-ci.

## <a name="set-up-gs1-policies-that-you-can-assign-to-mobile-device-menu-items"></a>Configurer des stratégies GS1 que vous pouvez attribuer aux éléments de menu d'appareil mobile

L'objectif de la norme GS1 est de permettre aux travailleurs de charger plusieurs valeurs lorsqu'ils scannent un seul code-barres une seule fois. Pour atteindre cet objectif, les responsables logistiques doivent mettre en place des stratégies GS1 qui indiquent au système comment interpréter les codes-barres à valeurs multiples. Plus tard, vous pouvez affecter des stratégies aux éléments de menu d'appareil mobile pour contrôler la façon dont un code-barres sera interprété lorsque les travailleurs le scannent pendant qu'ils utilisent un élément de menu spécifique.

Si aucune stratégie GS1 n'est affectée à un élément de menu, le système ne peut capturer qu'une seule valeur. Cette valeur est appliquée à l'entrée de l'application mobile qui est sélectionnée lorsque le travailleur effectue l'analyse, comme spécifié par la configuration GS1 générique. Si une stratégie GS1 est affectée à l'élément de menu, le système utilise toujours la configuration générique GS1 pour mapper la première valeur de code-barres au champ sélectionné. Cependant, il peut ensuite capturer des valeurs de champ supplémentaires, comme spécifié par la stratégie applicable.

### <a name="load-the-standard-specific-gs1-policies"></a>Charger les stratégies GS1 spécifiques standard

Pour démarrer rapidement, vous pouvez charger un ensemble de stratégies GS1. Vous pouvez ensuite étendre ou modifier les stratégies ultérieurement, selon vos besoins.

Pour charger les identificateurs d'application standard, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> GS1 \> Stratégie GS1**.
1. Dans le volet Actions, sélectionnez **Créer une configuration par défaut**.

> [!WARNING]
> La commande **Créer une configuration par défaut** supprime toutes les stratégies actuellement définies et les remplace par la liste standard de stratégies. Cependant, une fois la configuration par défaut chargé, vous pouvez personnaliser les stratégies selon vos besoins.

### <a name="set-up-custom-specific-gs1-policies"></a>Configurer des stratégies GS1 spécifiques standard

Pour configurer et personnaliser vos stratégies GS1, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> GS1 \> Stratégie GS1**.
1. Utilisez l’une des procédures suivantes :

    - Pour créer une stratégie : dans le volet Actions, sélectionnez **Nouveau**.
    - Pour modifier une stratégie existante, sélectionnez la stratégie dans le volet de liste.

1. Dans l’en-tête de la nouvelle stratégie ou de la stratégie sélectionnée, définissez les champs suivants :

    - **Nom de la stratégie** – Permet d'entrer un nom de stratégie.
    - **Description** – Permet d'entrer une brève description de la stratégie.

1. Dans le raccourci sous l'en-tête, mappez les noms de champ aux identificateurs d'application comme requis pour la stratégie actuelle. Utilisez les boutons de la barre d’outils pour ajouter et supprimer des lignes selon vos besoins. Pour chaque ligne, définissez les champs suivants :

    - **Champ** – Sélectionnez ou entrez le champ de saisie de l'application mobile auquel la valeur entrante doit être affectée. La valeur n'est pas le nom d'affichage que les travailleurs voient. Au lieu de cela, c'est le nom de clé qui est attribué au champ dans le code sous-jacent. La configuration par défaut fournit une collection de champs susceptibles d'être utiles et comprend des noms de clé intuitifs pour chaque champ et la fonctionnalité programmée correspondante. Cependant, vous devrez peut-être parler à vos partenaires de développement pour trouver les bonnes sélections pour votre implémentation.
    - **Identificateur d'application** – Sélectionnez l'identificateur d'application applicable, tel que défini sur la page **Identificateurs d'application GS1**. L'identificateur établit comment le code-barres sera interprété et stocké en tant que valeur pour le champ nommé. Une fois que vous avez sélectionné un identificateur d'application, le champ **Description** affiche la description de celui-ci.
    - **Tri** – Chaque code-barres multi-valeurs comprend une série d'identificateurs d'application, chacun étant suivi d'une valeur. La stratégie GS1 applicable identifie quel identificateur d'application est mappé à chaque champ de base de données. Cependant, si un code à barres utilise le même identificateur d'application plus d'une fois, le système utilise l'ordre dans lequel les identificateurs d'application apparaissent dans le code pour les mapper aux champs. Pour les lignes qui partagent un identificateur d'application avec une ou plusieurs autres lignes, utilisez ce champ pour établir l'ordre dans lequel les lignes correspondantes sont traitées. La ligne qui a la valeur de tri la plus basse sera traitée en premier.

> [!NOTE]
> Pour les codes-barres qui incluent plusieurs identificateurs d'application identiques, vous *devez* utiliser le champ **Tri** pour établir l'ordre des champs.

## <a name="assign-gs1-policies-to-mobile-device-menu-items"></a>Attribuer des stratégies GS1 aux éléments de menu des appareils mobiles

Par défaut, tous les éléments de menu des appareils mobiles fournissent des champs de saisie dans lesquels les travailleurs peuvent scanner une seule valeur, conformément à la configuration GS1 générique. Si vous souhaitez que les travailleurs puissent scanner plus d'une valeur de champ dans une seule analyse pour n'importe quel élément de menu d'appareil mobile, vous devez affecter une stratégie GS1 en procédant comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Créez ou ouvrez un élément de menu.
1. Sur le raccourci **Général**, définissez le champ **Stratégie GS1** sur la stratégie qui s'applique à l'élément de menu.

## <a name="gs1-setup-example"></a>Exemple de configuration GS1

Cet exemple s'applique à un système où les options GS1 sont configurées de la manière suivante :

- Sur la page **Paramètres de gestion des entrepôts**, les paramètres globaux suivants sont définis :

  - **Caractère FNC1 :** *\]C1*
  - **Séparateur de groupe :** *\~*

- Sur la page **Identificateurs d'application GS1**, les identificateurs d'application suivants sont pertinents pour cet exemple.

    | Identificateur d’application | Description  | Longueur fixe | Longueur | Type | Décimal |
    |---|---|---|---|---|---|
    | 01 | GTIN | Sélectionnée | 14 | Numérique | Compensé |
    | 10 | Numéro du lot | Compensé | 20 | Alphanumérique | Compensé |
    | 17 | Date d’expiration | Sélectionnée | 6 | Date | Compensé |
    | 30 | Quantité de réception | Compensé | 8 | Numérique | Compensé |

- Sur la page **Configuration générique GS1**, les paramètres suivants pour la stratégie GS1 générique sont pertinents pour cet exemple.

    | Champ | Identificateur d’application | Description  |
    |---|---|---|
    | ItemId | 01 | GTIN |

- Sur la page **Stratégie GS1**, il y a une stratégie où le champ **Nom de la stratégie** est défini sur *Réception d'achat*. Cette stratégie inclut les lignes suivantes :

    | Champ | Identificateur d’application | Description  | Tri |
    |---|---|---|---|
    | ExpDate | 17 | Date d’expiration | 0 |
    | InventBatchId | 10 | Numéro du lot | 0 |
    | Qté | 30 | Quantité de réception | 0 |

- Sur la page **Éléments de menu d'appareil mobile**, il y a un élément de menu nommé *Réception d'achat*. Son champ **Stratégie GS1** est défini sur *Réception d'achat*.

Une fois que les marchandises pour une commande fournisseur arrivent à l'entrepôt, le travailleur suit ces étapes.

1. Sur l'appareil mobile, sélectionnez l'élément de menu **Réception d'achat**.
1. Entrez le numéro de la commande fournisseur.
1. Sélectionnez le champ **Article** et scannez le code-barres suivant : *\]C10100000012345678\~3030\~10b1\~17220215*.

En raison des paramètres définis pour cet exemple, le système analyse le code-barres scanné de la manière suivante.

| Clé de champ | ID d’application | Valeur  | Note |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Parce que le travailleur a scanné dans le champ **Article**, la première valeur du code-barres est mappée sur ce champ. Le mappage est tiré de la configuration générique GS1. |
| Qté | 30 | 30 | Étant donné que plusieurs valeurs de champ sont capturées en une seule analyse, ce mappage et tous les mappages restants sont extraits de la stratégie GS1 qui est affectée à l'élément de menu **Réception d'achat**. Cette valeur est la quantité qui a été reçue. |
| InventBatchId | 10 | b1 | Cette valeur est l'ID de lot. |
| ExpDate | 17 | 220215 | Le format de date est AAMMJJ. Par conséquent, la date d'expiration est le 15 février 2022. |

Le reçu est ensuite enregistré et les valeurs de base de données pertinentes sont saisies après l'analyse unique.
