--- 
title: "Calculer l'amortissement des immobilisations dans les entités juridiques"
description: "Cette procédure décrit comment paramétrer et exécuter le processus d'amortissement pour plusieurs entités juridiques."
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d804480167414cd038f8229db312dc9c52d131f8
ms.openlocfilehash: 4c45da124136b7fecb916d2ff9098c8ffeff6cb1
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Calculer l'amortissement des immobilisations dans les entités juridiques

[!include [task guide banner](../../includes/task-guide-banner.md)]

L'amortissement d'immobilisation peut être exécuté dans les entités juridiques en une seule étape. Cette procédure décrit comment paramétrer et exécuter le processus pour plusieurs entités juridiques. Elle utilise le rôle de comptable.  

La société fictive USMF sert d'exemple dans cet enregistrement.


Étapes (16) sous-tâche : Paramétrer des journaux d'exécution d'amortissement de société croisée. 

1. Commencez par paramétrer les journaux à utiliser dans l'exécution de l'amortissement de société croisée dans chaque entité juridique. Accédez à Immobilisations > Paramétrage > Paramètres des immobilisations. 
2. Développez la section de propositions d'immobilisation. 
3. Créez un enregistrement avec le nom de journal à utiliser pour chaque couche de validation dans l'entité juridique. Si les registres ne sont pas validés dans la comptabilité, Aucun couche de validation doit être sélectionné avec le journal associé. Cliquez sur Ajouter. 
4. Dans le champ Couche de validation, entrez ou sélectionnez une valeur. 
5. Dans le champ Nom de journal, entrez ou sélectionnez une valeur. 
6. Répétez le paramétrage de journal sur la page Paramètres d'immobilisation dans chaque entité juridique. 

Sous-tâche : calculer l'amortissement

1. Utilisez la page Créer une proposition d'amortissement pour commencer l'exécution de l'amortissement dans les entités juridiques. Accédez à Immobilisations > Entrées de journal > Créer une proposition d'amortissement. 
2. Dans le champ Couche de validation, entrez ou sélectionnez une valeur. 
3. Le nom du journal sera issu par défaut des paramètres d'immobilisation. Il peut être remplacé ici pour l'entité juridique actuelle. 
4. Entrez une date dans le champ Date de fin. 
5. Sélectionnez les entités juridiques à inclure dans l'exécution d'amortissement. Seules les entités juridiques avec les journaux paramétrés pour les propositions d'immobilisation sur la page Paramètres d'immobilisation sont affichées dans la liste. 
6. Si elle est activée, l'option Valider les journaux valide automatiquement les journaux d'amortissement lors de leur création. Si elle n'est pas sélectionnée, les journaux sont créés, mais pas validés, afin que vous puissiez vérifier les détails avant la validation. Sélectionnez Oui dans le champ Valider les journaux. 
7. Les champs de filtrage incluent les immobilisations, les groupes, et les registres des entités juridiques sélectionnées pour cette exécution d'amortissement. 
8. L'option de traitement par lots est activée par défaut. Lorsque cette option est activée, la création et la validation du journal d'amortissement est exécutée en arrière-plan. 
9. Cliquez sur Créer un journal. 
10. Vous devez afficher les journaux d'amortissement créés dans les entités juridiques appropriées. Accédez à Immobilisations > Entrées de journal > Journal des immobilisations.

