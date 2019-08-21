---
title: Paramétrer la mise en conteneur
description: Cette rubrique décrit comment automatiser la mise en conteneur des charges dans le module Gestion des entrepôts.
author: ShylaThompson
manager: AnnBe
ms.date: 07/22/19
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba435ee145a8516391d7864bdfe338b0f3862f49
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847205"
---
# <a name="set-up-containerization"></a>Paramétrer la mise en conteneur

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette rubrique décrit comment automatiser la mise en conteneur des charges dans le module Gestion des entrepôts. La mise en conteneur automatisée crée des conteneurs et le travail de prélèvement pour les expéditions lorsqu'une vague est traitée et des lignes de travail peuvent être fractionnées en quantités ajustées aux conteneurs. Cela permet aux magasiniers de prélever les articles directement dans le conteneur sélectionné. Comparé au processus d'emballage manuel, des tâches telles que la création de conteneurs, l'affectation d'articles et la fermeture des conteneurs sont automatisées par le système. La société fictive USMF sert d'exemple dans cette procédure qui est effectuée par un gestionnaire des entrepôts.


## <a name="set-up-a-wave-template"></a>Paramétrage d'un modèle de vague
1. Dans le volet de navigation, accédez à **Modules > Gestion des entrepôts > Paramétrage > Vagues > Modèles de vague**.
2. Sélectionnez **Nouveau**.
3. Tapez une valeur dans le champ **Nom du modèle de vague**.
4. Tapez une valeur dans le champ **Description du modèle de vague**.
5. Entrez ou sélectionnez une valeur dans le champ **Site**.
6. Entrez ou sélectionnez une valeur dans le champ **Entrepôt**.
7. Développez la section **Méthodes**. Le volet **Méthodes sélectionnées** liste les méthodes pour le type de modèle de vague sélectionné. Le modèle de vague doit inclure la méthode de mise en conteneur.  
8. Tapez une valeur dans le champ **Code étape de vague**. Entrez un code étape de vague pour la méthode ajoutée, qui peut être n'importe quel code. Il est possible d'ajouter la méthode plusieurs fois et d'affecter différents codes étape de vague. Pour ce faire, sélectionnez **Répétition possible pour cette méthode** dans la page **Méthodes de traitement de la vague**.  
9. Sélectionnez **Enregistrer**.
10. Fermez la page.

## <a name="set-up-a-container-type"></a>Paramétrer un type de conteneur
1. Dans le volet de navigation, accédez à **Modules > Gestion des entrepôts > Paramétrage > Conteneurs > Types de conteneurs**. Vous pouvez définir vos conteneurs dans la page **Types de conteneurs**. Vous pouvez configurer les dimensions physiques des conteneurs, notamment le poids de la tare, le poids maximum, le volume maximum, la longueur, la largeur et la hauteur. Dans cet exemple, nous avons trois tailles de colis différentes.  
2. Sélectionnez **Nouveau**.
3. Tapez une valeur dans le champ **Code type de conteneur**.
4. Entrez un nombre dans le champ **Tare**.
5. Entrez un nombre dans le champ **Poids maximal**.
6. Entrez un nombre dans le champ **Volume**.
7. Entrez un nombre dans le champ **Longueur**.
8. Entrez un nombre dans le champ **Largeur**.
9. Entrez un nombre dans le champ **Hauteur**.
10. Tapez une valeur dans le champ **Description**.
11. Sélectionnez **Enregistrer**.
13. Répétez les étapes 2 à 11 deux fois pour créer trois types de conteneurs au total.
14. Fermez la page.

## <a name="set-up-a-container-group"></a>Paramétrer un groupe de conteneurs
1. Dans le volet de navigation, accédez à **Modules > Gestion des entrepôts > Paramétrage > Conteneurs > Groupes de conteneurs**.
2. Dans le volet Actions, sélectionnez **Nouveau**. Vous pouvez paramétrer des groupes logiques de types de conteneur. Pour chaque groupe, vous pouvez spécifier l'ordre dans lequel conditionner les conteneurs et le pourcentage de conteneurs à remplir. Les dimensions de taille de l'article sont utilisées pour déterminer s'il passera dans un conteneur. Le conteneur qui est le plus proche des dimensions de taille de l'article est utilisé. Si vous avez plusieurs types de conteneur dans un groupe, nous vous recommandons de réorganiser l'ordre par taille, afin que le conteneur le plus grand soit en premier, numéro 1 dans l'ordre, et que le plus petit conteneur soit le dernier.    
3. Dans le champ **ID groupe de conteneurs**, tapez une valeur que vous avez créée précédemment.
4. Tapez une valeur dans le champ **Description**.
5. Répétez les étapes 2 à 4 pour les trois types de conteneurs que vous avez créés précédemment.
6. Sélectionnez **Enregistrer**.
7. Fermez la page.

## <a name="set-up-a-container-build-template"></a>Paramétrer un modèle de création de conteneur
1. Dans le volet de navigation, accédez à **Modules > Gestion des entrepôts > Paramétrage > Conteneurs > Modèle de création de conteneur**.
2. Sélectionnez **Nouveau**. Le modèle de version du conteneur est basé sur le processus de mise en conteneur exécuté. Chaque modèle de version du conteneur définit le processus de mise en conteneur qui sera utilisé par un modèle de vague. L'option **Modifier la requête** vous permet de définir les conditions en fonction desquelles le modèle sélectionné sera traité. Par exemple, vous pouvez souhaiter exécuter uniquement la mise en conteneur pour des clients, des produits ou des entrepôts spécifiques ou vous pouvez ajouter des plages correspondantes de requête au modèle. Le champ **Code étape de vague** indique de quelle manière un modèle de création de conteneur est lié aux étapes dans un modèle de vague. Lorsqu'une vague est exécutée, elle détermine le ou les modèles de version du conteneur utilisés pour initialiser la mise en conteneur. Le champ Type de requête de base détermine quels éléments conditionner et sur quoi baser la requête de filtre. 
3. Tapez une valeur dans le champ **ID modèle de conteneur**.
4. Entrez ou sélectionnez une valeur dans le champ **ID groupe de conteneurs**.
5. Tapez une valeur dans le champ **Code étape de vague**.
6. Activez la case à cocher **Autoriser la répartition des prélèvements**.
7. Sélectionnez **Enregistrer**.
8. Sélectionnez **Contraintes de mélange de conteneur**. Les décompositions de la logique de mélange vous permet de définir des règles de conditionnement des lignes de répartition dans des conteneurs. Par exemple, si vous ajoutez le champ **Numéro d'article**, lorsque des articles sont affectés à des conteneurs, un nouveau conteneur sera créé lorsqu'il y aura un nouveau numéro d'article. Cela empêche des collaborateurs de conditionner des lignes de répartition pour deux clients différents dans le même conteneur.  
9. Sélectionnez **Nouveau**.
10. Sélectionnez une option dans le champ **Table**.
11. Entrez ou sélectionnez une valeur dans le champ **Sélection de champ**.
12. Cliquez sur **OK**.

