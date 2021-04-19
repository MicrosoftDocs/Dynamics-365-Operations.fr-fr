---
title: Gestion de la qualité pour les processus d’entrepôt
description: Cette rubrique fournit des informations sur la gestion de la qualité pour les processus d’entrepôt. Cette fonctionnalité étend les capacités de gestion de la qualité et permet aux utilisateurs d’intégrer des contrôles d’échantillonnage d’articles dans le processus de réception dans l’entrepôt en utilisant une gestion des entrepôts avancée.
author: Henrikan
ms.date: 04/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-02
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: a049a7832e02dbd2debdd016a6b723726cc25df0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834263"
---
# <a name="quality-management-for-warehouse-processes"></a>Gestion de la qualité pour les processus d’entrepôt

La fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ vous permet d’intégrer des contrôles d’échantillonnage d’articles dans le processus de réception dans l’entrepôt en utilisant une gestion des entrepôts avancée. Le travail en entrepôt peut être généré automatiquement pour déplacer le stock vers le lieu de contrôle de la qualité, en fonction d’un pourcentage ou d’une quantité fixe, ou en fonction de chaque *n* e contenant. Une fois un ordre de qualité terminé, le travail peut être généré automatiquement pour déplacer le stock vers le prochain emplacement du processus, en fonction des résultats de qualité.

La fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ étend les capacités de la fonctionnalité de base de la gestion de la qualité. Elle offre la possibilité de créer des ordres de qualité pour le stock qui est envoyé au site de contrôle de la qualité, bien que les ordres de qualité ne soient pas toujours requis. Par conséquent, elle permet un processus de contrôle de la qualité léger basé sur le travail en entrepôt.

## <a name="turn-on-the-quality-management-for-warehouse-processes-feature"></a>Activer la fonctionnalité Gestion de la qualité pour les processus d’entrepôt

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Gestion de la qualité pour les processus d’entrepôt*

## <a name="key-benefits"></a>Avantages clés

La fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ génère automatiquement du travail dans le cadre du processus de réception, pour déplacer la quantité de stock requise pour le contrôle de la qualité vers un emplacement de contrôle de la qualité. Si la quantité reçue dépasse la quantité requise pour le contrôle de la qualité (selon la configuration d’échantillonnage de l’article), la quantité excédentaire est déplacée vers un emplacement entrant défini dans la configuration de la directive d’emplacement. Une fois l’ordre de qualité validé, un travail est automatiquement généré pour déplacer la quantité de l’ordre de qualité vers un nouvel emplacement entrant ou de retour, en fonction du résultat de la validation et de la configuration de la directive d’emplacement. La génération automatique de travail qui n’a que la quantité à déplacer vers et depuis le contrôle de la qualité offre une expérience de processus intégrée.

> [!NOTE]
> Quand la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ est activée, vous pouvez toujours profiter du processus manuel. Dans le processus manuel, le mouvement de stock et le mouvement par modèle sont utilisés pour qu’un manutentionnaire déclenche la création d’un travail d’entrepôt pour déplacer le stock d’un emplacement de contrôle de la qualité vers un nouvel emplacement. Vous pouvez également configurer une directive d’emplacement entrant qui déplace le stock dans son intégralité d’un emplacement de réception vers un emplacement de contrôle de la qualité sans tenir compte de la configuration d’échantillonnage des articles.

## <a name="quality-management-and-the-quality-management-for-warehouse-processes-feature"></a>Gestion de la qualité et Gestion de la qualité pour les processus d’entrepôt

Quand la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ est activée, elle modifie la configuration des principales entités de gestion des entrepôts et de gestion de la qualité. L’illustration suivante donne un aperçu des entités qui activent les ordres de qualité pour les processus d’entrepôt. Le texte entre parenthèses indique les actions suggérées lorsque la gestion de la qualité a été appliquée avant que la fonctionnalité _Gestion de la qualité pour les processus de gestion d’entrepôt_ n’ait été activée.

![Entités de gestion de la qualité](media/quality-management-entity-diagram.png "Entités de gestion de la qualité")

## <a name="enablers-the-quality-item-sampling-and-quality-order-work-order-types"></a>Éléments permettant le changement : Types d’échantillonnage d’articles de qualité et d’ordres de travail d’ordre de qualité

La fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ présente deux types d’ordres de travail qui permettent le processus de création de travail :

- **Échantillonnage d’articles de qualité** - Ce type d’ordre de travail est utilisé pour créer un travail qui déplace l’inventaire enregistré vers le contrôle qualité.
- **Ordre de qualité** - Ce type d’ordre de travail est utilisé pour créer un travail qui déplace l’inventaire du contrôle qualité vers un nouvel emplacement, en fonction de la configuration de la directive d’emplacement.

### <a name="work-classes-location-directives-and-work-templates"></a>Classes de travail, instructions d’emplacement et modèles de travail

Les types d’ordre de travail _Échantillonnage d’articles de qualité_ et _Commande de qualité_ sont consommés par les directives d’emplacement, les classes de travail et les modèles de travail.

Avant que le travail en entrepôt puisse être généré automatiquement pour déplacer le stock vers le contrôle qualité, vous devez suivre ces étapes pour configurer votre système.

1. Créez des classes de travail distinctes pour les types d’ordre de travail _Échantillonnage d’articles de qualité_ et _Ordre de travail_. De cette façon, vous vous assurez que le travail approprié peut être généré automatiquement en fonction des deux types d’ordres de travail, et que ce travail peut ensuite être exécuté à l’aide de l’application mobile Gestion des entrepôts.
1. Paramétrez un modèle de travail pour chaque type d’ordre de travail :

    - Configurez un modèle de travail qui utilise le type d’ordre de travail _Échantillonnage d’articles de qualité_ pour déplacer automatiquement le stock enregistré vers un emplacement de contrôle qualité.
    - Configurez un modèle de travail qui utilise le type d’ordre de travail _Ordre de qualité_ pour déplacer le stock à partir d’un emplacement de contrôle qualité une fois le contrôle qualité terminé.

1. Pour chaque type d’ordre de travail, configurez des directives d’emplacement qui appliquent les emplacements de contrôle qualité corrects vers lesquels le stock doit être déplacé. Une fois le contrôle qualité terminé, la directive d’emplacement du type d’ordre de travail _Ordre de qualité_ garantit qu’un nouvel emplacement de destination sera sélectionné afin que le stock puisse être déplacé hors de l’emplacement de contrôle qualité.
1. Configurez les éléments de menu de l’appareil mobile appropriés pour prendre en charge le mouvement du stock reçu vers l’emplacement de contrôle qualité et le mouvement du stock qui réussit ou échoue au contrôle qualité de l’emplacement de contrôle qualité vers un nouvel emplacement.

Pour un exemple étape par étape qui montre comment terminer cette configuration, consultez l’[exemple de scénario](#example-scenario) à la fin de ce sujet.

## <a name="enable-a-warehouse-for-quality-management"></a>Activer un entrepôt pour la Gestion de la qualité

Avant que la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ puisse être appliquée à un entrepôt spécifique, vous devez suivre ces étapes pour rendre la fonctionnalité disponible pour cet entrepôt.

1. Accédez à **Gestion des entrepôts \> Configuration \> Entrepôt \> Emplacements fixes**.
1. Sélectionnez l’entrepôt pour activer la Gestion de la qualité.
1. Sur l’organisateur **Entrepôt**, définissez l’option **Activer l’ordre de qualité pour les processus d’entrepôt** sur _Oui_. (Notez que cette option peut être définie sur _Oui_ uniquement pour les entrepôts qui utilisent des processus de gestion d’entrepôt.)

Quand l’option **Activer l’ordre de qualité pour les processus d’entrepôt** est définie sur _Oui_, la configuration d’association de qualité contrôle si la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ est appliquée pour l’entrepôt sélectionné. Vous pouvez modifier le paramètre de l’option sur _Non_ à tout moment. Dans ce cas, la fonctionnalité ne s’appliquera plus à l’entrepôt, quelle que soit la configuration d’association de qualité.

## <a name="quality-control"></a>Contrôle de la qualité

La fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ contrôle plusieurs paramètres clés pour les associations de qualité et l’échantillonnage des éléments.

### <a name="quality-associations"></a>Associations de qualité

Chaque [enregistrement d’association de qualité](enable-quality-management.md) définit l’ensemble de tests, le niveau de qualité acceptable et le programme d’échantillonnage qui s’applique aux ordres de qualité générés. Pour paramétrer un enregistrement d’association de qualité, procédez comme suit.

1. Allez dans **Gestion des stocks \> Configuration \> Contrôle de la qualité \> Associations de qualité**.
1. Créez ou sélectionnez l’entrée d’association de qualité pour l’élément ou le groupe avec lequel vous travaillez, ou pour tous les éléments.
1. Sur l’organisateur **Conditions**, définissez le champ **Type d’entrepôt applicable** sur l’une des valeurs suivantes :

    - **Gestion de la qualité pour les processus d’entrepôt uniquement** - Activez la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_. Vous ne pouvez sélectionner cette valeur que si le type de référence est *Achat* ou *Production*.
    - **Tous** - Désactivez la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_. Sélectionnez cette valeur pour tous les types de référence sauf *Achat* et *Production*.

> [!NOTE]
> La fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ ne prend effet que si l’élément sur la ligne de document source utilise des processus avancés de gestion d’entrepôt et si l’option **Activer l’ordre de qualité pour les processus d’entrepôt** est définie sur _Oui_ pour l’entrepôt sur la ligne du document source.

Lorsque chaque article est enregistré (ou signalé comme terminé), le système détermine les associations de qualité qui lui sont applicables.

Quand la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ est activée, le type d’entrepôt applicable est logiquement inséré dans le quatrième groupe de recherche de la hiérarchie de recherche d’association de qualité. Le tableau suivant fournit une représentation logique de la hiérarchie de recherche.

| Groupe de recherche | Description |
|---|---|
| Groupe 1 | Pour chaque association de qualité, consultez les valeurs **Type de référence**, **Type d’événement** et **Correspondance d’exécution** par rapport à l’article. S’il existe une correspondance avec la ligne du document source, passez au groupe 2. |
| Groupe 2 | Pour chaque association de qualité, consultez la valeur **Code de l’article** (_Table_, _Groupe_ ou _Tous_) par rapport à l’article. _Table_ est plus spécifique que _Groupe_, et _Groupe_ est plus spécifique que _Tous_. S’il y a une correspondance pour _Table_ (un élément spécifique), passez au groupe 3. S’il n’y a pas de correspondance pour _Table_, recherchez une correspondance pour _Groupe_. S’il n’y a pas de correspondance pour _Groupe_, _Tous_ s’applique. S’il y a une correspondance, passez au groupe 3. |
| Groupe 3 | Pour chaque association de qualité, consultez les valeurs **Code de compte** et **Code ressource** par rapport à l’article. La logique appliquée ressemble à la logique appliquée pour la valeur **Code de l’article**. |
| Groupe 4 | Pour chaque association de qualité, consultez la valeur **Type d’entrepôt applicable** (_Gestion de la qualité pour les processus d’entrepôt uniquement_ ou _Tous_) par rapport à l’article. Si l’option **Activer l’ordre de qualité pour les processus d’entrepôt** est définie sur _Oui_ pour l’entrepôt sur le document source et l’article sur la ligne du document source est défini sur _Utiliser des processus de gestion d’entrepôt_, les deux associations où il y a une correspondance pour _Gestion de la qualité pour les processus d’entrepôt uniquement_ et les associations où il y a une correspondance pour _Tous_ sera applicable en parallèle, si les deux existent. Si l’option **Activer l’ordre de qualité pour les processus d’entrepôt** est définie sur _Non_ pour l’entrepôt sur la ligne du document source et que l’article sur la ligne du document source est défini sur _Utiliser les processus de gestion des entrepôts_, seule la gestion de la qualité sera applicable. |

Par exemple, vous avez défini un entrepôt où l’option **Activer l’ordre de qualité pour les processus d’entrepôt** est définie sur _Oui_ et vous disposez de deux associations de qualité définies sur le type de référence *Achat* : un pour tous les articles et un pour le type d’événement *enregistrement*. La seule différence entre les deux associations de qualité est la valeur **Type d’entrepôt applicable** : elle est définie sur _Tous_ pour une association de qualité et _Gestion de la qualité pour les processus d’entrepôt uniquement_ pour l’autre. Dans ce cas, les deux associations de qualité sont également spécifiques et les deux seront applicables.

La valeur du champ **Groupe de test** des associations qualité est également un facteur. Ce champ définit la procédure de test qui doit être appliquée. Si la valeur **Groupe de test** est identique pour les deux associations, seul un ordre de qualité est créé pour l’association de qualité où la valeur **Type d’entrepôt applicable** est _Gestion de la qualité pour les processus d’entrepôt uniquement_. Si la valeur **Groupe de test** n’est pas la même pour les deux associations, deux ordres de qualité seront créés. Le premier ordre de qualité est créé pour l’association de qualité où la valeur **Type d’entrepôt applicable** est _Gestion de la qualité pour les processus d’entrepôt uniquement_. Le second ordre de qualité est créé pour l’association de qualité où la valeur **Type d’entrepôt applicable** est _Tous_.

> [!NOTE]
> La valeur _Gestion de la qualité pour les processus d’entrepôt uniquement_ est considérée comme plus spécifique que _Tous_ lorsque les critères des associations de qualité des groupes 1 et 2 sont les mêmes, et lorsque le groupe de test est le même. Deux ordres de qualité ne sont créés que lorsque les groupes de tests diffèrent.

#### <a name="reference-types"></a>Types de référence

Quand la valeur du **Type de référence** est _Achat_, et que la valeur du **Type d’entrepôt applicable** est _Gestion de la qualité pour les processus d’entrepôt uniquement_, le champ **Type d’événement** sur l’organisateur **Processus** doit être défini sur _Enregistrement_. _Enregistrement_ est le seul type d’événement pris en charge pour le type de référence _Achat_ lorsque vous utilisez la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_.

#### <a name="quality-processing-policy"></a>Stratégie de traitement de la qualité

La fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ permet de créer du travail uniquement sur la base de l’échantillonnage des éléments. Par conséquent, il permet un processus léger. Le stock pour lequel le travail est créé dépend de l’échantillonnage des articles associé à l’association de qualité. Lorsque le processus léger est utilisé, après qu’un collaborateur a placé la quantité dans l’emplacement de contrôle qualité, le service qualité peut créer manuellement un ordre de qualité, si un ordre de qualité est requis.

Le champ **Stratégie de traitement de la qualité** sur l’organisateur **Processus de commande de qualité** contrôle si un ordre de qualité est également créé lors de la création d’un travail pour déplacer un élément vers l’emplacement de contrôle de qualité. Ce champ peut être défini sur _Créer un ordre de qualité_ ou _Créer un travail uniquement_. La valeur par défaut est _Créer un ordre de qualité_.

> [!NOTE]
> Que vous créiez des ordres de qualité manuellement ou automatiquement, le système génère automatiquement du travail pour déplacer les articles hors de l’emplacement de contrôle qualité lorsque l’ordre de qualité est marqué comme validé.

La création d’un travail d’ordre de qualité n’est pas liée à la configuration de l’association de qualité. S’il existe un modèle de travail qui a une valeur **Type d’ordre de travail** de *Ordre de qualité*, et si les critères de requête sont remplis pour ce modèle de travail, la validation d’un ordre de qualité déclenchera la création d’un travail d’ordre de qualité.

#### <a name="referenced-item-sampling"></a>Échantillonnage d’articles référencés

Chaque association de qualité doit référencer un échantillonnage d’article. Un échantillonnage d’article définit la quantité qui sera envoyée pour le contrôle qualité. Il peut être configuré afin de s’appliquer uniquement aux associations de qualité où la valeur **Type d’entrepôt applicable** est _Gestion de la qualité pour les processus d’entrepôt uniquement_. Si la valeur **Portée d’échantillonnage** d’un échantillonnage d’article est _Chargement_ ou _Expédition_, ou que la valeur **Spécifications de quantité** est _Contenant complet_, l’échantillonnage des articles ne peut être référencé que par des associations de qualité où la valeur **Type d’entrepôt applicable** est _Gestion de la qualité pour les processus d’entrepôt uniquement_.

Si vous définissez un échantillonnage d’article qui utilise le type d’entrepôt applicable _Gestion de la qualité pour les processus d’entrepôt uniquement_, vous recevrez une erreur si vous essayez de le référencer à partir d’une association de qualité qui n’utilise pas la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_.

> [!NOTE]
> L’échantillonnage d’article qui utilise le blocage complet n’est pas pris en charge pour les associations de qualité où le champ **Type d’entrepôt applicable** est défini sur _Gestion de la qualité pour les processus d’entrepôt uniquement_.

### <a name="item-sampling"></a>Échantillonnage d’article

L’échantillonnage d’article contrôle la fréquence d’envoi des articles pour le contrôle de la qualité. La fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ présente le concept de _portée d’échantillonnage d’article_. Le système utilise la portée d’échantillonnage d’article lorsqu’il évalue si et comment les ordres de qualité et/ou le travail d’échantillonnage d’article de qualité et le travail d’ordre de qualité doivent être créés.

Pour configurer l’échantillonnage d’article, accédez à **Gestion des stocks \> Configuration \> Contrôle de qualité \> Échantillonnage d’articles** et définissez le champ **Portée d’échantillonnage** sur l’une des valeurs suivantes :

- **Ordre** - La ligne du document source sert de base à l’évaluation de si et comment les ordres de qualité et/ou le travail d’échantillonnage d’article de qualité et le travail d’ordre de qualité sont créés. Cette valeur est la valeur par défaut et lorsqu’elle est sélectionnée, le système fonctionne de la même manière que lorsque la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ n’est pas activée.
- **Chargement** - Les chargements sont utilisés comme base pour évaluer si et comment un ordre de qualité et/ou un travail est créé. Cette valeur n’est disponible que lorsque la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ est activée.
- **Expédition** - Les expéditions sont utilisées comme base pour évaluer si et comment un ordre de qualité et/ou un travail est créé. Cette valeur n’est disponible que lorsque la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ est activée.

> [!NOTE]
> Quand le champ **Portée d’échantillonnage** est défini sur *Chargement* ou *Expédition*, l’entité de chargement et les entités d’expédition sont utilisées, si elles sont disponibles. Si elles ne sont pas disponibles, l’entité d’ordre sera utilisée.

La fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ présente également la valeur *Contenant complet* pour le champ **Spécifications de quantité**. Cette valeur prend en charge la création de travaux d’ordre de qualité et d’échantillonnage d’articles de qualité, basés sur des contenants. Lorsque vous sélectionnez cette valeur, les modifications suivantes se produisent :

- L’option **Répartition par article** et le champ **Par Nième contenant** sur l’organisateur **Processus** devient disponible.
- Le champ **Valeur** sur l’organisateur **Quantité d’échantillonnage** n’est plus disponible.
- Les options **Par quantité mise à jour**, **Emplacement**, et **Contenant** sont toutes définies sur *Oui*, et les paramètres ne peuvent pas être modifiés.

L’option **Répartition par article** contrôle si le nombre de contenants est évalué par article ou pour tous les articles de la portée d’échantillonnage. Les variantes de produits sont traitées comme le même article. Cette option contrôle également si le nombre de contenants est réinitialisé pour chaque élément.

La valeur du champ **Par Nième contenant** contrôle la fréquence de création des ordres de qualité par rapport au nombre d’articles enregistrés. Par exemple, une valeur de *3* enverra un article sur trois au contrôle de qualité, en commençant par le premier article. La valeur doit être supérieure à 0 (zéro).

Pendant que les employés reçoivent des articles à l’aide de l’application mobile Gestion des entrepôts, le système valide si une association de qualité est configurée pour chaque article entrant. Si une association de qualité est configurée, le système utilise l’enregistrement d’échantillonnage d’article configuré pour cette association de qualité pour déterminer comment il va créer des ordres de qualité, un travail d’échantillonnage d’articles de qualité et un travail de commande fournisseur.

> [!NOTE]
> Lorsque l’enregistrement de réception est effectué dans le client web (en utilisant la petite page d’enregistrement ou le journal d’arrivée des articles pour les lignes de commande fournisseur), aucun travail d’échantillonnage d’article ou de commande fournisseur ne sera créé, quelle que soit la configuration. Au lieu de cela, pour les articles qui correspondent à une association de qualité, l’échantillonnage d’article référencé sera utilisé pour contrôler la création d’ordres de qualité uniquement.

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Exemples de génération automatique d’ordres de qualité

Les exemples suivants montrent comment la configuration d’une association de qualité et d’un échantillonnage d’article associé affecte la génération d’ordres de qualité lorsque le champ **Type d’entrepôt applicable** est défini sur _Gestion de la qualité pour les processus d’entrepôt uniquement_.

Quand la valeur **Spécifications de quantité** est _Contenant complet_, le champ **Par Nième contenant** contrôle quel travail d’échantillonnage d’article de qualité de contenants est créé. Le premier contenant va toujours au contrôle de qualité, puis la valeur de ce champ spécifie que chaque *N* ième contenant après ce contenant devrait également disparaître.

La valeur **Type de référence** des exemples suivants est _Achat_, et l valeur de **Type d’événement** est *Enregistrement*.

| Portée de l’échantillonnage | Spécification de la quantité | Par quantité mise à jour | Par dimension de stockage | Répartition par article | Par nième contenant | Résultat |
|---|---|---|---|---|---|---|
| Commande | Contenant complet | Oui _(verrouillé/non modifiable)_ | <p>Emplacement : Oui</p><p>Contenant : Oui _(verrouillé/non modifiable)_</p> | N° | 3 | <p>**Quantité de ligne de commande : 100 EA**</p><ol><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 20 EA, LP1<p>Travail d’échantillonnage d’articles de qualité pour 20 EA</p><p>Ordre de qualité 1 pour 20 EA</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 20 EA, LP2<p>Travail de commande fournisseur pour 20 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 20 EA, LP3<p>Travail de commande fournisseur pour 20 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 20 EA, LP4<p>Travail d’échantillonnage d’articles de qualité pour 20 EA</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 20 EA, LP5<p>Travail de commande fournisseur pour 20 EA (rangé)</p></li></ol> |
| Commande | Quantité fixe = 1 | Oui | <p>Emplacement : Oui</p><p>Contenant : Oui</p> | N° | Non applicable | <p>**Quantité de ligne de commande : 100**</p><ol><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 20 EA, LP1<p>Travail d’échantillonnage d’articles de qualité pour 1 EA</p><p>Ordre de qualité 1 pour 1 EA</p><p>Travail de commande fournisseur pour 19 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 20 EA, LP2<p>Travail d’échantillonnage d’articles de qualité pour 1 EA</p><p>Ordre de qualité 1 pour 1 EA</p><p>Travail de commande fournisseur pour 19 (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 20 EA, LP3<p>Travail d’échantillonnage d’articles de qualité pour 1 EA</p><p>Ordre de qualité 1 pour 1 EA</p><p>Travail de commande fournisseur pour 19 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 20 EA, LP4<p>Travail d’échantillonnage d’articles de qualité pour 1 EA</p><p>Ordre de qualité 1 pour 1 EA</p><p>Travail de commande fournisseur pour 19 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 20 EA, LP5<p>Travail d’échantillonnage d’articles de qualité pour 1 EA</p><p>Ordre de qualité 1 pour 1 EA</p><p>Travail de commande fournisseur pour 19 EA (rangé)</p></li></ol> |
| Commande | Pourcentage = 10 | N° | <p>Emplacement : Non</p><p>Contenant : Non</p> | N° | Non applicable | <p>**Quantité de ligne de commande : 100 EA**</p><ol><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 50 EA, LP1<p>Travail d’échantillonnage d’articles de qualité pour 10 EA</p><p>Ordre de qualité 1 pour 10 EA</p><p>Travail de commande fournisseur pour 40 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 50 EA, LP2<p>Travail de commande fournisseur pour 50 EA (rangé)</p></li></ol> |
| Charge | Pourcentage = 5 | Oui _(verrouillé/non modifiable)_ | <p>Emplacement : Non</p><p>Contenant : Non</p> | N° | Non applicable | <p>**Quantité de ligne de commande : 500 EA**</p><p>**Deux chargements : premier chargement 200 EA, deuxième chargement 300 EA**</p><ol><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour le premier chargement de 100 EA<p>Travail d’échantillonnage d’articles de qualité pour 5 EA</p><p>Ordre de qualité 1 pour 5 EA</p><p>Travail de commande fournisseur pour 95 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour le premier chargement de 100 EA<p>Travail d’échantillonnage d’articles de qualité pour 5 EA</p><p>Ordre de qualité 1 pour 5 EA</p><p>Travail de commande fournisseur pour 95 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour le deuxième chargement de 300 EA<p>Travail d’échantillonnage d’articles de qualité pour 15 EA</p><p>Ordre de qualité 1 pour 15 EA</p><p>Travail de commande fournisseur pour 285 EA (rangé)</p></li></ol> |
| Commande | Pourcentage = 10 | N° | <p>Emplacement : Oui</p><p>Contenant : Oui</p> | N° | Non applicable | <p>**Quantité de ligne de commande : 100**</p><ol><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 50 EA, LP1<p>Travail d’échantillonnage d’articles de qualité pour 5 EA</p><p>Ordre de qualité 1 pour 5 EA</p><p>Travail de commande fournisseur pour 45 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 50 EA, LP2<p>Travail d’échantillonnage d’articles de qualité pour 5 EA</p><p>Ordre de qualité 1 pour 5 EA</p><p>Travail de commande fournisseur pour 45 (rangé)</p></li></ol> |
| Charger | Contenant complet | Oui _(verrouillé/non modifiable)_ | <p>Emplacement : Oui</p><p>Contenant : Oui _(verrouillé/non modifiable)_</p> | N° | 3 | <p>**Deux articles :**</p><ul><li>**Quantité de ligne de commande pour l’article A : 120 EA (4 palettes)**</li><li>**Quantité de ligne de commande pour l’article B : 90 EA (3 palettes)**</li></ul><p>**Un chargement, deux lignes de chargement avec chaque ligne de commande**</p><ol><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 30 EA, LP1<p>Travail d’échantillonnage d’articles de qualité pour 30 EA</p><p>Ordre de qualité 1 pour 30 EA</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 30 EA, LP2<p>Travail de commande fournisseur pour 30 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 30 EA, LP3<p>Travail de commande fournisseur pour 30 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 30 EA, LP4<p>Travail d’échantillonnage d’articles de qualité pour 30 EA</p><p>Ordre de qualité 1 pour 30 EA</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article B, 30 EA, LP5<p>Travail de commande fournisseur pour 30 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article B, 30 EA, LP6<p>Travail de commande fournisseur pour 30 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 30 EA, LP7<p>Travail d’échantillonnage d’articles de qualité pour 30 EA</p><p>Ordre de qualité 1 pour 30 EA</p></li></ol> |
| Charger | Contenant complet | Oui _(verrouillé/non modifiable)_ | <p>Emplacement : Oui</p><p>Contenant : Oui _(verrouillé/non modifiable)_</p> | Oui | 3 | <p>**Deux articles :**</p><ul><li>**Quantité de ligne de commande pour l’article A : 120 EA (4 palettes)**</li><li>**Quantité de ligne de commande pour l’article B : 90 EA (3 palettes)**</li></ul><p>**Un chargement, deux lignes de chargement avec chaque ligne de commande**</p><ol><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 30 EA, LP1<p>Travail d’échantillonnage d’articles de qualité pour 30 EA</p><p>Ordre de qualité 1 pour 30 EA</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 30 EA, LP2<p>Travail de commande fournisseur pour 30 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 30 EA, LP3<p>Travail de commande fournisseur pour 30 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 30 EA, LP4<p>Travail d’échantillonnage d’articles de qualité pour 30 EA</p><p>Ordre de qualité 1 pour 30 EA</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article B, 30 EA, LP5<p>Travail d’échantillonnage d’articles de qualité pour 30 EA</p><p>Ordre de qualité 1 pour 30 EA</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article B, 30 EA, LP6<p>Travail de commande fournisseur pour 30 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 30 EA, LP7<p>Travail de commande fournisseur pour 30 EA (rangé)</p></li></ol> |
| Charger | Pourcentage = 10 | Oui _(verrouillé/non modifiable)_ | <p>Emplacement : Non</p><p>Contenant : Non</p> | N° | Non applicable | <p>**Quantité de ligne de commande : 100 EA**</p><p>**Aucun chargement n’est créé. La portée de l’ordre est appliquée.**</p><ol><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 50 EA, LP1<p>Travail d’échantillonnage d’articles de qualité pour 5 EA</p><p>Ordre de qualité 1 pour 5 EA</p><p>Travail de commande fournisseur pour 45 EA (rangé)</p></li><li>Enregistrer la réception dans l’application mobile Gestion des entrepôts pour l’article A, 50 EA, LP2<p>Travail d’échantillonnage d’articles de qualité pour 5 EA</p><p>Ordre de qualité 1 pour 5 EA</p><p>Travail de commande fournisseur pour 45 EA (rangé)</p></li></ol> |

Lorsqu’un collaborateur valide l’un des ordres de qualité indiqués dans le tableau précédent, le système génère automatiquement un travail d’ordre de qualité pour déplacer le stock de l’emplacement de contrôle qualité vers l’emplacement défini dans la directive d’emplacement pour le type d’ordre de travail _Ordre de qualité_. Vous pouvez configurer n’importe quel emplacement à cet effet, comme un lieu de retour ou de stockage, en fonction du résultat du test pour l’ordre de qualité. Pour un exemple de cette configuration, consultez l’[exemple de scénario](#example-scenario) à la fin de ce sujet.

Vous pouvez rouvrir un ordre de qualité qui a déjà été validé, à condition que le travail de l’ordre de qualité lié au déplacement du stock depuis le site de contrôle qualité ne comporte pas de valeur **Statut du travail** de *Fermé* ou *En cours*.

## <a name="process-insights-when-multiple-quality-associations-coexist"></a>Informations sur le processus lorsque plusieurs associations de qualité coexistent

Plusieurs associations de qualité peuvent être définies et appliquées à la même ligne de document source, et le champ **Type d’entrepôt applicable** peut être défini sur _Gestion de la qualité pour les processus d’entrepôt uniquement_ pour certaines de ces associations de qualité et _Tous_ pour les autres.

Dans l’exemple suivant, la valeur de **Type de référence** est _Achat_.

1. La première association de qualité se configure de la manière suivante :

    - **Type d’entrepôt applicable :** *Gestion de la qualité pour les processus d’entrepôt uniquement*
    - **Code article :** *A0001*
    - **Code de compte :** *Tous*
    - **Groupe de test :** *Pièce jointe*
    - **Échantillonnage d’article :** *5 pcs*

1. La seconde association de qualité se configure de la manière suivante :

    - **Type d’entrepôt applicable :** *Tous*
    - **Code article :** *Tous*
    - **Code de compte :** *Tous*
    - **Groupe de test :** *Pièce jointe*
    - **Échantillonnage d’article :** *1 pcs*

1. La troisième association de qualité se configure de la manière suivante :

    - **Type d’entrepôt applicable :** *Gestion de la qualité pour les processus d’entrepôt uniquement*
    - **Code article :** *Tous*
    - **Code de compte :** *104*
    - **Groupe de test :** *Impédance*
    - **Échantillonnage d’articles :** *Un contenant sur deux* (Ce paramètre signifie que les premier, troisième, cinquième contenants reçus, et ainsi de suite, créeront un ordre de qualité.)

1. La quatrième association de qualité se configure de la manière suivante :

    - **Type d’entrepôt applicable :** *Tous*
    - **Code article :** *Tous*
    - **Code de compte :** *Tous*
    - **Groupe de test :** *Impédance*
    - **Échantillonnage d’article :** *5 pcs*

1. La cinquième association de qualité se configure de la manière suivante :

    - **Type d’entrepôt applicable :** *Tous*
    - **Code article :** *Tous*
    - **Code de compte :** *Tous*
    - **Groupe de test :** *Cône*
    - **Échantillonnage d’article :** *10 %*

Une commande fournisseur pour une quantité de 10 articles A0001 est maintenant créée pour le fournisseur 104. Ensuite, une ligne de commande fournisseur d’une quantité de 10 est enregistrée comme reçue dans un contenant à l’aide de l’application mobile Gestion des entrepôts. Voici le résultat :

- Il y a un seul ordre de qualité de la première association de qualité pour le groupe de test *Pièce jointe*. La quantité est de 5. Il n’y a pas d’ordre de qualité de la deuxième association de qualité, car les critères de la première association de qualité sont plus spécifiques par rapport au groupe de test *Pièce jointe*.
- Il y a un seul ordre de qualité de la troisième association de qualité pour le groupe de test *Impédance*. La quantité est de 10. Il n’y a pas d’ordre de qualité de la quatrième association de qualité, car les critères de la première association de qualité sont plus spécifiques par rapport au groupe de test *Impédance*.
- Il y a un seul ordre de qualité de la cinquième association de qualité pour le groupe de test *Cône*. La quantité est de 1.

Dans le cadre de la création d’un ordre de qualité pour chacune des trois associations de qualité, un travail d’échantillonnage des articles de qualité est également créé. La quantité enregistrée n’est que de 10. Cependant, en raison de la configuration d’échantillonnage d’article, la somme des quantités d’ordre de qualité qui sont créées pour le type d’entrepôt applicable *Gestion de la qualité pour les processus d’entrepôt uniquement* est de 16, ce qui dépasse la quantité physique enregistrée de 10. Par conséquent, le travail ne sera pas créé pour les quantités d’ordre de qualité complète (16), car seulement 10 sont physiquement disponibles pour le déplacement vers le site de contrôle qualité. La priorité utilisée pour créer un travail d’échantillonnage d’articles de qualité suit l’ordre de création des ordres de qualité :

- **Premier ordre de qualité (quantité = 5) :** Un travail d’échantillonnage des éléments de qualité est créé pour 5. Il reste maintenant une quantité de 5 (10 - 5) pour la création ultérieure de travaux d’échantillonnage d’articles de qualité.
- **Second ordre de qualité (quantité = 10) :** Un travail d’échantillonnage des éléments de qualité est créé pour 5. Il reste maintenant une quantité de 0 (zéro) pour la création ultérieure de travaux d’échantillonnage d’articles de qualité.
- **Troisième ordre de qualité (quantité = 1) :** Aucun travail d’échantillonnage des éléments de qualité n’est créé.

Dans le cadre du processus de création des ordres de qualité, un blocage des stocks d’une quantité de 10 est créé. Ce blocage des stocks est référencé par rapport à chacun des trois ordres de qualité. La somme des quantités d’ordre de qualité est de 16.

Lorsque les ordres de qualité sont validés, le système essaie de créer un travail d’ordre de qualité pour chaque ordre de qualité qui est validé. Étant donné que la somme des quantités d’ordre de qualité dépasse la quantité réellement bloquée et donc disponible pour la création de travail, le travail d’ordre de qualité ne peut pas être créé pour les quantités d’ordre de qualité complètes, comme indiqué ici. (Cet exemple est la suite de l’exemple précédent.)

1. **Validez le deuxième ordre de qualité créé (quantité = 10). Un travail d’ordre de qualité est créé pour une quantité de 4.**

    La création d’un travail d’ordre de qualité est déclenchée par une modification de la quantité de blocage des stocks. Étant donné que la somme des quantités d’ordre de qualité était de 16, la validation d’une quantité de 10 entraînera la validation des quantités d’ordre de qualité restantes égales à 6. La quantité de blocage des stocks est réduite de 10 à 6. La quantité réduite de 4 est allouée à la création de travaux d’ordre de qualité.

2. **Validez le premier ordre de qualité créé (quantité = 5). Un travail d’ordre de qualité est créé pour une quantité de 5.**

    La création d’un travail d’ordre de qualité est déclenchée par une modification de la quantité de blocage des stocks. Étant donné que la somme des quantités d’ordre de qualité était de 6, la validation d’une quantité de 5 entraînera la validation des quantités d’ordre de qualité restantes égales à 1. La quantité de blocage des stocks est réduite de 6 à 1. La quantité réduite de 5 est allouée à la création de travaux d’ordre de qualité.

3. **Validez le troisième ordre de qualité créé (quantité = 1). Un travail d’ordre de qualité est créé pour une quantité de 1.**

    La création d’un travail d’ordre de qualité est déclenchée par une modification de la quantité de blocage des stocks. Étant donné que la somme des quantités d’ordre de qualité était de 1, la validation d’une quantité de 1 entraînera la validation des quantités d’ordre de qualité restantes égales à 0 (zéro). Le blocage des stocks est supprimé (c’est-à-dire que la quantité de blocage des stocks est réduite de 1 à 0). La quantité réduite de 1 est allouée à la création de travaux d’ordre de qualité.

> [!NOTE]
> La création d’un travail d’ordre de qualité dépend de la quantité de blocage des stocks qui est référencée par rapport à un ou plusieurs ordres de qualité. Si la somme des quantités d’ordre de qualité dépasse la quantité de blocage de stock référencée, l’ordre dans lequel les ordres de qualité sont validés détermine la création du travail d’ordre de qualité.

## <a name="canceling-quality-item-sampling-work"></a>Annulation d’un travail d’échantillonnage d’articles de qualité

Vous pouvez annuler le travail créé pour l’échantillonnage d’article de qualité. Pour contrôler ce qui se produit lorsque ce travail est annulé, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.
1. Sur l’onglet **Général**, sur l’organisateur **Travail**, définissez l’option **Annuler l’enregistrement de la réception lors de l’annulation d’un travail** sur l’une des valeurs suivantes :

    - **Oui** - Lorsque le travail d’échantillonnage d’articles de qualité est annulé, l’ordre de qualité associé est supprimé et le stock n’est pas enregistré.
    - **Non** - Lorsque le travail d’échantillonnage d’articles de qualité est annulé, l’ordre de qualité associé n’est pas supprimé et le stock n’est pas non enregistré.

## <a name="cross-docking"></a>Cross-docking

Vous pouvez avoir une configuration d’association de qualité qui crée un travail d’échantillonnage d’article. Cependant, lorsque le cross-docking existe en parallèle avec une association de qualité qui crée un travail d’échantillonnage d’articles de qualité, s’il n’y a que la quantité suffisante pour satisfaire le cross-docking, seul le travail d’échantillonnage d’articles est créé. Dans les cas où l’option **Activer l’ordre de qualité pour les processus d’entrepôt** est définie sur _Oui_ pour l’entrepôt de réception, et que le champ **Type d’entrepôt applicable** est défini sur _Gestion de la qualité pour les processus d’entrepôt uniquement_ pour une association de qualité, la création d’un travail d’échantillonnage d’article de qualité prime sur la création d’un travail de cross-docking. Si la quantité dépasse le besoin de cross-docking, le système crée toujours uniquement un travail d’échantillonnage d’articles.

## <a name="destructive-testing"></a>Tests destructifs

Vous pouvez définir un groupe de tests qui effectue des tests destructifs. Dans le cas d’un test destructif, l’hypothèse est que, quel que soit le résultat du test, la quantité de l’article testé sera détruite dans le cadre du test. La façon dont la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ prend en charge les tests destructifs ressemble à la façon dont la gestion de la qualité les prend en charge lorsque la fonctionnalité n’est pas activée. Avant de valider l’ordre de qualité, le contrôleur qualité doit spécifier le lieu de prélèvement pour la quantité qui a été détruite. Vous pouvez enregistrer le prélèvement sur la page de l’ordre de qualité en sélectionnant **Stock \> Prélever** sur le volet Action. Une fois le prélèvement de la quantité d’ordre de qualité enregistré, la validation peut être terminée.

## <a name="example-scenario"></a>Exemple de scénario

### <a name="prepare-the-scenario"></a>Préparer le scénario

Pour exécuter ce scénario, vous devez préparer votre système de la manière suivante :

- Assurez-vous que les données de démonstration sont installées sur le système et sélectionnez l’entité juridique **USMF**.
- Activez la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Configurez l’entrepôt 51 pour utiliser la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ comme suit :

    1. Accédez à **Gestion des entrepôts \> Configuration \> Entrepôt \> Emplacements fixes**.
    1. Sélectionner l’entrepôt 51.
    1. Sur l’organisateur **Entrepôt**, définissez l’option **Activer l’ordre de qualité pour les processus d’entrepôt** sur *Oui*.

### <a name="quality-in-setup--move-to-the-quality-control-location"></a>Configuration de la qualité d’entrée - Déplacer vers l’emplacement de contrôle de la qualité

Vous devez maintenant préparer une configuration de base qui permettra à votre système de prendre en charge la fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ pour l’entrepôt 51. (Les données de démonstration définissent un emplacement de gestion de la qualité nommé *QMS*. Cet emplacement est référencé plusieurs fois dans ce scénario.) Vous préparerez les éléments suivants, comme décrit dans les paragraphes de cette section :

- Classe de travail
- Modèle de travail
- Instruction d’emplacement
- Échantillonnage d’article
- Association de qualité
- Options de menu d’appareil mobile

#### <a name="work-class-for-quality-in"></a>Classe de travail pour la qualité entrante

1. Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Classes de travail**.
1. Créez une classe de travail et définissez les valeurs suivantes :

    - **ID classe de travail :** _QualityIn_
    - **Description :** _Échantillonnage d’articles de qualité_
    - **Type d’ordre de travail :** _Échantillonnage d’articles de qualité_

#### <a name="work-template"></a>Modèle de travail

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Définissez le champ **Type d’ordre de travail** sur _Échantillonnage d’articles de qualité_.
1. Créez un modèle de travail et définissez les valeurs suivantes :

    - **Modèle de travail :** _51 Quality_
    - **Description du modèle de travail :** _51 Quality_

1. Ajoutez une ligne au modèle de travail et définissez les valeurs suivantes :

    - **Type de travail :** _Choisir_
    - **ID classe de travail :** _QualityIn_

1. Ajoutez une seconde ligne au modèle de travail et définissez les valeurs suivantes :

    - **Type de travail :** _Put_
    - **ID classe de travail :** _QualityIn_

#### <a name="location-directive"></a>Instruction d’emplacement

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.
1. Définissez le champ **Type d’ordre de travail** sur _Échantillonnage d’articles de qualité_.
1. Créez une instruction d’emplacement et définissez les valeurs suivantes :

    - **Nom :** _51 to quality_
    - **Type de travail :** _Put_
    - **Site :** 5
    - **Entrepôt :** _51_

1. Ajoutez une ligne pour l’instruction d’emplacement et définissez les valeurs suivantes :

    - **Quantité de départ :** _1_
    - **Quantité d’arrivée :** _1000000_

1. Créez une action d’instruction d’emplacement et définissez la valeur suivante :

    - **Nom :** _Quality_

1. Pour la nouvelle action d’instruction d’emplacement, sélectionnez **Modifier la requête** et spécifiez un enregistrement de **Plage** avec les valeurs suivantes :

    - **Table :** *Emplacements*
    - **Champ :** _Location profile ID_
    - **Critères :** *QMS*

1. Sélectionnez **OK** pour enregistrer la requête ainsi que la nouvelle instruction d’emplacement.

Ensuite, vous devez modifier la séquence des instructions d’emplacement de commande fournisseur existantes pour l’entrepôt 51. Les données de démonstration incluent deux instructions d’emplacement avec une valeur de **Type d’ordre de travail** de _Achat_ : l’une est nommée _51 QMS_ et l’autre, _51 PO Direct_. Pour garantir que la fonctionnalité *Gestion de la qualité pour les processus d’entrepôt* est appliquée pour l’entrepôt 51, vous devez vous assurer que l’instruction d’emplacement _51 QMS_ n’est pas appliquée. Cependant, au lieu de supprimer cette instruction d’emplacement (car vous voudrez peut-être l’utiliser à l’avenir), vous pouvez simplement changer la séquence.

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.
1. Définissez le champ **Type d’ordre de travail** sur _Commande fournisseur_.
1. Dans la liste des séquences, sélectionnez le numéro de séquence 5, pour l’instruction d’emplacement _51 PO Direct_.
1. Déplacez la séquence sélectionnée jusqu’au numéro de séquence 4.
1. Vérifiez que le numéro de séquence de l’instruction d’emplacement _51 QMS_ est maintenant au moins 5.

#### <a name="item-sampling"></a>Échantillonnage d’article

La fonctionnalité _Gestion de la qualité pour les processus d’entrepôt_ ajoute de nouvelles capacités d’échantillonnage d’articles. La valeur de **Portée d’échantillonnage** peut maintenant être _Ordre_, _Expédition_ ou _Chargement_, et la valeur de **Quantité d’échantillonnage** peut maintenant être _Contenant complet_.

1. Allez dans **Gestion des stocks \> Configuration \> Contrôle de la qualité \> Échantillonnage d’article**.
1. Créez un enregistrement d’échantillonnage d’article et définissez les valeurs suivantes :

    - **Échantillonnage d’articles :** _3rd LP_
    - **Description :** _Un contenant sur trois_
    - **Portée de l’échantillonnage :** _Ordre_

1. Sur l’organisateur **Quantité d’échantillonnage**, définissez le champ **Spécifications de quantité** sur _Contenant complet_.
1. Sur l’organisateur **Processus**, définissez le champ **Par Nième contenant** sur _3_.
1. Dans la section **Par dimension de stockage**, activez **Entrepôt** et **Statut du stock**.

#### <a name="quality-associations"></a>Associations de qualité

Créez une association de qualité qui utilisera le nouvel échantillonnage d’article.

1. Allez dans **Gestion des stocks \> Configuration \> Contrôle de la qualité \> Associations de qualité**.
1. Créez un enregistrement d’association de qualité et définissez les valeurs suivantes :

    - **Type de référence :** _Achat_
    - **Code article :** _Table_
    - **Article :** _M9201_
    - **Site :** _5_

1. Sur l’organisateur **Processus**, définissez le champ **Type d’événement** sur *Enregistrement*.
1. Sur l’organisateur **Conditions**, définissez le champ **Type d’entrepôt applicable** sur *Gestion de la qualité pour les processus d’entrepôt uniquement*.
1. Sur l’organisateur **Processus d’ordre de qualité**, définissez le champ **Stratégie de traitement de la qualité** sur _Créer un ordre de qualité_.
1. Sur l’organisateur **Spécifications**, cliquez avec le bouton droit dans le champ **Groupe de test**, puis sélectionnez **Afficher les détails** pour ouvrir la page **Groupes de tests**.
1. Sur la page **Groupes de tests** sur la page, sous l’onglet **Vue d’ensemble** de la grille supérieure, créez un groupe de test et définissez les valeurs suivantes :

    - **Groupe de test :** _QMS_
    - **Description :** _QMS test_
    - **Quantité acceptable :** _100_
    - **Échantillonnage d’articles :** _3rd LP_ (Sélectionner)

1. Sur l’onglet **Vue d’ensemble** de la grille inférieure, ajoutez un enregistrement pour un test et définissez les valeurs suivantes :

    - **Séquence :** *1*
    - **Test :** *Mesure de la Pièce jointe*

1. Sur l’onglet **Test** de la grille inférieure, définissez les valeurs suivantes :

    - **Variables de test :** *Réussite/échec*
    - **Résultat par défaut :** *Réussite*

1. Enregistrez le nouveau groupe de test et fermez la page **Groupes de tests**.
1. De retour sur la page **Associations de qualité**, dans le champ **Groupe de test**, sélectionnez **QMS**.
1. Enregistrez l’enregistrement.

#### <a name="mobile-device-menu-items-for-quality-in"></a>Éléments de menu des appareils mobiles pour une entrée de qualité

Pour terminer la configuration afin de pouvoir déplacer les marchandises vers l’emplacement de contrôle qualité, vous devez rendre le travail d’échantillonnage d’articles de qualité disponible à partir d’un élément de menu de l’appareil mobile.

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Sélectionnez le élément de menu de l’appareil mobile **Rangement d’achat**.
1. Sur l’organisateur **Classes de travail**, ajoutez l’ID de la classe de travail *QualityIn*.

#### <a name="summary-your-setup-to-move-goods-to-quality-control"></a>Résumé : Votre configuration pour déplacer les marchandises vers le contrôle qualité

Vous avez maintenant défini une association de qualité qui utilise la fonctionnalité *Gestion de la qualité pour les processus d’entrepôt* pour déclencher la création d’un ordre de qualité. Vous avez configuré les données de travail et d’emplacement pour l’entrepôt 51 pour vous assurer qu’un travail spécifique est créé lors de l’enregistrement de l’achat de l’article M9201. Cette configuration garantit qu’un contenant sur trois enregistré sera déplacé vers un emplacement de qualité (_QMS_), et qu’un ordre de qualité sera créé pour la quantité de contenants. Tout le reste sera déplacé vers le rangement plutôt que l’emplacement de contrôle de qualité.

### <a name="process-quality-management-work"></a>Travail de gestion de la qualité des processus

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Créez une commande fournisseur et définissez les valeurs suivantes :

    - **Spécifiez un compte fournisseur :** *104*
    - **Entrepôt :** *51*

1. Ajoutez une ligne de commande fournisseur et définissez les valeurs suivantes :

    - **Article :** *M9201*
    - **Quantité :** *20*
    - **UdM :** *ea*
    - **Entrepôt :** *51*

1. Notez le numéro de la commande fournisseur afin de pouvoir l’utiliser ultérieurement.
1. Accédez à un appareil mobile ou à un émulateur qui exécute l’application mobile Gestion des entrepôts et connectez-vous à l’entrepôt 51 avec l’ID utilisateur *51* et le mot de passe *1*.
1. Aller à **Entrant \> Réception d’achat** et entrez les valeurs suivantes :

    - **PONum :** Numéro de la commande fournisseur récemment créée
    - **Qté :** *5*
    - **Unité :** *ea*

1. Continuez à recevoir par rapport à la ligne, *5 ch* à la fois, jusqu’à ce que la ligne soit entièrement reçue. (Un total de quatre contenants sera créé.)
1. Déconnectez-vous de l’application mobile Gestion des entrepôts.
1. De retour sur le client web, accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Recherchez et ouvrez votre commande fournisseur.
1. Dans la section **Lignes de commande fournisseur**, sélectionnez la ligne du numéro d’article *M9201*, puis cliquez sur **Lignes de commande fournisseur \> Détails du travail**.
1. Notez que les deuxième et troisième en-têtes de travail créés sont des travaux de rangement réguliers, tandis que les premier et quatrième en-têtes de travail sont des travaux d’échantillonnage d’articles de qualité. Ce résultat est cohérent avec la configuration d’échantillonnage des articles, qui est configurée pour échantillonner un contenant sur trois.

#### <a name="move-to-the-quality-control-location"></a>Déplacer vers l’emplacement de contrôle qualité

Vous allez maintenant déplacer les contenants vers leurs emplacements désignés. Les premier et quatrième contenants iront à l’emplacement de contrôle qualité, tandis que les deuxième et troisième contenants iront directement au stockage.

1. Accédez à un appareil mobile ou à un émulateur qui exécute l’application mobile Gestion des entrepôts et connectez-vous à l’entrepôt 51 avec l’ID utilisateur *51* et le mot de passe *1*.
1. Aller à **Entrant \> Rangement d’achat** et rangez chaque contenant de la procédure précédente jusqu’à ce que vous ayez fermé tout le travail.

#### <a name="summary-process-quality-management-work"></a>Résumé : Travail de gestion de la qualité des processus

Vous avez maintenant exécuté le travail d’échantillonnage d’articles de qualité pour les premier et quatrième contenants en les déplaçant vers l’emplacement de contrôle qualité. Vous avez également rangé les deuxième et troisième contenants. L’étape suivante consiste à effectuer les tests et le contrôle de l’ordre de qualité.

### <a name="quality-out-setup-move-from-the-quality-control-location-to-storage-or-return"></a>Configuration de la sortie de qualité : passer de l’emplacement de contrôle qualité au stockage ou au retour

Lorsque les collaborateurs signalent des résultats d’ordre de qualité, le système génère automatiquement du travail.

Vous allez maintenant poursuivre la configuration de base requise pour la classe de travail, le modèle de travail et l’instruction d’emplacement pour activer la gestion de la qualité pour les processus d’entrepôt, afin que le travail requis puisse être créé pour déplacer la quantité d’ordre de qualité de l’emplacement de contrôle qualité vers un emplacement de l’entrepôt désigné.

#### <a name="work-class-for-quality-out"></a>Classe de travail pour la qualité sortante

1. Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Classes de travail**.
1. Créez une classe de travail et définissez les valeurs suivantes :

    - **ID classe de travail :** *QualityOut*
    - **Description :** *Qualité sortante*
    - **Type d’ordre de travail :** *Ordre de qualité*

#### <a name="work-templates"></a>Modèles de travail

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Changez la valeur **Type d’ordre de travail** sur *Ordre de qualité*.
1. Créez un modèle de travail et définissez les valeurs suivantes :

    - **Modèle de travail :** *51 qualité sortante*
    - **Description du modèle de travail :** *51 qualité sortante*

1. Ajoutez une ligne et définissez les valeurs suivantes :

    - **Type de travail :** *Choisir*
    - **ID classe de travail :** **QualityOut**

1. Ajoutez une seconde ligne et définissez les valeurs suivantes :

    - **Type de travail :** *Put*
    - **ID classe de travail :** *QualityOut*

#### <a name="location-directives"></a>Instructions d’emplacement

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.
1. Changez la valeur **Type d’ordre de travail** sur *Ordre de qualité*.
1. Créez une instruction d’emplacement et définissez les valeurs suivantes :

    - **Nom :** *51 Pass*
    - **Type de travail :** *Put*
    - **Site :** *5*
    - **Entrepôt :** *51*

1. Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue de l’éditeur de requêtes.
1. Dans l’onglet **Plage**, définissez les valeurs suivantes :

    - **Table :** *Ordres de qualité*
    - **Champ :** *Statut*
    - **Critères :** *Pass*

1. Sélectionnez **OK** pour enregistrer la requête et fermer la boîte de dialogue.
1. Sur l’organisateur **Lignes**, ajoutez une ligne et définissez les valeurs suivantes :

    - **Quantité de départ :** *1*
    - **Quantité d’arrivée :** *1000000*

1. Sur l’organisateur **Actions de l’instruction d’emplacement**, ajoutez une ligne et définissez la valeur suivante :

    - **Nom :** *Pass*

1. Sur l’organisateur **Actions d’instruction d’emplacement**, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue de l’éditeur de requêtes.
1. Dans l’onglet **Plage**, définissez les valeurs suivantes :

    - **Table :** *Emplacements*
    - **Champ :** *ID zone*
    - **Critères :** *En bloc*

1. Sélectionnez **OK** pour enregistrer la requête et fermer la boîte de dialogue.
1. Sur le volet Action, sélectionnez **Enregistrer** pour enregistrer la requête ainsi que la nouvelle instruction d’emplacement.
1. Créez une seconde instruction d’emplacement et définissez les valeurs suivantes :

    - **Nom :** *51 Échec*
    - **Type de travail :** *Put*
    - **Site :** *5*
    - **Entrepôt :** *51*

1. Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue de l’éditeur de requêtes.
1. Dans l’onglet **Plage**, définissez les valeurs suivantes :

    - **Table :** *Ordres de qualité*
    - **Champ :** *Statut*
    - **Critères :** *Échec*

1. Sélectionnez **OK** pour enregistrer la requête et fermer la boîte de dialogue.
1. Sur l’organisateur **Lignes**, ajoutez une ligne et définissez les valeurs suivantes :

    - **Quantité de départ :** *1*
    - **Quantité d’arrivée :** *1000000*

1. Sur l’organisateur **Actions de l’instruction d’emplacement**, ajoutez une ligne et définissez la valeur suivante :

    - **Nom :** *Échec*

1. Sur l’organisateur **Actions d’instruction d’emplacement**, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue de l’éditeur de requêtes.
1. Dans l’onglet **Plage**, définissez les valeurs suivantes :

    - **Table :** *Emplacements*
    - **Champ :** *ID zone*
    - **Critères :** *Retour*

1. Sélectionnez **OK** pour enregistrer la requête et fermer la boîte de dialogue.
1. Sur le volet Action, sélectionnez **Enregistrer** pour enregistrer la requête ainsi que la nouvelle instruction d’emplacement.

#### <a name="mobile-device-menu-items-for-quality-out"></a>Éléments de menu des appareils mobiles pour une sortie de qualité

1. Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.
1. Sélectionnez le élément de menu de l’appareil mobile **Rangement QMS**.
1. Sur l’organisateur **Classes de travail**, ajoutez l’ID de la classe de travail *QualityPut*.

Les manutentionnaires pourront désormais choisir un travail d’ordre de qualité en utilisant l’élément du menu **Rangement QMS**. Les marchandises qui ont échoué le contrôle de qualité des marchandises peuvent être placées dans un lieu de retour et les marchandises qui ont réussi peuvent être placées dans l’emplacement bulk-001.

#### <a name="summary-your-setup-to-move-goods-from-quality-control"></a>Résumé : Votre configuration pour déplacer les marchandises à partir du contrôle qualité

Vous avez configuré les données de travail et d’emplacement pour l’entrepôt 51 pour vous assurer qu’un travail est créé automatiquement lors de l’achèvement des ordres de qualité. Cette configuration garantit que chaque contenant dont la qualité est contrôlée est déplacé vers un emplacement en bloc ou un emplacement de retour.

### <a name="process-quality-management-work"></a>Travail de gestion de la qualité des processus

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.
1. Sélectionnez le premier ordre de qualité pour les quantités enregistrées.
1. Sélectionnez **Valider**. Le statut du test est mis à jour sur *Échec*.
1. Allez dans **Gestion des entrepôts \> Tout le travail**.
1. Ouvrez le travail que vous venez de créer et notez que la valeur **Type d’ordre de travail** est *Ordre de qualité*. Le travail comprend une ligne où l’emplacement de rangement est *Retour* et le statut est *Échec*. (Si le statut de l’ordre de qualité était *Réussite*, l’emplacement de rangement serait *En bloc* à la place.)
1. Revenez à **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.
1. Sélectionnez le second ordre de qualité pour les articles enregistrés.
1. Sélectionnez **Résultats** au-dessus de la grille inférieure. Mettez à jour la valeur **Quantité de résultats** sur *5* et vérifiez que la valeur **Résultat du test** est remplacée par une coche.
1. Cliquez sur **Valider**, puis fermez la page.
1. De retour sur la page **Ordres de qualité**, sélectionnez **Valider** et faites la validation. Le statut est mis à jour sur *Réussite*.

    > [!NOTE]
    > L’événement de validation déclenche la création du travail d’ordre de qualité pour déplacer la quantité de l’emplacement de contrôle qualité vers un nouvel emplacement.

1. Allez dans **Gestion des entrepôts \> Tout le travail**.
1. Sélectionnez le travail qui vient d’être créé et notez qu’un deuxième en-tête de travail d’ordre de qualité a été créé, où l’emplacement de rangement est *BULK-001*.
1. Accédez à un appareil mobile ou à un émulateur qui exécute l’application mobile Gestion des entrepôts et connectez-vous à l’entrepôt 51 avec l’ID utilisateur *51* et le mot de passe *1*.
1. Aller à **Qualité \> Ranger à partir de QMS** et traitez chacun des contenants liés aux deux éléments de travail, de sorte que tout le travail soit fermé.

> [!NOTE]
> Envisagez d’ajouter l’entrée de sortie de qualité à un élément de menu de l’appareil mobile où le code d’activité est *Afficher la liste de travail ouverte*. Pour obtenir un exemple, voir l’élément de menu d’appareil mobile nommé **Liste de travail** dans les données de démonstration. Ajoutez d’abord la classe de travail *Ordre de qualité* à un élément de menu dirigé par l’utilisateur, car cette classe de travail est nécessaire pour que le travail soit affiché dans la liste de travail. Ajoutez ensuite la classe de travail *Ordre de qualité* à l’élément du menu **Liste de travail**. Les utilisateurs qui ont accès à la liste des travaux pourront ensuite sélectionner et traiter le travail généré automatiquement par la validation de l’ordre de qualité.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]