---
title: Nombre de registres par journal
description: Cet article décrit la relation entre les journaux et les registres d’immobilisations lorsque vous créez une acquisition d’immobilisations ou une proposition d’amortissement via un traitement par lots. Vous pouvez définir le nombre maximum de registres inclus pour chaque acquisition et pour l’amortissement.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-19
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2dbd50963cf13f00e09b82e884cd8ebc0b67d424
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883327"
---
# <a name="number-of-books-per-journal"></a>Nombre de registres par journal

[!include [banner](../includes/banner.md)]

Cet article décrit la relation entre les journaux et les registres d’immobilisations lorsque vous créez une acquisition d’immobilisations ou une proposition d’amortissement via un traitement par lots. Vous pouvez définir le nombre maximal de registres inclus pour chaque acquisition et pour l’amortissement en utilisant les champs de la section **Nombre de registres par journal** sur l’onglet **Général** de la page **Paramètres des immobilisations** (**Immobilisations \> Paramétrage \> Paramètres des immobilisations**). Ces champs vous permettent de répartir le nombre de registres d’immobilisation par journal d’acquisition et journal d’amortissement.

Pour une proposition d’acquisition, la valeur par défaut est d’au moins 10 000 registres. Pour une proposition d’amortissement, la valeur par défaut est d’au moins 2 000 registres.

Par exemple, s’il y a 4 000 immobilisations et que deux registres sont associés à chaque actif, un registre sera publié dans la couche actuelle et l’autre registre sera publié dans la couche fiscale. Si vous acquérez 4 000 immobilisations via un traitement par lots, le traitement par lots qui crée un journal d’acquisition d’immobilisations contiendra 4 000 registres d’immobilisations.

> [!NOTE]
> Le journal qui est créé continuera d’être utilisé jusqu’à ce que le travail par lots soit terminé.
>
> Les registres dérivés ne sont pas inclus dans le nombre maximum de registres par revue.

Vous pouvez utiliser le traitement par lots pour exécuter l’amortissement pour le même ensemble d’immobilisations acquises. Par exemple, un traitement par lots crée deux journaux d’amortissement, chacun se composant de 2 000 registres d’immobilisations. Le premier journal contiendra des registres associés aux immobilisations numérotées de 1 à 2 000. Le second journal contiendra alors des registres associés aux immobilisations numérotées de 2 001 à 4 000.

Le travail de traitement par lots exclut les registres fermés. Par exemple, dans un traitement par lots pour l’amortissement, 10 des 2 000 premiers registres sont fermés. Dans le cas, le premier journal contiendra des registres associés aux immobilisations numérotées de 1 à 2 011. Le second journal contiendra alors des registres associés aux immobilisations numérotées de 2 012 à 4 000.

> [!NOTE]
> Si vous avez des ID d’immobilisation avec des séparateurs différents (tels que – ou /) et que vous créez des transactions d’immobilisation dans des traitements par lots, vous devez exécuter un traitement par lots distinct pour chaque type de séparateur. Le système ne peut pas traiter différents séparateurs dans le même traitement par lots.

La limite du nombre de registres est appliquée si les ID d’éléments en double n’existent pas dans le même journal. Cependant, si l’ID d’actif est le même que l’ID de registres, le nombre de registres par journal peut être dépassé pour conserver l’ID d’actif dans le même journal.

Par exemple, il existe 5 001 ID d’immobilisation, trois registres sont associés à chaque ID d’immobilisation et chaque registre d’immobilisation est enregistré dans la même couche de comptabilisation. Vous exécutez l’amortissement pendant trois mois consécutifs, sans synthèse.  Le journal d’amortissement sera créé via un traitement par lots, et le système créera sept journaux contenant 667 ID d’immobilisation et trois registres pour chaque ID d’immobilisation. Le résultat sera 2 001 registres. Par conséquent, dans trois mois, il y aura 6 003 lignes de journal pour conserver les mêmes ID d’actif dans le même journal. Le système créera également un journal contenant 332 ID d’immobilisation et trois registres pour chaque ID d’immobilisation. Dans trois mois, il y aura 2 988 lignes.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
