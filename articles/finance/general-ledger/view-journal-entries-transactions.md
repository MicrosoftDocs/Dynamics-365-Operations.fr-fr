---
title: Afficher les entrées de journal et les transactions
description: Cet article explique les différentes manières dont vous pouvez afficher les entrées de journal et les transactions.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13031
ms.assetid: 281c7ea6-4dfd-4d1f-994f-c361ee299dbe
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 79329b60f0aa7ce196b55a1483b07f8b9ea7e3cf
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443174"
---
# <a name="view-journal-entries-and-transactions"></a>Afficher les entrées de journal et les transactions

[!include [banner](../includes/banner.md)]

Cet article explique les différentes manières dont vous pouvez afficher les entrées de journal et les transactions. 

Les utilisateurs qui souhaitent afficher les journaux et les transactions peuvent accéder aux données selon plusieurs méthodes. Ils peuvent tirer profit des pages de recherche qui permettent d’accéder aux détails ou utiliser diverses options d’état dans la comptabilité.

## <a name="voucher-transactions"></a>Pièces comptables
**Transactions de N° document** est une page de recherche dans laquelle vous pouvez sélectionner des tables et des champs divers pour spécifier les critères du solde ou de la transaction que vous recherchez. Par exemple, vous pouvez afficher toutes les transactions pour une date ou un compte spécifique, ou toutes les transactions du type **Exécution** qui figurent dans une couche de validation spécifique. Par défaut, la page affiche le numéro de journal, le n° document, la date, puis le compte principal, mais vous pouvez ajouter des tables, des champs et des critères supplémentaires pour affiner votre recherche.

## <a name="audit-trail"></a>Piste d’audit
**Piste d’audit** est une page de recherche qui indique les types de transactions, des descriptions, l’auteur par qui les transactions ont été créées, et quand elles ont été créées. À partir de la page de recherche **Piste d’audit**, vous pouvez afficher les transactions de N° document.

## <a name="financial-reports"></a>États financiers
Vous pouvez également explorer et analyser les écritures comptables en exécutant les états financiers. Étant donné que la création d’états financiers peut être basée sur des comptes, des dimensions, des catégories de compte ou une combinaison des trois, vous pouvez afficher les transactions selon diverses méthodes d’accès. Si vous avez besoin de plus d’informations sur les écritures comptables, vous pouvez également inclure plusieurs propriétés de transaction dans le cadre de la création d’état. De même, si vous souhaitez afficher les transactions qui constituent un solde comptable, vous pouvez accéder aux détails des transactions du compte, comme vous pouvez le faire à partir de la page de liste **Balance comptable**.

## <a name="ledger-reports"></a>États de comptabilité
Outre les états financiers, vous pouvez utiliser les états suivants de comptabilité pour afficher les transactions de comptabilité :

-   **Relevé de dimension** – Cet état affiche les transactions par jour et par compte et contient également des options pour afficher les transactions par dimension et période.
-   **Liste des écritures comptables** – Cet état affiche les transactions dans les devises de transaction, comptables et de déclaration pour un compte.
-   **Journal d’impression** – Cet état affiche le résultat d’un journal validé. Vous pouvez exécuter la génération d’état par numéro de lot ou le type de journal, ou ajouter des champs supplémentaires.
-   **Transactions validées par journal** – Cet état affiche les transactions validées dans un journal, regroupées par document.
-   **Liste des transactions par date** – Cet état affiche toutes les transactions par date, ainsi que le numéro de journal, le N° document et le compte général. Il indique également les transactions dans les devises de transaction, comptables et de déclaration.
-   **Origine de la transaction** – Cet état de transaction affiche le compte par journal, et par devise de transaction, comptable et de déclaration. Il indique également chaque ligne du journal qui a été utilisé comme contrepartie.


## <a name="additional-resources"></a>Ressources supplémentaires
- [Soldes de la comptabilité](general-ledger-account-balances.md) 
- [Explorateur de comptabilité source](../accounts-payable/accounting-source-explorer.md)
- [Vue d’ensemble des états financiers](financial-reporting-getting-started.md)
- [Afficher les entrées de journal ou les transactions](tasks/view-journal-entries-or-transactions.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]