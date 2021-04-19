---
title: Activer un calcul de taxe différé sur les journaux
description: Cette rubrique explique comment activer la fonctionnalité Différer un calcul de taxe pour améliorer les performances du calcul de taxe lorsque le volume de lignes de journal est très important.
author: ericwang
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: acf5ead6ed90d4dbb41de08520cde8085a7f3935
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823714"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a>Activer un calcul de taxe différé sur les journaux
[!include [banner](../includes/banner.md)]


Cette rubrique explique comment différer le calcul de la taxe sur les journaux. Cette capacité aide à améliorer les performances des calculs de taxe lorsqu’il existe plusieurs lignes de journal.

Par défaut, les montants de taxe sur les lignes de journal sont calculés lorsque des champs liés aux taxes sont mis à jour. Ces champs comprennent les champs de groupes de taxes et les groupes de taxes d’articles. Toute mise à jour d’une ligne de journal provoque le recalcul des montants de taxe pour toutes les lignes de journal. Bien que ce comportement permette à l’utilisateur de voir les montants de taxe calculés en temps réel, cela peut également affecter les performances si le nombre de lignes de journal est très importante.

La fonction Calcul de taxe différé permet de retarder le calcul de taxe sur les journaux et donc de corriger les problèmes de performances. Lorsque cette fonction est activée, les montants des taxes sont calculés uniquement lorsqu’un utilisateur sélectionne **Taxe** ou valide le journal.

Vous pouvez retarder le calcul des taxes à trois niveaux :

- Entité juridique
- Nom de journal
- En-tête de journal

Le système octroie la priorité au paramètre de l’en-tête du journal. Par défaut, ce paramètre provient du nom du journal. Par défaut, le paramètre du nom du journal provient du paramètre sur la page **Paramètres de comptabilité** lorsque le nom du journal est créé. Les sections suivantes expliquent la procédure d’activation du calcul de taxe différé pour les entités juridiques, les noms de journaux, et les en-têtes de journal.

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a>Activez le calcul de taxe différé au niveau de l’entité juridique

1. Accédez à **Comptabilité \> Paramétrage de la comptabilité \> Paramètres de comptabilité**.
2. Sous l’onglet **Taxe**, sous l’organisateur **Général**, définissez l’option **Calcul de la taxe différé** sur **Oui**.

![Image des paramètres de comptabilité](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a>Activez le calcul de taxe différé au niveau du nom du journal

1. Accédez à **Comptabilité \> Paramétrage du journal \> Noms des journaux**.
2. Sous l’organisateur **Général**, dans la section **Taxe**, définissez l’option **Calcul de la taxe différé** sur **Oui**.

![Images des noms des journaux](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a>Activez le calcul de taxe différé au niveau de l’en-tête du journal

1. Allez dans **Comptabilité \> Entrées de journal \> Journaux des opérations diverses**.
2. Sélectionnez **Nouveau**.
3. Sélectionner un nom de journal.
4. Dans l’onglet **Paramétrage**, définissez l’option **Calcul de la taxe différé** sur **Oui**.

![Image de la page du journal des opérations diverses](media/delayed-tax-calculation-journal-header.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]