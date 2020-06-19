---
title: Gérer les politiques d'achat et de vente de congés
description: Vous pouvez permettre aux employés d'acheter et de vendre des congés dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 859445f2b6e980b5960e512e69129f6a8fc6df2b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429011"
---
# <a name="manage-buy-and-sell-leave-policies"></a>Gérer les politiques d'achat et de vente de congés

[!include [banner](includes/preview-feature.md)]

Vous pouvez permettre aux employés d'acheter des congés en créant une stratégie d'achat de congés.  

## <a name="enable-employees-to-buy-and-sell-leave"></a>Permettre aux employés d'acheter et de vendre des congés

1. Dans la page **Paramètres de congé et d'absence**, sélectionnez **Oui** pour **Autoriser les employés à acheter des congés**. 

## <a name="create-a-buy-leave-policy"></a>Créer une stratégie d'achat de congé

1. Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**. 

2. Sélectionnez **Stratégie d'achat et de vente de congés**.

3. Sélectionnez **Nouveau**.

4. Entrez un **Nom** et une **Description** pour la stratégie sous **Stratégie d'achat et de vente de congés**. 

5. Sélectionnez un **Type de stratégie**. 

   Les types de stratégie disponibles sont **Quantité** et **Heures par semaine**. Sélectionnez **Quantité** pour entrer une **Quantité fixe** pour les quantités maximales que les employés peuvent acheter et vendre. Si vous sélectionnez **Heures par semaine**, le temps de travail défini dans les horaires de travail attribués à l'employé sera utilisé pour déterminer la quantité maximale de la stratégie. 

6. Sélectionnez une **Date de début** et une **Date de fin** pour la stratégie. Les demandes d'achat ou de vente de congés ne pourront être soumises que pendant cette période. 

7. Sous **Stratégie d'achat**, sélectionnez **Équivalence temps plein** (ETP) pour calculer la quantité maximale au prorata de l'ETP défini pour le poste du collaborateur. Si le type de stratégie est **Quantité**, entrez une **Quantité maximale fixe**. 

8. Sélectionnez **Ajouter** pour ajouter les types de congés à acheter par les collaborateurs. Vous pouvez ajouter plusieurs types de congés à la stratégie. 

9. Entrer les **Mois de service** pour le type de congé afin d'autoriser différents mois de service pour déterminer la quantité maximale qu'un collaborateur peut acheter. 

10. Entrez la **Quantité maximale** pour le type de congé. 

11. Entrez le **Taux** auquel le collaborateur achètera le congé. 

12. Entrez éventuellement le **Code de rémunération** à utiliser pour acheter des congés. 

13. Définissez éventuellement s'il faut utiliser l'ETP pour déterminer la quantité maximale pour le type de congé. 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>Ajouter la stratégie d'achat et de vente de congés à un plan de congé et d'absence

1. Dans la page **Congé et absence**, sélectionnez un plan de congé et d'absence.

2. Sous **Règles**, sélectionnez **Stratégie d'achat et de vente de congés**.

## <a name="see-also"></a>Voir également :

[Vue d'ensemble des congés et des absences](hr-leave-and-absence-overview.md)</br>
[Configurer les types de congé et d'absence](hr-leave-and-absence-types.md)</br>
[Régulariser les plans de congé et d'absence](hr-leave-and-absence-accrue.md)</br>
[Achat et vente de congés](hr-employee-self-service-buy-sell-leave.md)

