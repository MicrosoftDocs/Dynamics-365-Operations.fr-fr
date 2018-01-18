--- 
title: " Créer des groupes d'autorisations de PDV"
description: "Cette procédure indique comment créer un groupe d'autorisations de PDV."
author: scott-tucker
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e924dc59c3e4cb9b6979014852512453dd3d70db
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-pos-permission-groups"></a> Créer des groupes d'autorisations de PDV

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure indique comment créer un groupe d'autorisations de PDV. La société fictive utilisée pour créer cette tâche est USRT. Cette tâche est destinée au rôle Gestionnaire des opérations de vente au détail.

1. Accédez à Groupes d'autorisations.
2. Cliquez sur Nouveau.
3. Dans le champ ID groupe d'autorisations du PDV, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Sélectionnez Oui dans le champ Afficher les entrées de l'horloge de pointage.
    * Vous pouvez maintenant activer ou désactiver diverses autorisations pour votre groupe d'autorisations PDV. Pour certaines autorisations, vous pouvez définir une valeur qui sera utilisée pour évaluer si l'utilisateur PDV peut effectuer l'action.  Ce guide de tâches active quelques autorisations qui peuvent être accordées à un caissier.  
6. Sélectionnez Oui dans le champ Autoriser la création de commandes.
7. Sélectionnez Oui dans le champ Autoriser la modification de commandes.
8. Sélectionnez Oui dans le champ Autoriser la récupération de commandes.
9. Sélectionnez Oui dans le champ Autoriser la modification du mot de passe.
10. Sélectionnez Oui dans le champ Autoriser la clôture en aveugle.
11. Cliquez sur Enregistrer.
    * Une fois vos modifications enregistrées, vous devez exécuter le programme de répartition du personnel pour que les modifications soient appliquées aux canaux de vente au détail.  
12. Fermez la page.
13. Accédez à Tâches.
    * Nous allons ensuite affecter le groupe d'autorisations PDV à une tâche.  
14. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
15. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
16. Cliquez sur Modifier.
17. Développez la section Classification des tâches.
18. Dans le champ Groupe d'autorisations du PDV, saisissez ou sélectionnez une valeur.
    * Tous les collaborateurs affectés à des postes pour cette tâche utilisent les paramètres de ce groupe d'autorisations PDV sauf si les autorisations de PDV des collaborateurs ont été remplacées au niveau de leur poste.  
19. Cliquez sur Enregistrer.
    * Une fois vos modifications enregistrées, vous devez exécuter le programme de répartition du personnel pour que les modifications soient appliquées aux canaux de vente au détail.  


