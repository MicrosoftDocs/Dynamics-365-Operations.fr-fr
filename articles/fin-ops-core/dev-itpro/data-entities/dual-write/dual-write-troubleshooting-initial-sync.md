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
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410079"
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

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Échecs d'auto-référence ou de référence circulaire lors de la synchronisation initiale

Vous pouvez recevoir un message d'erreur si l'un de vos mappages présente des auto-références ou des références circulaires : Ces erreurs entrent dans les catégories suivantes :

- [Mappage d'entité Fournisseurs V2 vers msdyn_vendors](#error-vendor-map)
- [Mappage d'entité Clients V3 vers Comptes](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a>Résoudre une erreur dans un mappage d'entité Fournisseurs V2 vers msdyn_vendors

Vous pouvez rencontrer les erreurs de synchronisation initiale suivantes sur le mappage de **Fournisseurs V2** vers **msdyn_vendors** si les entités comportent des enregistrements existants avec des valeurs dans les champs **PrimaryContactPersonId** et **InvoiceVendorAccountNumber**. C'est parce que **InvoiceVendorAccountNumber** est un champ qui fait référence à lui-même et que **PrimaryContactPersonId** est une référence circulaire dans le mappage des fournisseurs.

*Impossible de résoudre le GUID pour le champ : <field>. La recherche est introuvable : <value>. Essayez ces URL pour vérifier si les données de référence existent : https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity> ?$select=<field>&$filter=<field> eq <value>*

Voici quelques exemples :

- *Impossible de résoudre le GUID pour le champ : msdyn_vendorprimarycontactperson.msdyn_contactpersonid. La recherche est introuvable : 000056. Essayez ces URL pour vérifier si les données de référence existent : https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *Impossible de résoudre le GUID pour le champ : msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. La recherche est introuvable : V24-1. Essayez ces URL pour vérifier si les données de référence existent : https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1*

Si vous avez des enregistrements comportant des valeurs dans ces champs dans l'entité fournisseur, suivez les étapes de la section ci-dessous pour terminer la synchronisation initiale avec succès.

1. Dans l'application Finance and Operations, supprimez les champs **PrimaryContactPersonId** et **InvoiceVendorAccountNumber** du mappage et enregistrez les modifications.

    1. Accédez à la page de mappage en double écriture pour **Fournisseurs V2 (msdyn_vendors)** et sélectionnez l'onglet **Mappages d'entités**. Dans le filtre de gauche, sélectionnez **Finance and Operations apps.Fournisseurs V2**. Dans le filtre de droite, sélectionnez **Ventes.Fournisseur**.

    2. Recherchez **primarycontactperson** pour trouver le champ source **PrimaryContactPersonId**.
    
    3. Cliquez sur le bouton **Actions** et sélectionnez **Supprimer**.
    
        ![Auto-référence ou référence circulaire 3](media/vend_selfref3.png)
    
    4. Répétez l'opération pour supprimer le champ **InvoiceVendorAccountNumber**.
    
        ![Auto-référence ou référence circulaire 4](media/vend-selfref4.png)
    
    5. Enregistrez les modifications de mappage.

2. Désactivez le suivi des modifications pour l'entité **Fournisseurs V2**.

    1. Accédez à **Gestion des données \> Entités de données**.
    
    2. Sélectionnez l'entité **Fournisseurs V2**.
    
    3. Cliquez sur **Options** dans la barre de menus, puis sur **Suivi des modifications**.
    
        ![Auto-référence ou référence circulaire 5](media/selfref_options.png)
    
    4. Cliquez sur **Désactiver le suivi des modifications**.
    
        ![Auto-référence ou référence circulaire 6](media/selfref_tracking.png)

3. Exécutez la synchronisation initiale du mappage **Fournisseurs V2 (msdyn_vendors)**. La synchronisation initiale doit s'exécuter correctement sans aucune erreur.

4. Exécutez la synchronisation initiale pour le mappage **Contacts CDS V2 (contacts)**. Vous devez synchroniser ce mappage si vous souhaitez synchroniser le champ de contact principal sur l'entité des fournisseurs, car les enregistrements de contacts doivent également être synchronisés initialement.

5. Ajoutez les champs **PrimaryContactPersonId** et **InvoiceVendorAccountNumber** de nouveau dans le mappage **Fournisseurs V2 (msdyn_vendors)** et enregistrez le mappage.

6. Exécutez à nouveau la synchronisation initiale du mappage **Fournisseurs V2 (msdyn_vendors)**. Tous les enregistrements seront synchronisés, car le suivi des modifications est désactivé.

7. Activez le suivi des modifications pour l'entité **Fournisseurs V2**.

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a>Résoudre une erreur dans le mappage d'entité Clients V3 vers Comptes

Vous pouvez rencontrer les erreurs de synchronisation initiale suivantes sur le mappage de **Clients V3** vers **Comptes** si les entités comportent des enregistrements existants avec des valeurs dans les champs **ContactPersonID** et **InvoiceAccount**. C'est parce que **InvoiceAccount** est un champ qui fait référence à lui-même et que **ContactPersonID** est une référence circulaire dans le mappage des fournisseurs.

*Impossible de résoudre le GUID pour le champ : <field>. La recherche est introuvable : <value>. Essayez ces URL pour vérifier si les données de référence existent : https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity> ?$select=<field>&$filter=<field> eq <value>*

- *Impossible de résoudre le GUID pour le champ : primarycontactid.msdyn_contactpersonid. La recherche est introuvable : 000056. Essayez ces URL pour vérifier si les données de référence existent : https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *Impossible de résoudre le GUID pour le champ : msdyn_billingaccount.accountnumber. La recherche est introuvable : 1206-1. Essayez ces URL pour vérifier si les données de référence existent : https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*

Si vous avez des enregistrements comportant des valeurs dans ces champs dans l'entité client, suivez les étapes de la section ci-dessous pour terminer la synchronisation initiale avec succès. Vous pouvez utiliser cette approche pour toutes les entités prêtes à l'emploi telles que les comptes et les contacts.

1. Dans l'application Finance and Operations, supprimez les champs **ContactPersonID** et **InvoiceAccount** du mappage **Clients V3 (comptes)** et enregistrez le mappage.

    1. Accédez à la page de mappage en double écriture pour **Clients V3 (comptes)** et sélectionnez l'onglet **Mappages d'entités**. Dans le filtre de gauche, sélectionnez **Finance and Operations apps.Clients V3**. ns le filtre de droite, sélectionnez **Common Data Service.Compte**.

    2. Recherchez **contactperson** pour trouver le champ source **ContactPersonID**.
    
    3. Cliquez sur le bouton **Actions** et sélectionnez **Supprimer**.
    
        ![Auto-référence ou référence circulaire 3](media/cust_selfref3.png)
    
    4. Répétez l'opération pour supprimer le champ **InvoiceAccount**.
    
        ![Auto-référence ou référence circulaire](media/cust_selfref4.png)
    
    5. Enregistrez les modifications de mappage.

2. Désactivez le suivi des modifications pour l'entité **Clients V3**.

    1. Accédez à **Gestion des données \> Entités de données**.
    
    2. Sélectionnez l'entité **Clients V3**.
    
    3. Cliquez sur **Options** dans la barre de menus, puis sur **Suivi des modifications**.
    
        ![Auto-référence ou référence circulaire 5](media/selfref_options.png)
    
    4. Cliquez sur **Désactiver le suivi des modifications**.
    
        ![Auto-référence ou référence circulaire 6](media/selfref_tracking.png)

3. Exécutez la synchronisation initiale pour le mappage **Clients V3 (Comptes)**. La synchronisation initiale doit s'exécuter correctement sans aucune erreur.

4. Exécutez la synchronisation initiale pour le mappage **Contacts CDS V2 (contacts)**. Il existe 2 mappages du même nom. Sélectionnez celui portant la description **Modèle à double écriture pour la synchronisation entre FO.CDS Fournisseur Contacts V2 et CDS.Contacts. Nécessite un nouveau package \[Dynamics365SupplyChainExtended\].** Dans l'onglet **Détails** du mappage.

5. Ajoutez les champs **InvoiceAccount** et **ContactPersonId** de nouveau dans le mappage **Clients V3 (Comptes)** et enregistrez le mappage. Maintenant, les deux champs **InvoiceAccount** et **ContactPersonId** font à nouveau partie du mode de synchronisation en direct. À l'étape suivante, vous achèverez la synchronisation initiale de ces champs.

6. Exécutez la synchronisation à nouveau initiale pour le mappage **Clients V3 (Comptes)**. Le suivi des modifications étant désactivé, l'exécution de la synchronisation synchronisera les données pour **InvoiceAccount** et **ContactPersonId** de l'application Finance and Operations vers Common Data Service.

7. Pour synchroniser les données pour **InvoiceAccount** et **ContactPersonId** depuis Common Data Service vers Finance and Operations, vous utilisez un projet d'intégration de données.

    1. Dans Power Apps, créez un projet d'intégration de données entre **Ventes.Compte** et les entités **Finance and Operations apps.Clients V3**. La direction des données doit aller de Common Data Service vers l'application Finance and Operations.  Comme **InvoiceAccount** est un nouvel attribut en double écriture, vous pouvez souhaiter ignorer la synchronisation initiale pour cet attribut. Pour plus d'informations, voir [Intégration des données dans Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).

        L'image suivante montre un projet qui met à jour **CustomerAccount** et **ContactPersonId**.

        ![Auto-référence ou référence circulaire](media/cust_selfref6.png)

    2. Ajoutez les critères de l'entreprise dans le filtre du côté Common Data Service, car seuls les enregistrements correspondant aux critères de filtrage seront mis à jour dans l'application Finance and Operations. Pour ajouter un filtre, cliquez sur l'icône de filtre. Dans la boîte de dialogue **Modifier la requête**, vous pouvez ajouter une requête de filtre telle que **_msdyn_company_value eq '\<guid\>'**. Si l'icône de filtre n'est pas présente, créez un ticket de support pour demander à l'équipe d'intégration de données d'activer la fonction de filtrage sur votre locataire. Si vous n'entrez pas de requête de filtre pour **_msdyn_company_value**, tous les enregistrements sont synchronisés.

        ![Auto-référence ou référence circulaire](media/cust_selfref7.png)

        Ceci termine la synchronisation initiale des enregistrements.

8. Activez le suivi des modifications pour l'entité **Clients V3** dans l'application Finance and Operations.

