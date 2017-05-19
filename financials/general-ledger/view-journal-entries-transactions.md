---
title: "Afficher les entrées de journal et les transactions"
description: "Cet article explique les différentes manières dont vous pouvez afficher les entrées de journal et les transactions."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13031
ms.assetid: 281c7ea6-4dfd-4d1f-994f-c361ee299dbe
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 021a74811212f65977407b8454086b0e7b703a2f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="view-journal-entries-and-transactions"></a>Afficher les entrées de journal et les transactions

[!include[banner](../includes/banner.md)]


Cet article explique les différentes manières dont vous pouvez afficher les entrées de journal et les transactions. 

Les utilisateurs qui souhaitent afficher les journaux et les transactions peuvent accéder aux données selon plusieurs méthodes. Ils peuvent tirer profit des pages de recherche qui permettent d'accéder aux détails ou utiliser diverses options d'état dans la comptabilité.

## <a name="voucher-transactions"></a>Pièces comptables
**Transactions de N° document** est une page de recherche dans laquelle vous pouvez sélectionner des tables et des champs divers pour spécifier les critères du solde ou de la transaction que vous recherchez. Par exemple, vous pouvez afficher toutes les transactions pour une date ou un compte spécifique, ou toutes les transactions du type **Exécution** qui figurent dans une couche de validation spécifique. Par défaut, la page affiche le numéro de journal, le n° document, la date, puis le compte principal, mais vous pouvez ajouter des tables, des champs et des critères supplémentaires pour affiner votre recherche.

## <a name="audit-trail"></a>Piste d'audit
**Piste d'audit** est une page de recherche qui indique les types de transactions, des descriptions, l'auteur par qui les transactions ont été créées, et quand elles ont été créées. À partir de la page de recherche **Piste d'audit**, vous pouvez afficher les transactions de N° document.

## <a name="financial-reports"></a>États financiers
Vous pouvez également explorer et analyser les écritures comptables en exécutant les états financiers. Étant donné que la création d'états financiers peut être basée sur des comptes, des dimensions, des catégories de compte ou une combinaison des trois, vous pouvez afficher les transactions selon diverses méthodes d'accès. Si vous avez besoin de plus d'informations sur les écritures comptables, vous pouvez également inclure plusieurs propriétés de transaction dans le cadre de la création d'état. De même, si vous souhaitez afficher les transactions qui constituent un solde comptable, vous pouvez accéder aux détails des transactions du compte, comme vous pouvez le faire à partir de la page de liste **Balance comptable**.

## <a name="ledger-reports"></a>États de comptabilité
Outre les états financiers, vous pouvez utiliser les états suivants de comptabilité pour afficher les transactions de comptabilité :

-   **Relevé de dimension** – Cet état affiche les transactions par jour et par compte et contient également des options pour afficher les transactions par dimension et période.
-   **Liste des écritures comptables** – Cet état affiche les transactions dans les devises de transaction, comptables et de déclaration pour un compte.
-   **Journal d'impression** – Cet état affiche le résultat d'un journal validé. Vous pouvez exécuter la génération d'état par numéro de lot ou le type de journal, ou ajouter des champs supplémentaires.
-   **Transactions validées par journal** – Cet état affiche les transactions validées dans un journal, regroupées par document.
-   **Liste des transactions par date** – Cet état affiche toutes les transactions par date, ainsi que le numéro de journal, le N° document et le compte général. Il indique également les transactions dans les devises de transaction, comptables et de déclaration.
-   **Origine de la transaction** – Cet état de transaction affiche le compte par journal, et par devise de transaction, comptable et de déclaration. Il indique également chaque ligne du journal qui a été utilisé comme contrepartie.


##<a name="see-also"></a>Voir également :
- [Soldes de la comptabilité](general-ledger-account-balances.md) 
- [Explorateur de comptabilité source](..\accounts-payable\accounting-source-explorer.md)
- [États financiers](financial-reporting-getting-started.md)




