---
title: Principes de réduction des remises
description: Cette rubrique décrit la procédure de configuration des principes de réduction. Les principes de réduction contrôlent le comportement de l’application de plusieurs remises à un même article ou une même transaction.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 5a8bbfaff05b665cb85e9166cfc76363c4aedb64
ms.sourcegitcommit: 890a0b3eb3c1f48d786b0789e5bb8641e0b8455e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5919841"
---
# <a name="rebate-reduction-principles"></a>Principes de réduction des remises

[!include [banner](../includes/banner.md)]

Vous pouvez regrouper les accords de gestion des remises en *principes de réduction* pour réduire les autres provisions associées à un article et/ou pour réduire les valeurs résultantes des calculs de remise. Une fois les principes de réduction des remises définis, vous pouvez éventuellement les affecter, selon vos besoins, aux lignes de vos accords de gestion des remises.

Les règles du principe de réduction de remise ne s’appliquent que lorsque des accords de remise se chevauchent. Par conséquent, elles peuvent accorder plusieurs remises dans des situations où plusieurs remises ne sont pas dues.

## <a name="manage-rebate-reduction-principles"></a>Gérer les principes de réduction des remises

Pour utiliser les principes de réduction des remises, accédez à **Gestion des remises \> Paramétrage \> Principes de réduction des remises**. Utilisez ensuite les boutons du volet Actions pour ajouter et supprimer des principes de réduction selon vos besoins. Pour chaque principe, définissez les champs comme décrit dans le tableau suivant.

| Champ | Description |
|---|---|
| Principe de réduction des remises | Saisissez un nom unique pour le principe de réduction de remise. |
| Description | Saisissez une description pour le principe de réduction de remise. |
| Appliquer la réduction | Cochez cette case pour appliquer une base de réduction aux remises qui appartiennent à ce principe de réduction de remise. |
| Base de réduction | Si vous avez coché la case **Appliquer la réduction**, sélectionnez la base de réduction (*Provision*, *Remises*, ou *Les deux*). Si vous sélectionnez *Les deux*, et si une provision et une remise ont été validés pour un accord précédent, seule la remise sera appliquée. |
| Exclure de la réduction | Si cette case est cochée, les provisions et remises qui appartiennent à ce principe de réduction de remise seront exclues des réductions ultérieures. Le paramètre du champ **Base de réduction** ne s’applique pas à ce paramètre. |

## <a name="examples-of-rebate-reduction-principle-setups"></a>Exemples de configurations de principe de réduction de remise

Le tableau suivant montre quelques exemples typiques de configurations de principe de réduction de remise. Pour chacun de ces principes de réduction de remise, la valeur du champ **Description** décrit le but du principe de réduction de remise.

| principe de réduction des remises | Description | Appliquer la réduction | Base de réduction | Exclure de la réduction |
|---|---|---|---|---|
| Différé | Réduire la remise | Oui | Les deux | N° |
| Exclreb | Exclure la remise | Oui | Remise | Oui |
| Quantité multiple | Plusieurs remises | Oui | Les deux | Oui |
| None | Provision et remise seulement | N° | Les deux | Oui |
| Mise en service | Provision seulement | Oui | Mise en service | N° |
| Remise | Remise seulement | Oui | Remise | Oui |

## <a name="examples-of-rebate-reduction-principle-calculations"></a>Exemples de calculs de principe de réduction de remise

Vous avez une commande client qui comporte une seule ligne de commande client. Cette ligne a une valeur de 1000 USD. Les accords suivants s’appliquent à la commande :

- **Accord 1 :** 10 pour cent sur 1000 USD
- **Accord 2 :** 15 pour cent sur 1000 USD
- **Accord 3 :** 20 pour cent sur 1000 USD
- **Accord 4 :** 25 pour cent sur 1000 USD

L’ordre de traitement est très important. L’ordre de traitement est basé sur la façon dont vous travaillez, comme décrit dans [Traiter, examiner et valider les remises](process-review-post.md).

Par exemple, le tableau suivant résume le résultat si vous utilisez l’ordre *1, 2, 3, 4*, et si vous ne traitez que les provisions.

| Transaction | Description et paramètres | Résultat de la provision |
|---|---|---|
| 1 | <p>La classification ne vérifie pas les autres accords pour les réductions. Le contrôle est effectué à la fois pour les provisions et les remises.</p><ul><li>**Appliquer la réduction :** *Non*</li><li>**Base de réduction :** *Les deux*</li><li>**Exclure de la réduction :** *Non*</li></ul> | 1000 USD × 10 % = 100 USD |
| 2 | <p>La classification vérifie les autres accords de réduction, mais est signalée de sorte qu’elle soit elle-même ignorée. Le contrôle est effectué uniquement pour les remises.</p><ul><li>**Appliquer la réduction :** *Oui*</li><li>**Base de réduction :** *Remise*</li><li>**Exclure de la réduction :** *Oui*</li></ul> | 1000 USD × 15 % = 150 USD |
| 3 | <p>La classification vérifie les autres accords pour les réductions. Le contrôle est effectué à la fois pour les provisions et les remises.</p><ul><li>**Appliquer la réduction :** *Oui*</li><li>**Base de réduction :** *Les deux*</li><li>**Exclure de la réduction :** *Non*</li></ul> | (1000 USD – Accord 1) × 20 % = 180 USD |
| 4 | <p>La classification vérifie les autres accords pour les réductions. Le contrôle est effectué à la fois pour les provisions et les remises.</p><ul><li>**Appliquer la réduction :** *Oui*</li><li>**Base de réduction :** *Les deux*</li><li>**Exclure de la réduction :** *Non*</li></ul> | (1000 USD – Accord 1 – Accord 3) × 25 % = 180 USD |

Le tableau suivant montre quelques exemples où la provision est traitée dans selon différents ordres, et où différents totaux sont donc atteints. L’écart dans les provisions dépend de l’ordre dans lequel le système traite les accords. Il est important que vous compreniez comment l’ordre de traitement affecte le montant final de la remise.

| Ordre | Calcul |
|---|---|
| 1<br>(1, 2, 3, 4) | <ul><li>**Accord 1 :** 1000 USD × 10 % = 100 USD</li><li>**Accord 2 :** 1000 USD × 15 % = 150 USD</li><li>**Accord 3 :** (1000 USD – Accord 1) × 20 % = 180 USD</li><li>**Accord 4 :** (1000 USD - Accord 1 - Accord 2) × 25 % = 180 USD</li><li>**Provision totale :** 610 USD</li></ul> |
| 2<br>(4, 3, 2, 1) | <ul><li>**Accord 4 :** 1000 x 25 % = 250 USD</li><li>**Accord 3 :** (1000 USD – Accord 4) × 20 % = 150 USD</li><li>**Accord 2 :** 1000 x 15 % = 150 USD</li><li>**Accord 1 :** 1000 x 10 % = 100 USD</li><li>**Provision totale :** 650 USD</li></ul> |
| 3<br>(3, 2, 1, 4) | <ul><li>**Accord 3 :** 1000 x 20 % = 200 USD</li><li>**Accord 2 :** 1000 x 15 % = 150 USD</li><li>**Accord 1 :** 1000 x 10 % = 100 USD</li><li>**Accord 4 :** (1000 USD - Accord 3 - Accord 1) × 25 % = 175 USD</li><li>**Provision totale :** 625 USD</li></ul> |
| 4<br>(2, 4, 1, 3) | <ul><li>**Accord 2 :** 1000 USD × 15 % = 150 USD</li><li>**Accord 4 :** 1000 USD × 25 % = 250 USD</li><li>**Accord 1 :** 1000 USD × 10 % = 100 USD</li><li>**Accord 3 :** (1000 USD - Accord 4 - Accord 1) × 20 % = 130 USD</li><li>**Provision totale :** 630 USD</li></ul> |
