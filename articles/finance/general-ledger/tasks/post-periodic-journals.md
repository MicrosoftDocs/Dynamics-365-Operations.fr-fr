---
title: Valider des journaux périodiques
description: Les journaux périodiques sont parfois appelés journaux récurrents car le montant, le texte, ainsi que d’autres informations sont répétés à chaque extraction du journal périodique.
author: aprilolson
ms.date: 11/21/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bdc1d9f67a515e3cdc45e173b88982feceb0ebfd
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799384"
---
# <a name="post-periodic-journals"></a>Valider des journaux périodiques

[!include [banner](../../includes/banner.md)]

Les journaux périodiques sont parfois appelés journaux récurrents car le montant, le texte, ainsi que d’autres informations sont répétés à chaque extraction du journal périodique. Lorsque vous créez le journal périodique vous devez spécifier l’intervalle de périodes de la récurrence (des jours ou des mois, par exemple). Ce guide de tâche crée un journal périodique avec une récurrence mensuelle.

1. Accédez au **volet Navigation > Modules > Comptabilité > Tâches périodiques > Journaux périodiques**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Nom**, saisissez ou sélectionnez une valeur.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Tapez une valeur dans le champ **Description**. La description contiendra par la suite le nom du journal périodique, veillez donc à lui attribuer un nom pertinent.
6. Dans le **Volet Actions**, cliquez sur **Lignes**. Un journal périodique inclut généralement plusieurs lignes de journal. Ce guide de tâche ajoutera toutefois une seule ligne.
7. Entrez une date dans le champ **Date**. Le champ **Date** contient la date de validation pour le transfert suivant dans le journal d’opérations diverses. Pour les journaux qui sont extraits chaque mois, il est recommandé d’utiliser la date du mois de validation. Il s’agit généralement de la première ou de la dernière date de la période. À l’aide du champ **Date vide**, il est possible de laisser le champ **Date** vide lors de la récupération du journal. Le champ sera mis à jour avec la date récurrente suivante lorsque des transactions seront extraites. 
8. Dans le champ **Compte**, spécifiez les valeurs souhaitées.
9. Dans le champ **Description**, saisissez ou sélectionnez une valeur.
10. Fermez la page.
11. Dans le champ **Débit**, saisissez un nombre.
12. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
13. Dans le champ **Unité**, sélectionnez **Mois**.
14. Dans le champ **Nombre d’unités**, entrez **1**.
15. Dans le champ **Dernière date**, saisissez une date. Le fait d’entrer le dernier jour dans la période précédente empêche de créer le journal récurrent par erreur dans la période de début incorrecte. La dernière date sera mise à jour ultérieurement à chaque extraction du journal périodique. 
16. Cliquez sur **Enregistrer**.
17. Allez dans le **Volet de navigation > Modules > Comptabilité > Entrées de journal > Journaux des opérations diverses**.
18. Cliquez sur **Nouveau**.
19. Dans le champ **Nom**, saisissez ou sélectionnez une valeur.
20. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
21. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
22. Tapez une valeur dans le champ **Description**.
23. Dans le **Volet Actions**, cliquez sur **Lignes**.
24. Dans le **volet Actions**, cliquez sur **Journal périodique**.
25. Cliquez sur **Extraire le journal**.
26. Entrez une date dans le champ **Date de fin**. La **Date de fin** sert de date limite aux lignes de document périodiques. Selon le paramètre de récurrence, la **Dernière date** et la **Date de fin**, la même ligne peut être incluse plusieurs fois dans le journal obtenu. La **Date de fin** est mise à jour automatiquement en fonction de la date de session du dernier transfert de la ligne périodique dans un journal. 
27. Saisissez ou sélectionnez une valeur dans le champ **Numéro de journal périodique**.
28. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
29. Cliquez sur **OK**. Le journal périodique peut désormais être révisé, approuvé ou validé selon les besoins et le paramétrage.   


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
