---
title: Résoudre les problèmes lors de la synchronisation initiale
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes susceptibles de survenir pendant la synchronisation initiale.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d51b547093825a6e7730b5fdfcfb1c081776c63c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172712"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Résoudre les problèmes lors de la synchronisation initiale

[!include [banner](../../includes/banner.md)]



Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service. Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes susceptibles de survenir pendant la synchronisation initiale. 

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d'administrateur système ou les identifiants d'admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d'identification sont requis.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Vérifier les erreurs de synchronisation initiales dans une application Finance and Operations

Après avoir activé les modèles de mappage, le statut des cartes doit être **En cours d'exécution**. Si le statut est défini sur **Pas en cours d'exécution**, des erreurs se sont produites lors de la synchronisation initiale. Pour afficher les erreurs, sélectionnez l'onglet **Détails de la synchronisation initiale** sur la page **Double écriture**.

![Onglet Détails de la synchronisation initiale](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Vous ne pouvez pas terminer la synchronisation initiale : 400 Bad Request

**Rôle requis pour résoudre le problème :** Administrateur système

Vous pouvez recevoir le message d'erreur suivant lorsque vous essayez d'exécuter le mappage et la synchronisation initiale :

*Le serveur distant a renvoyé une erreur : (400) Bad Request.), l'exportation AX a rencontré une erreur*

Voici un exemple du message de l'intégralité du message d'erreur.

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

Si cette erreur se produit régulièrement et si vous ne pouvez pas terminer la synchronisation initiale, procédez comme suit pour résoudre le problème.

1. Connectez-vous à la machine virtuelle pour l'application Finance and Operations.
2. Ouvrez Microsoft Management Console. 
3. Dans le volet **Services**, assurez-vous que le service de structure d'exportation et d'importation des données Microsoft Dynamics 365 est en cours d'exécution. Redémarrez-le s'il a été arrêté, car la synchronisation initiale l'exige.

## <a name="initial-synchronization-error-403-forbidden"></a>Erreur de synchronisation initiale : 403 Forbidden

Vous pouvez recevoir le message d'erreur suivant pendant la synchronisation initiale :

*(\[Forbidden\], Le serveur distant a renvoyé une erreur : (403) Forbidden.), l'exportation AX a rencontré une erreur*

Pour régler le problème, procédez comme suit.

1. Connectez-vous à l'application Finance and Operations.
2. Sur la page **Applications Azure Active Directory**, supprimez le client **DtAppID**, puis ajoutez-le à nouveau.

![Liste des applications Azure AD](media/aad_applications.png)

## <a name="self-reference-failures-during-initial-synchronization"></a>Échecs d'auto-référence lors de la synchronisation initiale

Vous pouvez recevoir un message d'erreur qui ressemble à l'exemple suivant si l'un de vos mappages a des références automatiques :

*Sur les fournisseurs V2, l'erreur suivante : ID enregistrement : nouvel enregistrement, Message d'erreur : Impossible de résoudre le guid pour le champ : msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. La valeur de recherche est introuvable : CN-001. Essayez cette URL pour vérifier si les données de référence existent : `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*

Ce type d'erreur se produit lors de la synchronisation initiale des mappages dotés d'auto-références. Dans l'exemple précédent, le compte de facture de champ fait référence à l'entité fournisseur.

Pour résoudre le problème, vous devrez peut-être exécuter le mappage deux fois avant la réussite de la synchronisation initiale.

