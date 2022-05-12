---
title: Codes-barres GS1
description: Cette rubrique décrit comment configurer les codes-barres GS1 et les codes QR afin que les étiquettes puissent être scannées dans un entrepôt.
author: Mirzaab
ms.date: 03/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: ea928bc8a020035adb36ae2e7873c656e8c3985d
ms.sourcegitcommit: 1050e58e621d9a0454895ed07c286936f8c03320
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2022
ms.locfileid: "8625276"
---
# <a name="gs1-bar-codes"></a>Codes-barres GS1

[!include [banner](../includes/banner.md)]

Les employés d’entrepôt doivent souvent effectuer plusieurs tâches quand  ils utilisent un lecteur d’appareil mobile pour enregistrer les mouvements d’un article, d’une palette ou d’un conteneur. Ces tâches peuvent inclure à la fois la lecture de codes-barres et la saisie manuelle d’informations sur l’appareil mobile. Les codes-barres utilisent un format spécifique à l’entreprise que vous définissez et gérez à l’aide de Microsoft Dynamics 365 Supply Chain Management.

Les formats de codes-barres GS1 pour les étiquettes d’expédition ont été développés pour fournir une norme mondiale pour l’échange de données entre les entreprises. Ils sont disponibles dans les symbologies linéaires (1D) (formats de code-barres), telles que GS1-128, et les symbologies 2D, telles que les codes GS1 DataMatrix et les codes QR GS1. Les codes-barres GS1 encodent non seulement les données, mais vous permettent également d’utiliser une liste prédéfinie d’*identifiants d’application* pour définir la signification des données. La norme GS1 définit le format des données et les différents types de données qui peuvent être utilisés pour encoder. Contrairement aux anciens codes-barres standards, les codes-barres GS1 peuvent avoir plusieurs éléments de données. Par conséquent, une seule lecture de code-barres peut capturer plusieurs types d’informations sur le produit, telles que le lot et la date d’expiration.

La prise en charge du format GS1 dans Supply Chain Management simplifie considérablement le processus de lecture dans les entrepôts où les palettes et les conteneurs sont étiquetés à l’aide de codes-barres au format GS1. Les employés d’entrepôt peuvent extraire toutes les informations requises grâce à une simple lecture d’un code-barres GS1. En éliminant le besoin de faire plusieurs lectures et/ou de saisir manuellement des informations, les codes-barres GS1 aident à réduire le temps associé aux tâches. Dans le même temps, ils contribuent également à améliorer la précision.

Les responsables logistiques doivent configurer la liste requise d’identificateurs d’application et associer chacun d’eux aux éléments de menu appropriés de l’appareil mobile. Les identificateurs d’application peuvent ensuite être utilisés dans les entrepôts en tant que paramètre global à des fins de déplacement et d’emballage. Par conséquent, toutes les étiquettes d’expédition prendront une forme unifiée.

Sauf indication contraire, cette rubrique utilise le terme *code-barres* pour faire référence à la fois aux codes-barres linéaires (1D) et aux codes-barres 2D.

## <a name="the-gs1-bar-code-format"></a>Le format de code à barres GS1

Les Spécifications générales GS1 spécifient quelles symbologies peuvent être utilisées pour les codes à barres GS1 et comment encoder les données dans le code à barres. Cette section fournit une brève introduction au sujet. Pour tous les détails, consultez les [Spécifications générales GS1](https://www.gs1.org/docs/barcodes/GS1_General_Specifications.pdf) qui sont publiées par GS1. Le document des spécifications GS1 est régulièrement mis à jour et les informations qu’il fournit sont à jour avec la version 22.0 des spécifications générales de GS1.

Les codes-barres GS1 utilisent les symbologies suivantes :

- **Codes à barres linéaires ou 1D** : GS1-128 et GS1 DataBar
- **Codes-barres 2D** : GS1 DataMatrix, GS1 QR Code et GS1 Dotcode

Notez qu’il existe des mentions spéciales de GS1 dans GS1-128, qui est un cas particulier du code à barres linéaire Code-128 ordinaire, GS1 DataMatrix et GS1 QR Code. La différence entre la version GS1 et la version non GS1 est la présence d’un caractère spécial (FNC1) comme premier caractère dans les données du code à barres. La présence d’un caractère FNC1 indique que les données du code à barres doivent être interprétées conformément à la spécification GS1.

Les données dans le code à barres lui-même se composent de plusieurs éléments de données, dont chacun est identifié par un identifiant d’application au début du champ. Habituellement, les données sont également présentées sous le code à barres dans un format lisible par l’homme, où l’identifiant de l’application est indiqué entre parenthèses. Voici un exemple : `(01) 09521101530001 (17) 210119 (10) AB-123`. Ce code-barres contient trois éléments :

- **Identifiant d’application 01** : le numéro d’article de commerce international (GTIN) GS1 de l’article.
- **Idientifiant d’application 17** : la date d’expiration.
- **Identifiant d’application 10** : le numéro de lot.

Pour chaque élément, les données peuvent avoir une longueur prédéfinie ou une longueur variable. Il existe une liste fixe d’identifiants d’application qui ont des longueurs prédéfinies. Tous les autres identifiants d’application ont une longueur variable, et la liste des identifiants d’application GS1 spécifie la longueur maximale et le format des données. Par exemple, l’identifiant d’application 01 a une longueur prédéfinie de 16 caractères (deux pour l’identifiant d’application lui-même, puis 14 pour le GTIN), et l’identifiant d’application 17 a une longueur prédéfinie de huit caractères (deux pour l’identifiant d’application lui-même, puis six pour la date). Cependant, l’identifiant d’application 10 a deux chiffres pour l’identifiant d’application lui-même, puis jusqu’à 20 caractères alphanumériques.

Quand des éléments sont assemblés, si un élément suit un élément de longueur variable, un caractère séparateur doit être utilisé. Ce séparateur peut être soit le caractère spécial FNC1, soit le caractère séparateur de groupe (un caractère non imprimable qui a le code ASCII 29 et le code hexadécimal 1D). Le séparateur ne doit pas être utilisé après le dernier élément. Bien que le séparateur ne doive pas non plus être utilisé après des éléments qui ont une longueur prédéfinie, sa présence n’est pas une erreur critique.

Dans les données de code à barres de l’exemple précédent d’un code à barres contenant les identifiants d’application 01, 17 et 10, les données d’un symbole Code-128, QR Code ou DataMatrix seront codées sous la forme `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` (les identifiants d’application sont indiqués en gras). Il est recommandé que tout élément de longueur variable soit placé à la fin, pour éliminer le besoin d’un caractère séparateur de groupe supplémentaire. Cependant, le code à barres peut également avoir un ordre différent des éléments, où le séparateur est obligatoire. Voici un exemple : `<FNC1>`**`01`**`09521101530001`**`10`**`AB-123<GS>`**`17`**`210119`.

### <a name="dates-and-decimal-numbers"></a>Dates et nombres décimaux

Les dates sont toujours représentées sous le format *AAMMJJ*, où le siècle de l’année est déterminé par les spécifications GS1. Seules les dates comprises entre 49 ans dans le passé et 50 ans dans le futur (par rapport à l’année en cours) peuvent être représentées.

Certains éléments de données contiennent des nombres décimaux. Par exemple, les identifiants d’application 3100, 3101, ... 3105 représentent un poids net en kilogrammes. Étant donné que ces identifiants d’application ont une longueur prédéfinie de 10, six chiffres sont disponibles pour la quantité. La position de la virgule décimale est spécifiée par le dernier chiffre de l’identifiant de l’application. Par conséquent, cette famille d’identifiants d’application peut également être représentée comme *310n*. Étant donné que la norme GS1 spécifie qu’il doit toujours y avoir au moins un chiffre à gauche de la virgule décimale, un maximum de cinq décimales est autorisé.

Voici quelques exemples qui montrent comment le nombre *123456* sera interprété par différents identifiants d’application (en gras) :

- **`3100`**`123456` &rarr; 123456 (entier)
- **`3101`**`123456`&rarr; 12345,6 (une décimale)
- **`3102`**`123456`&rarr; 1234,56 (deux décimales)
- **`3103`**`123456` &rarr; 123,456 (trois décimales)
- **`3104`**`123456`&rarr; 12,3456 (quatre décimales)
- **`3105`**`123456` &rarr; 1,23456 (cinq décimales)

## <a name="scanning-gs1-bar-codes-in-supply-chain-management"></a>Lecture des codes-barres GS1 dans Supply Chain Management

Pour scanner les codes-barres GS1, les magasiniers utilisent un scanner intégré ou connecté à un appareil mobile. Le scanner transmet ensuite le code-barres scanné à l’application mobile Warehouse Management sous la forme d’une série d’événements clavier. Ce mode de fonctionnement est également connu sous le nom de *clavier wedge* ou *wedge*. L’application mobile envoie ensuite le texte reçu tel quel à Supply Chain Management. Quand le système reçoit des données d’entrée, il détermine d’abord si les données commencent par l’un des préfixes configurés qui indiquent que les données sont en fait un code à barres GS1 (voir la section [Configurer les options globales de GS1](#set-gs1-options)). Si les données scannées commencent par l’un de ces préfixes, le système utilise un analyseur GS1 pour analyser les données et extraire les éléments de données individuels en fonction de leurs identifiants d’application. Une fois les données analysées, le champ de saisie actuel ou plusieurs champs seront remplis avec les données lues.

### <a name="configuration-of-bar-code-scanner-hardware-and-software"></a>Configuration du matériel et du logiciel du lecteur de codes à barres

Pour que Supply Chain Management reconnaisse et décode correctement les codes-barres GS1, le scanner matériel ou le logiciel qui le prend en charge doit être configuré pour effectuer les actions suivantes :

- Ajoutez un préfixe aux codes-barres scannés, afin que le système puisse reconnaître un code-barres GS1.
- Convertissez le caractère ASCII de séparation de groupe non imprimable (code ASCII 29 ou code hexadécimal 1D) en un caractère imprimable, tel qu’un tilde (~).

Bien que vous puissiez ajouter n’importe quel préfixe au code-barres scanné, une option consiste à ajouter un identifiant de symbologie ISO/IEC 15424, également appelé *Identifiant AIM*. Cet identifiant à trois caractères commence par `]`, a ensuite un caractère qui identifie la symbologie utilisée, puis a un nombre qui est utilisé comme modificateur supplémentaire. Par exemple, l’identifiant AIM `]C1` spécifie un code à barres Code 128 (en raison du caractère `C`), et le modificateur `1` spécifie qu’il y a un caractère FNC1 en première position des données. D’autre part, `]C0` est un code à barres Code 128 qui a n’importe quel autre caractère comme premier caractère des données.

Les cinq identifiants de symbologie suivants correspondent aux codes à barres GS1 qui ont des éléments d’identifiant d’application :

- `]C1` – Code 128 (`C`) avec le caractère FNC1 en première position (`1`), également connu sous le nom de GS1-128.
- `]e0` – GS1 DataBar.
- `]d2` – DataMatrix (`d`) avec ECC 200 et FNC1 en première position (`2`), également connu sous le nom de GS1 DataMatrix.
- `]Q3` – Symbole de QR Code (`Q`) Modèle 2 avec FNC1 en première position (`3`), également connu sous le nom de QR Code GS1.
- `]J1` – GS1 DotCode.

Si vous utilisez ces identifiants, la compatibilité avec les codes à barres non GS1 nécessite que les scanners ou le logiciel de numérisation soient configurés pour supprimer tous les identifiants qui ne correspondent pas aux identifiants GS1. Par exemple, si vous scannez un code-barres Code 39 « normal », le préfixe `]A0` sera ajouté. Comme le système ne comprendra pas ce préfixe comme l’un des préfixes GS1, il l’interprétera comme une donnée et produira des résultats inattendus.

> [!NOTE]
> Pour plus de commodité, les versions 2.0.17.0 et ultérieures de l’application mobile Warehouse Management supprimeront tous les préfixes AIM qui ne sont pas inclus dans la liste précédente. Ce comportement prend en charge les cas où vous pouvez configurer le scanner pour ajouter le préfixe AIM mais pas pour supprimer les préfixes indésirables.

### <a name="single-and-multiple-field-scanning"></a>Lecture d’un champ et de plusieurs champs

Une fois les données analysées à partir du code-barres, elles sont introduites dans les contrôles de flux de l’appareil mobile. Il existe deux méthodes qui seront traitées tour à tour :

- **Lecture d’un seul champ** : cette méthode ne remplit que le champ dans lequel le code-barres a été scanné. Par exemple, si vous scannez le code-barres `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` alors que le curseur est dans le champ **Article**, le GTIN `09521101530001` du code-barres sera saisi dans ce champ. Si vous scannez le même code-barres alors que le curseur est dans le champ **ID Lot**, le numéro de lot `AB-123` du code-barres sera saisi. Ce mode fonctionne pour tous les champs dans tous les flux et nécessite uniquement que la configuration générique GS1 soit configurée. Si un code-barres contient plusieurs éléments, il doit tout de même être scanné plusieurs fois, car une seule partie du code-barres à la fois sera saisie dans le flux de l’appareil mobile. Ce comportement est contrôlé par la configuration générique GS1, comme décrit dans la section [Établir la configuration GS1 générique](#generic-gs1-setup).
- **Lecture de plusieurs champs** : cette méthode remplit plusieurs champs quand un code-barres est scanné, en envoyant les données supplémentaires dans l’état de flux de l’appareil mobile. Par exemple, la stratégie est configurée pour envoyer l’identifiant d’application 01 dans le contrôle `ItemId` et l’identifiant d’application 10 dans le champ `InventBatchId`. Dans ce cas, si vous scannez le code-barres `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123`, les données des deux variables seront envoyées en même temps. Par conséquent, le système ne vous demandera pas l’article et/ou le numéro de lot dans le flux. Ce comportement est contrôlé par les stratégies GS1 qui sont liées aux éléments de menu, comme décrit dans la section [Configurer des stratégies GS1 à attribuer aux éléments de menu de l’appareil mobile](#policies-for-menus).

> [!WARNING]
> Les stratégies GS1 par défaut ont été testées pour fonctionner sans comportement inattendu. Cependant, la personnalisation des stratégies GS1 liées aux éléments de menu peut entraîner un comportement inattendu, car le flux peut ne pas s’attendre à ce que certaines données soient disponibles à un moment donné.

## <a name="turn-on-the-gs1-feature"></a>Activer la fonctionnalité GS1

Pour pouvoir utiliser cette fonctionnalité, vous devez l’activer dans le système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Scanner les codes-barres GS1*

### <a name="turn-on-the-enhanced-parser-for-gs1-barcodes-feature"></a>Activer la fonctionnalité Analyseur amélioré pour les codes-barres GS1

Si vous utilisez des codes-barres GS1, nous vous recommandons d’activer également la fonctionnalité *Analyseur amélioré pour les codes-barres GS1*. Cette fonctionnalité fournit une implémentation améliorée de l’analyseur de code-barres GS1. Elle apporte les améliorations suivantes :

- Elle suit l’algorithme des spécification générale GS1 pour l’analyse des données de symbole et vérifie que les données du symbole sont conformes à la spécification.
- Elle ne vous oblige pas à configurer une valeur **Longueur maximale de l’identifiant** et utilise la correspondance de préfixe la plus longue à partir des identifiants d’application configurés.
- Elle vous permet de configurer plus facilement les identifiants d’application décimaux en utilisant la lettre *n* pour correspondre à n’importe quel nombre. Par exemple, vous pouvez configurer un seul identifiant d’application (*310n*) au lieu d’identifiants d’application distincts (*3101*, *3102*, *3103*, etc).
- Elle corrige un problème où des données mal codées sont interprétées comme des données de champ.
- Elle est assortie d’une classe distincte qui peut être réutilisée dans d’autres contextes et permet d’utiliser un point d’extensibilité pour manipuler les données numérisées avant que les champs de flux ne soient remplis.

## <a name="set-up-global-gs1-options"></a><a name="set-gs1-options"></a>Configurer les options GS1 globales

La page **Paramètres de gestion des entrepôts** fournit quelques paramètres qui établissent les options GS1 globales.

Pour paramétrer les options GS1 globales, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Paramètres de gestion des entrepôts**.
1. Dans le raccourci **Codes-barres**, définissez les champs suivants :

    - **Caractère FNC1**, **Caractère Datamatrix** et **Caractère QR Code** : spécifiez les caractères qui doivent être interprétés comme un préfixe pour chaque type de code à barres GS1.
    - **Séparateur de groupe** : spécifiez le caractère qui remplace le caractère ASCII de séparation de groupe.
    - **Longueur maximale de l’identificateur** – Spécifiez le nombre maximal de caractères autorisé pour l’identificateur de l’application. Ce champ n’est pas obligatoire si la fonctionnalité *Analyseur GS1 amélioré* est activée dans votre système.

> [!NOTE]
> Les préfixes indiquent au système qu’un code-barres est encodé selon la norme GS1. Jusqu’à trois préfixes (**Caractère FNC1**, **Caractère Datamatrix** et **Caractère Code QR**) peuvent être utilisés simultanément et à diverses fins.

## <a name="gs1-application-identifiers"></a>Identificateurs d’application de GS1

Les formats GS1 encodent non seulement les données, mais vous permettent également d’utiliser une liste prédéfinie d’identificateurs d’application pour définir la signification des données. Les responsables logistiques doivent configurer la liste requise d’identificateurs d’application et associer chacun d’eux aux éléments de menu appropriés de l’appareil mobile. Les identificateurs peuvent ensuite être utilisés dans les entrepôts en tant que paramètre global à des fins de déplacement et d’emballage. Par conséquent, toutes les étiquettes d’expédition prendront une forme unifiée.

Le système utilise les données, en particulier les identificateurs d’application prédéfinis, pour établir les règles qui doivent être appliquées à l’information scannée pertinente.

Chaque identificateur d’application signale au système que les caractères suivants dans le code-barres scanné doivent être considérés comme un bloc d’informations cryptées. La configuration des identificateurs d’application définit comment le système doit interpréter un code-barres et l’enregistrer en tant que valeur dans le système.

Les responsables logistiques peuvent utiliser les identificateurs d’application internationaux standard et/ou créer les leurs.

### <a name="load-the-standard-application-identifiers"></a>Charger les identificateurs d’application standard

Pour démarrer rapidement, vous pouvez charger une liste d’identificateurs d’applications internationaux courants. Vous pouvez ensuite étendre ou modifier la liste ultérieurement, selon vos besoins.

Pour charger les identificateurs d’application standard, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> GS1 \> Identificateurs d’application GS1**.
1. Dans le volet Actions, sélectionnez **Créer une configuration par défaut**.

> [!WARNING]
> La commande **Créer une configuration par défaut** supprime tous les identificateurs d’application actuellement définis et les remplace par la liste standard. Cependant, après avoir chargé la configuration par défaut, vous pouvez personnaliser la liste selon vos besoins.

### <a name="set-up-custom-application-identifiers"></a>Configurer des identificateurs d’application personnalisés

Si certains ou tous les identificateurs d’application utilisés par votre entreprise diffèrent de l’ensemble standard, vous pouvez créer vos propres codes à partir de zéro ou personnaliser l’ensemble standard selon vos besoins.

Pour configurer et personnaliser vos propres identificateurs d’application GS1, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> GS1 \> Identificateurs d’application GS1**.
1. Utilisez l’une des procédures suivantes :

    - Pour créer un identificateur, dans le volet Action, sélectionnez **Nouveau**.
    - Pour modifier un identificateur existant : Sélectionnez l’identificateur, puis, dans le volet Actions, sélectionnez **Modifier**.

1. Définissez les champs suivants pour le nouvel identificateur ou l’identificateur sélectionné :

    - **Identificateur d’application** – Saisissez le code d’identification de l’identificateur d’application. Typiquement, ce code est un entier à deux chiffres, mais il peut être plus long. Pour les valeurs décimales, le dernier chiffre indique le nombre de décimales. Pour plus d’informations, consultez la description de la case à cocher **Décimale** plus loin dans cette liste. Si la fonctionnalité *Analyseur amélioré pour les codes-barres GS1* est activée, vous pouvez créer un identifiant d’application unique pour toutes les variantes de décimales en utilisant la lettre *n* comme dernier caractère de l’identifiant d’application. Par exemple, vous pouvez configurer un seul identifiant d’application (*310n*) au lieu d’un identifiant d’application distinct pour chaque position décimale (*3101*, *3102*, *3103*, etc).
    - **Description** – Permet d’entrer une brève description de l’identificateur.
    - **Longueur fixe** – Cochez cette case si les valeurs analysées à l’aide de cet identificateur d’application ont un nombre fixe de caractères. Décochez cette case si la longueur des valeurs est variable. Dans ce cas, vous devez indiquer la fin de la valeur en utilisant le caractère séparateur de groupe que vous avez spécifié sur la page **Paramètres de gestion des entrepôts**.
    - **Longueur** – Saisissez le nombre maximal de caractères pouvant apparaître dans les valeurs analysées à l’aide de cet identificateur d’application. Si la case **Longueur fixe** est cochée, exactement ce nombre de caractères est attendu.
    - **Type** – Sélectionnez le type de valeur qui est scanné à l’aide de cet identificateur d’application (*Numérique*, *Alphanumérique* ou *Date*). Pour plus d’informations sur la manière dont les dates et les nombres sont représentés dans les données de code à barres, consultez la section [Dates et nombres décimaux](#dates-and-decimal-numbers).
    - **Décimale** – Cochez cette case si la valeur comprend un point décimal implicite. Si cette case est cochée, le système utilisera le dernier chiffre de l’identificateur de l’application pour déterminer le nombre de décimales. Pour plus d’informations sur la manière dont les dates et les nombres sont représentés dans les données de code à barres, consultez la section [Dates et nombres décimaux](#dates-and-decimal-numbers).

> [!WARNING]
> Bien que le système vous permette de cocher la case **Longueur fixe** pour tout identifiant d’application, elle doit être utilisée uniquement pour le sous-ensemble d’identifiants d’application qui ont une longueur prédéfinie conformément aux spécifications générales de GS1. L’analyseur GS1 amélioré contient déjà la liste de tous les identifiants d’application qui ont une longueur prédéfinie.

> [!NOTE]
> La valeur **Séparateur de groupe** indiquée sur la page **Paramètres de gestion des entrepôts** est facultative si une valeur suivie d’un identifiant d’application a une longueur fixe.

## <a name="establish-the-generic-gs1-setup"></a><a name="generic-gs1-setup"></a>Établir la configuration GS1 générique

La configuration GS1 générique établit une collection de mappages communs. Ces mappages font correspondre chaque champ de saisie pertinent de l’application mobile à l’identificateur d’application qui contrôle la manière dont les valeurs des codes-barres scannés doivent être interprétées et stockées dans ce champ. Par défaut, ces paramètres s’appliquent à tous les scans pour tous les éléments de menu de l’appareil mobile. Cependant, ils peuvent être écrasés pour un ou plusieurs champs spécifiques par une stratégie GS1 affectée à un élément de menu spécifique.

La configuration GS1 générique ne permet de scanner qu’une seule valeur à la fois. Par conséquent, si vous souhaitez charger plusieurs valeurs de champ à partir d’un seul scan, vous devez configurer une stratégie GS1 pour les éléments de menu pertinents.

Pour plus d’informations sur les stratégies GS1, consultez la section suivante.

### <a name="load-the-standard-generic-gs1-setup"></a>Charger la configuration GS1 générique standard

La page **Configuration GS1 générique** vous permet de charger un ensemble standard de mappages entre les champs d’appareil mobile et les identifiants d’application standard créés par la configuration par défaut.

Pour établir la configuration GS1 générique, allez dans **Gestion des entrepôts \> Paramétrage \> GS1 \> Configuration générique GS1**. Sélectionnez ensuite **Créer une configuration par défaut** pour attribuer automatiquement un identificateur d’application approprié à chaque champ généralement utilisé par les éléments de menu de l’appareil mobile.

> [!WARNING]
> Si une configuration GS1 générique existe déjà, la commande **Créer une configuration par défaut** la supprime complètement et charge la configuration standard.

### <a name="customize-the-standard-generic-gs1-setup"></a>Personnaliser la configuration GS1 générique standard

Pour personnaliser la configuration GS1 générique, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> GS1 \> Configuration générique GS1**.
1. Utilisez l’une des procédures suivantes :

    - Pour créer un mappage : dans le volet Actions, sélectionnez **Nouveau**.
    - Pour modifier un mappage existant : Sélectionnez le mappage, puis, dans le volet Actions, sélectionnez **Modifier**.

1. Définissez les champs suivants pour le nouveau mappage ou le mappage sélectionné :

    - **Champ** – Sélectionnez ou entrez le champ de saisie de l’application mobile auquel la valeur entrante doit être affectée. La valeur n’est pas le nom d’affichage que les travailleurs voient. Au lieu de cela, c’est le nom de clé qui est attribué au champ dans le code sous-jacent. La configuration par défaut fournit une collection de champs susceptibles d’être utiles et comprend des noms de clé intuitifs pour chaque champ et la fonctionnalité programmée correspondante. Cependant, vous devrez peut-être parler à vos partenaires de développement pour trouver les bonnes sélections pour votre implémentation.
    - **Identificateur d’application** – Sélectionnez l’identificateur d’application applicable, tel que défini sur la page **Identificateurs d’application GS1**. L’identificateur établit comment le code-barres sera interprété et stocké en tant que valeur pour le champ nommé. Une fois que vous avez sélectionné un identificateur d’application, le champ **Description** affiche la description de celui-ci.

## <a name="set-up-gs1-policies-to-be-to-mobile-device-menu-items"></a><a name="policies-for-menus"></a>Configurer des stratégies GS1 à attribuer aux éléments de menu de l’appareil mobile

L’objectif de la norme GS1 est de permettre aux travailleurs de charger plusieurs valeurs quand  ils scannent un seul code-barres une seule fois. Pour atteindre cet objectif, les responsables logistiques doivent mettre en place des stratégies GS1 qui indiquent au système comment interpréter les codes-barres à valeurs multiples. Plus tard, vous pouvez affecter des stratégies aux éléments de menu d’appareil mobile pour contrôler la façon dont un code-barres sera interprété quand les travailleurs le scannent pendant qu’ils utilisent un élément de menu spécifique.

Si aucune stratégie GS1 n’est affectée à un élément de menu, le système ne peut capturer qu’une seule valeur. Cette valeur est appliquée à l’entrée de l’application mobile qui est sélectionnée quand le travailleur effectue l’analyse, comme spécifié par la configuration GS1 générique. Si une stratégie GS1 est affectée à l’élément de menu, le système utilise toujours la configuration générique GS1 pour mapper la première valeur de code-barres au champ sélectionné. Cependant, il peut ensuite capturer des valeurs de champ supplémentaires, comme spécifié par la stratégie applicable.

### <a name="load-the-standard-specific-gs1-policies"></a>Charger les stratégies GS1 spécifiques standard

Pour démarrer rapidement, vous pouvez charger un ensemble de stratégies GS1. Vous pouvez ensuite étendre ou modifier les stratégies ultérieurement, selon vos besoins.

Pour charger les identificateurs d’application standard, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> GS1 \> Stratégie GS1**.
1. Dans le volet Actions, sélectionnez **Créer une configuration par défaut**.

> [!WARNING]
> La commande **Créer une configuration par défaut** supprime toutes les stratégies actuellement définies et les remplace par la liste standard de stratégies. Cependant, une fois la configuration par défaut chargé, vous pouvez personnaliser les stratégies selon vos besoins.

### <a name="set-up-custom-specific-gs1-policies"></a>Configurer des stratégies GS1 spécifiques standard

> [!WARNING]
> Certaines stratégies GS1 peuvent ne pas fonctionner avec tous les flux mobiles que vous utilisez. Quand vous configurez des stratégies GS1 personnalisées, vous devez tester le flux de l’appareil mobile en utilisant différentes informations qui seront analysées à différents points du flux. De cette façon, vous pouvez déterminer si le flux se comporte comme prévu.

Pour configurer et personnaliser vos stratégies GS1, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> GS1 \> Stratégie GS1**.
1. Utilisez l’une des procédures suivantes :

    - Pour créer une stratégie : dans le volet Actions, sélectionnez **Nouveau**.
    - Pour modifier une stratégie existante, sélectionnez la stratégie dans le volet de liste.

1. Dans l’en-tête de la nouvelle stratégie ou de la stratégie sélectionnée, définissez les champs suivants :

    - **Nom de la stratégie** – Permet d’entrer un nom de stratégie.
    - **Description** – Permet d’entrer une brève description de la stratégie.

1. Dans le raccourci sous l’en-tête, mappez les noms de champ aux identificateurs d’application comme requis pour la stratégie actuelle. Utilisez les boutons de la barre d’outils pour ajouter et supprimer des lignes selon vos besoins. Pour chaque ligne, définissez les champs suivants :

    - **Champ** – Sélectionnez ou entrez le champ de saisie de l’application mobile auquel la valeur entrante doit être affectée. La valeur n’est pas le nom d’affichage que les travailleurs voient. Au lieu de cela, c’est le nom de clé qui est attribué au champ dans le code sous-jacent. La configuration par défaut fournit une collection de champs susceptibles d’être utiles et comprend des noms de clé intuitifs pour chaque champ et la fonctionnalité programmée correspondante. Cependant, vous devrez peut-être parler à vos partenaires de développement pour trouver les bonnes sélections pour votre implémentation.
    - **Identificateur d’application** – Sélectionnez l’identificateur d’application applicable, tel que défini sur la page **Identificateurs d’application GS1**. L’identificateur établit comment le code-barres sera interprété et stocké en tant que valeur pour le champ nommé. Une fois que vous avez sélectionné un identificateur d’application, le champ **Description** affiche la description de celui-ci.
    - **Tri** – Chaque code-barres multi-valeurs comprend une série d’identificateurs d’application, chacun étant suivi d’une valeur. La stratégie GS1 applicable identifie quel identificateur d’application est mappé à chaque champ de base de données. Cependant, si un code à barres utilise le même identificateur d’application plus d’une fois, le système utilise l’ordre dans lequel les identificateurs d’application apparaissent dans le code pour les mapper aux champs. Pour les lignes qui partagent un identificateur d’application avec une ou plusieurs autres lignes, utilisez ce champ pour établir l’ordre dans lequel les lignes correspondantes sont traitées. La ligne qui a la valeur de tri la plus basse sera traitée en premier.

> [!NOTE]
> Pour les codes-barres qui incluent plusieurs identificateurs d’application identiques, vous *devez* utiliser le champ **Tri** pour établir l’ordre des champs.

## <a name="assign-gs1-policies-to-mobile-device-menu-items"></a>Attribuer des stratégies GS1 aux éléments de menu des appareils mobiles

Par défaut, tous les éléments de menu des appareils mobiles fournissent des champs de saisie dans lesquels les travailleurs peuvent scanner une seule valeur, conformément à la configuration GS1 générique. Si vous souhaitez que les travailleurs puissent scanner plus d’une valeur de champ dans une seule analyse pour n’importe quel élément de menu d’appareil mobile, vous devez affecter une stratégie GS1 en procédant comme suit.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Créez ou ouvrez un élément de menu.
1. Sur le raccourci **Général**, définissez le champ **Stratégie GS1** sur la stratégie qui s’applique à l’élément de menu.

## <a name="gs1-setup-example"></a>Exemple de configuration GS1

Cet exemple s’applique à un système où les options GS1 sont configurées de la manière suivante :

- Sur la page **Paramètres de gestion des entrepôts**, les paramètres globaux suivants sont définis :

    - **Caractère FNC1 :** *\]C1*
    - **Séparateur de groupe :** *\~*

- Sur la page **Identificateurs d’application GS1**, les identificateurs d’application suivants sont pertinents pour cet exemple.

    | Identificateur d’application | Description | Longueur fixe | Longueur | Type | Décimal |
    |---|---|---|---|---|---|
    | 01 | GTIN | Sélectionnée | 14 | Numérique | Compensé |
    | 10 | Numéro du lot | Compensé | 20 | Alphanumérique | Compensé |
    | 17 | Date d’expiration | Sélectionnée | 6 | Date | Compensé |
    | 30 | Quantité de réception | Compensé | 8 | Numérique | Compensé |

- Sur la page **Configuration générique GS1**, les paramètres suivants pour la stratégie GS1 générique sont pertinents pour cet exemple.

    | Champ | Identificateur d’application | Description |
    |---|---|---|
    | ItemId | 01 | GTIN |

- Sur la page **Stratégie GS1**, il y a une stratégie où le champ **Nom de la stratégie** est défini sur *Réception d’achat*. Cette stratégie inclut les lignes suivantes :

    | Champ | Identificateur d’application | Description | Tri |
    |---|---|---|---|
    | ExpDate | 17 | Date d’expiration | 0 |
    | InventBatchId | 10 | Numéro du lot | 0 |
    | Qté | 30 | Quantité de réception | 0 |

- Sur la page **Éléments de menu d’appareil mobile**, il y a un élément de menu nommé *Réception d’achat*. Son champ **Stratégie GS1** est défini sur *Réception d’achat*.

Une fois que les marchandises pour une commande fournisseur arrivent à l’entrepôt, le travailleur suit ces étapes.

1. Sur l’appareil mobile, sélectionnez l’élément de menu **Réception d’achat**.
1. Entrez le numéro de la commande fournisseur.
1. Sélectionnez le champ **Article**, puis scannez le code-barres suivant : `]C10100000012345678~3030~10b1~17220215`.

En raison des paramètres définis pour cet exemple, le système analyse le code-barres scanné de la manière suivante.

| Clé de champ | ID d’application | Valeur | Note |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Parce que le travailleur a scanné dans le champ **Article**, la première valeur du code-barres est mappée sur ce champ. Le mappage est tiré de la configuration générique GS1. |
| Qté | 30 | 30 | Étant donné que plusieurs valeurs de champ sont capturées en une seule analyse, ce mappage et tous les mappages restants sont extraits de la stratégie GS1 qui est affectée à l’élément de menu **Réception d’achat**. Cette valeur est la quantité qui a été reçue. |
| InventBatchId | 10 | b1 | Cette valeur est l’ID de lot. |
| ExpDate | 17 | 220215 | Le format de date est AAMMJJ. Par conséquent, la date d’expiration est le 15 février 2022. |

Le reçu est ensuite enregistré et les valeurs de base de données pertinentes sont saisies après l’analyse unique.
