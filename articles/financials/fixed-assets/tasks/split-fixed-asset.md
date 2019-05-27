---
title: Fractionner une immobilisation
description: Ce guide de tâche fractionnera un pourcentage d'un registre d'immobilisations en un nouveau registre d'immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6be9de64265a4d7b5c91af3ee8acfce80c78e0f1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566890"
---
# <a name="split-a-fixed-asset"></a>Fractionner une immobilisation

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche fractionnera un pourcentage d'un registre d'immobilisations en un nouveau registre d'immobilisations.  Il utilise le rôle de comptable et les données de démonstration de la société USMF fictive.


## <a name="create-a-new-fixed-asset"></a>Créer une nouvelle immobilisation
1. Accédez à Immobilisations > Immobilisations > Immobilisations.
2. Cliquez sur Nouveau.
3. Saisissez ou sélectionnez une valeur dans le champ Groupe d'immobilisations.
4. Notez le numéro d'immobilisation à utiliser dans le processus de fractionnement ultérieurement.
5. Tapez une valeur dans le champ Nom.
6. Permet de fermer l'écran.

## <a name="split-a-fixed-asset"></a>Fractionner une immobilisation
1. Dans la liste, recherchez et sélectionnez l'immobilisation à fractionner.
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
3. Cliquez sur Registres.
    * Sélectionnez le registre pour fractionner la nouvelle immobilisation.  
4. Cliquez sur Fonctions.
5. Cliquez sur Fractionner une immobilisation.
6. Dans le champ À l'immobilisation, entrez ou sélectionnez une valeur.
7. Dans le champ Vers le registre, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Entrez une date dans le champ Date de transaction.
9. Entrez un numéro dans le champ Pourcentage.
10. Dans le champ Nom de journal, entrez ou sélectionnez une valeur.
11. Cliquez sur OK.

## <a name="post-the-journal-transaction"></a>Valider la transaction de journal
1. Accédez à Immobilisations > Entrées de journal > Journal des immobilisations.
2. Dans la liste, sélectionnez le journal créé avec le processus de fractionnement.
3. Cliquez sur Lignes.
    * Vérifiez les lignes de journal créées.  Une transaction d'ajustement d'acquisition est créée pour l'actif original pour diminuer la valeur par le pourcentage spécifié lors du processus de fractionnement.  Une transaction d'acquisition est créée pour le nouvel actif pour le même montant.  
4. Cliquez sur Valider.

