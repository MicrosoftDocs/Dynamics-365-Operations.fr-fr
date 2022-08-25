---
title: Créer des groupes d’autorisations PDV
description: Cet article illustre la création d’un groupe d’autorisations du PDV.
author: josaw1
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.industry: Retail
ms.search.form: RetailPosPermissionGroup, HcmJob
ms.openlocfilehash: 0aa394e5dc6685954c31cdddae7cdc042b80af29
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277958"
---
# <a name="create-pos-permission-groups"></a>Créer des groupes d’autorisations PDV

[!include [banner](../includes/banner.md)]

Cet article illustre la création d’un groupe d’autorisations du PDV. La société fictive utilisée pour créer cette tâche est USRT. Cette tâche est destinée au rôle Gestionnaire des opérations Commerce.

1. Dans le volet de navigation, accédez à **Modules > Commerce et vente au détail > Employés > Groupes d’autorisations**.
2. Sélectionnez **Nouveau**.
3. Entrez une valeur dans le champ **ID groupe d’autorisations du PDV**.
4. Tapez une valeur dans le champ **Description**.
5. Sélectionnez **Oui** dans le champ **Afficher les entrées de l’horloge de pointage**. Vous pouvez maintenant activer ou désactiver diverses autorisations pour votre groupe d’autorisations PDV. Pour certaines autorisations, vous pouvez définir une valeur qui sera utilisée pour évaluer si l’utilisateur PDV peut effectuer l’action. Ce guide de tâches active quelques autorisations qui peuvent être accordées à un caissier.  
6. Sélectionnez **Oui** dans le champ **Autoriser la création de commandes**.
7. Sélectionnez **Oui** dans le champ **Autoriser la modification de commandes**.
8. Sélectionnez **Oui** dans le champ **Autoriser la récupération de commandes**.
9. Sélectionnez **Oui** dans le champ **Autoriser la modification du mot de passe**.
10. Sélectionnez **Oui** dans le champ **Autoriser la clôture en aveugle**.
11. Sélectionnez **Enregistrer**. Une fois vos modifications enregistrées, vous devez exécuter le programme de répartition du personnel pour que les modifications soient appliquées aux canaux Commerce. 
12. Dans le volet de navigation, allez dans **Modules > Ressources humaines > Tâches > Tâches**.
13. Nous allons ensuite affecter le groupe d’autorisations PDV à une tâche. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
14. Sélectionnez **Modifier**.
15. Développez la section **Classification des tâches**.
16. Dans le champ Groupe d’autorisations du PDV, saisissez ou sélectionnez une valeur. Tous les collaborateurs affectés à des postes pour cette tâche utilisent les paramètres de ce groupe d’autorisations PDV sauf si les autorisations de PDV des collaborateurs ont été remplacées au niveau de leur poste.  
17. Sélectionnez **Enregistrer**. Une fois vos modifications enregistrées, vous devez exécuter le programme de répartition du personnel pour que les modifications soient appliquées aux canaux.  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
