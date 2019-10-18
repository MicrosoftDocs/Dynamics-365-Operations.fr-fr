---
title: Calculer l'amortissement des immobilisations dans les entités juridiques
description: L'amortissement d'immobilisation peut être exécuté dans les entités juridiques en une seule étape.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 500aa71e57f9c1ac8d1a2a080468381bc248741c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187013"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Calculer l'amortissement des immobilisations dans les entités juridiques

[!include [task guide banner](../../includes/task-guide-banner.md)]

L'amortissement d'immobilisation peut être exécuté dans les entités juridiques en une seule étape. Cette procédure décrit comment paramétrer et exécuter le processus pour plusieurs entités juridiques. Elle utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.


## <a name="set-up-cross-company-depreciation-run-journals"></a>Paramétrer les journaux d'exécution de l'amortissement entre sociétés
1. Accédez à Immobilisations > Paramétrage > Paramètres des immobilisations.
2. Développez la section de propositions d'immobilisation.
3. Cliquez sur Ajouter.
4. Dans le champ Couche de validation, entrez ou sélectionnez une valeur.
5. Dans le champ Nom de journal, entrez ou sélectionnez une valeur.
    * Répétez le paramétrage de journal sur la page Paramètres d'immobilisation dans chaque entité juridique.  

## <a name="depreciation-run"></a>Exécution de l'amortissement
1. Accédez à Immobilisations > Entrées de journal > Créer une proposition d'amortissement.
2. Dans le champ Couche de validation, entrez ou sélectionnez une valeur.
    * Le nom du journal sera issu par défaut des paramètres d'immobilisation. Il peut être remplacé ici pour l'entité juridique actuelle.  
3. Entrez une date dans le champ Date de fin.
    * Sélectionnez les entités juridiques à inclure dans l'exécution d'amortissement.  
    * Seules les entités juridiques avec les journaux paramétrés pour les propositions d'immobilisation sur la page Paramètres d'immobilisation sont affichées dans la liste.  
4. Sélectionnez Oui dans le champ Valider les journaux.
    * Les champs de filtrage incluent les immobilisations, les groupes, et les registres des entités juridiques sélectionnées pour cette exécution d'amortissement.  
    * L'option de traitement par lots est activée par défaut. Lorsque cette option est activée, la création et la validation du journal d'amortissement est exécutée en arrière-plan.  
5. Cliquez sur Créer un journal.
6. Accédez à Immobilisations > Entrées de journal > Journal des immobilisations.

