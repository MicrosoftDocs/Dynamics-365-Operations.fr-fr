---
title: Intégration de note
description: Cet article décrit l’intégration des données de note en double écriture.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f09d455181b7929e25d5238949a0236ac60d457b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289014"
---
# <a name="note-integration"></a>Intégration de note

[!include [banner](../../includes/banner.md)]



Au cours des processus métier, les utilisateurs de Microsoft Dynamics 365 recueillent souvent des informations sur leurs clients. Ces informations sont enregistrées sous forme d’activités et de notes. Cet article décrit l’intégration des données de note en double écriture.

Les informations client peuvent être classées des manières suivantes :

+ **Informations exploitables qu’un utilisateur Dynamics 365 gère au nom d’un client** – Par exemple, Contoso (un utilisateur de Dynamics 365) réalise un jeu télévisé. L’un des clients de Contoso (un client) souhaite assister au jeu télévisé. Le client demande à un employé de Contoso de lui réserver une place dans le jeu télévisé. La réservation a lieu dans le calendrier du participant à l’événement de Contoso.
+ **Informations exploitables pour un utilisateur Dynamics 365** – Par exemple, un client qui achète une unité Surface entre des instructions spéciales indiquant que l’appareil doit être mis dans un emballage cadeau avant la livraison. Ces instructions constituent des informations exploitables qui doivent être gérées par l’employé de Contoso responsable de l’emballage.
+ **Informations non exploitables** – Par exemple, un client visite le magasin Contoso et, au cours de sa conversation avec un collaborateur du magasin, exprime son intérêt pour les jeux et accessoires de jeux *Halo*. Le collaborateur du magasin prend note de ces informations. Le moteur de recommandations de produits l’utilise ensuite pour faire des recommandations au client.

En général, les informations exploitables sont capturées en tant qu’ *activités* dans les applications de finances et d’opérations et les applications customer engagement. Les informations non exploitables sont capturées en tant que *notes* dans les applications de finances et d’opérations et en tant qu’ *annotations* dans les applications customer engagement.

> [!TIP]
> Bien que les notes soient destinées à des informations non exploitables, les applications ne vous empêcheront pas de les utiliser pour stocker et gérer des informations exploitables si vous souhaitez les utiliser de cette manière.

Microsoft publie actuellement des fonctionnalités pour l’intégration des notes. (La fonctionnalité d’intégration des activités sera publiée ultérieurement.) L’intégration des notes est disponible pour les clients, les fournisseurs, les commandes client et les commandes fournisseur.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Créer une note dans une application customer engagement

Pour créer une note dans une application customer engagement, puis la synchroniser avec une application de finances et d’opérations, suivez ces étapes.

1. Dans l’application customer engagement, ouvrez l’enregistrement de compte d’un client.
2. Dans le volet **Chronologie**, sélectionnez le signe plus (**+**), puis sélectionnez **Note** pour créer une note.

    ![Création d’une note dans l’application customer engagement.](media/notes-ce-1.png)

3. Entrez un titre et une description, puis sélectionnez **Ajouter une note**.

    ![Saisie d’un titre et d’une description.](media/notes-ce-2.png)

    La nouvelle note est ajoutée à la chronologie du client.

    ![Nouvelle note sur la chronologie du client.](media/notes-ce-3.png)

4. Connectez-vous à l’application de finances et d’opérations et ouvrez le même enregistrement client. Notez que le bouton **Pièces jointes** (symbole de trombone) dans le coin supérieur droit indique que l’enregistrement a une pièce jointe.

    ![Notification concernant une pièce jointe.](media/notes-ce-4.png)

5. Sélectionnez le bouton **Pièces jointes** pour ouvrir la page **Pièces jointes**. Vous devriez trouver la note que vous avez créée dans l’application customer engagement.

    ![Note de l’application customer engagement.](media/notes-ce-5.png)

Toutes les mises à jour de la note sont synchronisées entre l’application de finances et d’opérations et l’application customer engagement.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>Créer une note dans une application de finances et d’opérations

Vous pouvez également créer une note dans une application de finances et d’opérations, et elle sera synchronisée avec une application customer engagement.

Pour créer une note dans une application de finances et d’opérations, puis la synchroniser avec une application customer engagement, suivez ces étapes.

1. Dans l’application de finances et d’opérations, sur la page **Pièces jointes**, sélectionnez **Nouveau** \> **Note**.

    ![Créez une note dans l’application de finances et d’opérations.](media/notes-fo-1.png)

2. Entrez un titre et un bref ensemble d'instructions, puis sélectionnez **Enregistrer**.

    ![Saisie d’un titre et d’instructions.](media/notes-fo-2.png)

3. Dans l’application customer engagement, mettez à jour l’enregistrement. La nouvelle note doit figurer sur la chronologie.

    ![Nouvelle note sur la chronologie dans l’application customer engagement.](media/notes-fo-3.png)

Vous pouvez classer une note comme interne ou externe.

- Dans l’application de finances et d’opérations, sur la page **Pièces jointes**, ouvrez la note, puis, dans le champ **Restriction**, sélectionnez **Interne** ou **Externe**.

    ![Champ de restriction.](media/notes-fo-4.png)

Vous pouvez également créer une URL.

1. Dans l’application de finances et d’opérations, sur la page **Pièces jointes**, sélectionnez **Nouveau** \> **URL**.
2. Entrez un titre et l’URL.
3. Dans le champ **Restriction**, sélectionnez **Interne** ou **Externe**.

    ![Créer une URL dans l’application de finances et d’opérations.](media/notes-fo-5.png)

4. Sélectionnez **Enregistrer**.

    Étant donné que les applications customer engagement n’ont pas de type d’URL, l’URL est intégrée à la double écriture en tant que note.

    ![URL apparaissant en tant que note dans l’application customer engagement.](media/notes-ce-6.png)

> [!NOTE]
> Les pièces jointes ne sont pas prises en charge.

## <a name="templates"></a>Modèles

L’intégration de notes comprend une collection de mappages de tables qui fonctionnent ensemble pendant l’interaction des données, comme indiqué dans le tableau suivant.

| Application de finances et d’opérations | Application customer engagement | Description |
|----------------------------|-------------------------|-------------|
| [Pièces jointes clients](mapping-reference.md#230) | Annotations | Entreprises qui utilisent du texte brut et des URL pour capturer des informations spécifiques aux clients (pour les organisations et les personnes). |
| [Pièces jointes de document fournisseur](mapping-reference.md#231) | Annotations | Entreprises qui utilisent du texte brut et des URL pour capturer des informations spécifiques aux fournisseurs (pour les organisations et les personnes). |
| [Pièces jointes des documents d’en-tête de commande client](mapping-reference.md#229) | Annotations | Entreprises qui utilisent du texte brut et des URL pour capturer des informations spécifiques aux commandes client. |
| [Pièces jointes des documents d’en-tête de commande fournisseur](mapping-reference.md#232) | Annotations | Entreprises qui utilisent du texte brut et des URL pour capturer des informations spécifiques aux commandes fournisseur. |

## <a name="limitations"></a>Limitations

Une fois que vous avez installé la solution de notes, vous ne pouvez pas la désinstaller. 

Pour plus d’informations, voir [Référence de mappage en double écriture](mapping-reference.md).

