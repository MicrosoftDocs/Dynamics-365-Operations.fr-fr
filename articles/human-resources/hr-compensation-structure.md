---
title: Développer une structure de rémunération
description: Cet article décrit la création d’un régime de rémunération fixe et l’inscription des employés au régime par le biais de règles d’admissibilité.
author: andreabichsel
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2649a392b5c8bb2482622eba22b0b2f458058314dce25a8b9032eb2ef518240c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732367"
---
# <a name="develop-a-compensation-structure"></a>Développer une structure de rémunération

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit la création d’un régime de rémunération fixe et l’inscription des employés au régime par le biais de règles d’admissibilité. Cet article utilise les données de démonstration USMF et s’adresse aux gestionnaires des rémunérations et avantages.

## <a name="create-a-fixed-compensation-plan"></a>Création d’un régime de rémunération fixe

1. Sélectionnez **Gestion des rémunérations**.

2. Sélectionnez **Régimes de rémunération fixe**.

3. Sélectionnez **Nouveau**.

4. Dans le champ **Régime**, entrer une valeur.

5. Dans le champ **Description**, entrez une valeur.

6. Entrez une date dans le champ **Date d’effet**.

7. Dans le champ **Type**, choisissez si le régime de rémunération fixe est un régime de type **Structure**, **Niveau** ou **Échelon**.

8. La case à cocher **Recommandation autorisée** sert de valeur par défaut pour toutes les actions ajoutées à ce régime dans un événement de processus. Le fait d’autoriser les recommandations vous permet d’ignorer le montant indicatif calculé lors du traitement de la rémunération.

9. Le champ **Tolérance Hors de portée** vous permet de spécifier la manière dont vous souhaitez gérer les montants de rémunération se trouvant en dehors de la plage de structure de rémunération spécifiée pour le niveau donné. La définition du champ **Tolérance hors plage** sur **Aucun** vous permet d’utiliser n’importe quel montant de rémunération. Si la tolérance est définie sur **Souple**, les utilisateurs sont avertis si le montant de rémunération est inférieur au montant minimal ou supérieur au montant maximal de point de référence pour ce niveau. Les utilisateurs peuvent ignorer l’avertissement et continuer. Si la tolérance est définie sur **Absolu**, une erreur est générée si la rémunération de l’employé est en dehors des points de référence minimum et maximum pour ce niveau et la rémunération de l’employé est automatiquement ajustée pour se situer dans la marge.

10. Le champ **Règle d’embauche** calcule la rémunération d’un employé lors d’un événement de processus. Une **Règle d’embauche** en **Pourcentage** calcule une augmentation au prorata de la durée pendant laquelle le travailleur a été employé dans le cycle.

11. Tapez une valeur dans le champ **Devise**.

12. Saisissez ou sélectionnez une valeur dans le champ **Conversion de taux de salaire**.

13. Développez la section **Matrice d’utilisation de tranche**. Vous pouvez éventuellement ajouter des enregistrements d’utilisation de tranche pour que les employés atteignent la valeur médiane plus rapidement et atteignent le maximum de leur tranche moins vite.

14. Sélectionnez **Enregistrer**. Cela active le bouton **Paramétrer la rémunération**. Vous pouvez continuer à définir votre structure de rémunération pour le régime.

15. Sélectionnez **Paramétrer la rémunération**. Vous pouvez créer une structure de rémunération en utilisant l’une des trois méthodes suivantes :

    - Créer une structure entièrement nouvelle en sélectionnant un ensemble de points de référence et en ajoutant des niveaux pour créer votre propre structure.
    - Copier une structure de rémunération en utilisant un plan existant comme point de départ et la modifier pour le nouveau plan.
    - Sélectionner une grille de rémunération existante. Si un autre régime utilise déjà la grille de rémunération, l’autre régime reflète également les modifications apportées à la grille.

16. Sélectionnez **Créer une nouvelle matrice de rémunération à partir d’une matrice existante**.

17. Saisissez ou sélectionnez une valeur dans le champ **Copier à partir de la grille**. Vous pouvez éventuellement modifier le nom de la nouvelle grille de rémunération que vous créez en copiant la grille sélectionnée.

18. Cliquez sur **OK**.

19. Sélectionnez **Modification en masse**. Les **Modifications en masse** vous permettent de conserver les montants de matrice de rémunération en appliquant un pourcentage ou un montant fixe d’augmentation à un ou plusieurs niveaux ou points de référence.

20. Entrez un nombre dans le champ **Montant d’ajustement**.

21. Dans la liste, cochez ou décochez toutes les lignes.

22. Cliquez sur **Appliquer à la grille**.

23. Fermez la page. Après avoir créé la structure de rémunération, vous pouvez sélectionner les points de référence à utiliser comme point de contrôle pour le régime de rémunération fixe. Le point de contrôle est utilisé pour calculer le coefficient de comparaison d’un employé.

24. Saisissez ou sélectionnez une valeur dans le champ **Point de contrôle**.

25. Fermez la page.

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a>Créer une règle d’admissibilité pour le régime de rémunération fixe

Vous ne pouvez pas affecter un régime de rémunération fixe à un employé tant que vous n’avez pas défini de règles d’admissibilité pour le régime.  

1. Sélectionnez **Règles d’admissibilité**.

2. Sélectionnez **Nouveau**.

3. Saisissez ou sélectionnez une valeur dans le champ **Admissibilité**.

4. Dans le champ **Description**, entrez une valeur.

5. Entrez une date dans le champ **Date d’effet**. Les régimes de rémunération fixe et variable utilisent des règles d’admissibilité. Dans le champ **Type**, sélectionnez le type de régime.

6. Dans le champ **Plan**, saisissez ou sélectionnez une valeur. Sélectionnez les critères que l’employé doit remplir pour prétendre à l’enregistrement dans un régime de rémunération. Les critères peuvent inclure :

    - **Département**
    - **Syndicat**
    - **Emplacement** (**Région de rémunération**)
    - **Tâche**
    - **Fonction**
    - **Type de poste**
    - **Niveau de rémunération**
    
    L’employé doit remplir tous les critères spécifiés pour être admissible dans un régime de rémunération. Si vous ne spécifiez aucun critère, tous les employés sont admissibles pour le régime de rémunération. Si un employé ne répond pas aux critères spécifiés dans la règle d’admissibilité, ou si une règle d’admissibilité n’a pas été spécifiée pour un régime de rémunération, ce régime de rémunération n’apparaît pas dans la recherche lorsque vous créez un enregistrement de rémunération fixe pour un employé.

7. Fermez la page.

8. Fermez la page.



[!INCLUDE[footer-include](../includes/footer-banner.md)]