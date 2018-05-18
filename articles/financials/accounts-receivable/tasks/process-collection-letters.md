--- 
title: Traiter les lettres de relance
description: "Cette procédure indique comment créer, imprimer, et valider les lettres de relance."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dc837ea6513992a5f94e48baa366e279df297866
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="process-collection-letters"></a>Traiter les lettres de relance

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment créer, imprimer, et valider les lettres de relance. La société fictive USMF est citée en exemple dans cette tâche.


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Configuration d'une séquence de lettres de relance sur le profil de validation
1. Accédez à Crédit et relances > Paramétrage > Profils de validation client.
2. Cliquez sur Modifier.
    * Sélectionnez une séquence de lettres de relance dans la liste déroulante. Si vous ne souhaitez pas générer de lettres de relance pour les transactions utilisant ce profil de validation, laissez le champ vide.  
    * L'onglet Restrictions de table vous permet de modifier la manière dont les lettres de relance sont traitées. Si ce champ est défini sur Oui, les lettres de relance sont créées pour ce profil de validation.  
3. Fermez la page.

## <a name="create-collection-letters"></a>Créer des lettres de relance
1. Accédez à Crédit et relances > Lettre de relance > Créer des lettres de relance.
    * Vous devez sélectionner les types de transaction pour lesquels vous allez recueillir des lettres. Toutes les transactions en cours pour ces types sont incluses dans le calcul de ces montants.  
2. Dans le champ Lettre de relance, sélectionnez une option.
3. Spécifiez la date de la lettre de relance.
    * Il existe deux options de profil de validation : Compte : utilisez le profil de validation affecté au compte client pour chaque note d'intérêt.   Sélectionner : Utilisez le profil de validation sélectionné dans le champ Profil de validation.  
    * Sélectionnez un profil de validation si vous avez remplacé « Origine du profil de validation » par « Sélectionner ».  
4. Développez les enregistrements pour inclure la section.
5. Cliquez sur Filtre.
6. Dans le champ Critères, entrez un ID client. Par exemple, entrez US-001.
7. Cliquez sur OK.
8. Cliquez sur OK.

## <a name="print-collection-letters"></a>Imprimer/valider des lettres de relance
1. Accédez à Crédit et relances > Lettre de relance > Examiner et traiter les lettres de relance.
2. Sélectionnez Créé dans le champ Statut.
3. Dans le champ Imprimé, sélectionnez « Non imprimé ».
4. Cliquez sur Imprimer.
5. Cliquez sur Note de lettre de relance.
6. Développez les enregistrements pour inclure la section.
7. Spécifiez la date limite pour les validations.
8. Cliquez sur OK pour imprimer la lettre de relance.

## <a name="post-the-collection-letter"></a>Valider la lettre de relance
1. Cliquez sur Valider.
2. Entrer la date de validation pour la lettre de relance.
3. Développez les enregistrements pour inclure la section.
4. Cliquez sur OK.
5. Sélectionnez Validé dans le champ Statut.
6. Dans le champ Imprimé, sélectionnez une option.


