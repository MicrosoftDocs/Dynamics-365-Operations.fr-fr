---
title: Développer le plan et la structure du salaire/de la rémunération
description: Ce guide de tâche décrit le processus de création d'un régime de rémunération fixe et d'activation des employés à inscrire dans le plan via des règles d'admissibilité.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f0732736736fdc87f3367f24b1d20b9fa6efc59
ms.sourcegitcommit: ef08bf1258aefb525d56bf85ef19311be26ab94c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2019
ms.locfileid: "1794902"
---
# <a name="develop-salarycompensation-structure-and-plan"></a>Développer le plan et la structure du salaire/de la rémunération

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche décrit le processus de création d'un régime de rémunération fixe et d'activation des employés à inscrire dans le plan via des règles d'admissibilité. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF et la tâche est destinée aux gestionnaires de rémunération et avantages.


## <a name="create-fixed-compensation-plan"></a>Créer un régime de rémunération fixe.
1. Cliquez sur Gestion des rémunérations.
2. Cliquez sur Régimes de rémunération fixe.
3. Cliquez sur Nouveau.
4. Dans le champ Plan, tapez une valeur.
5. Dans le champ Description, entrez une valeur.
6. Entrez une date dans le champ Date d'effet.
7. Dans le champ Type, choisissez si le régime de rémunération fixe est un régime de structure, de niveau ou d'échelon.
8. La case à cocher Recommandation autorisée sert de valeur par défaut pour toutes les actions ajoutées à ce plan dans un événement de processus.  Le fait d'autoriser les recommandations vous permet d'ignorer le montant indicatif calculé lors du traitement de la rémunération.
9. La tolérance Hors de portée vous permet de spécifier la manière dont vous souhaitez gérer les montants de rémunération se trouvant en dehors de la plage de structure de rémunération spécifiée pour le niveau donné.  Si la tolérance Hors de portée est définie sur Aucun, tous les montants de rémunération sont autorisés.  Si la tolérance est définie sur Souple, l'utilisateur est averti si le montant de rémunération est inférieur au montant minimal de point de référence pour ce niveau (ou supérieur au montant maximal). L'utilisateur peut ignorer l'avertissement et continuer.  Si la tolérance est définie sur Absolu, cela génèrera une erreur si la rémunération de l'employé est définie en dehors des points de référence minimum et maximum pour ce niveau et cela réglera automatiquement la rémunération de l'employé pour qu'elle se situe dans la marge.
10. Le champ Règle d'embauche est utilisé lorsqu'un événement de processus de rémunération est exécuté pour calculer la rémunération de l'employé.  Une règle d'embauche en pourcentage calculera une augmentation au prorata de la durée pendant laquelle le travailleur a été employé dans le cycle.
11. Tapez une valeur dans le champ Devise.
12. Saisissez ou sélectionnez une valeur dans le champ Conversion de taux de salaire.
13. Développez la section Matrice d'utilisation de tranche.
    * Vous pouvez éventuellement ajouter des enregistrements d'utilisation de tranche pour que les employés atteignent la valeur médiane plus rapidement et atteignent le maximum de leur tranche moins vite.  
14. À ce stade, vous devez enregistrer le régime de rémunération fixe pour activer le bouton Paramétrer la rémunération et continuer à définir la structure de rémunération pour le régime.  Cliquez sur Enregistrer.
15. Cliquez sur Paramétrer la rémunération.
    * Il existe trois manières de créer une structure de rémunération. 1 : Créer une structure entièrement nouvelle en sélectionnant un ensemble de points de référence et en ajoutant des niveaux pour créer votre propre structure. 2 : Copier une structure de rémunération en utilisant un plan existant comme point de départ et la modifier pour le nouveau plan. 3 : Sélectionner une grille de rémunération existante. Si la grille de rémunération est déjà utilisée par un autre plan, toutes les modifications apportées à la grille seront également répercutées dans l'autre plan.  
16. Activez l'option Créer une nouvelle matrice de rémunération à partir d'une matrice existante.
17. Saisissez ou sélectionnez une valeur dans le champ Copier à partir de la grille.
    * Vous pouvez éventuellement modifier le nom de la nouvelle grille de rémunération qui sera créée comme copie de la grille sélectionnée.  
18. Cliquez sur OK.
19. Cliquez sur Modification en masse.
    * Les modifications en masse vous permettent de conserver les montants de matrice de rémunération en appliquant un pourcentage ou un montant fixe d'augmentation à un ou plusieurs niveaux et/ou points de référence.  
20. Entrez un numéro dans le champ Montant d'ajustement.
21. Dans la liste, cochez ou décochez toutes les lignes.
22. Cliquez sur Appliquer à la grille.
23. Fermez la page.
    * Une fois qu'une structure de rémunération a été créée ou sélectionnée, vous pouvez sélectionner les points de référence à utiliser comme point de contrôle pour le régime de rémunération fixe.  Le point de contrôle est utilisé pour calculer le coefficient de comparaison d'un employé.  
24. Saisissez ou sélectionnez une valeur dans le champ Point de contrôle.
25. Fermez la page.

## <a name="create-an-eligibility-rule-for-the-new-fixed-compensation-plan"></a>Créer une règle d'admissibilité pour le nouveau régime de rémunération fixe
    * Le nouveau régime de rémunération fixe ne peut pas être affecté à un employé tant que des règles d'admissibilité n'ont pas été définies pour le régime.  
1. Cliquez sur Règles d'admissibilité.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Admissibilité.
4. Dans le champ Description, entrez une valeur.
5. Entrez une date dans le champ Date d'effet.
    * Les règles d'admissibilité s'appliquent aux régimes de rémunération fixe et variable.  Dans le champ Type, sélectionnez le type de régime auquel cet ensemble de règles d'admissibilité est destiné.  
6. Dans le champ Régime, saisissez ou sélectionnez une valeur.
    * Sélectionnez les critères que l'employé doit remplir pour prétendre à l'enregistrement dans un régime de rémunération. Les critères peuvent inclure un département, un syndicat, un emplacement (région de rémunération), une tâche, une fonction, un type de tâche ou un niveau de rémunération. L'employé doit remplir tous les critères spécifiés pour être admissible dans un régime de rémunération. Si aucun critère n'est spécifié, tous les employés sont admissibles pour le régime de rémunération. Si un employé ne répond pas aux critères spécifiés dans la règle d'admissibilité, ou si une règle d'admissibilité n'a pas été spécifiée pour un régime de rémunération, ce régime de rémunération n'apparaît pas dans la recherche lorsque vous créez un enregistrement de rémunération fixe pour un employé.  
7. Fermez la page.
8. Fermez la page.

