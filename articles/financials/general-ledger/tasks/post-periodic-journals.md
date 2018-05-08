--- 
title: "Valider des journaux périodiques"
description: "Les journaux périodiques sont parfois appelés journaux récurrents car le montant, le texte, ainsi que d'autres informations sont répétés à chaque extraction du journal périodique."
author: aprilolson
manager: AnnBe
ms.date: 02/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 8eae11e0501db78e467e517b29a2bc19f5765e75
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="post-periodic-journals"></a>Valider des journaux périodiques

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les journaux périodiques sont parfois appelés journaux récurrents car le montant, le texte, ainsi que d'autres informations sont répétés à chaque extraction du journal périodique. Lorsque vous créez le journal périodique vous devez spécifier l'intervalle de périodes de la récurrence (des jours ou des mois, par exemple). Ce guide de tâche crée un journal périodique avec une récurrence mensuelle.



1. Accédez à Comptabilité > Tâches périodiques > Journaux périodiques.
2. Cliquez sur Nouveau.
3. Saisissez ou sélectionnez une valeur dans le champ Nom.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Dans le champ Description, entrez une valeur.
    * La description contiendra par la suite le nom du journal périodique, veillez donc à lui attribuer un nom pertinent.  
6. Cliquez sur Lignes.
    * Un journal périodique inclut généralement plusieurs lignes de journal. Ce guide de tâche ajoutera toutefois une seule ligne.  
7. Entrez une date dans le champ Date.
    * Le champ Date contient la date de validation pour le transfert suivant dans le journal d'opérations diverses. Pour les journaux qui sont extraits chaque mois, il est recommandé d'utiliser la date du mois de validation, généralement la première ou la dernière date de la période. Il est possible de laisser le champ Date vide et de donner une date lorsque le journal est récupéré, à l'aide du champ Date vide.    Le champ est automatiquement mis à jour avec la date récurrente suivante lorsque des transactions sont extraites.  
8. Dans le champ Compte, spécifiez les valeurs souhaitées.
9. Dans le champ Description, entrez une valeur.
10. Fermez la page.
11. Entrez un nombre dans le champ Débit.
12. Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.
13. Sélectionnez « Mois » dans le champ Unité.
14. Entrez 1 dans le champ Nombre d'unités.
15. Entrez une date dans le champ Dernière date.
    * Le fait d'entrer le dernier jour dans la période précédente empêche de créer le journal récurrent par erreur dans la période de début incorrecte. La dernière date sera mise à jour ultérieurement à chaque extraction du journal périodique.  
16. Cliquez sur Enregistrer.
17. Allez dans le Tableau de bord par défaut.
18. Accédez à Comptabilité > Entrées de journal > Journaux des opérations diverses.
19. Cliquez sur Nouveau.
20. Saisissez ou sélectionnez une valeur dans le champ Nom.
21. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
22. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
23. Dans le champ Description, entrez une valeur.
24. Cliquez sur Lignes.
25. Cliquez sur Journal périodique.
26. Cliquez sur Extraire le journal.
27. Entrez une date dans le champ Date de fin.
    * La date de fin sert de date limite aux lignes de document périodiques. Selon le paramètre de récurrence, il est possible d'inclure la dernière date et la date de fin sur la même ligne plusieurs fois dans le journal obtenu. La date de fin est automatiquement mise à jour en fonction de la date de session du dernier transfert de la ligne périodique dans un journal.  
28. Saisissez ou sélectionnez une valeur dans le champ Numéro de journal périodique.
29. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
30. Cliquez sur OK.
    * Le journal périodique peut désormais être révisé, approuvé ou validé selon les besoins et le paramétrage.  


