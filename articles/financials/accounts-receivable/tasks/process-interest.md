---
title: Traiter les intérêts
description: Cette procédure permet d'indiquer comment créer, imprimer, et valider les notes d'intérêt.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7170a7a14237058064ed3091e9437cae312e6bd5
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916274"
---
# <a name="process-interest"></a>Traiter les intérêts

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure permet d'indiquer comment créer, imprimer, et valider les notes d'intérêt. La société fictive USMF est citée en exemple dans cette tâche.


## <a name="set-up-interest-on-the-posting-profile"></a>Paramétrer des intérêts dans le profil de validation
1. Dans le **Volet de navigation**, accédez à **Modules > Crédit et recouvrements > Paramétrage > Profils de validation des clients**.
2. Cliquez sur **Modifier**.
3. Dans l'**organisateur Paramétrage**, dans le champ **Code d'intérêt**, sélectionnez un code d'intérêt dans la liste déroulante. Si vous ne souhaitez pas calculer d'intérêts pour les transactions utilisant ce profil de validation, laissez le champ vide. L'organisateur **Restriction de table** vous permet de modifier la manière dont les intérêts sont traités. Si ce champ est défini sur Oui, les intérêts sont calculés pour ce profil de validation.  

## <a name="calculate-interest"></a>Calculer les intérêts
1. Dans le **Volet de navigation**, accédez à **Modules > Crédit et recouvrements > Intérêt > Créer des notes d'intérêt**.
2. Vous devez sélectionner les types de transaction pour lesquels vous voulez calculer les intérêts. Toutes les transactions en cours pour ces types sont incluses dans le calcul de ces montants.  
3. Si vous définissez **Intérêt** sur « Oui », vous calculerez les intérêts sur les intérêts. Vous pouvez vérifier les règles régissant le calcul des intérêts sur les intérêts avant de les inclure pour ces transactions.  
4. Dans le champ **Date de début**, entrez une date à partir de laquelle cet intérêt est calculé. Si vous ne spécifiez pas de **Date de début**, alors toutes les notes d'intérêt non validées sont annulées et les intérêts sont recalculés à partir de la date de la transaction.
5. Dans le champ **Date de fin**, entrez une date de fin à laquelle cet intérêt est calculé.
6. Dans le champ **Origine du profil de validation**, sélectionnez une option. Il existe trois options de profil de validation :
    - Compte : Utilisez le profil de validation affecté au compte client pour chaque note d'intérêt. 
    - Sélectionner : Utilisez le profil de validation sélectionné dans le champ Profil de validation.
    - Transaction : Utilisez le profil de validation individuel des transactions sur lesquelles les intérêts sont calculés pour chaque note d'intérêt. Les transactions auxquelles vous n'avez attribué aucun profil de validation emploient le profil de validation spécifié dans la zone Comptabilité et taxe de l'écran Paramètres de la comptabilité client.  
7. Développez l'organisateur **Enregistrements à inclure**.
8. Cliquez sur **Filtre**.
9. Dans le champ **Critères**, entrez un ID client. Par exemple, entrez US-001.
6. Cliquez sur **OK**.
7. Cliquez sur **OK**.

## <a name="print-interest-notes"></a>Imprimer des notes d'intérêt
1. Dans le **Volet de navigation**, accédez à **Modules > Crédit et recouvrements > Intérêt > Examiner et traiter les notes d'intérêt**.
2. Dans le champ **Statut**, sélectionnez « Créé ».
3. Dans le champ **Imprimé**, sélectionnez « Non imprimé ».
4. Cliquez sur **Imprimer**.
5. Développez l'organisateur **Enregistrements à inclure**.
6. Cliquez sur **OK**.
7. Fermez la page.

## <a name="post-the-interest-note"></a>Valider la note d'intérêt
1. Sélectionnez une note d'intérêt qui est prête à valider (le statut est créé).
2. Cliquez sur **Valider**.
3. Entrez la date de validation pour la note d'intérêt. Sélectionnez Oui pour créer une écriture comptable générale pour chaque note d'intérêt. Si vous ne sélectionnez pas Oui, les intérêts de toutes les notes d'intérêt du client sont cumulés et validés dans une transaction de la Comptabilité.  
4. Développez l'organisateur **Enregistrements à inclure**.
5. Cliquez sur **OK**.
6. Dans le champ **Statut**, sélectionnez « Validé ».

