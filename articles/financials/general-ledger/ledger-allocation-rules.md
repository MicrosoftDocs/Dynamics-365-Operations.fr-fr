---
title: Règles d'affectation comptable
description: Cet article fournit des informations générales sur les règles de répartition comptable. Il décrit les différents composants de ces règles de répartition et les méthodes de répartition utilisables pour elles.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: abbeb1bb4481139dff902916362a479f94fb96e5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "365728"
---
# <a name="ledger-allocation-rules"></a>Règles d'affectation comptable

[!include [banner](../includes/banner.md)]

Cet article fournit des informations générales sur les règles de répartition comptable. Il décrit les différents composants de ces règles de répartition et les méthodes de répartition utilisables pour elles.

Les règles de répartition comptable permettent de calculer et de générer automatiquement les journaux de répartition et les écritures de compte pour la répartition des soldes comptables ou des montants fixes. Les modes de répartition peuvent être variables ou fixes. Les modes de répartition suivants peuvent être utilisés pour les règles de répartition comptable :

-   **Base** – Cette méthode variable est utilisée lorsque la répartition dépend du solde comptable réel, basé sur des critères de filtre. Par exemple, les dépenses publicitaires peuvent être réparties sur la base des ventes de chaque département par rapport aux ventes totales du département.
-   **Pourcentage fixe** et **Poids fixe** – Pour ces méthodes, le pourcentage ou le poids de répartition est défini directement pour la règle. Par exemple, les dépenses publicitaires peuvent être réparties de telle sorte que le département A reçoit 70 % des dépenses publicitaires et le département B 30 %.
-   **Valeurs égales** – Cette méthode répartit équitablement le montant sur chaque destination définie. Par exemple, si les destinations sont définies pour le département A et le département B, les dépenses publicitaires peuvent être affectées de telle sorte que le département A et le département B reçoivent 50 % des dépenses publicitaires.

Si Base est utilisé comme mode de répartition pour une règle de répartition, vous devez également définir des règles de base de répartition comptable distinctes. Le processus « Traiter la demande de répartition » permet aux utilisateurs de traiter la règle de répartition comptable et d'afficher un aperçu des écritures de journal de répartition générées avant de valider ou de supprimer les répartitions calculées.

## <a name="components-of-ledger-allocation-rules"></a>Composants des règles de répartition comptable
Chaque règle de répartition contient quatre composants : général, source, destination et contrepartie. Un composant supplémentaire, règles de base de répartition comptable, est nécessaire si Base est utilisé comme mode de répartition. Chaque composant fournit une partie essentielle des informations nécessaires pour traiter les répartitions.

-   **Général** – Ce composant est l'endroit où l'utilisateur spécifie des options telles que le mode de répartition, les paramètres de la règle intersociétés et l'activation ou non de la règle.
-   **Source** – Ce composant est l'endroit où l'utilisateur spécifie les données source pour la répartition. La répartition peut être basée sur les soldes comptables (**Source de données** = **Comptabilité**) ou des montants fixes (**Source de données** = **Valeur fixe**). Lorsque **Source de données** est défini sur **Comptabilité**, les critères de filtre source doivent être définis pour la règle de répartition comptable (par exemple, pour les dépenses publicitaires).
-   **Destination** – Ce composant définit la manière dont le résultat du calcul de la répartition doit être distribué et comptabilisé. Par exemple, il peut y avoir une ligne de destination pour chaque département.
-   **Contrepartie** – Ce composant définit la manière dont les comptes principaux et les dimensions doivent être déterminés pour les entrées de contrepartie qui soldent les entrées de destination. Les options définies par l'utilisateur sont généralement utilisées à la place des comptes et dimensions basés sur la source. Lorsque **Source de données** est défini sur **Valeur fixe**, **Source** ne peut pas être utilisé comme option.
-   **Règles de base de répartition comptable** – Ces règles utilisent leurs propres critères de filtre source pour déterminer les soldes comptables à utiliser pour la répartition (par exemple, le produit par département). Chaque règle de base de répartition peut être utilisée avec plusieurs règles de répartition.




