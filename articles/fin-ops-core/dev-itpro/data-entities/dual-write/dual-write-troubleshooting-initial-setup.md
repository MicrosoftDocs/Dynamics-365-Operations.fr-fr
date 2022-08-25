---
title: Résoudre les problèmes lors de la configuration initiale
description: Cet article fournit des informations pour la résolution des problèmes pouvant survenir lors de la configuration initiale de l’intégration de la double écriture.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d33fc6f4895b53f16cc6957a3a2fc6b1abe90a2f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289512"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Résoudre les problèmes lors de la configuration initiale

[!include [banner](../../includes/banner.md)]

Cet article fournit des informations sur le dépannage de l’intégration de la double-écriture entre les applications de finances et d’opérations et Dataverse. Notamment elle fournit des informations pour la résolution des problèmes pouvant survenir lors de la configuration initiale de l’intégration de la double écriture.

> [!IMPORTANT]
> Certains des problèmes abordés dans cet article peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Vous ne pouvez pas lier une application de finances et d’opérations à Dataverse

**Rôle requis pour configurer la double écriture :** Administrateur système dans les applications de finances et d’opérations et Dataverse.

Les erreurs sur la page **Lien de configuration vers Dataverse** sont généralement causés par des problèmes de configuration ou d’autorisations incomplets. Veillez à ce que l’ensemble du contrôle d’intégrité passe sur la page **Lien de configuration vers Dataverse**, comme indiqué dans l’illustration suivante. Vous ne pouvez pas lier la double écriture sauf si le contrôle d’intégrité réussit.

![Contrôle d’intégrité réussi.](media/health_check.png)

Vous devez avoir les identifiants d’admin client Azure AD pour lier les environnements de finances et d’opérations et Dataverse. Après avoir lié les environnements, les utilisateurs peuvent se connecter en utilisant leurs informations d’identification de compte et mettre à jour une carte de table existante.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Trouver la limite du nombre tables juridiques ou de sociétés pouvant être liées pour la double écriture

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez d’activer des cartes :

*Échec de la double écriture - Échec de l’enregistrement du plugin : [(Impossible d’obtenir la carte de partition pour le projet DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. L’erreur dépasse le nombre maximal de partitions autorisé pour le mappage DWM – 1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)], Une ou plusieurs erreurs se sont produites.*

La limite actuelle lorsque vous liez les environnements est d’environ 40 tables juridiques. Cette erreur se produit si vous essayez d’activer des cartes et si plus de 40 tables juridiques sont liées entre les environnements.

## <a name="connection-set-failed-while-linking-environment"></a>Échec de l’ensemble de connexion lors de la liaison de l’environnement

Lors de la liaison de l’environnement à double écriture, l’action échoue avec un message d’erreur :

*Échec de l’enregistrement de l’ensemble de connexion ! Un élément avec la même clé a déjà été ajouté.*

La double écriture ne prend pas en charge plusieurs entités juridiques/sociétés portant le même nom. Par exemple, si vous avez deux sociétés avec le nom « DAT » dans le Dataverse alors il obtient ce message d’erreur.

Pour débloquer le client, supprimez les enregistrements en double de la table **cdm_company** dans Dataverse. Aussi, si la table **cdm_company** a des enregistrements avec un nom vide, supprimez ou corrigez ces enregistrements.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>Erreur à l’ouverture de la page Double écriture dans les applications de finances et d’opérations

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez de lier un environnement Dataverse pour la double écriture :

*Le code d’état de réponse n’indique pas la réussite : 404 (Introuvable).*

Cette erreur se produit lorsque l’étape de consentement de l’application n’est pas terminée. Vous pouvez valider si le consentement a été donné en vous connectant à `portal.azure.com` en utilisant le compte administrateur du client et vérifiez si l’application tierce avec ID `33976c19-1db5-4c02-810e-c243db79efde` apparaît dans la liste des applications d’entreprise d’AAD. Si ce n’est pas le cas, réexécutez l’étape de consentement comme décrit dans la section suivante.

### <a name="providing-app-consent"></a>Fournir le consentement de l’application

+ Lancez l’URL suivante en utilisant vos informations d’identification d’administrateur.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ Sélectionnez **Accepter** pour consentir. Vous donnez votre consentement pour installer l’application (avec `id=33976c19-1db5-4c02-810e-c243db79efde`) dans votre client.
+ Cette application est requise pour que Dataverse communique avec les applications de finances et d’opérations.

    ![Résolution des problèmes lors de la synchronisation initiale.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> Si cela ne fonctionne pas, lancez l’URL en mode privé de Microsoft Edge ou en mode navigation privée de Chrome.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>L’environnement de finances et d’opérations n’est pas détectable

Vous pouvez recevoir le message d’erreur suivant :

*L’environnement des applications de finances et d’opérations \*\*\*.cloudax.dynamics.com n’est pas détectable.*

Deux choses peuvent causer un problème avec l’environnement non détectable :

+ L’utilisateur utilisé pour la connexion n’est pas dans le même client que l’instance de finances et d’opérations.
+ Des instances de finances et d’opérations héritées hébergées par Microsoft présentaient un problème de découverte. Pour résoudre ce problème, mettez à jour l’instance de finances et d’opérations. L’environnement devient détectable avec n’importe quelle mise à jour.

## <a name="403-forbidden-error-while-connections-are-being-created"></a>Erreur 403 (Forbidden) lors de la création des connexions

Dans le cadre du processus de liaison à double écriture, deux connexions Power Apps (également appelées connexion *Apihub*) sont créés au nom de l’utilisateur dans l’environnement Dataverse. Si le client n’a pas de licence pour l’environnement Power Apps, la création des connexions ApiHub échoue et une erreur 403 (Forbidden) s’affiche. Voici un exemple du message d’erreur :

> MSG=\[Échec de la configuration de l’environnement d’écriture double. Détails de l’erreur : Le code d’état de réponse n’indique pas la réussite : 403 (Forbidden). - Le code d’état de réponse n’indique pas la réussite : 403 (Interdit).\] STACKTRACE=\[   at Microsoft.Dynamics.Integrator.ProjectManagementService.DualWrite.DualWriteConnectionSetProcessor.\<CreateDualWriteConnectionSetAsync\>d\_\_29.MoveNext() in X:\\bt\\1158727\\repo\\src\\ProjectManagementService\\DualWrite\\DualWriteConnectionSetProcessor.cs:line 297 --- End of stack trace from previous location where exception was thrown --- at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw() at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task) at Microsoft.Dynamics.Integrator.ProjectManagementService.Controllers.DualWriteEnvironmentManagementController.\<SetupDualWriteEnvironmentAsync\>d\_\_34.MoveNext() in X:\\bt\\1158727\\repo\\src\\ProjectManagementService\\Controllers\\DualWriteEnvironmentManagementController.cs:line 265\]

Cette erreur se produit en raison de l’absence d’une licence Power Apps. Attribuez une licence appropriée (par exemple, une version d’évaluation Power Apps 2) à l’utilisateur, afin que ce dernier ait l’autorisation de créer les connexions. Pour vérifier la licence, le client peut se rendre sur le site [Mon compte](https://portal.office.com/account/?ref=MeControl#subscriptions) pour afficher les licences actuellement attribuées à l’utilisateur.

Pour plus d’informations sur la licence Power Apps, voir les articles suivants :

- [Affecter des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide)
- [Achetez Power Apps pour votre organisation](/power-platform/admin/signup-for-powerapps-admin)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

