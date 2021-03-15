---
title: Paramétrer les matières dangereuses
description: Cette rubrique explique comment configurer les données requises pour classer les articles en tant que matières dangereuses. Lorsque vous créez une commande client qui comprend un article classé comme matière dangereuse, le système génère une documentation sur les matières dangereuses pour cette commande client lors de son expédition.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: db0d78c7a6fa69aa4e0c4c82f92c33daabda073f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983339"
---
# <a name="set-up-hazardous-materials"></a>Paramétrer les matières dangereuses

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Pour utiliser la fonctionnalité de matières dangereuses, vous devez d’abord configurer les données requises pour classer les articles comme matières dangereuses. Ensuite, lorsque vous créez une commande client qui comprend un article classé comme matière dangereuse, le système génère une documentation sur les matières dangereuses pour cette commande client lors de son expédition.

## <a name="turn-on-the-hazardous-materials-feature-for-your-system"></a>Activer la fonction de matières dangereuses pour votre système

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des informations sur les produits*
- **Nom de la fonctionnalité :** *Informations sur les produits dangereux et documentation d’expédition*

## <a name="hazardous-material-regulations"></a>Réglementations sur les matières dangereuses

Pour utiliser les processus de matières dangereuses, vous devez d’abord créer une réglementation. Les réglementations définissent la manière dont le texte d’expédition imprimé est créé pour un article. Elles définissent également les modes de livraison associés.

Voici quelques réglementations courantes :

- **ADR** - Règlements liés au transport international de marchandises dangereuses par route
- **CFR 49** - Réglementation aux États-Unis pour le transport de marchandises dangereuses
- **IMDG** - Le code IMDG (International Marine Dangerous Goods)
- **IATA** - Règlement sur les marchandises dangereuses de l’Association internationale du transport aérien (IATA)

Ces réglementations permettent de déterminer les informations à afficher lorsque vous imprimez le texte d’expédition d’un article. Vous pouvez définir autant de réglementations que vous devez respecter.

> [!IMPORTANT]
> La fonctionnalité de configuration des codes d’information liés aux matières dangereuses ne rend pas votre entreprise conforme aux réglementations. Ce n’est qu’un outil qui vous aide à créer des processus pour votre entreprise.

En règle générale, une réglementation est disponible pour un mode de transport spécifique, tel que le fret maritime, le fret routier ou le fret aérien. Par conséquent, vous pouvez associer chaque réglementation à un mode de livraison. Le mode de livraison sera utilisé lors de l’impression de documents spécifiques dans la gestion d’entrepôt. Dans la gestion des entrepôts, chaque expédition est liée à un transporteur et à un service de transporteur qui sont configurés dans le module **Transport**. Le mode de livraison est associé au transporteur associé et au service de transporteur. Lorsque vous générez un état, le mode de livraison est utilisé pour rechercher le texte d’impression d’expédition associé à un article lancé.

Ces données de configuration ne sont pas spécifiques à chaque entité juridique (entreprise). Par conséquent, vous pouvez disposer d’un ensemble commun d’informations sur les matières dangereuses qui est partagé entre toutes vos entités juridiques.

Pour chaque règlementation, vous pouvez définir une liste d’articles et l’utiliser comme un modèle de liste associé aux articles lancés. Pour chaque règlementation, vous pouvez également définir une configuration d’impression. Une configuration d’impression vous permet de définir la manière dont le texte d’expédition d’un article est construit. La configuration d’impression est utilisée pour créer le texte d’impression d’expédition pour un article lancé.

Pour configurer des réglementations sur les matières dangereuses, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Règlementation sur les matières dangereuses**. Sur la page **Règlementation sur les matières dangereuses**, vous pouvez créer un nombre illimité de réglementations et les configurer à l’aide des champs décrits dans les sous-sections suivantes.

### <a name="hazardous-material-regulation-header"></a>En-tête de la réglementation sur les matières dangereuses

Chaque règlementation a un code et une description. Le tableau suivant décrit les champs disponibles dans l’en-tête.

| Champ | Description |
|---|---|
| Code de réglementation | Entrez un code pour identifier l’enregistrement de réglementation sur les matières dangereuses. |
| Description | Entrez une description de la règlementation sur les matières dangereuses. |

### <a name="print-setup-fasttab"></a>Raccourci Configuration de l’impression

Chaque règlementation peut avoir n’importe quel nombre de configurations d’impression. Vous définissez les paramètres d’impression sur le raccourci **Configuration de l’impression**. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque configuration d’impression.

| Champ | Description |
|---|---|
| Ordre | Définissez l’ordre dans lequel les champs seront référencés dans le texte d’expédition. |
| Champ d’impression | Sélectionnez le champ à inclure dans le texte d’expédition. Tous les champs relatifs aux matières dangereuses ne pourront pas être imprimés. Seuls les champs communs utilisés pour définir le texte d’expédition dans les différentes réglementations seront disponibles. Vous devez définir le premier champ d’impression comme un séparateur de champ avec une valeur **Séquence** de *0* (zéro), afin qu’il puisse être utilisé comme séparateur entre d’autres champs. Une seule référence au séparateur de champ est requise.<p>Les valeurs disponibles sont les suivantes :</p><ul></li><li>**Séparateur de champ** – Ce champ d’impression est utilisé comme séparateur de champ pour le texte. Un seul séparateur de champ est requis dans la séquence. Habituellement, vous devez définir la valeur **Séquence** pour ce champ d’impression sur *0* (zéro). Le système recherchera un séparateur de champ et utilisera le premier qu’il trouve dans la liste. La valeur de texte utilisée dans la chaîne proviendra du champ **Imprimer après**.</li><li>**Identification** – Ce champ d’impression place le [code et/ou la description d’identification](#identification) dans le texte imprimé.</li><li>**Classe** – Ce champ d’impression place le [code et/ou la description de classe](#classes) dans le texte imprimé.</li><li>**Division** – Ce champ d’impression place le [code et/ou la description de division](#divisions) dans le texte imprimé.</li><li>**Groupe d’emballage** – Ce champ d’impression place le [code et/ou la description du groupe d’emballage](#packing-group) dans le texte imprimé.</li><li>**Code et/ou description du tunnel** – Ce champ d’impression place le [code et/ou la description du tunnel](#tunnel) dans le texte imprimé.</li><li>**Nom d’expédition précis** – Ce champ d’impression place le [nom d’expédition précis](hazmat-items.md#hazmat-description) dans le texte imprimé.</li><li>**Nom technique** – Ce champ d’impression place le [nom technique et/ou la description](#technical-name) dans le texte imprimé.</li><li>**Catégorie de transport** – Ce champ d’impression place le [code et/ou la description de la catégorie de transport](#transport-category) dans le texte imprimé.</li><li>**Rangement** – Ce champ d’impression place le [code et/ou la description de rangement](#stowage) dans le texte imprimé.</li><li>**Texte fixe** – Ce champ d’impression entre le texte défini dans le champ **Texte fixe** pour cette ligne.</li><li>**Code et/ou description de l’étiquette** – Ce champ d’impression place le [code et/ou la description de l’étiquette](#label) dans le texte imprimé.</li><li>**Emballage aérien** – Ce champ d’impression place le [code et/ou la description des instructions d’emballage aérien](#packing-instruction) dans le texte imprimé.</li><li>**Quantité limitée** – Ce champ d’impression vérifie si l’article est marqué comme [article en quantité limitée](hazmat-items.md#material-management) et, si c’est le cas, entre le texte défini dans le champ **Texte fixe** pour cette ligne.</li><li>**Description de l’emballage** – Ce champ d’impression place la [description de l’emballage](#packing-description) dans le texte imprimé.</li></ul> |
| Imprimer avant | Entrez le texte à imprimer avant le contenu défini par le paramètre **Champ d’impression**. |
| Imprimer après | Entrez le texte à imprimer après le contenu défini par le paramètre **Champ d’impression**. |
| Imprimer avec le précédent | Cochez cette case pour empêcher l’impression du séparateur de champ entre le champ précédent et ce champ. Cochez cette case pour les champs d’impression qui sont facultatifs ou inclus avec un autre champ d’impression. |
| Texte fixe | Si vous définissez le champ **Impression** sur **Texte fixe** ou **Quantité limitée**, entrez le texte à imprimer. |
| Inclure dans une impression | Sélectionnez la ou les valeurs du champ d’impression sélectionné à imprimer pour cette ligne. Vous pouvez imprimer le code, la description ou à la fois le code et la description. |

### <a name="mode-of-delivery-fasttab"></a>Raccourci Mode de livraison

La réglementation est une table partagée et n’est pas spécifique à chaque entité juridique. Cependant, les modes de livraison sont spécifiques à l’entité juridique. Par conséquent, lorsque vous configurez un mode de livraison, vous devez sélectionner la relation entre le règlement, l’entité juridique et le mode de livraison.

Le tableau suivant décrit les champs disponibles dans le raccourci **Mode de livraison**.

| Champ | Description |
|---|---|
| Société | Sélectionnez une entité juridique à associer à cette réglementation. |
| Mode de livraison | En fonction de l’entité juridique que vous avez sélectionnée, sélectionnez le mode de livraison qui doit être associé à la réglementation. |

### <a name="country-fasttab"></a>Raccourci Pays

À des fins de référence, vous pouvez répertorier les pays ou régions pour lesquels le règlement est pertinent. Cependant, lorsque les rapports d’expédition sont exécutés, seul le mode de livraison est utilisé pour déterminer la réglementation. Lorsque vous examinez une expédition d’entrepôt, il n’y a pas de lien direct avec le mode de livraison. L’expédition peut être associée à un transporteur associé et au service de transporteur. Lorsque vous définissez un service de transporteur, vous devez l’associer à un mode de livraison. Cette relation sera utilisée sur les rapports d’expédition, tels que le connaissement pour trouver le texte d’impression d’expédition d’un article.

Le tableau suivant décrit le champ disponible dans le raccourci **Pays**.

| Champ | Description |
|---|---|
| Pays/région | Sélectionnez un pays/région à associer à la réglementation. |

## <a name="material-codes"></a><a name="hazmat-codes"></a>Codes matières

Les codes matières définissent les paramètres liés à un composant dangereux spécifique pouvant être inclus dans un produit lancé. Chaque code matière appartient à une réglementation spécifique sur les matières dangereuses et sa définition doit être conforme à cette réglementation. Lorsque vous appliquez un code article à un produit lancé en utilisant le champ **Code matière**, tous les paramètres de matières dangereuses du code matière sont automatiquement appliqués à ce produit. Par conséquent, le processus de configuration des produits commercialisés est plus rapide et moins sujet aux erreurs.

Pour gérer vos définitions de matières dangereuses, procédez comme suit.

1. Accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Règlementation sur les matières dangereuses**.
2. Sélectionnez la réglementation pour laquelle configurer une définition de matière dangereuse.
3. Dans le volet Actions, sous l’onglet **Paramétrage**, sélectionnez **Matières dangereuses**.
4. Dans le champ **Code matière**, saisissez un code matière pour la définition de matière dangereuse. Vous sélectionnerez cette valeur lorsque vous appliquerez le code article à un produit lancé.

    Le champ **Code de règlementation** est en lecture seule et montre la règlementation que vous avez sélectionnée à l’étape 2.

5. Utilisez les champs restants de cette page pour créer et configurer chaque matière dangereuse qui s’applique à la réglementation sélectionnée. Les champs disponibles sont un sous-ensemble des champs de matières dangereuses disponibles pour les produits lancés individuellement. Pour plus d’informations, consultez [Matières dangereuses dans les produits, les commandes, les expéditions et les chargements](hazmat-items.md).

## <a name="hazardous-material-classification-groups"></a><a name="classification-groups"></a>Groupes de classification des matières dangereuses

Chaque groupe de classification des matières dangereuses définit un groupe de valeurs de champ qui établissent un modèle. Vous pouvez utiliser ce modèle ultérieurement, lorsque vous définissez des informations sur les matières dangereuses pour un article lancé.

Lorsque vous affectez le code d’un groupe de classification de matières dangereuses à un article lancé, les informations associées à ce groupe de classification sont copiées dans les champs appropriés de l’article. Par conséquent, vous pouvez simplifier les processus de configuration en établissant un ensemble de valeurs de champ associées que vous utilisez souvent ensemble.

Ces données de configuration ne sont pas spécifiques à chaque entité juridique. Par conséquent, vous pouvez disposer d’un ensemble commun d’informations sur les matières dangereuses qui est partagé entre toutes vos entités juridiques.

Pour configurer des groupes de classification des matières dangereuses, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Groupe de classification des matières dangereuses**. Sur la page **Groupe de classification des matières dangereuses**, vous pouvez créer un nombre illimité de groupes et les configurer à l’aide des champs décrits dans le tableau suivant.

| Champ | Description |
|---|---|
| Code groupe | Permet d’entrer un code d’identification du groupe. |
| Description | Permet d’entrer une description du groupe. |
| Code classe | Permet d’associer un [code de classe](#classes) de matière dangereuse au groupe. |
| Code division | Permet d’associer un [code de division](#divisions) de matière dangereuse au groupe. |
| Code du groupe d’emballage | Associer un [code de groupe d’emballage](#packing-group) au groupe. |
| Code de catégorie de transport | Associer un [code de catégorie de transport](#transport-category) au groupe. |
| Multiplicateur | Entrez le multiplicateur de matières dangereuses qui s’applique à la classe et à la division de matières dangereuses sélectionnées, conformément à la réglementation applicable. Ce multiplicateur est utilisé dans le cadre de la formule qui calcule le total des *points de matières dangereuses* inclus dans un chargement ou une expédition. Pour plus d’informations sur les points de matières dangereuses et ce multiplicateur, voir [le raccourci Gestion des matières](hazmat-items.md#material-management). |

## <a name="hazardous-material-classes"></a><a name="classes"></a>Classes de matières dangereuses

Une classe de matières dangereuses est généralement mappée à la liste des classes fournies dans la réglementation à laquelle vous vous conformez. Par exemple, la réglementation américaine CFR 49 répertorie les liquides inflammables et les combustibles comme « classe 3 ». Vous pouvez configurer les classes qui sont pertinentes pour les articles que vous devez classer.

Chaque classe sera affectée à une configuration de matières dans la liste des matières liée à la réglementation. Vous attribuerez une classe à chaque article lancé selon les besoins, pour décrire la nature dangereuse d’un produit.

Ces données de configuration ne sont pas spécifiques à chaque entité juridique. Par conséquent, vous pouvez disposer d’un ensemble commun d’informations sur les matières dangereuses qui est partagé entre toutes vos entités juridiques.

Les classes de matières dangereuses fonctionnent avec des divisions, des groupes et des groupes de compatibilité de la manière suivante :

- Lorsque vous affectez une classe de matières dangereuses à un article lancé, vous devez également affecter une [division des matières dangereuses](#divisions).
- Vous pouvez utiliser des classes de matières dangereuses avec des [groupes de classification des matières dangereuses](#classification-groups) pour établir un modèle de codes pour la configuration des éléments.
- Vous pouvez utiliser des [groupes de compatibilité des matières dangereuses](#compatibility-groups) pour déterminer quelles classes et divisions de matières dangereuses peuvent être expédiées ensemble.

Pour configurer des classes de matières dangereuses, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Classe de matières dangereuses**. Sur la page **Classe de matières dangereuses**, vous pouvez créer un nombre illimité de classes et les configurer à l’aide des champs décrits dans le tableau suivant.

| Champ | Description |
|---|---|
| Code classe | Permet d’entrer un code d’identification de cette classe. Vous définissez ce code pour l’article. Il sera ensuite utilisé dans les listes de recherche lorsque vous affecterez une classe de matières dangereuses à un article lancé. |
| Description | Entrez une description de la classe. |

## <a name="hazardous-material-divisions"></a><a name="divisions"></a>Divisions de matières dangereuses

Une division de matières dangereuses est un sous-ensemble d’une classe de matières dangereuses. Vous devez attribuer à la fois une division et une classe à chaque produit qui comprend des matières dangereuses.

Pour les classes qui n’ont pas de division, créez une division où le code est *0*. Par exemple, dans le règlement IATA, les matières radioactives de classe 7 n’ont pas de subdivisions. Dans ce cas, vous allez créer une division *0* que vous pourrez associer à un produit lancé lorsque vous affecterez la classe.

Ces données de configuration ne sont pas spécifiques à chaque entité juridique. Par conséquent, vous pouvez disposer d’un ensemble commun d’informations sur les matières dangereuses qui est partagé entre toutes vos entités juridiques.

Les divisions de matières dangereuses fonctionnent avec des classes, des groupes et des groupes de compatibilité des façons suivantes :

- Lorsque vous affectez une division de matières dangereuses à un article lancé, vous devez également affecter une [classe des matières dangereuses](#classes).
- Vous pouvez utiliser des divisions de matières dangereuses avec des [groupes de classification des matières dangereuses](#classification-groups) pour établir un modèle de codes pour la configuration des éléments.
- Vous pouvez utiliser des [groupes de compatibilité des matières dangereuses](#compatibility-groups) pour déterminer quelles classes et divisions de matières dangereuses peuvent être expédiées ensemble.

Pour configurer des divisions de matières dangereuses, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Division des matières dangereuses**. Sur la page **Division de matières dangereuses**, vous pouvez créer un nombre illimité de divisions et les configurer à l’aide des champs décrits dans le tableau suivant.

| Champ | Description |
|---|---|
| Division | Entrez un code à utiliser comme numéro de référence pour la division. |
| Description | Entrez une description de la division. |
| Classe | Recherchez et affectez la classe à laquelle appartient la division. |

## <a name="hazardous-material-compatibility-groups"></a><a name="compatibility-groups"></a>Groupes de compatibilité des matières dangereuses

Les groupes de compatibilité des matières dangereuses déterminent les classes et divisions de matières dangereuses pouvant être expédiées ensemble. Lorsque les opérateurs créent des chargements ou des expéditions d’entrepôt, ils peuvent exécuter un contrôle de compatibilité qui émettra un avertissement si le chargement ou l’expédition comprend des articles qui n’appartiennent pas tous au même groupe de compatibilité.

Ces données de configuration ne sont pas spécifiques à chaque entité juridique. Par conséquent, vous pouvez disposer d’un ensemble commun d’informations sur les matières dangereuses qui est partagé entre toutes vos entités juridiques.

Pour configurer des groupes de compatibilité des matières dangereuses, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Groupe de compatibilité des matières dangereuses**. Sur la page **Groupe de compatibilité des matières dangereuses**, vous pouvez créer un nombre illimité de groupes de compatibilité et les configurer à l’aide des champs décrits dans les sous-sections suivantes.

### <a name="hazardous-material-compatibility-group-header"></a>En-tête de groupe de compatibilité des matières dangereuses

Chaque groupe de compatibilité a un code et une description. Le tableau suivant décrit les champs disponibles dans l’en-tête.

| Champ | Description |
|---|---|
| Groupe de compatibilité | Permet d’entrer un code d’identification du groupe de compatibilité |
| Description | Permet d’entrer une description du groupe de compatibilité. |

### <a name="compatibility-group-details"></a>Détails du groupe de compatibilité

Chaque groupe de compatibilité établit une liste des classes et divisions de matières dangereuses pouvant être expédiées ensemble.

| Champ | Description |
|---|---|
| Classe | Sélectionnez une classe de matières dangereuses compatible avec toutes les autres classes du groupe. |
| Division | Sélectionnez une division de matières dangereuses appartenant à la classe sélectionnée. |

## <a name="hazardous-material-specification-values"></a>Valeurs de spécification des matières dangereuses

Microsoft Dynamics 365 Supply Chain Management fournit plusieurs types de spécifications de matières dangereuses. Pour chaque type, vous devez établir un ensemble de valeurs centralisé pour chaque champ pertinent. Les utilisateurs peuvent ensuite sélectionner parmi ces valeurs lorsqu’ils configurent des définitions de matières dangereuses ou des produits lancés. Supply Chain Management fournit une collection de pages sur lesquelles vous pouvez établir les valeurs. Chaque page est dédiée à un type de spécification. Pour obtenir une description de chaque spécification disponible et des informations sur la manière d’établir les valeurs disponibles pour celle-ci, consultez les sous-sections suivantes.

Un exemple de spécification de matières dangereuses est le _code de rangement_, qui spécifie comment une matière donnée peut être stockée pendant le transport. En utilisant les informations de cette section, vous établissez une collection centrale de codes de rangement. Cette collection sera ensuite présentée aux utilisateurs dans une liste déroulante lorsqu’ils définiront le code de rangement pour un produit lancé.

Ces valeurs de spécification de matières dangereuses ne sont pas spécifiques à chaque entité juridique. Par conséquent, vous pouvez avoir un ensemble de valeurs communes qui sont partagées entre toutes vos entités juridiques.

Vous utiliserez des [codes matières](#hazmat-codes) pour établir des collections communes de paramètres pour chaque spécification, telle qu’elle s’applique à une réglementation donnée. Vous pouvez ensuite appliquer le code approprié à chaque produit lancé selon vos besoins. Pour plus d’informations sur l’application d’un code de matière dangereuse à un produit lancé spécifique et sur la configuration des paramètres individuels de ce produit pour toute spécification décrite ici, voir [Matières dangereuses dans les produits, les commandes, les expéditions et les chargements](hazmat-items.md).

### <a name="hazardous-material-emergency-response"></a>Réponse d’urgence concernant une matière dangereuse

La spécification *Intervention d’urgence relative aux matières dangereuses* indique les mesures à prendre en cas de problème pendant le transport d’un produit contenant une matière dangereuse donnée.

Pour configurer des valeurs pour cette spécification, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Intervention d’urgence relative aux matières dangereuses**. Sur la page **Intervention d’urgence relative aux matières dangereuses**, vous pouvez créer n’importe quel nombre de valeurs et configurer chacune avec un code de classification et une brève description.

### <a name="hazardous-material-identification"></a><a name="identification"></a>Identification des matières dangereuses

La spécification *Identification des matières dangereuses* identifie la classe ou la nature d’une matière dangereuse. La valeur est généralement un code basé sur une norme des Nations Unies (O.N.U.). Chaque classe est identifiée par un code et une description, et peut fixer des limites sur les méthodes de transport. Par exemple, pour identifier un article ou une matière inflammable, vous créez une classe de matières dangereuses qui utilise le code *FL* et la description *Inflammable*. Vous spécifiez également que la classe ne doit pas être transportée par voie aérienne.

Pour configurer des valeurs pour cette spécification, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Identification des matières dangereuses**. Sur la page **Indentification des matières dangereuses**, vous pouvez créer n’importe quel nombre de valeurs et les configurer à l’aide des champs décrits dans le tableau suivant.

| Champ | Description |
|---|---|
| Identification | Entrez un code à utiliser comme numéro de référence qui identifie cette classe de matières dangereuses. |
| Description | Entrez une description de cette classe. |
| Interdire au transport aérien | Cochez cette case pour indiquer que cette classe de matières dangereuses ne doit pas être transportée par voie aérienne. |
| Interdire au transport maritime | Cochez cette case pour indiquer que cette classe de matières dangereuses ne doit pas être transportée par voie maritime. |

### <a name="hazardous-material-label"></a><a name="label"></a>Étiquette de matières dangereuses

La spécification *Étiquette de matière dangereuse* identifie l’étiquette de marchandises dangereuses qui doit être apposée sur les produits lancés pertinents. Les étiquettes elles-mêmes décriront comment le produit doit être manipulé. Par exemple, vous avez un produit qui contient un gaz toxique. Dans ce cas, vous configurez un code d’étiquette qui représente l’étiquette de gaz toxique. Vous créez également votre processus d’entreprise afin qu’il recherche cette valeur lorsque vous expédiez des produits.

Pour configurer des valeurs pour cette spécification, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Étiquette de matière dangereuse**. Sur la page **Étiquette de matière dangereuse**, vous pouvez créer n’importe quel nombre d’étiquettes et configurer chacune avec un code d’identification et une brève description.

### <a name="hazardous-material-packing-descriptions"></a><a name="packing-description"></a>Descriptions des emballages de matières dangereuses

La spécification *Descriptions d’emballage des matières dangereuses* indique comment un article dangereux doit être emballé. Par exemple, il peut devoir être emballé dans un type spécifique de fût en acier ou dans un autre type d’emballage spécial.

Pour configurer des valeurs pour cette spécification, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Descriptions d’emballage des matières dangereuses**. Sur la page **Descriptions d’emballage des matières dangereuses**, vous pouvez créer n’importe quel nombre de descriptions d’emballage et configurer chacune avec un code d’identification et une brève description.

### <a name="hazardous-material-packing-group"></a><a name="packing-group"></a>Groupe d’emballage des matières dangereuses

La spécification *Groupe d’emballage de matières dangereuses* identifie le groupe d’emballage pour un article dangereux. Le groupe d’emballage vous permet de définir un code et une description pour indiquer comment les articles de matières dangereuses doivent être emballés pendant le transport ou l’expédition. Le groupe d’emballage est affecté à l’article par le biais de la page **Article matières dangereuses**.

Pour configurer des valeurs pour cette spécification, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Groupe d’emballage de matières dangereuses**. Sur la page **Groupe d’emballage de matières dangereuses**, vous pouvez créer n’importe quel nombre de groupes d’emballage et configurer chacune avec un code d’identification et une brève description.

### <a name="hazardous-material-packing-instruction"></a><a name="packing-instruction"></a>Instructions d’emballage des matières dangereuses

La spécification *Instruction d’emballage des matières dangereuses* identifie les instructions d’emballage qui doivent être suivies lorsqu’un article dangereux donné est préparé pour le transport aérien.

Pour configurer des valeurs pour cette spécification, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Instruction d’emballage des matières dangereuses**. Sur la page **Instructions d’emballage des matières dangereuses**, vous pouvez créer n’importe quel nombre d’identificateurs d’instructions d’emballage et configurer chacune avec un code d’identification et une brève description.

### <a name="hazardous-material-stowage"></a><a name="stowage"></a>Arrimage des matières dangereuses

La spécification *Rangement de matières dangereuses* indique comment un produit doit être stocké sur un navire lorsqu’il est transporté par fret maritime.

Pour configurer des valeurs pour cette spécification, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Rangement de matière dangereuse**. Sur la page **Rangement de matière dangereuse**, vous pouvez créer n’importe quel nombre d’identificateurs de rangement et configurer chacune avec un code d’identification et une brève description.

### <a name="hazardous-material-transport-category"></a><a name="transport-category"></a>Catégorie de transport des matières dangereuses

La spécification *Catégorie de transport de matières dangereuses* est généralement utilisée pour regrouper des produits dangereux similaires dans les états. Par exemple, les catégories de transport sont utilisées sur l’état **Récapitulatif de l’expédition**, que vous pouvez imprimer à partir de l’enregistrement d’expédition de l’entrepôt.

Pour configurer des valeurs pour cette spécification, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Catégorie de transport des matières dangereuses**. Sur la page **Catégorie de transport des matières dangereuses**, vous pouvez créer n’importe quel nombre de catégories de transport et configurer chacune avec un nom d’affichage et une brève description.

### <a name="hazardous-material-technical-name"></a><a name="technical-name"></a>Nom technique des matières dangereuses

La spécification *Nom technique des matières dangereuses* peut être utilisée pour fournir un nom d’entreprise communément utilisé ou interne qui décrit chaque matériau.

Pour configurer des valeurs pour cette spécification, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Nom technique des matières dangereuses**. Sur la page **Nom technique des matières dangereuses**, vous pouvez créer n’importe quel nombre de noms techniques de et configurer chacune avec un nom d’affichage et une brève description.

### <a name="hazardous-material-tunnel"></a><a name="tunnel"></a>Tunnel des matières dangereuses

La spécification *Tunnel de matières dangereuses* limite les types de tunnels dans lesquels une matière dangereuse peut être transportée en identifiant les types de tunnels qui doivent être utilisés. Les catégories de tunnels sont établies par les réglementations applicables pour le transport de matières dangereuses. Cette spécification s’applique généralement uniquement au transport routier.

Pour configurer des valeurs pour cette spécification, accédez à **Gestion des informations sur les produits \> Configurer \> Documentation d’expédition de matières dangereuses \> Tunnel de matière dangereuse**. Sur la page **Tunnel de matière dangereuse**, vous pouvez créer n’importe quel nombre d’identificateurs de tunnels et configurer chacun avec un code d’identification et une brève description.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]