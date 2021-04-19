---
title: Résoudre les problèmes lors de la configuration initiale
description: Cette rubrique fournit des informations pour la résolution des problèmes pouvant survenir lors de la configuration initiale de l’intégration de la double écriture.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9ffb1378eccf175fbb9bd84228f91ba606125a63
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753988"
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

![Contrôle d’intégrité réussi](media/health_check.png)

Vous devez avoir les identifiants d’admin client Azure AD pour lier les environnements Finance and Operations et Dataverse. Après avoir lié les environnements, les utilisateurs peuvent se connecter en utilisant leurs informations d’identification de compte et mettre à jour une carte de table existante.

## <a name="error-when-you-open-the-link-to-dataverse-page"></a>Erreur lorsque vous ouvrez la page Lier à Dataverse

**Informations d’identification requises pour résoudre le problème :** admin client Azure AD

Vous pouvez recevoir le message d’erreur suivant lorsque vous ouvrez la page **Lier à Dataverse** dans une application Finance and Operations :

*Le code d’état de réponse n’indique pas la réussite : 404 (Introuvable).*

Cette erreur se produit lorsque l’étape de consentement n’est pas terminée. Pour valider si l’étape de consentement est terminée, connectez-vous à portal.Azure.com en utilisant le compte admin client Azure AD et voyez si l’application tierce avec l’ID **33976c19-1db5-4c02-810e-c243db79efde** apparaît dans la liste **Applications d’entreprise** Azure AD. Si ce n’est pas le cas, vous devez fournir le consentement de l’application.

Pour fournir le consentement de l’application, procédez comme suit.

1. Ouvrez l’URL suivante en utilisant vos informations d’identification d’administrateur. Vous devriez être invité à donner votre consentement.

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. Sélectionnez **Accepter** pour indiquer que vous donnez votre consentement pour installer l’application avec l’ID **33976c19-1db5-4c02-810e-c243db79efde** dans votre client.

    > [!TIP]
    > Cette application est nécessaire pour lier les applications Dataverse et Finance and Operations. Si vous rencontrez des problèmes avec cette étape, ouvrez votre navigateur en mode navigation privée (dans Google Chrome) ou en mode InPrivate (dans Microsoft Edge).

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a>Vérifier que les données d’entreprise et les équipes en double écriture sont correctement configurées lors de la liaison

Pour garantir le bon fonctionnement de la double écriture, les sociétés que vous sélectionnez lors de la configuration sont créées dans l’environnement Dataverse. Par défaut, ces sociétés sont en lecture seule et la propriété **IsDualWriteEnable** est définie sur la valeur **True**. De plus, le propriétaire et l’équipe de l’unité commerciale propriétaire par défaut et l’équipe sont créés et comprennent le nom de l’entreprise. Avant d’activer les cartes, vérifiez que le propriétaire de l’équipe par défaut est spécifié. Pour trouver la table **Sociétés (CDM\_Company)**, procédez comme suit.

1. Dans l’application pilotée par modèle dans Dynamics 365, sélectionnez le filtre dans le coin supérieur droit.
2. Dans la liste déroulante sélectionnez **Société**.
3. Sélectionnez **Exécuter** pour voir les résultats.
4. Sélectionnez la société qui était liée lorsque vous avez configuré la double écriture.
5. Vérifiez que la colonne **Équipe propriétaire par défaut** a une valeur. Dans l’illustration suivante, la colonne **Équipe propriétaire par défaut** est définie sur **Double écriture USMF**.

    ![Vérification de l’équipe propriétaire par défaut](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Trouver la limite du nombre tables juridiques ou de sociétés pouvant être liées pour la double écriture

Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez d’activer des cartes :

*Échec de la double écriture - Échec de l’enregistrement du plugin : \[(Impossible d’obtenir la carte de partition pour le projet DWM - 1ae35e60-4bc2-4905-88ea-69efd3b29260 - 7f12cb89-1550-42e2-858e-4761fc1443ea. L’erreur dépasse le nombre maximal de partitions autorisé pour le mappage DWM - 1ae35e60-4bc2-4905-88ea-69efd3b29260 – 7f12cb89-1550-42e2-858e-4761fc1443ea) \], Une ou plusieurs erreurs se sont produites.*

La limite actuelle lorsque vous liez les environnements est d’environ 40 tables juridiques. Cette erreur se produit si vous essayez d’activer des cartes et si plus de 40 tables juridiques sont liées entre les environnements.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]