---
title: Inscription d'un employé à un régime de rémunération variable
description: La gestionnaire de rémunération et avantages peut inscrire des employés dans des régimes de rémunération variable pour calculer des primes en espèces ou non pour les employés.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 361403d61be64cfc58b3c2296937109b13a2b244
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418487"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a>Inscription d'un employé à un régime de rémunération variable

La gestionnaire de rémunération et avantages peut inscrire des employés dans des régimes de rémunération variable pour calculer des primes en espèces ou non pour les employés. Cette procédure suppose qu'un régime de rémunération variable a été créé avec le champ Activer l'inscription défini sur Oui, et que des règles d'admissibilité ont été créées pour ce régime de rémunération variable. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Pour démarrer cette procédure, accédez à Ressources humaines > Collaborateurs > Employés > Rémunération > Inscription au régime variable

1. Cliquez sur Nouveau.
2. Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * La recherche est filtrée pour afficher uniquement les régimes de rémunération variable auxquels l'employé peut prétendre en fonction des règles d'admissibilité.  
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Activez ou désactivez l'extension de la section Général.
5. Entrez une date dans le champ Date d'effet.
6. Cliquez sur Enregistrer.
7. Activez ou désactivez l'extension de la section Remplacements.
    * Le cas échéant, une date de règle d'embauche peut être définie pour remplacer la date d'embauche d'un employé lorsque la règle d'embauche spécifiée pour le régime de rémunération variable sélectionné est Pourcentage.  
    * Si le régime variable est un pourcentage du régime de base, le pourcentage de prime peut être remplacé pour l'employé. Si le régime de rémunération variable est un nombre d'unités du régime, le nombre d'unités peut être remplacé pour l'employé.  
    * Si un montant fixe doit être octroyé à l'employé pour sa prime, ce montant peut être défini ici.  
8. Activez ou désactivez l'extension de la section Remplacements organisationnels.
    * Si les performances de l'employé doivent prendre en compte les performances de différents départements ou d'un département autre que celui affecté au poste de l'employé, le département peut être remplacé. La colonne de pourcentage doit être égale à 100.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]