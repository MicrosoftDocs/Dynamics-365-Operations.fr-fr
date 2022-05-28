---
title: Paramétrer des périodes de règlement fiscal
description: Cette rubrique explique comment configurer des périodes de règlement de la taxe de vente dans Dynamics 365 Finance.
author: twheeloc
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 197b85fb88f966b0a13fc061e2e780dd84e74acb
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735812"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Paramétrer des périodes de règlement fiscal

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment paramétrer les périodes de règlement fiscal. Les périodes de règlement fiscal contiennent des informations sur l’intervalle pour lequel les taxes doivent être déclarées et payées. Un processus de règlement peut être exécuté pour une période de règlement pour un intervalle de dates spécifique. Tous les codes taxe associés à la période de règlement seront fixés. Selon la configuration de l'administration fiscale associée, l'impôt à payer est validé soit dans un fournisseur soit dans un compte général.

La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à **Taxes > Taxes indirectes >Taxe > Périodes de règlement fiscal**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Période de règlement**, saisissez une valeur.
4. Tapez une valeur dans le champ **Description**.
5. Dans le champ **Administration**, sélectionnez l’administration fiscale qui reçoit les états et les règlements créés pour la période de règlement.
6. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
7. Dans le champ **Conditions de paiement**, sélectionnez l’enregistrement souhaité dans le menu déroulant. L’administration fiscale associée peut être paramétrée comme fournisseur et le règlement fiscal va créer une facture fournisseur en cours. Les conditions de paiement définissent la date d’échéance pour la facture fournisseur en cours.  
8. Sélectionnez un type pour les intervalles des périodes de règlement.
9. Entrez le nombre d’unités de l’intervalle par période. Un trimestre a 3 mois, par exemple.
10. Activez ou désactivez la case à cocher **Utiliser le traitement par lots pour le règlement de la taxe**. Le processus de règlement pour la période de règlement peut être traité en tant que traitement par lots en arrière-plan. Cette opération est recommandée pour un grand nombre de transactions de taxe dans un intervalle de périodes.
11. Activez ou désactivez la case à cocher **Empêcher la génération des transactions de taxe de contrepartie**. Par défaut, le système génère des transactions de taxe de contrepartie au cours de le processus de règlement, ce qui peut entraîner des problèmes de performances s’il existe un grand nombre de transactions de taxe au sein d’un intervalle de périodes. Activez cette case à cocher pour empêcher la génération des transactions de taxe de contrepartie.
12. Développez l’onglet **Intervalles de périodes**.
13. Sélectionnez **Ajouter**.
14. Dans le champ **Date de début** dans la nouvelle ligne, saisissez une date.
15. Entrez une date dans le champ **Date de fin**.
16. Sélectionnez **Nouvel intervalle de périodes**. Une fois que le premier intervalle de périodes a été entré, de nouvelles périodes peuvent être créées automatiquement. Si nécessaire, vous pouvez revenir et ajouter de nouveaux intervalles de périodes.  
17. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
