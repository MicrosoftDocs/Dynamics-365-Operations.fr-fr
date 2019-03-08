---
title: Configurer des tâches automatiques dans un workflow
description: Cette rubrique explique comment configurer les propriétés d'une tâche automatique.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a9f37228beedafa085987668d5c89b06c6c9d61
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "365107"
---
# <a name="configure-automated-tasks-in-a-workflow"></a>Configurer des tâches automatiques dans un workflow

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer les propriétés d'une tâche automatique.

Pour configurer une tâche automatique, dans l'éditeur de workflow, cliquez avec le bouton droit sur la tâche, puis cliquez sur **Propriétés** pour ouvrir la page **Propriétés**. Suivez ensuite les procédures suivantes pour configurer les propriétés de la tâche automatique.

## <a name="name-the-task"></a>Saisie d'un nom pour la tâche

Procédez comme suit pour entrer un nom pour la tâche automatique.

1. Dans le volet gauche, cliquez sur **Paramètres de base**.
2. Entrez un nom unique pour la tâche dans le champ **Nom**.

## <a name="specify-when-notifications-are-sent"></a>Spécification du moment où les notifications sont envoyées

Vous pouvez envoyer des notifications aux personnes lorsqu'une tâche automatique a été effectuée ou annulée. Procédez comme suit pour indiquer quand les notifications sont envoyées, et à qui.

1. Dans le volet gauche, cliquez sur **Notifications**.
2. Activez la case à cocher en regard des événements pour lesquels envoyer des notifications :

    - **Exécution** – Des notifications sont envoyées lorsque la tâche a été exécutée.
    - **Annulé** – Des notifications sont envoyées lorsque la tâche a été annulée.

3. Sélectionnez la ligne pour un événement sélectionné à l'étape 2.
4. Entrez le texte de la notification dans la zone de texte de l'onglet **Texte de notification**.
5. Pour personnaliser la notification, vous pouvez insérer des espaces réservés. Ils sont remplacés par les données appropriées lorsque la notification s'affiche pour les utilisateurs. Pour insérer un espace réservé, procédez comme suit :

    1. Dans la zone de texte, cliquez pour spécifier l'endroit où l'espace réservé doit figurer.
    2. Cliquez sur **Insérer un espace réservé**.
    3. Dans la liste qui s'affiche, sélectionnez l'espace réservé que vous souhaitez insérer.
    4. Cliquez sur **Insérer**

6. Suivez les étapes suivantes pour ajouter une traduction de la notification.

    1. Cliquez sur **Traductions**.
    2. Dans la page qui s'affiche, cliquez sur **Ajouter**.
    3. Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.
    4. Entrez le texte dans le champ **Texte traduit**.
    5. Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l'étape 5.
    6. Cliquez sur **Fermer**.

7. Spécifiez à qui les notifications sont envoyées sous l'onglet **Destinataire**. Sélectionnez l'une des options du tableau suivant et suivez les étapes supplémentaires concernant l'option avant de passer à l'étape 8.

    <table>
    <thead>
    <tr>
    <th>Option</th>
    <th>Destinataires de la notification</th>
    <th>Étapes supplémentaires</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Participant</td>
    <td>Utilisateurs affectés à un groupe ou à un rôle spécifique</td>
    <td>
    <ol>
    <li>Après avoir sélectionné <strong>Participant</strong>, sous l'onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</li>
    <li>Dans la liste <strong>Participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Utilisateur du workflow</td>
    <td>Utilisateurs participant au workflow actuel</td>
    <td>
    <ul>
    <li>Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l'onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Utilisateur</td>
    <td>Utilisateurs Microsoft Dynamics 365 for Finance and Operations spécifiques</td>
    <td>
    <ol>
    <li>Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l'onglet <strong>Utilisateur</strong>.</li>
    <li>La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs Finance and Operations. Sélectionnez les utilisateurs à qui envoyer les notifications, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Répétez les étapes 3 à 7 pour chaque événement que vous avez sélectionné à l'étape 2.
