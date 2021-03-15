---
title: Nombre de registres par journal
description: Cette rubrique décrit la relation entre les journaux et les registres d’immobilisations lorsque vous créez une acquisition d’immobilisations ou une proposition d’amortissement via un traitement par lots. Vous pouvez définir le nombre maximum de registres inclus pour chaque acquisition et pour l’amortissement.
author: moaamer
manager: Ann Beebe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-19
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: cfb9a9e1456a7d9067e3c4369a7eb7150326655d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988950"
---
# <a name="number-of-books-per-journal"></a>Nombre de registres par journal

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la relation entre les journaux et les registres d’immobilisations lorsque vous créez une acquisition d’immobilisations ou une proposition d’amortissement via un traitement par lots. Vous pouvez définir le nombre maximal de registres inclus pour chaque acquisition et pour l’amortissement en utilisant les champs de la section **Nombre de registres par journal** sur l’onglet **Général** de la page **Paramètres des immobilisations** (**Immobilisations \> Configurer \> Paramètres des immobilisations**). Ces champs vous permettent de répartir le nombre de registres d’immobilisation par journal d’acquisition et journal d’amortissement.

Pour une proposition d’acquisition, la valeur par défaut est d’au moins 10 000 registres. Pour une proposition d’amortissement, la valeur par défaut est d’au moins 2 000 registres.

Par exemple, s’il y a 4 000 immobilisations et que deux registres sont associés à chaque actif, un registre sera publié dans la couche actuelle et l’autre registre sera publié dans la couche fiscale. Si vous acquérez 4 000 immobilisations via un traitement par lots, le traitement par lots qui crée un journal d’acquisition d’immobilisations contiendra 4 000 registres d’immobilisations.

> [!NOTE]
> Le journal qui est créé continuera d’être utilisé jusqu’à ce que le travail par lots soit terminé.
>
> Les registres dérivés ne sont pas inclus dans le nombre maximum de registres par revue.

Vous pouvez utiliser le traitement par lots pour exécuter l’amortissement pour le même ensemble d’immobilisations acquises. Par exemple, un traitement par lots crée deux journaux d’amortissement, chacun se composant de 2 000 registres d’immobilisations. Le premier journal contiendra des registres associés aux immobilisations numérotées de 1 à 2 000. Le second journal contiendra alors des registres associés aux immobilisations numérotées de 2 001 à 4 000.

Le travail de traitement par lots exclut les registres fermés. Par exemple, dans un traitement par lots pour l’amortissement, 10 des 2 000 premiers registres sont fermés. Dans le cas, le premier journal contiendra des registres associés aux immobilisations numérotées de 1 à 2 011. Le second journal contiendra alors des registres associés aux immobilisations numérotées de 2 012 à 4 000.

La limite du nombre de registres est appliquée si les ID d’éléments en double n’existent pas dans le même journal. Cependant, si l’ID d’actif est le même que l’ID de registres, le nombre de registres par journal peut être dépassé pour conserver l’ID d’actif dans le même journal.

Par exemple, il existe 5 001 ID d’immobilisation, trois registres sont associés à chaque ID d’immobilisation et chaque registre d’immobilisation est enregistré dans la même couche de comptabilisation. Vous exécutez l’amortissement pendant trois mois consécutifs, sans synthèse.  Le journal d’amortissement sera créé via un traitement par lots, et le système créera sept journaux contenant 667 ID d’immobilisation et trois registres pour chaque ID d’immobilisation. Le résultat sera 2 001 registres. Par conséquent, dans trois mois, il y aura 6 003 lignes de journal pour conserver les mêmes ID d’actif dans le même journal. Le système créera également un journal contenant 332 ID d’immobilisation et trois registres pour chaque ID d’immobilisation. Dans trois mois, il y aura 2 988 lignes.

> [!Note] 
> Si le paramètre **Cumuler l’amortissement** est activé lorsque vous créez une proposition d'amortissement, alors la valeur du champ **Nombre de registres par journal - Proposition d'amortissement** n'a aucun effet. Dans ce cas, le nombre de livres par journal est de 6000, qui est la limite interne définie.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]