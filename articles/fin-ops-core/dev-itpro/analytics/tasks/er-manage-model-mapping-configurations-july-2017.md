---
title: Gérer la mise en correspondance de modèle de gestion des états électroniques dans des configurations ER distinctes
description: Cette rubrique décrit comment gérer la mise en correspondance des modèles de gestion des états électroniques dans des configurations de gestion des états électroniques distinctes.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f1013cfc9f421525fb0661cd5ace5eeaa157f9a
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093796"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a>Gérer la mise en correspondance de modèle de gestion d’états électroniques dans des configurations de gestion d’états électroniques distinctes

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut gérer des mises en correspondance de modèle d’états électroniques dans des configurations ER distinctes. Dans ce guide de tâche, vous allez créer les configurations ER requises pour l’exemple de société, Litware, Inc. Pour réaliser les étapes de ce guide de tâche, vous devez d’abord effectuer les étapes du guide de tâche, « ER Créer un fournisseur de configuration et le marquer comme actif ». 

Comme les configurations ER sont partagées entre les sociétés, vous pouvez réaliser les étapes de ce guide de tâche en utilisant l’ensemble de données de société de votre choix. La fonctionnalité de ce guide de tâche est disponible si vous avez installé l’un des correctifs suivants : https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 pour la version 7.0 de Dynamics AX ou https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 pour la version Dynamics 365 for Operations.

1. Accédez à Administration d’organisation > Espaces de travail > États électroniques.
    * Vérifiez que le fournisseur de la configuration pour la société fictive Litware, Inc. est disponible et marqué comme actif. Si ce fournisseur de configuration ne s’affiche pas, vous devez d’abord effectuer les étapes du guide de tâche, Créer un fournisseur de configuration et le marquer comme actif.   

## <a name="add-a-new-er-model-configuration"></a>Ajouter une nouvelle configuration du modèle ER
1. Cliquez sur Configurations des états.
    * Ajoutez une nouvelle configuration du modèle. Le nom doit être unique dans l’arborescence de configurations.  
2. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
3. Dans le champ Nom, tapez « Exemple de modèle de données ».
    * Exemple de modèle de données  
4. Cliquez sur Créer une configuration.
5. Cliquez sur Concepteur.
6. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
7. Dans le champ Nom, tapez « Racine ».
    * Racine  
8. Cliquez sur Ajouter.
9. Cliquez sur Nouveau pour ouvrir la boîte de dialogue.
10. Dans le champ Nom, tapez « Société ».
    * Société  
11. Cliquez sur Ajouter.
12. Dans le champ Description, entrez le texte, Description de l’entité juridique ou de la société à laquelle un utilisateur est connecté au moment de l’exécution. 
    * Description de l’entité juridique ou de la société à laquelle un utilisateur est connecté au moment de l’exécution.  
13. Cliquez sur Référence racine.
14. Cliquez sur OK.
15. Cliquez sur Enregistrer.
16. Fermez la page.
17. Cliquez sur Modifier le statut.
18. Cliquez sur Terminé.
19. Cliquez sur OK.

## <a name="add-a-new-er-model-mapping-configuration"></a>Ajouter une nouvelle configuration de mise en correspondance du modèle de données ER
1. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
2. Dans le champ Nouveau, entrez « Mise en correspondance de modèle basée sur le modèle de données Exemple de modèle de données ».
3. Dans le champ Nom, tapez « Exemple de mise en correspondance ».
    * Exemple de mise en correspondance  
4. Cliquez sur Créer une configuration.
5. Développez la section Conditions préalables.
    * Le groupe de composants prérequis Implémentations a été ajouté automatiquement. Le groupe contient le composant prérequis qui fait référence à la configuration de modèle de données parent et est marqué comme implémentation. Cela signifie que cette configuration de mise en correspondance de modèle Exemple de mise en correspondance est considérée comme l’implémentation du modèle de données, Exemple de modèle de données. Par conséquent, ce composant forcera ER à télécharger la configuration de mise en correspondance de modèle, Exemple de mise en correspondance, à partir d’un référentiel ER lorsque la configuration de modèle, Exemple de modèle de données, est téléchargée.   
6. Cliquez sur Concepteur.
    * La configuration de mise en correspondance de modèle créée contient une nouvelle mise en correspondance vide portant le même nom que la configuration créée. Lorsqu’une configuration de modèle parent sélectionnée contient des mises en correspondance de modèle, celles-ci sont copiées dans une nouvelle configuration de mise en correspondance de modèle.   
7. Cliquez sur Concepteur.
8. Dans l’arborescence, sélectionnez « Dynamics 365 for Operations\Table ».
9. Cliquez sur Ajouter racine.
10. Dans le champ Nom, tapez « Société ».
    * Société  
11. Dans le champ Table, tapez « CompanyInfo ».
    * CompanyInfo  
12. Cliquez sur OK.
13. Dans l’arborescence, développez « Société ».
14. Dans l’arborescence, développez « Company\find() ».
15. Dans l’arborescence, sélectionnez « Company\find()\Name ».
16. Cliquez sur Lier.
17. Cliquez sur Enregistrer.
18. Fermez la page.
19. Fermez la page.
20. Dans le volet Actions, cliquez sur Configurations.
21. Cliquez sur Paramètres utilisateur.
22. Sélectionnez Oui dans le champ Paramètres d’exécution.
23. Cliquez sur OK.
24. Cliquez sur Modifier.
25. Sélectionnez Oui dans le champ Exécuter le brouillon.

## <a name="add-a-new-er-format-configuration"></a>Ajouter une nouvelle configuration du format ER
1. Dans l’arborescence, sélectionnez « Exemple de modèle de données ».
2. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
3. Dans le champ Nouveau, entrez « Format basé sur le modèle de données Exemple de modèle de données ».
4. Dans le champ Nom, tapez « Exemple de format ».
    * Exemple de format  
5. Cliquez sur Créer une configuration.
6. Cliquez sur Concepteur.
7. Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.
8. Dans l’arborescence, sélectionnez « Texte\Chaîne ».
9. Cliquez sur OK.
10. Cliquez sur l’onglet Mise en relation.
11. Dans l’arborescence , développez « model ».
12. Dans l’arborescence, sélectionnez « model\Company ».
13. Cliquez sur Lier.
14. Cliquez sur Enregistrer.
15. Fermez la page.
    * Exécutez la version brouillon du format créé à des fins de test.  
16. Cliquez sur Exécuter.
    * Dans l’organisateur Versions, cliquez sur Exécuter.  
17. Cliquez sur OK.
    * Examinez la sortie qui contient le nom de la société dans laquelle l’utilisateur exécutant cette configuration de format est connecté. La configuration de mise en correspondance de modèle créée est utilisée par cette configuration de format, car une seule configuration disponible contient les mises en correspondance de modèle requises.   

## <a name="add-alternative-er-model-mapping-configuration"></a>Ajouter une autre configuration de mise en correspondance de modèle ER
1. Dans l’arborescence, sélectionnez « Exemple de modèle de données ».
2. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
3. Dans le champ Nouveau, entrez « Mise en correspondance de modèle basée sur le modèle de données Exemple de modèle de données ».
4. Dans le champ Nom, tapez « Exemple de mise en correspondance (autre) ».
    * Exemple de mise en correspondance (autre)  
5. Cliquez sur Créer une configuration.
6. Cliquez sur Concepteur.
7. Cliquez sur Concepteur.
8. Dans l’arborescence, sélectionnez « Dynamics 365 for Operations\Table ».
9. Cliquez sur Ajouter racine.
10. Dans le champ Nom, tapez « Société ».
    * Société  
11. Dans le champ Table, tapez « CompanyInfo ».
    * CompanyInfo  
12. Cliquez sur OK.
13. Cliquez sur Modifier.
14. Dans l’arborescence, sélectionner « String\CONCATENATE ».
15. Cliquez sur Ajouter une fonction.
16. Dans l’arborescence, développez « Société ».
17. Dans l’arborescence, développez « Company\find() ».
18. Dans l’arborescence, sélectionnez « Company\find()\Name ».
19. Cliquez sur Ajouter une source de données.
20. Dans le champ Formule, tapez une valeur.
    * CONCATENATE(Company.’find()’.Name, ";",  
21. Dans l’arborescence, sélectionnez « Company\find()\Company(DataArea) ».
22. Cliquez sur Ajouter une source de données.
23. Dans le champ Formule, tapez une valeur.
    * CONCATENATE(Company.’find()’.Name, ";", Company.’find()’.DataArea)  
24. Cliquez sur Enregistrer.
25. Fermez la page.
26. Cliquez sur Enregistrer.
27. Fermez la page.
28. Fermez la page.
29. Sélectionnez Oui dans le champ Exécuter le brouillon.

## <a name="use-an-existing-er-model-mapping-configuration"></a>Utiliser une configuration de mise en correspondance de modèle ER existante
1. Dans l’arborescence, sélectionnez « Exemple de modèle de données\Exemple de format ».
2. Cliquez sur Exécuter.
    * La version brouillon sélectionnée de la configuration du format ER ne peut pas être exécutée, car plusieurs configurations de mise en correspondance de modèle sont disponibles pour le modèle de données non défini qui a été sélectionné comme source de données du format ER en cours d’exécution.   
    * Ensuite, vous définirez l’autre configuration de mise en correspondance de modèle comme celle à partir de laquelle les mises en correspondance de modèle seront utilisées comme sources de données du format ER en cours d’exécution.   
3. Dans l’arborescence, sélectionnez « Exemple de modèle de données\Exemple de mise en correspondance (autre) ».
4. Sélectionnez Oui dans le champ Valeur par défaut de la mise en correspondance des modèles.
5. Dans l’arborescence, sélectionnez « Exemple de modèle de données\Exemple de format ».
6. Cliquez sur Exécuter.
7. Cliquez sur OK.
    * La configuration de mise en correspondance de modèle par défaut est utilisée par cette configuration de format pour générer le document électronique (la sortie créée contient le code de la société).  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]