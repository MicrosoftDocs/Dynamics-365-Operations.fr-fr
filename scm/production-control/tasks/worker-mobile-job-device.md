--- 
title: "Configurer un collaborateur à l'aide du périphérique de travail mobile"
description: "Cette procédure vous indique comment affecter des rôles corrects au compte utilisateur d'un collaborateur, puis autoriser ce collaborateur à effectuer des enregistrements d'atelier."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 7da224809946d90387668d25c5aed5b61f6a7b72
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Configurer un collaborateur à l'aide du périphérique de travail mobile

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous indique comment affecter des rôles corrects au compte utilisateur d'un collaborateur, puis autoriser ce collaborateur à effectuer des enregistrements d'atelier.


## <a name="assign-roles-to-user-account"></a>Affecter des rôles au compte utilisateur
1. Accédez à Administration système > Utilisateurs > Utilisateurs.
2. Utilisez le filtre rapide pour filtrer sur le nom d'un collaborateur pour lequel le compte utilisateur est associé au rôle d'opérateur. Dans les données d'exemple, le nom est Shannon.
3. Mettre en surbrillance l'enregistrement du compte utilisateur.
4. Dans la liste, cliquez sur le lien « Nom » de la ligne sélectionnée pour afficher les détails du compte utilisateur.
5. Dans l'arborescence, sélectionnez « Rôles\opérateur ».
6. Fermez la page des détails du compte utilisateur.
7. Fermez la page.

## <a name="configure-worker-account"></a>Paramétrez le compte du collaborateur.
1. Accédez à Ressources humaines > Collaborateurs > Collaborateurs.
2. Utilisez le filtre rapide pour filtrer sur le nom d'un collaborateur pour lequel le compte utilisateur est associé au rôle d'opérateur. Dans les données d'exemple, le nom est Shannon.
3. Mettre en surbrillance l'enregistrement du compte utilisateur.
4. Dans la liste, cliquez sur le lien « Nom » de la ligne sélectionnée pour afficher les détails du compte utilisateur.
5. Cliquez sur l'onglet Emploi.
6. Développez l'organisateur Enregistrement du temps et cliquez sur Activer sur les terminaux d'enregistrement.
7. Cliquez sur Activer sur les terminaux d'enregistrement.
8. Dans le champ Groupe de calcul, saisissez ou sélectionnez une valeur.
9. Dans le champ Groupe de calcul par défaut, saisissez ou sélectionnez une valeur.
10. Dans le champ Groupe d'approbation, saisissez ou sélectionnez une valeur.
11. Dans le champ Profil standard, saisissez ou sélectionnez une valeur.
12. Dans le champ Groupe de profils, saisissez ou sélectionnez une valeur.
13. Cliquez sur OK.
14. Cliquez sur Modifier pour saisir un numéro de badge pour le nouveau collaborateur qualifié pour l'enregistrement des heures.
15. Dans le champ ID badge, tapez une valeur.
16. Cliquez sur Enregistrer.
17. Utilisez le raccourci SaveRecord.
18. Fermez la page des détails du collaborateur.
19. Fermez la page.

## <a name="assign-worker-to-device-group"></a>Affectez le collaborateur au groupe de périphériques.
1. Accédez à Contrôle de la production > Paramétrage > Contrôle et suivi de la production > Configurer le bon de travail pour les périphériques.
2. Cliquez sur Ajouter.
3. Dans la liste, marquez la ligne sélectionnée.
4. Cliquez sur OK.
5. Cliquez sur Modifier.
6. Dans le champ Unité de production, vous pouvez définir le filtre par défaut pour le collaborateur. Cela garantit que seules les tâches de production pour l'unité de production sélectionnée sont affichées lorsque le collaborateur se connecte au périphérique.
7. Fermez la page.


