--- 
title: "Définir une logique de mise en conteneur"
description: "Cette procédure décrit comment automatiser la mise en conteneur des charges dans la gestion des entrepôts."
author: YuyuScheller
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: aeb7d956560c513c08d5e20dcf20989b49137a52
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-containerization"></a>Définir une logique de mise en conteneur

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment automatiser la mise en conteneur des charges dans la gestion des entrepôts. La mise en conteneur automatisée crée des conteneurs et le travail de prélèvement pour les expéditions lorsqu'une vague est traitée et des lignes de travail peuvent être fractionnées en quantités ajustées aux conteneurs. Cela permet aux magasiniers de prélever les articles directement dans le conteneur sélectionné. Comparé au processus d'emballage manuel, des tâches telles que la création de conteneurs, l'affectation d'articles et la fermeture des conteneurs sont automatisées par le système. La société fictive USMF sert d'exemple dans cette procédure qui est effectuée par un gestionnaire des entrepôts.


## <a name="set-up-a-wave-template"></a>Paramétrage d'un modèle de vague
1. Accédez à Gestion des entrepôts > Paramétrage > Vagues > Modèles de vague.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Modèle de vague.
4. Tapez une valeur dans le champ Description du modèle de vague.
5. Saisissez ou sélectionnez une valeur dans le champ Site.
6. Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.
7. Développez la section Méthodes.
    * Le volet Méthodes sélectionnées liste les méthodes pour le type de modèle de vague sélectionné. Le modèle de vague doit inclure la méthode de mise en conteneur.  
8. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
9. Tapez une valeur dans le champ Code étape de vague.
    * Entrez un code étape de vague pour la méthode ajoutée, qui peut être n'importe quel code. Il est possible d'ajouter la méthode plusieurs fois et d'affecter différents codes étape de vague. Pour ce faire, sélectionnez Répétition possible pour cette méthode dans la page Méthodes de traitement de la vague.  
10. Cliquez sur Enregistrer.
11. Fermez la page.

## <a name="set-up-a-container-type"></a>Paramétrer un type de conteneur
1. Accédez à Gestion des entrepôts > Paramétrage > Conteneurs > Types de conteneurs.
    * Vous pouvez définir vos conteneurs dans la page Types de conteneurs. Vous pouvez configurer les dimensions physiques des conteneurs, notamment le poids de la tare, le poids maximum, le volume maximum, la longueur, la largeur et la hauteur. Dans cet exemple, nous avons trois tailles de colis différentes.  
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Type de conteneur.
4. Entrez un nombre dans le champ Tare.
5. Entrez un nombre dans le champ Poids maximal.
6. Dans le champ Volume, entrez un nombre.
7. Dans le champ Longueur, entrez un nombre.
8. Entrez un nombre dans le champ Largeur.
9. Entrez un nombre dans le champ Hauteur.
10. Dans le champ Description, entrez une valeur.
11. Cliquez sur Enregistrer.
12. Cliquez sur Nouveau.
13. Tapez une valeur dans le champ Type de conteneur.
14. Dans le champ Description, entrez une valeur.
15. Entrez un nombre dans le champ Tare.
16. Entrez un nombre dans le champ Poids maximal.
17. Dans le champ Volume, entrez un nombre.
18. Dans le champ Longueur, entrez un nombre.
19. Entrez un nombre dans le champ Largeur.
20. Entrez un nombre dans le champ Hauteur.
21. Cliquez sur Enregistrer.
22. Cliquez sur Nouveau.
23. Tapez une valeur dans le champ Type de conteneur.
24. Dans le champ Description, entrez une valeur.
25. Entrez un nombre dans le champ Tare.
26. Entrez un nombre dans le champ Poids maximal.
27. Dans le champ Volume, entrez un nombre.
28. Dans le champ Longueur, entrez un nombre.
29. Entrez un nombre dans le champ Largeur.
30. Entrez un nombre dans le champ Hauteur.
31. Cliquez sur Enregistrer.
32. Fermez la page.

## <a name="set-up-a-container-group"></a>Paramétrer un groupe de conteneurs
1. Accédez à Gestion des entrepôts > Paramétrage > Conteneurs > Groupes de conteneurs.
2. Cliquez sur Nouveau.
    * Vous pouvez paramétrer des groupes logiques de types de conteneur. Pour chaque groupe, vous pouvez spécifier l'ordre dans lequel conditionner les conteneurs et le pourcentage de conteneurs à remplir. Les dimensions de taille de l'article sont utilisées pour déterminer s'il passera dans un conteneur. Le conteneur qui est le plus proche des dimensions de taille de l'article est utilisé. Si vous avez plusieurs types de conteneur dans un groupe, nous vous recommandons de réorganiser l'ordre par taille, afin que le conteneur le plus grand soit en premier, numéro 1 dans l'ordre, et que le plus petit conteneur soit le dernier.    
3. Tapez une valeur dans le champ ID groupe de conteneurs.
4. Dans le champ Description, entrez une valeur.
5. Cliquez sur Nouveau.
6. Dans la liste, marquez la ligne sélectionnée.
7. Saisissez ou sélectionnez une valeur dans le champ Type de conteneur.
8. Cliquez sur Nouveau.
9. Dans la liste, marquer la ligne sélectionnée.
10. Saisissez ou sélectionnez une valeur dans le champ Type de conteneur.
11. Cliquez sur Nouveau.
12. Dans la liste, marquer la ligne sélectionnée.
13. Saisissez ou sélectionnez une valeur dans le champ Type de conteneur.
14. Cliquez sur Enregistrer.
15. Fermez la page.

## <a name="set-up-a-container-build-template"></a>Paramétrer un modèle de création de conteneur
1. Accédez à Gestion des entrepôts > Paramétrage > Conteneurs > Modèles de création de conteneur.
2. Cliquez sur Nouveau.
    * Le modèle de version du conteneur est basé sur le processus de mise en conteneur exécuté. Chaque modèle de version du conteneur définit le processus de mise en conteneur qui sera utilisé par un modèle de vague. L'option Modifier la requête vous permet de définir les conditions en fonction desquelles le modèle sélectionné sera traité. Par exemple, vous pouvez souhaiter exécuter uniquement la mise en conteneur pour des clients, des produits ou des entrepôts spécifiques ou vous pouvez ajouter des plages correspondantes de requête au modèle. Le champ Code étape de vague indique de quelle manière un modèle de création de conteneur est lié aux étapes dans un modèle de vague. Lorsqu'une vague est exécutée, elle détermine le ou les modèles de version du conteneur utilisés pour initialiser la mise en conteneur. Le champ Type de requête de base détermine quels éléments conditionner et sur quoi baser la requête de filtre.  
3. Dans la liste, marquez la ligne sélectionnée.
4. Tapez une valeur dans le champ ID modèle de conteneur.
5. Saisissez ou sélectionnez une valeur dans le champ ID groupe de conteneurs.
6. Tapez une valeur dans le champ Code étape de vague.
7. Activez la case à cocher Autoriser la répartition des prélèvements.
8. Cliquez sur Enregistrer.
9. Cliquez sur Contraintes de mélange de conteneur.
    * Les décompositions de la logique de mélange vous permet de définir des règles de conditionnement des lignes de répartition dans des conteneurs. Par exemple, si vous ajoutez le champ Numéro d'article, lorsque des articles sont affectés à des conteneurs, un nouveau conteneur sera créé lorsqu'il y aura un nouveau numéro d'article. Cela empêche des collaborateurs de conditionner des lignes de répartition pour deux clients différents dans le même conteneur.  
10. Cliquez sur Nouveau.
11. Sélectionnez une option dans le champ Table.
12. Saisissez ou sélectionnez une valeur dans le champ Sélection de champ.
13. Cliquez sur OK.


