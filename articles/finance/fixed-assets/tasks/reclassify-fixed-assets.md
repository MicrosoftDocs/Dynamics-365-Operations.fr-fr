---
title: Reclassifier des immobilisations
description: Cet article explique le processus de reclassement des actifs. Pour reclassifier une immobilisation, vous devez la transférer à un nouveau groupe d’immobilisations ou lui affecter un nouveau numéro d’immobilisation au sein du même groupe.
author: moaamer
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4bd901b1709f0b006cecfbbf6d8c170b56f89d19
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284361"
---
# <a name="reclassify-fixed-assets"></a>Reclassifier des immobilisations

[!include [banner](../../includes/banner.md)]

Pour reclassifier une immobilisation, vous devez la transférer à un nouveau groupe d’immobilisations ou lui affecter un nouveau numéro d’immobilisation au sein du même groupe. 

Lorsqu’une immobilisation est reclassifiée :

- Tous les registres de l’immobilisation existante sont créés pour la nouvelle immobilisation. Les informations paramétrées pour l’immobilisation originale sont copiées vers la nouvelle immobilisation. Le statut des registres de l’immobilisation originale est Clôturé. 

- Les nouveaux registres des nouvelles immobilisations indiquent la date de reclassification dans le champ **Date d’acquisition**. La date dans le champ **Date d’exécution de l’amortissement** est copiée à partir des informations originales relatives à l’actif. Si l’amortissement a déjà commencé, le champ **Date du dernier amortissement** affiche la date de la reclassification. 

- Les transactions d’immobilisation existantes relatives à l’immobilisation originale sont annulées et regénérées pour la nouvelle immobilisation.

- Lorsqu’un actif faisant l’objet d’une transaction de transfert a été reclassé, le système affiche un message dans le **Centre d’action** pour indiquer qu’une opération de transfert n’a pas été effectuée pendant le processus de reclassement. Il est nécessaire de terminer une transaction de transfert pour déplacer les transactions de reclassement existantes vers les dimensions financières appropriées. 

   Au cours du processus de reclassement, le système exécute les actions suivantes pour reclasser le solde de l’actif de l’actif d’origine vers le nouvel actif. 
   
   - Le processus de reclassement copie les données du livre d’immobilisations d’origine vers le nouveau livre d’immobilisations.

   - La transaction de reclassement utilise les informations de l’acquisition comptabilisée d’origine qui incluent des informations sur la dimension financière qui sont incluses dans la transaction d’acquisition.  
   
   - Dans le même temps, le processus de reclassement annule la transaction initiale d’acquisition et de transfert d’actifs. 

Le diagramme et la procédure suivants fournissent un exemple du processus de reclassement. 

[![Schéma illustrant le processus de reclassement.](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)

Procédez comme suit pour reclassifier une immobilisation :

1. Allez dans **Immobilisations > Tâches périodiques > Reclassement.**
2. Dans le champ **Groupe d’immobilisations**, sélectionnez le groupe à reclasser.
3. Dans le champ **Numéro d’immobilisation**, sélectionnez l’immobilisation à reclasser.
4. Dans le champ **Nouveau groupe d’immobilisations**, sélectionnez un groupe vers lequel transférer l’immobilisation.
    * Si le nouveau groupe d’immobilisations est associé à une souche de numéros, le champ **Nouveau numéro d’immobilisation** est mis à jour avec le numéro de la nouvelle souche de numéros du groupe d’immobilisations. Sinon, le champ **Nouveau numéro d’immobilisation** est mis à jour avec le numéro de la nouvelle souche de numéros configuré dans la page **Paramètres d’immobilisation**. Si une souche de numéros n’est pas configurée dans la page **Paramètres d’immobilisation**, entrez un nombre dans le champ **Nouveau numéro d’immobilisation**.  
5. Dans le champ **Date de reclassification**, entrez une date.
6. Dans le champ **Souche de N° documents**, entrez ou sélectionnez une valeur.
7. Cliquez sur **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
