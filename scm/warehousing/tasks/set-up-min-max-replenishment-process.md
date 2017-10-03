--- 
title: "Paramétrer un processus de réapprovisionnement minimum/maximum"
description: "Cette procédure décrit la manière de paramétrer un nouveau processus de réapprovisionnement qui utilise une stratégie de réapprovisionnement minimal/maximal."
author: perlynne
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
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 01a0c42c43a23234e0e355193f8dd7e8ee116f71
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-a-min-max-replenishment-process"></a>Paramétrer un processus de réapprovisionnement minimum/maximum

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit la manière de paramétrer un nouveau processus de réapprovisionnement qui utilise une stratégie de réapprovisionnement minimal/maximal. Lorsque le stock passe en dessous du niveau minimal, le travail est créé pour réapprovisionner l'emplacement. La procédure indique également comment utiliser les emplacements de prélèvement fixes pour autoriser la remise en stock même si le stock passe en dessous du niveau minimal et comment activer le processus de réapprovisionnement pour qu'il s'exécute régulièrement en utilisant un traitement par lots. Ces tâches sont généralement effectuées par un responsable de l'entrepôt. Vous pouvez exécuter cette procédure dans les données fictives de la société USMF à l'aide des valeurs d'exemple dans les notes, ou pouvez l'exécuter sur vos propres données. Si vous utilisez vos propres données, vérifiez que vous avez un entrepôt qui est activé pour les processus de gestion des entrepôts.


## <a name="create-a-fixed-picking-location"></a>Créer un emplacement de prélèvement fixe
1. Accédez à Gestion des entrepôts > Paramétrage > Entrepôt > Emplacements fixes.
    * Il s'agit d'une tâche facultative pour le réapprovisionnement minimum/maximum, mais si vous utilisez un emplacement de prélèvement fixe, cela permet de réapprovisionner le stock même s'il passe en dessous du niveau minimal, car le système peut déterminer les articles qui doivent être réapprovisionnés, même s'il n'en reste plus.  
2. Cliquez sur Nouveau.
3. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
    * Si vous utilisez USMF, vous pouvez sélectionner l'article A0001.  
4. Saisissez ou sélectionnez une valeur dans le champ Site.
    * Si vous utilisez USMF, vous pouvez sélectionner site 2.  
5. Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.
    * Si vous utilisez USMF, vous pouvez sélectionner l'entrepôt 24.  
6. Saisissez ou sélectionnez une valeur dans le champ Emplacement.
    * Si vous utilisez USMF, vous pouvez sélectionner CP-003.  
7. Fermez la page.

## <a name="create-a-replenishment-location-directive"></a>Créer une instruction de réassort d'entrepôt
1. Accédez à Gestion des entrepôts > Configuration > Instructions d'emplacements.
    * Les directives d'emplacement permettent de déterminer où les articles doivent être prélevés à partir du processus de réapprovisionnement.  
2. Sélectionnez Réapprovisionnement dans le champ Type d'ordre d'exécution.
3. Cliquez sur Nouveau.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Type de travail, sélectionnez « Prélever ».
6. Saisissez ou sélectionnez une valeur dans le champ Site.
    * Si vous utilisez USMF, vous pouvez sélectionner site 2.  
7. Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.
    * Si vous utilisez USMF, vous pouvez sélectionner l'entrepôt 24.  
8. Cliquez sur Enregistrer.
9. Cliquez sur Nouveau.
10. Dans la liste, marquez la ligne sélectionnée.
11. Dans le champ Quantité d'arrivée, entrez un nombre.
    * Par exemple, vous pouvez définir sur 9999.  
12. Activez la case à cocher Autoriser le fractionnement.
    * Si vous sélectionnez cette option, le processus de création de travail laissera les quantités sur des lignes de travail être fractionnées entre plusieurs emplacements.  
13. Cliquez sur Enregistrer.
14. Cliquez sur Nouveau.
15. Dans la liste, marquez la ligne sélectionnée.
16. Tapez une valeur dans le champ Nom.
17. Cliquez sur Enregistrer.
18. Cliquez sur Modifier la demande.
    * Vous pouvez modifier cette requête pour ajouter des restrictions dans lesquelles le stock peut être sélectionné à partir du processus de réapprovisionnement. Le stock peut par exemple uniquement être utilisé à partir de la zone de stockage en gros de l'entrepôt.  
19. Cliquez sur OK.
20. Fermez la page.

## <a name="create-a-replenishment-work-template"></a>Créer un modèle de travail de réapprovisionnement
1. Accédez à Gestion des entrepôts > Configuration > Travail > Modèles de travail.
    * Le modèle de travail permet de guider le système à propos du travail minimum/maximum de réapprovisionnement à créer. Il doit au minimum y avoir une ligne de modèle de travail pour le prélèvement et le rangement. Le modèle de travail indique qu'il n'est pas valide tant que toutes les informations nécessaires n'ont pas été renseignées.  
2. Sélectionnez Réapprovisionnement dans le champ Type d'ordre d'exécution.
3. Cliquez sur Nouveau.
4. Dans le champ Modèle de travail, tapez une valeur.
5. Cliquez sur Enregistrer.
6. Cliquez sur Nouveau.
7. Dans le champ Type de travail, sélectionnez « Prélever ».
8. Saisissez ou sélectionnez une valeur dans le champ ID classe de travail.
    * Il doit s'agir d'une classe de travail concernant le réapprovisionnement. Si vous utilisez USMF, sélectionnez Réapprovisionner.  
9. Cliquez sur Nouveau.
10. Dans la liste, marquez la ligne sélectionnée.
11. Dans le champ Type de travail, sélectionnez « Put ».
12. Saisissez ou sélectionnez une valeur dans le champ ID classe de travail.
13. Cliquez sur Enregistrer.
14. Fermez la page.

## <a name="create-a-new-replenishment-template"></a>Créer un modèle de réapprovisionnement
1. Accédez à Gestion des entrepôts > Paramétrage > Réapprovisionnement > Modèles de réapprovisionnement.
    * Le modèle de réapprovisionnement permet de définir les articles et les quantités, et l'emplacement à réapprovisionner.  
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Modèle de réapprovisionnement.
    * Donnez un nom au modèle pour indiquer qu'il est destiné au réapprovisionnement minimum/maximum.  
4. Dans le champ Description, entrez une valeur.
5. Activez la case à cocher Autoriser la demande de vague pour utiliser des quantités non réservées.
    * Si cette option est sélectionnée, elle permet au réapprovisionnement de demande de vague de consommer des quantités associées au réapprovisionnement minimum/maximum. Par exemple, cela peut être utile si le travail minimum/maximum de réapprovisionnement n'est pas traité immédiatement, pour éviter de créer un travail inutile de réapprovisionnement.  
6. Cliquez sur Nouveau.
7. Entrez un nombre dans le champ Numéro de souche.
8. Dans le champ Description, entrez une valeur.
9. Dans la liste, marquez la ligne sélectionnée.
10. Saisissez ou sélectionnez une valeur dans le champ Unité de réapprovisionnement.
    * Par exemple, sélectionnez pcs. Ce paramètre est obligatoire. Il permet de spécifier une unité de mesure différente pour le travail de réapprovisionnement comparé à l'unité spécifiée pour les niveaux des stocks minimum et maximum dans ce modèle.  
11. Saisissez ou sélectionnez une valeur dans le champ Modèle de travail.
    * Choisissez le modèle de travail créé précédemment.  
12. Entrez un nombre dans le champ Quantité minimale.
    * Sélectionnez la quantité minimale qui doit déclencher le réapprovisionnement. Par exemple, paramétrez cela sur 50. Il est possible de laisser cette valeur sur zéro, si vous réapprovisionnez un emplacement fixe et si l'option Réapprovisionner les emplacements fixes vides est définie sur Oui. Il est également recommandé de sélectionner l'option Réapprovisionner uniquement des emplacements fixes pour des raisons de performances.  
13. Entrez un nombre dans le champ Quantité maximale.
    * Par exemple, définissez cette valeur sur 100.  
14. Saisissez ou sélectionnez une valeur dans le champ Unité.
    * Affectez l'unité des quantités minimales et maximales. Par exemple, paramétrez cela sur pcs.  
15. Activez la case à cocher Réapprovisionner les emplacements fixes vides.
    * Activez cette case à cocher pour réapprovisionner les emplacements fixes lorsqu'ils sont vides. Sinon, seuls les emplacements où il existe une quantité disponible seront réapprovisionnés.  
16. Activez la case à cocher Réapprovisionner uniquement des emplacements fixes.
17. Cliquez sur Sélectionner les produits.
    * Il s'agit de l'emplacement pour définir quels produits doivent être réapprovisionnés. Si l'option d'emplacements de prélèvement fixes est activée, vous devez également définir les emplacements de cette requête. Variante : des requêtes spécifiques sont disponibles, ainsi que des requêtes spécifiques à un produit.  
18. Sélectionnez la ligne Articles.
19. Tapez une valeur dans le champ Critères.
    * Sélectionnez les articles devant être réapprovisionnés à des emplacements fixes. Par exemple, entrez A* pour sélectionner tous les numéros d'article commençant par A.  
20. Cliquez sur Ajouter.
    * Ajoutez l'entité Emplacement (à moins qu'elle existe déjà) pour pouvoir limiter le travail de réapprovisionnement à des emplacements fixes de prélèvement dans une zone spécifique de l'entrepôt.  
21. Dans la liste, marquez la ligne sélectionnée.
22. Paramétrez le champ Table sur Emplacements.
23. Dans le champ Champ, sélectionnez ID profil d'emplacement.
24. Dans le champ Critères, saisissez ou sélectionnez une valeur.
25. Cliquez sur OK.
26. Fermez la page.

## <a name="set-the-replenishment-process-to-run-as-a-batch-job"></a>Paramétrer le processus de réapprovisionnement pour s'exécuter comme un traitement par lots
1. Accédez à Gestion des entrepôts > Réapprovisionnement > Réapprovisionnements.
    * La page Réapprovisionnements vous permet de définir l'exécution du réapprovisionnement comme un traitement par lots ou pour demander qu'il soit lancé manuellement.  
2. Cliquez sur Filtre.
3. Dans la liste, marquez la ligne sélectionnée.
4. Dans le champ Critères, saisissez ou sélectionnez une valeur.
5. Cliquez sur OK.
6. Développez la section Exécuter à l'arrière-plan.
7. Définissez l'option Traitement par lots sur Oui.
8. Cliquez sur Répétition.
9. Sélectionnez l'option Pas de date de fin.
10. Définissez le modèle de récurrence.
    * Par exemple, sélectionnez Jours.  
11. Cliquez sur OK.
12. Cliquez sur OK.


