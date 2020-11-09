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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 4d0ca1fb4b7a4964194516544686b6bb7d26e76c
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997324"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Résoudre les problèmes lors de la synchronisation initiale

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service. Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes susceptibles de survenir pendant la synchronisation initiale.

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d'administrateur système ou les identifiants d'admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d'identification sont requis.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Vérifier les erreurs de synchronisation initiales dans une application Finance and Operations

Après avoir activé les modèles de mappage, le statut des cartes doit être **En cours d'exécution**. Si le statut est défini sur **Pas en cours d'exécution** , des erreurs se sont produites lors de la synchronisation initiale. Pour afficher les erreurs, sélectionnez l'onglet **Détails de la synchronisation initiale** sur la page **Double écriture**.

![Erreur sur l'onglet Détails de la synchronisation initiale](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Vous ne pouvez pas terminer la synchronisation initiale : 400 Bad Request

**Rôle requis pour résoudre le problème :** Administrateur système

Vous pouvez recevoir le message d'erreur suivant lorsque vous essayez d'exécuter le mappage et la synchronisation initiale :

*(\[Bad Request\], Le serveur distant a renvoyé une erreur : (400) Bad Request.), l'exportation AX a rencontré une erreur*

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
3. Dans le volet **Services** , assurez-vous que le service de structure d'exportation et d'importation des données Microsoft Dynamics 365 est en cours d'exécution. Redémarrez-le s'il a été arrêté, car la synchronisation initiale l'exige.

## <a name="initial-synchronization-error-403-forbidden"></a>Erreur de synchronisation initiale : 403 Forbidden

Vous pouvez recevoir le message d'erreur suivant pendant la synchronisation initiale :

*(\[Forbidden\], Le serveur distant a renvoyé une erreur : (403) Forbidden.), l'exportation AX a rencontré une erreur*

Pour régler le problème, procédez comme suit.

1. Connectez-vous à l'application Finance and Operations.
2. Sur la page **Applications Azure Active Directory** , supprimez le client **DtAppID** , puis ajoutez-le à nouveau.

![Client DtAppID dans la liste des applications Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Échecs d'auto-référence ou de référence circulaire lors de la synchronisation initiale

Vous pouvez recevoir un message d'erreur si l'un de vos mappages présente des auto-références ou des références circulaires : Ces erreurs entrent dans les catégories suivantes :

- [Erreurs dans le mappage d'entités Fournisseurs V2–avec–Fournisseurs_msdyn](#error-vendor-map)
- [Erreurs dans le mappage d'entités Clients V3-avec-Comptes](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a>Résoudre les erreurs dans le mappage d'entités Fournisseurs V2–avec–Fournisseurs_msdyn

Vous pouvez rencontrer les erreurs de synchronisation initiale suivantes pour le mappage de **Fournisseurs V2** avec **Fournisseurs\_msdyn** si les entités comportent des enregistrements existants avec des valeurs dans les champs **PrimaryContactPersonId** et **InvoiceVendorAccountNumber**. Ces erreurs se produisent parce que **InvoiceVendorAccountNumber** est un champ qui fait référence à lui-même et que **PrimaryContactPersonId** est une référence circulaire dans le mappage des fournisseurs.

Les messages d'erreur que vous recevez auront le formulaire suivant.

*Impossible de résoudre le GUID pour le champ : \<field\>. La recherche est introuvable : \<value\>. Essayez ces URL pour vérifier si les données de référence existent : `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Voici quelques exemples :

- *Impossible de résoudre le GUID pour le champ : msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. La recherche est introuvable : 000056. Essayez ces URL pour vérifier si les données de référence existent : `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Impossible de résoudre le GUID pour le champ : msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. La recherche est introuvable : V24-1. Essayez ces URL pour vérifier si les données de référence existent : `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*

Si des enregistrements de l'entité fournisseur ont des valeurs dans les champs **PrimaryContactPersonId** et **InvoiceVendorAccountNumber** , suivez les étapes de la section ci-dessous pour effectuer la synchronisation initiale.

1. Dans l'application Finance and Operations, supprimez les champs **PrimaryContactPersonId** et **InvoiceVendorAccountNumber** du mappage et enregistrez le mappage.

    1. Dans la page de mappage en double écriture pour **Fournisseurs V2 (fournisseurs\_msdyn)** , dans l'onglet **Mappages d'entités** dans le filtre, sélectionnez **App.Finance and Operations.Fournisseurs V2**. Dans le filtre de droite, sélectionnez **Ventes.Fournisseur**.
    2. Recherchez **primarycontactperson** pour trouver le champ source **PrimaryContactPersonId**.
    3. Sélectionnez **Actions** , puis sélectionnez **Supprimer**.

        ![Suppression du champ PrimaryContactPersonId](media/vend_selfref3.png)

    4. Répétez cette procédure pour supprimer le champ **InvoiceVendorAccountNumber**.

        ![Suppression du champ InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. Enregistrez vos modifications dans le mappage.

2. Désactivez le suivi des modifications pour l'entité **Fournisseurs V2**.

    1. Dans l'espace de travail **Gestion des données** , sélectionnez la vignette **Entités de données**.
    2. Sélectionnez l'entité **Fournisseurs V2**.
    3. Dans le volet Actions, sélectionnez **Options** , puis sélectionnez **Change tracking**.

        ![Sélection de l'option de Suivi des modifications](media/selfref_options.png)

    4. Sélectionnez **Désactiver le suivi des modifications**.

        ![Sélection du paramètre Désactiver le suivi des modifications](media/selfref_tracking.png)

3. Exécutez la synchronisation initiale du mappage **Fournisseurs V2 (fournisseurs\_msdyn)**. La synchronisation initiale doit s'exécuter correctement sans aucune erreur.
4. Exécutez la synchronisation initiale pour le mappage **Contacts CDS V2 (contacts)**. Vous devez synchroniser ce mappage si vous souhaitez synchroniser le champ de contact principal sur l'entité des fournisseurs, car la synchronisation initiale doit également être effectuée pour les enregistrements de contacts.
5. Ajoutez les champs **PrimaryContactPersonId** et **InvoiceVendorAccountNumber** de nouveau dans le mappage **Fournisseurs V2 (fournisseurs\_msdyn)** , puis enregistrez le mappage.
6. Exécutez à nouveau la synchronisation initiale du mappage **Fournisseurs V2 (fournisseurs\_msdyn)**. Parce que le suivi des modifications est désactivé, tous les enregistrements seront synchronisés.
7. Réactivez le suivi des modifications pour l'entité **Fournisseurs V2**.

## <a name="resolve-errors-in-the-customers-v3toaccounts-entity-mapping"></a><a id="error-customer-map"></a>Résoudre des erreurs dans le mappage d'entité Clients V3–vers–Comptes

Vous pouvez rencontrer les erreurs de synchronisation initiale suivantes pour le mappage de **Clients V3** avec **Comptes** si les entités comportent des enregistrements existants avec des valeurs dans les champs **ContactPersonID** et **InvoiceAccount**. Ces erreurs se produisent parce que **InvoiceAccount** est un champ qui fait référence à lui-même et que **ContactPersonID** est une référence circulaire dans le mappage des fournisseurs.

Les messages d'erreur que vous recevez auront le formulaire suivant.

*Impossible de résoudre le GUID pour le champ : \<field\>. La recherche est introuvable : \<value\>. Essayez ces URL pour vérifier si les données de référence existent : `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Voici quelques exemples :

- *Impossible de résoudre le GUID pour le champ : primarycontactid.msdyn\_contactpersonid. La recherche est introuvable : 000056. Essayez ces URL pour vérifier si les données de référence existent : `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Impossible de résoudre le GUID pour le champ : msdyn\_billingaccount.accountnumber. La recherche est introuvable : 1206-1. Essayez ces URL pour vérifier si les données de référence existent : `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*

Si des enregistrements de l'entité client ont des valeurs dans les champs **ContactPersonID** et **InvoiceAccount** , suivez les étapes de la section ci-dessous pour effectuer la synchronisation initiale. Vous pouvez utiliser cette approche pour toutes les entités prêtes à l'emploi telles que **Comptes** et **Contacts**.

1. Dans l'application Finance and Operations, supprimez les champs **ContactPersonID** et **InvoiceAccount** du mappage **Clients V3 (comptes)** et enregistrez le mappage.

    1. Dans la page de mappage en double écriture pour **Clients V3 (comptes)** , dans l'onglet **Mappages d'entités** , sous le filtre de gauche, sélectionnez **Finance and Operations apps.Clients V3**. ns le filtre de droite, sélectionnez **Common Data Service.Compte**.
    2. Recherchez **contactperson** pour trouver le champ source **ContactPersonID**.
    3. Sélectionnez **Actions** , puis sélectionnez **Supprimer**.

        ![Suppression du champ PrimaryContactPersonId](media/cust_selfref3.png)

    4. Répétez cette procédure pour supprimer le champ **InvoiceAccount**.

        ![Suppression du champ InvoiceAccount](media/cust_selfref4.png)

    5. Enregistrez vos modifications dans le mappage.

2. Désactivez le suivi des modifications pour l'entité **Clients V3**.

    1. Dans l'espace de travail **Gestion des données** , sélectionnez la vignette **Entités de données**.
    2. Sélectionnez l'entité **Clients V3**.
    3. Dans le volet Actions, sélectionnez **Options** , puis sélectionnez **Change tracking**.

        ![Sélection de l'option de Suivi des modifications](media/selfref_options.png)

    4. Sélectionnez **Désactiver le suivi des modifications**.

        ![Sélection du paramètre Désactiver le suivi des modifications](media/selfref_tracking.png)

3. Exécutez la synchronisation initiale pour le mappage **Clients V3 (Comptes)**. La synchronisation initiale doit s'exécuter correctement sans aucune erreur.
4. Exécutez la synchronisation initiale pour le mappage **Contacts CDS V2 (contacts)**.

    > [!NOTE]
    > Il y a deux cartes qui portent le même nom. Veillez à sélectionner le mappage ayant la description suivante dans l'onglet **Détails**  : **Modèle à double écriture pour la synchronisation entre FO.CDS Fournisseur Contacts V2 et CDS.Contacts. Nécessite un nouveau package \[Dynamics365SupplyChainExtended\].**

5. Ajoutez les champs **InvoiceAccount** et **ContactPersonId** de nouveau dans le mappage **Clients V3 (Comptes)** , puis enregistrez le mappage. Les deux champs **InvoiceAccount** et **ContactPersonId** font maintenant partie à nouveau du mode de synchronisation en direct. À l'étape suivante, vous effectuerez la synchronisation initiale de ces champs.
6. Exécutez à nouveau la synchronisation initiale pour le mappage **Clients V3 (Comptes)**. Le suivi des modifications étant désactivés, les données de **InvoiceAccount** et **ContactPersonId** seront synchronisées à partir de l'application Finance and Operations avec Common Data Service.
7. Pour synchroniser les données pour **InvoiceAccount** et **ContactPersonId** depuis Common Data Service vers l'application Finance and Operations, vous utilisez un projet d'intégration de données.

    1. Dans Power Apps, créez un projet d'intégration de données entre **Ventes.Compte** et les entités **Finance and Operations apps.Clients V3**. La direction des données doit aller de Common Data Service vers l'application Finance and Operations. Comme **InvoiceAccount** est un nouvel attribut en double écriture, vous pourrez souhaiter ignorer la synchronisation initiale pour cet attribut. Pour plus d'informations, voir [Intégration des données dans Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).

        L'illustration suivante montre un projet qui met à jour **CustomerAccount** et **ContactPersonId**.

        ![Projet d'intégration de données pour mettre à jour CustomerAccount et ContactPersonId](media/cust_selfref6.png)

    2. Ajoutez les critères de l'entreprise dans le filtre du côté Common Data Service, car seuls les enregistrements correspondant aux critères de filtrage seront mis à jour dans l'application Finance and Operations. Pour ajouter un filtre, sélectionnez le bouton de filtre. Ensuite, dans la boîte de dialogue **Modifier la requête** , vous pouvez ajouter une requête de filtre telle que **\_msdyn\_company\_value eq '\<guid\>'**. 

        > [REMARQUE] Si le bouton de filtre n'est pas présent, créez un ticket de support pour demander à l'équipe d'intégration de données d'activer la fonction de filtrage sur votre locataire.

        Si vous n'entrez pas de requête de filtre pour **\_msdyn\_company\_value** , tous les enregistrements seront synchronisés.

        ![Ajout d'une requête de filtre](media/cust_selfref7.png)

    La synchronisation initiale des enregistrements est maintenant terminée.

8. Dans l'application Finance and Operations, réactivez le suivi des modifications pour l'entité **Clients V3**.
