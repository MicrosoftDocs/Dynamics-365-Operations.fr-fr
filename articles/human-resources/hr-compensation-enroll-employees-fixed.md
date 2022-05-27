---
title: Inscrire un employé à un régime de rémunération fixe
description: La gestionnaire de rémunération et avantages peut affecter des employés à des régimes de rémunération fixe pour gérer leur salaire de base.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d611f2631a59fbe1e131e82ca9937a5adaaf2ebd
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688739"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>Inscrire un employé à un régime de rémunération fixe


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

La gestionnaire de rémunération et avantages peut affecter des employés à des régimes de rémunération fixe pour gérer leur salaire de base. Cette procédure suppose qu’un régime fixe ait été créé et activé, et que des règles d’admissibilité aient été définies pour le régime. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Pour démarrer la procédure, accédez à **Ressources humaines** > **Collaborateurs** > **Employés** > **Rémunération** > **Régime fixe**.

1. Cliquez sur **Nouveau**.
2. Dans le champ **Action**, sélectionnez une action de rémunération fixe de type **Embaucher/Rembaucher** pour décrire la modification concernant la rémunération de l’employé.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Dans le champ **Poste**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Le niveau affiché provient du raccourci **Compensation** > champ **Niveau**  depuis la **Tâche** qui est attribuée à la **Position**. Le niveau doit être défini sur cette tâche pour que la rémunération puisse être affectée à l’employé.  
6. Dans le champ **Régime**, sélectionnez le régime de rémunération fixe pour l’employé. La recherche du **plan** est filtrée pour afficher uniquement les régimes auxquels l’employé peut prétendre en fonction des **règles d’admissibilité**.
7. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Les dates **d’effet** et **d’expiration** pour la valeur de rémunération sont définies par défaut entre la date de début et de fin de l’affectation de poste du collaborateur. Vous pouvez modifier ces dates si nécessaire.  
    * Si le régime de rémunération fixe est un régime à étapes, sélectionnez l’étape contenant le taux de salaire approprié pour l’employé. Si le régime de rémunération fixe est un régime de niveau, entrez le taux de salaire approprié pour l’employé. Le taux de salaire sera validé par rapport aux paramètres de tolérance pour le plan, et les points de référence minimum et maximum pour le niveau de rémunération de la tâche.  
8. Cliquez sur **OK**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
