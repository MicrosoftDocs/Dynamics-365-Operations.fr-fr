---
title: Intégration d’une note
description: Cette rubrique décrit l’intégration des données d’une note en double écriture.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
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
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: ceb5b7c90cc7efa0049d0278e2c245228e5b52bd
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186784"
---
# <a name="note-integration"></a>Intégration d’une note

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Au cours des processus métier, les utilisateurs de Microsoft Dynamics 365 recueillent souvent des informations sur leurs clients. Ces informations sont enregistrées sous forme d’activités et de notes. Cette rubrique décrit l’intégration des données d’une note en double écriture.

Les informations client peuvent être classées des manières suivantes :

+ **Informations exploitables qu’un utilisateur Dynamics 365 gère au nom d’un client** – Par exemple, Contoso (un utilisateur de Dynamics 365) réalise un jeu télévisé. L’un des clients de Contoso (un client) souhaite assister au jeu télévisé. Le client demande à un employé de Contoso de lui réserver une place dans le jeu télévisé. La réservation a lieu dans le calendrier du participant à l’événement de Contoso.
+ **Informations exploitables pour un utilisateur Dynamics 365** – Par exemple, un client qui achète une unité Surface entre des instructions spéciales indiquant que l’appareil doit être mis dans un emballage cadeau avant la livraison. Ces instructions constituent des informations exploitables qui doivent être gérées par l’employé de Contoso responsable de l’emballage.
+ **Informations non exploitables** – Par exemple, un client visite le magasin Contoso et, au cours de sa conversation avec un collaborateur du magasin, exprime son intérêt pour les jeux et accessoires de jeux *Halo*. Le collaborateur du magasin prend note de ces informations. Le moteur de recommandations de produits l’utilise ensuite pour faire des recommandations au client.

En général, les informations exploitables sont capturées en tant qu’*activités* dans les applications Finance and Operations et les applications Customer Engagement. En général, les informations non exploitables sont capturées en tant que *notes* dans les applications Finance and Operations et en tant qu’*annotations* dans les applications Customer Engagement.

> [!TIP]
> Bien que les notes soient destinées à des informations non exploitables, les applications ne vous empêcheront pas de les utiliser pour stocker et gérer des informations exploitables si vous souhaitez les utiliser de cette manière.

Microsoft publie actuellement des fonctionnalités pour l’intégration des notes. (La fonctionnalité d’intégration des activités sera publiée ultérieurement.) L’intégration des notes est disponible pour les clients, les fournisseurs, les commandes client et les commandes fournisseur.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Créer une note dans une application Customer Engagement

Pour créer une note dans une application Customer Engagement, puis la synchroniser avec une application Finance and Operations, procédez comme suit.

1. Dans l’application Customer Engagement, ouvrez l’enregistrement de compte d’un client.
2. Dans le volet **Chronologie**, sélectionnez le signe plus (**+**), puis sélectionnez **Note** pour créer une note.

    ![Création d’une note dans l’application Customer Engagement](media/notes-ce-1.png)

3. Entrez un nom et une description, puis sélectionnez **Ajouter une note**.

    ![Saisie d’un titre et d’une description](media/notes-ce-2.png)

    La nouvelle note est ajoutée à la chronologie du client.

    ![Nouvelle note sur la chronologie du client](media/notes-ce-3.png)

4. Connectez-vous à l’application Finance and Operations et ouvrez le même enregistrement client. Notez que le bouton **Pièces jointes** (symbole de trombone) dans le coin supérieur droit indique que l’enregistrement a une pièce jointe.

    ![Notification concernant une pièce jointe](media/notes-ce-4.png)

5. Sélectionnez le bouton **Pièces jointes** pour ouvrir la page **Pièces jointes**. Vous devriez trouver la note que vous avez créée dans l’application Customer Engagement.

    ![Note de l’application Customer Engagement](media/notes-ce-5.png)

Toutes les mises à jour de la note sont synchronisées entre l’application Finance and Operations et l’application Customer Engagement.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>Créer une note dans une application Finance and Operations

Vous pouvez également créer une note dans une application Finance and Operations, puis la synchroniser avec une application Customer Engagement.

Pour créer une note dans une application Finance and Operations, puis la synchroniser avec une application Customer Engagement, procédez comme suit.

1. Dans l’application Finance and Operations, sur la page **Pièces jointes**, sélectionnez **Nouveau** \> **Note**.

    ![Création d’une note dans l’application Finance and Operations](media/notes-fo-1.png)

2. Entrez un titre et des instructions brèves, puis sélectionnez **Enregistrer**.

    ![Saisie d’un titre et d’instructions](media/notes-fo-2.png)

3. Dans l’application Customer Engagement, mettez à jour l’enregistrement. La nouvelle note doit figurer sur la chronologie.

    ![Nouvelle note sur la chronologie dans l’application Customer Engagement](media/notes-fo-3.png)

Vous pouvez classer une note comme interne ou externe.

- Dans l’application Finance and Operations, sur la page **Pièces jointes**, ouvrez la note, puis, dans le champ **Restriction**, sélectionnez **Interne** ou **Externe**.

    ![Champ de restriction](media/notes-fo-4.png)

Vous pouvez également créer une URL.

1. Dans l’application Finance and Operations, sur la page **Pièces jointes**, sélectionnez **Nouveau** \> **URL**.
2. Entrez un titre et l’URL.
3. Dans le champ **Restriction**, sélectionnez **Interne** ou **Externe**.

    ![Création d’une URL dans l’application Finance and Operations](media/notes-fo-5.png)

4. Sélectionnez **Enregistrer**.

    Étant donné que les applications Customer Engagement n’ont pas de type d’URL, l’URL est intégrée à la double écriture en tant que note.

    ![URL apparaissant en tant que note dans l’application Customer Engagement](media/notes-ce-6.png)

> [!NOTE]
> Les pièces jointes ne sont pas prises en charge.

## <a name="templates"></a>Modèles

L’intégration de notes comprend un ensemble de mappages de tables qui fonctionnent ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.

| Application Finance and Operations | Application Customer Engagement | Description |
|----------------------------|-------------------------|-------------|
| [Pièces jointes clients](mapping-reference.md#230) | Annotations | Entreprises qui utilisent du texte brut et des URL pour capturer des informations spécifiques aux clients (pour les organisations et les personnes). |
| [Pièces jointes de document fournisseur](mapping-reference.md#231) | Annotations | Entreprises qui utilisent du texte brut et des URL pour capturer des informations spécifiques aux fournisseurs (pour les organisations et les personnes). |
| [Pièces jointes des documents d’en-tête de commande client](mapping-reference.md#229) | Annotations | Entreprises qui utilisent du texte brut et des URL pour capturer des informations spécifiques aux commandes client. |
| [Pièces jointes des documents d’en-tête de commande fournisseur](mapping-reference.md#232) | Annotations | Entreprises qui utilisent du texte brut et des URL pour capturer des informations spécifiques aux commandes fournisseur. |

## <a name="limitations"></a>Limitations

Une fois que vous avez installé la solution de notes, vous ne pouvez pas la désinstaller. 

Pour plus d’informations, voir [Référence de mappage en double écriture](mapping-reference.md).
