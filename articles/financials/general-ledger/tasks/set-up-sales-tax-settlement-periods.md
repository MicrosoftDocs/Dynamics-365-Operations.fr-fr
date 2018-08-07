--- 
title: "Paramétrer des périodes de règlement fiscal"
description: "Les périodes de règlement fiscal contiennent des informations sur l'intervalle pour lequel les taxes doivent être déclarées et payées."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: ab7d3a00a327f42a9f70c954d9b64a360a7f9163
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-sales-tax-settlement-periods"></a>Paramétrer des périodes de règlement fiscal

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les périodes de règlement fiscal contiennent des informations sur l'intervalle pour lequel les taxes doivent être déclarées et payées. Un processus de règlement peut être exécuté pour une période de règlement pour un intervalle de dates spécifique. Tous les codes taxe associés à la période de règlement seront fixés. Selon la configuration de l'administration fiscale associée, l'impôt à payer est validé soit dans un fournisseur soit dans un compte général.



La société fictive USMF est citée en exemple dans cette tâche.



1. Accédez à Taxes > Taxes indirectes >Taxe > Périodes de règlement fiscal.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Période de règlement.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Administration, sélectionnez l'administration fiscale qui reçoit les états et les règlements créés pour la période de règlement.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Dans le champ Conditions de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * L'administration fiscale associée peut être paramétrée comme fournisseur et le règlement fiscal va créer une facture fournisseur en cours. Les conditions de paiement définissent la date d'échéance pour la facture fournisseur en cours.  
9. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
10. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
11. Sélectionnez un type pour les intervalles des périodes de règlement.
12. Entrez le nombre d'unités de l'intervalle par période. Un trimestre a 3 mois, par exemple.
13. Activez ou désactivez la case à cocher Utiliser le traitement par lots pour le règlement de la taxe.
    * Le processus de règlement pour la période de règlement peut être traité en tant que traitement par lots en arrière-plan. Cette opération est recommandée pour un grand nombre de transactions de taxe dans un intervalle de périodes.  
14. Développez l'onglet Intervalles de périodes.
15. Cliquez sur Ajouter.
16. Dans la liste, marquez la ligne sélectionnée.
17. Entrez une date dans le champ Date de début.
18. Entrez une date dans le champ Date de fin.
19. Cliquez sur Nouvel intervalle de périodes.
    * Une fois que le premier intervalle de périodes a été entré, de nouvelles périodes peuvent être créées automatiquement. Si nécessaire, vous pouvez revenir et ajouter de nouveaux intervalles de périodes.  
20. Fermez la page.


