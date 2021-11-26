---
title: Vue d’ensemble des séquences de nombres
description: Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transactions qui en exigent.
author: SunilGarg
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceConfiguration
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "15461"
- intro-internal
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d65eb3824cfa158e6b382ee7bae2c86aab9396b
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778327"
---
# <a name="number-sequences-overview"></a>Vue d’ensemble des séquences de nombres

[!include [banner](../includes/banner.md)]

Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transactions qui en exigent. Un enregistrement de données principales ou de transaction nécessitant un identificateur est également appelé *référence*.

Avant de pouvoir créer des enregistrements pour une référence, vous devez paramétrer une souche de numéros et l’associer à la référence. Nous vous recommandons d’utiliser les pages du module **Administration d’organisation** pour paramétrer les souches de numéros. Si des paramètres spécifiques au module sont requis, vous pouvez utiliser la page des paramètres d’un module pour spécifier les souches de numéros pour les références dans ce module. Par exemple, dans les modules **Comptabilité client** et **Comptabilité fournisseur** , vous pouvez paramétrer des groupes de souches de numéros pour attribuer des souches de numéros spécifiques à des clients ou fournisseurs donnés.

Lorsque vous paramétrez une souche de numéros, vous devez spécifier une portée, qui définit l’organisation qui l’utilise. La portée peut être **Partagée**, **Société**, **Entité juridique** ou **Unité opérationnelle**. Les portées **Entité juridique** et **Société** peuvent également être combinées avec **Période de calendrier fiscal** pour créer des souches de numéros encore plus spécifiques.

Les formats de souches de numéros sont composés de segments. Les souches de numéros dotées d’une portée autre que **Partagée** peuvent contenir des segments qui correspondent à la portée. Par exemple, une souche de numéros dotée du type de portée **Entité juridique** peut contenir un segment d’entité juridique. En incluant un segment de portée dans le format de souche de numéros, vous pouvez identifier la portée d’un enregistrement particulier en consultant son numéro.

Outre les segments qui correspondent aux portées, les formats de souche de numéros peuvent contenir les segments **Constante** et **Alphanumérique**. Un segment **Constante** contient un ensemble de lettres, de nombres ou de symboles qui ne change pas. Un segment **Alphanumérique** contient un ensemble de lettres ou de nombres qui est incrémenté à chaque fois qu’un nombre est utilisé. Utilisez un symbole numérique (\#) pour représenter les numéros de l’incrémentation et une esperluette (&) pour représenter les lettres de l’incrémentation. Par exemple, le format \#\#\#\#\#\_2017 crée la séquence 00001\_2017, 00002\_2017, etc.

## <a name="number-sequence-examples"></a>Exemples de souches de numéros

Les exemples suivants indiquent comment utiliser les segments pour créer des formats de souches de numéros. Ils démontrent notamment les effets de l’utilisation des segments de portée.

### <a name="expense-report-numbers"></a>Numéros d’états de dépenses

Dans l’exemple suivant, les numéros d’états de dépenses sont paramétrés pour l’entité juridique **CS**.

- **Secteur :** Déplacements et dépenses
- **Référence :** Numéro de l’état de dépenses
- **Portée :** Entité juridique
- **Entité juridique :** CS

| Segments  | Type de segment | Valeur     |
|-----------|--------------|-----------|
| Segment 1 | Entité juridique | CS        |
| Segment 2 | Constante     | -DÉPENSES- |
| Segment 3 | Alphanumérique | \#\#\#\#  |

**Exemple de numéro mis en forme** : CS-EXPENSE-0039

Vous pouvez paramétrer un format de souche de numéros similaire pour d’autres entités juridiques. Par exemple, pour l’entité juridique **RW**, si vous modifiez uniquement la valeur du segment d’entité juridique, le numéro mis en forme est RW-EXPENSE-0039. Vous pouvez également modifier l’ensemble du format de souche de numéros pour d’autres entités juridiques. Par exemple, vous pouvez omettre le segment de portée d’entité juridique pour créer un numéro mis en forme tel que Exp-0001.

### <a name="sales-order-numbers"></a>Numéros de commandes client

Dans l’exemple suivant, les numéros de commandes client sont paramétrés pour l’ID société **CEU**.

- **Secteur :** Ventes
- **Référence :** Commande client
- **Portée :** Société
- **Société :** CEU

| Segments  | Type de segment | Valeur    |
|-----------|--------------|----------|
| Segment 1 | Constante     | SO-      |
| Segment 2 | Alphanumérique | \#\#\#\# |

**Exemple de numéro mis en forme** : SO-0029

Même si un segment de portée n’est pas inclus dans le format, la numérotation redémarre pour chaque ID société. Si vous utilisez le même format pour tous les ID société, les mêmes numéros sont utilisés dans chaque société. Par exemple, le numéro de commande client SO-0029 est utilisé dans chaque société. Vous pouvez également modifier l’ensemble du format de souche de numéros pour d’autres ID société.

### <a name="purchase-requisition-numbers"></a>Numéros de demandes d’achat

Dans l’exemple suivant, les numéros de demandes d’achat fonctionnent dans l’ensemble de l’organisation.

- **Secteur :** Achat
- **Référence :** Demande d’achat
- **Portée :** Partagée

| Segments  | Type de segment | Valeur    |
|-----------|--------------|----------|
| Segment 1 | Constante     | Req      |
| Segment 2 | Alphanumérique | \#\#\#\# |

**Exemple de numéro mis en forme** : Req0052

Comme la portée est **Partagée**, le format de souche de numéros est utilisé dans l’ensemble de l’organisation. Vous ne pouvez pas paramétrer différents formats de souches de numéros pour différentes parties de l’organisation.

## <a name="performance-considerations-for-number-sequences"></a>Remarques importantes relatives aux performances des souches de numéros

Avant de paramétrer des souches de numéros, prenez en compte les informations suivantes sur l’impact de la configuration des souches de numéros sur les performances.

### <a name="continuous-and-non-continuous-number-sequences"></a>Souches de numéros continues et non continues

Les souches de numéros peuvent être continues ou non continues. Une souche de numéros continue ne saute aucun numéro, mais les numéros peuvent ne pas être utilisés dans l’ordre. Les numéros d’une souche de numéros non continue sont utilisés dans l’ordre, mais la souche de numéros peut sauter des numéros. Par exemple, si un utilisateur annule une transaction, un numéro est généré, mais n’est pas utilisé. Dans une souche de numéros continue, ce numéro est recyclé ultérieurement. Dans une souche de numéros non continue, le numéro n’est pas utilisé.

Les souches de numéros continues sont généralement requises pour les documents externes, tels que les commandes fournisseur, les commandes client et les factures. Cependant, les souches de numéros continues peuvent réduire le temps de réponse système car le système doit demander un numéro dans la base de données à chaque fois qu’un nouveau document ou enregistrement est créé.

Si vous utilisez une souche de numéros non continue, vous pouvez activer **Préaffectation** dans l’organisateur **Performances** de la page **Souches de numéros**. Lorsque vous spécifiez une quantité de numéros à préaffecter, le système sélectionne ces numéros et les stocke dans la mémoire. De nouveaux numéros sont demandés dans la base de données uniquement après que la quantité préaffectée a été utilisée.

Sauf si des règlementations exigent l’utilisation de souches de numéros continues, il est recommandé d’utiliser des souches de numéros non continues afin de bénéficier de performances optimales.

### <a name="automatic-cleanup-of-number-sequences"></a>Nettoyage automatique des souches de numéros

En cas de panne de courant, d’erreur de l’application ou de panne imprévue, le système ne peut pas recycler les numéros automatiquement pour les souches de numéros continues. Vous pouvez exécuter le processus de nettoyage manuellement ou automatiquement pour récupérer les numéros perdus.

Veillez à tenir compte de l’utilisation du serveur lorsque vous planifiez le processus de nettoyage. Nous vous recommandons d’effectuer le nettoyage en tant que traitement par lots pendant les heures creuses.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
