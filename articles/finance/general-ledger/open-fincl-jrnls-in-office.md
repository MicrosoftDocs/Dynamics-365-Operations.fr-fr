---
title: Ouvrir des modèles de journal financier dans Office
description: Cette rubrique décrit les problèmes qui peuvent se produire lorsque vous créez des journaux financiers personnalisés à l’aide d’un modèle Microsoft Excel.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 099d3c0074a86913b79b732a4c2a34b6e6488672
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2022
ms.locfileid: "8723076"
---
# <a name="open-financial-journal-templates-in-office"></a>Ouvrir des modèles de journal financier dans Office

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les problèmes qui peuvent se produire lorsque vous créez des journaux financiers personnalisés à l’aide d’un modèle Microsoft Excel.

## <a name="symptom"></a>Problème

Vous avez créé un modèle Excel personnalisé pour les journaux financiers, mais il n’apparaît pas dans le menu **Ouvrir les lignes dans Excel**. Ou bien, il apparaît dans le menu, mais un autre modèle est ouvert lorsque vous le sélectionnez.

## <a name="resolution"></a>Résolution

La fonctionnalité Ouvrir dans Excel par défaut utilise la source de données racine (table) de la page actuelle pour déterminer les modèles Office ou les entités de données qui apparaissent comme options dans le menu **Ouvrir dans Excel**. Ce comportement n’est pas une expérience idéale pour les journaux financiers, car ces derniers utilisent les mêmes tables (LedgerJournalTable et LedgerJournalTrans) comme source de données racine de nombreux autres types de journaux.

Pour les journaux financiers, la fonctionnalité Ouvrir les lignes dans Excel est destinée à afficher des modèles conçus pour le journal dans le contexte duquel vous travaillez actuellement, comme le journal des opérations diverses ou un journal des paiements. Par exemple, un modèle destiné à être utilisé avec un journal des paiements fournisseur sera conçu pour appliquer votre compte principal comme compte fournisseur.

Si vous souhaitez promouvoir un modèle afin qu’il soit disponible dans les menus **Ouvrir les lignes dans Excel** et **Ouvrir dans Excel**, une expérience simple pour les développeurs consiste à implémenter l’interface **LedgerIJournalExcelTemplate** et à étendre la classe **DocuTemplateRegistrationBase**. De nombreux exemples de cette approche sont implémentés dans le système. Un exemple qui peut servir de référence est l’interface **LedgerDailyJournalExcelTemplate** créée pour le journal des opérations diverses (ou le journal quotidien).

Lorsque l’interface **LedgerIJournalExcelTemplate** est implémentée pour votre modèle, le menu **Ouvrir les lignes dans Excel** filtrera les modèles selon le type de votre journal et n’affichera que les modèles disponibles pour ce journal. L’interface fournit également une méthode de validation qui garantit qu’un modèle ne peut pas être ouvert pour un journal s’il ne répond pas aux exigences du type de compte. Par exemple, vous pouvez spécifier que le type de compte doit être **Fournisseur** ou **Général**.

Pour plus d’informations sur cette fonctionnalité, consultez [Ajouter des modèles au menu Ouvrir les lignes dans Excel](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).
