---
title: Fractionner une immobilisation
description: Cette rubrique explique comment fractionner un pourcentage d'un registre d'immobilisations en un nouveau registre d'immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40703622bc8c7a21451d31e7606596c5edbe90f7
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000291"
---
# <a name="split-a-fixed-asset"></a>Fractionner une immobilisation

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment fractionner un pourcentage d'un registre d'immobilisations en un nouveau registre d'immobilisations. Il utilise le rôle de comptable et les données de démonstration de la société USMF fictive.

## <a name="create-a-new-fixed-asset"></a>Créer une nouvelle immobilisation

1. Dans le volet de navigation, accédez à **Modules \> Immobilisations \> Immobilisations \> Immobilisations**.
2. Sélectionnez **Nouveau**.
3. Entrez ou sélectionnez une valeur dans le champ **Groupe d'immobilisations**. Notez le numéro d'immobilisation à utiliser dans le processus de fractionnement ultérieurement.
4. Dans le champ **Nom** , entrez une valeur.
5. Permet de fermer l'écran.

## <a name="split-a-fixed-asset"></a>Fractionner une immobilisation

Avant qu'un actif entièrement amorti ne soit fractionné, le statut du registre des immobilisations doit être modifié manuellement de **Clôturé** à **En cours**. Cette étape est obligatoire car le statut du registre doit être **En cours** si vous devez valider des transactions pour l'immobilisation (par exemple, pour une vente de cession). Une fois le statut du registre des immobilisations modifié, procédez comme suit pour fractionner l'immobilisation.

1. Dans la liste, recherchez et sélectionnez le lien de l'immobilisation à fractionner.
2. Sélectionnez **Registres**. Sélectionnez le registre pour fractionner la nouvelle immobilisation.
3. Sélectionnez **Fonctions**.
4. Sélectionnez **Fractionner une immobilisation**.
5. Dans le champ **À l'immobilisation** , entrez ou sélectionnez une valeur.
6. Dans le champ **Vers le registre** , sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
7. Entrez une date dans le champ **Date de transaction**.
8. Entrez un numéro dans le champ **Pourcentage**.
9. Dans le champ **Nom de journal** , entrez ou sélectionnez une valeur.
10. Cliquez sur **OK**.

## <a name="post-the-journal-transaction"></a>Valider la transaction de journal

1. Dans le volet de navigation, accédez à **Modules \> Immobilisations \> Entrées de journal \> Journal des immobilisations**.
2. Dans la liste, sélectionnez le journal créé avec le processus de fractionnement.
3. Sélectionnez **Lignes**.

    - Vérifiez les lignes de journal créées.
    - Une transaction d'ajustement d'acquisition est créée pour l'actif original pour diminuer la valeur par le pourcentage spécifié lors du processus de fractionnement.
    - Une transaction d'acquisition est créée pour le nouvel actif pour le même montant.

4. Sélectionnez **Valider**.
