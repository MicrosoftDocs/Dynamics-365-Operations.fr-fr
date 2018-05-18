--- 
title: "Générer un plan avec contrainte"
description: "Cette procédure indique comment créer un plan qui prend en compte des contraintes en termes de matière et de capacité."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 59c6a4a2b239b3fd6b6ddc8f06bfd007f0191f0a
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="generate-a-constrained-plan"></a>Générer un plan avec contrainte

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment créer un plan qui prend en compte des contraintes en termes de matière et de capacité. Le plan vérifie que la fabrication ne démarre pas avant que les matières soient disponibles et que des ressources ne soient pas surréservées. 

Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au gestionnaire de production.


## <a name="set-up-a-constrained-plan"></a>Paramétrer un plan avec contrainte
1. Cliquez sur Planification.
2. Cliquez sur Plans généraux.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Exemple : StaticPlan  
4. Sélectionnez Oui dans le champ Capacité finie.
5. Entrez 30 dans le champ Plage de gestion de la capacité finie.
6. Développez les plages de gestion dans la section des jours.
7. Sélectionnez Oui dans le champ Capacité.
8. Entrez un nombre dans le champ Plage de gestion de planification de capacité (jours).
    * Exemple : 60  
9. Sélectionnez Oui dans le champ Retards calculés.
10. Entrez un nombre dans le champ Calculer la plage de gestion des retards (jours).
    * Exemple : 60  
11. Développez la section Retards calculés.
12. Sélectionnez Oui dans le champ Ajouter le retard calculé à la date de besoin.
13. Sélectionnez Oui dans le champ Ajouter le retard calculé à la date de besoin.
14. Sélectionnez Oui dans le champ Ajouter le retard calculé à la date de besoin.
15. Fermez la page.

## <a name="create-a-constrained-plan"></a>Créer un plan avec contrainte
1. Cliquez sur Exécuter.
2. Saisissez ou sélectionnez une valeur dans le champ Plan général.
    * Sélectionnez le plan pour lequel vous avez défini des contraintes.  
3. Cliquez sur OK.
    * Cette opération peut prendre du temps.  
4. Cliquez sur Ordres prévisionnels.


