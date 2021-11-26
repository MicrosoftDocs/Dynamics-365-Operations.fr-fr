---
title: Gérer les politiques d’achat et de vente de congés
description: Vous pouvez permettre aux employés d’acheter et de vendre des congés dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 06682a81b09f90de0ef5eb1b656338e634f229db
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728879"
---
# <a name="manage-buy-and-sell-leave-policies"></a>Gérer les stratégies d’achat et de vente de congés

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous pouvez permettre aux employés de vendre et d’acheter des congés en créant une stratégie de vente et d’achat de congés. Vous pouvez configurer ces stratégies pour utiliser le workflow pour les approbations, définir des montants et des taux maximums et des tarifs pour l’achat et la vente. 

## <a name="enable-employees-to-buy-and-sell-leave"></a>Permettre aux employés d’acheter et de vendre des congés

1. Dans la page **Paramètres de congé et d’absence**, sélectionnez **Oui** pour **Autoriser les employés à acheter des congés** et **Autoriser les employés à vendre des congés**.

## <a name="create-a-buy-and-sell-leave-policy"></a>Créer une stratégie d’achat et de vente de congés

1. Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**. 

2. Sélectionnez **Stratégie d’achat et de vente de congés**.

3. Sélectionnez **Nouveau**.

4. Entrez un **Nom** et une **Description** pour la stratégie sous **Stratégie d’achat et de vente de congés**. 

5. Sélectionnez un **Type de stratégie**. 

   Les types de stratégie disponibles sont **Quantité** et **Heures par semaine**. Sélectionnez **Quantité** pour entrer une **Quantité fixe** pour les quantités maximales que les employés peuvent acheter et vendre. Si vous sélectionnez **Heures par semaine**, le temps de travail défini dans les horaires de travail attribués à l’employé sera utilisé pour déterminer la quantité maximale de la stratégie. 

6. Sélectionnez une **Date de début** et une **Date de fin** pour la stratégie. Les demandes d’achat ou de vente de congés ne pourront être soumises que pendant cette période. 

7. Sélectionnez un **ID de workflow** pour la stratégie. Toutes les demandes d’achat et de vente utiliseront ce workflow pour examen et approbation. 

8. Sous **Stratégie d’achat**, sélectionnez **Équivalence temps plein** (ETP) pour calculer la quantité maximale au prorata de l’ETP défini pour le poste du collaborateur. Si le type de stratégie est **Quantité**, entrez une **Quantité maximale fixe**. 

9. Sélectionnez **Ajouter** pour ajouter les types de congés à acheter par les collaborateurs. Vous pouvez ajouter plusieurs types de congés à la stratégie. 

10. Entrer les **Mois de service** pour le type de congé afin d’autoriser différents mois de service pour déterminer la quantité maximale qu’un collaborateur peut acheter. 

11. Entrez la **Quantité maximale** pour le type de congé. 

12. Entrez le **Taux** auquel le collaborateur achètera le congé. 

13. Entrez éventuellement le **Code de rémunération** à utiliser pour acheter des congés. 

14. Définissez éventuellement s’il faut utiliser l’ETP pour déterminer la quantité maximale pour le type de congé. 

15. Pour créer une stratégie de vente, suivez les étapes 8 à 14 sous **Stratégie de vente**. 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>Ajouter la stratégie d’achat et de vente de congés à un plan de congé et d’absence

1. Dans la page **Congé et absence**, sélectionnez un plan de congé et d’absence.

2. Sous **Règles**, sélectionnez **Stratégie d’achat et de vente de congés**.

## <a name="see-also"></a>Voir également :

[Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)</br>
[Configurer les types de congé et d’absence](hr-leave-and-absence-types.md)</br>
[Régulariser les plans de congé et d’absence](hr-leave-and-absence-accrue.md)</br>
[Achat et vente de congés](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
