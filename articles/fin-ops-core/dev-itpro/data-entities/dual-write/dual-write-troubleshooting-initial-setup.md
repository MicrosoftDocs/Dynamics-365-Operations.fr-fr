---
title: Résoudre les problèmes lors de la configuration initiale
description: Cette rubrique fournit des informations pour la résolution des problèmes pouvant survenir lors de la configuration initiale de l’intégration de la double écriture.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: c9bf5d9017579b4207e09769cff38361442e3938
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781438"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Résoudre les problèmes lors de la configuration initiale

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique fournit des informations sur la résolution des problèmes de l’intégration de la double écriture entre les applications Finance and Operations et Dataverse. Notamment elle fournit des informations pour la résolution des problèmes pouvant survenir lors de la configuration initiale de l’intégration de la double écriture.

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Vous ne pouvez pas lier une application Finance and Operations à Dataverse

**Rôle requis pour configurer la double écriture :** Administrateur système dans les applications Finance and Operations et Dataverse.

Les erreurs sur la page **Lien de configuration vers Dataverse** sont généralement causés par des problèmes de configuration ou d’autorisations incomplets. Veillez à ce que l’ensemble du contrôle d’intégrité passe sur la page **Lien de configuration vers Dataverse**, comme indiqué dans l’illustration suivante. Vous ne pouvez pas lier la double écriture sauf si le contrôle d’intégrité réussit.

![Contrôle d’intégrité réussi.](media/health_check.png)

Vous devez avoir les identifiants d’admin client Azure AD pour lier les environnements Finance and Operations et Dataverse. Après avoir lié les environnements, les utilisateurs peuvent se connecter en utilisant leurs informations d’identification de compte et mettre à jour une carte de table existante.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Trouver la limite du nombre tables juridiques ou de sociétés pouvant être liées pour la double écriture

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez d’activer des cartes :

*Échec de la double écriture - Échec de l’enregistrement du plugin : [(Impossible d’obtenir la carte de partition pour le projet DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. L’erreur dépasse le nombre maximal de partitions autorisé pour le mappage DWM - 1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)], Une ou plusieurs erreurs se sont produites.*

La limite actuelle lorsque vous liez les environnements est d’environ 40 tables juridiques. Cette erreur se produit si vous essayez d’activer des cartes et si plus de 40 tables juridiques sont liées entre les environnements.

## <a name="connection-set-failed-while-linking-environment"></a>Échec de l’ensemble de connexion lors de la liaison de l’environnement

Lors de la liaison de l’environnement à double écriture, l’action échoue avec un message d’erreur :

*Échec de l’enregistrement de l’ensemble de connexion ! Un élément avec la même clé a déjà été ajouté.*

La double écriture ne prend pas en charge plusieurs entités juridiques/sociétés portant le même nom. Par exemple, si vous avez deux sociétés avec le nom « DAT » dans le Dataverse alors il obtient ce message d’erreur.

Pour débloquer le client, supprimez les enregistrements en double de la table **cdm_company** dans Dataverse. Aussi, si la table **cdm_company** a des enregistrements avec un nom vide, supprimez ou corrigez ces enregistrements.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>Erreur lors de l’ouverture de la page Double écriture dans les applications Finance and Operations

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez de lier un environnement Dataverse pour la double écriture :

*Le code d’état de réponse n’indique pas la réussite : 404 (Introuvable).*

Cette erreur se produit lorsque l’étape de consentement de l’application n’est pas terminée. Vous pouvez valider si le consentement a été donné en vous connectant à `portal.azure.com` en utilisant le compte administrateur du client et vérifiez si l’application tierce avec ID `33976c19-1db5-4c02-810e-c243db79efde` apparaît dans la liste des applications d’entreprise d’AAD. Si ce n’est pas le cas, réexécutez l’étape de consentement comme décrit dans la section suivante.

### <a name="providing-app-consent"></a>Fournir le consentement de l’application

+ Lancez l’URL suivante en utilisant vos informations d’identification d’administrateur.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ Sélectionnez **Accepter** pour consentir. Vous donnez votre consentement pour installer l’application (avec `id=33976c19-1db5-4c02-810e-c243db79efde`) dans votre client.
+ Cette application est requise pour que Dataverse communique avec les applications Finance and Operations.

    ![Résolution des problèmes lors de la synchronisation initiale.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> Si cela ne fonctionne pas, lancez l’URL en mode privé de Microsoft Edge ou en mode navigation privée de Chrome.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>L’environnement Finance and Operations n’est pas détectable

Vous pouvez recevoir le message d’erreur suivant :

L’environnement des applications *Finance and Operations \*\*\*.cloudax.dynamics.com n’est pas détectable.*

Deux choses peuvent causer un problème avec l’environnement non détectable :

+ L’utilisateur utilisé pour la connexion n’est pas dans le même client que l’instance Finance and Operations.
+ Des instances Finance and Operations héritées hébergées par Microsoft présentaient un problème de découverte. Pour résoudre ce problème, mettez à jour l’instance Finance and Operations. L’environnement devient détectable avec n’importe quelle mise à jour.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
