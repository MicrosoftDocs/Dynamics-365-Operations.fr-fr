---
title: Configurer des processus d'approbation dans un workflow
description: La procédure suivante permet de configurer les propriétés du processus d'approbation.
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
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 08641eaac31813a8bee3231118f8e2bf802ea3e1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555531"
---
# <a name="configure-approval-processes-in-a-workflow"></a>Configurer des processus d'approbation dans un workflow

[!include [banner](../includes/banner.md)]

La procédure suivante permet de configurer les propriétés du processus d'approbation.

Pour configurer un processus d'approbation, dans l'éditeur de workflow, cliquez avec le bouton droit sur l'élément d'approbation, puis cliquez sur **Propriétés** pour ouvrir l'écran **Propriétés**.

## <a name="name-the-approval-process"></a>Saisie d'un nom pour le processus d'approbation

Procédez comme suit pour entrer un nom pour le processus d'approbation.

1. Dans le volet gauche, cliquez sur **Paramètres de base**.
2. Dans le champ **Nom**, entrez un nom unique pour le processus d'approbation.

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a>Indication du moment où le système agit automatiquement sur le document

Vous pouvez configurer le système pour qu'il agisse automatiquement sur le document s'il répond à certaines conditions. Par exemple, le système peut approuver les états de dépenses dont le montant total est inférieur à USD 100. Procédez comme suit pour indiquer quand le système agit sur le document.

1. Dans le volet gauche, cliquez sur **Actions automatiques**.
2. Activez la case à cocher **Activer les actions automatiques**.
3. Cliquez sur **Ajouter une condition**.
4. Permet d'entrer une condition.
5. Entrez d'autres conditions, le cas échéant.
6. Pour vérifier que les conditions que vous avez entrées sont correctement configurées, procédez comme suit :

    1. Cliquez sur **Test** pour ouvrir l'écran **Condition de workflow de test**.
    2. Sélectionnez un enregistrement dans la zone **Contrôler la condition** de l'écran.
    3. Cliquez sur **Tester**. Le système évalue l'enregistrement pour déterminer s'il répond aux conditions que vous avez spécifiées.
    4. Cliquez sur **OK** ou sur **Annuler** pour revenir à l'écran **Propriétés**.

7. Dans la liste **Action de saisie automatique**, sélectionnez l'action que le système doit appliquer au document.

## <a name="specify-when-notifications-are-sent"></a>Spécification du moment où les notifications sont envoyées

Vous pouvez envoyer des notifications aux personnes lorsqu'un document a été approuvé, rejeté, délégué ou réaffecté, ou encore lorsqu'une modification a été demandée. Procédez comme suit pour indiquer quand les notifications sont envoyées, et à qui.

1. Dans le volet gauche, cliquez sur **Notifications**.
2. Activez la case à cocher en regard des événements pour lesquels envoyer des notifications :

    - **Déléguer** – Lorsqu'un document a été affecté à un autre utilisateur pour approbation.
    - **Réaffecter** – Lorsque l'utilisateur affecté n'a pas agi sur un document dans le délai imparti.
    - **Approuver** – Lorsqu'un document a été approuvé.
    - **Rejeter** – Lorsqu'un document a été rejeté.
    - **Demander une modification** – Lorsque l'utilisateur affecté a demandé une modification du document envoyé.

3. Sélectionnez la ligne pour un événement sélectionné à l'étape 2.
4. Cliquez sur l'onglet **Texte de notification**.
5. Dans la zone de texte, entrez le texte de la notification.
6. Pour personnaliser le texte, vous pouvez insérer des espaces réservés qui seront remplacés par les données appropriées lorsqu'ils apparaissent aux utilisateurs. Pour insérer un espace réservé, procédez comme suit :

    1. Cliquez dans la zone de texte à l'endroit où l'espace réservé doit figurer.
    2. Cliquez sur **Insérer un espace réservé**.
    3. Dans la liste affichée, sélectionnez l'espace réservé que vous souhaitez insérer.
    4. Cliquez sur **Insérer**

7. Pour ajouter des traductions de la notification, cliquez sur **Traductions**. Dans l'écran affiché, procédez comme suit :

    1. Cliquez sur **Ajouter**.
    2. Dans la liste affichée, sélectionnez la langue dans laquelle vous allez saisir le texte.
    3. Entrez le texte dans la zone de texte **Texte traduit**.
    4. Pour personnaliser le texte, insérez des espaces réservés.
    5. Cliquez sur **Fermer**.

8. Cliquez sur l'onglet **Destinataire**.
9. Spécifiez à qui les notifications sont envoyées. Sélectionnez l'une des options du tableau suivant et suivez les étapes supplémentaires concernant l'option avant de passer à l'étape 10.

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
    <td><strong>Participant</strong></td>
    <td>Utilisateurs affectés à un groupe ou à un rôle spécifique</td>
    <td>
    <ol>
    <li>Après avoir sélectionné <strong>Participant</strong>, cliquez sur l'onglet <strong>Basé sur les rôles</strong>.</li>
    <li>Dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</li>
    <li>Dans la liste <strong>Participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Utilisateur du workflow</strong></td>
    <td>Utilisateurs participant au workflow actuel</td>
    <td>
    <ol>
    <li>Sélectionnez <strong>Utilisateur du workflow</strong>, puis cliquez sur l'onglet <strong>Utilisateur du workflow</strong>.</li>
    <li>Dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Utilisateur</strong></td>
    <td>Utilisateurs Microsoft Dynamics 365 for Finance and Operations spécifiques</td>
    <td>
    <ol>
    <li>Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l'onglet <strong>Utilisateur</strong>.</li>
    <li>La liste <strong>Utilisateurs disponibles</strong> : inclut tous les utilisateurs Microsoft Dynamics 365 for Finance and Operations. Sélectionnez les utilisateurs à qui envoyer les notifications, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. Répétez les étapes 3 à 9 pour chaque événement que vous avez sélectionné à l'étape 2.

## <a name="specify-a-final-approver"></a>Spécification d'un approbateur final

Vous voudrez peut-être désigner un approbateur final pour les cas où l'approbateur est la seule personne à soumettre le document pour approbation. Pour indiquer un approbateur final, procédez comme suit.

1. Dans le volet gauche, cliquez sur **Paramètres avancés**.
2. Activez la case à cocher **Utiliser l'approbateur final**.
3. Dans la liste, sélectionnez l'utilisateur qui sera l'approbateur final.

## <a name="set-a-time-limit"></a>Définition d'un délai limite

Si le processus d'approbation doit être exécuté dans un certain délai, procédez comme suit.

> [!NOTE]
> Les options sélectionnées dans ces étapes remplacent celles sélectionnées dans les zones **Affectation** et **Escalade** de chaque étape d'approbation.

1. Dans le volet gauche, cliquez sur **Paramètres avancés**.
2. Activez la case à cocher **Définir une limite de temps pour l'élément** **de workflow**.
3. Dans le champ **Durée**, spécifiez quand le processus d'approbation doit être exécuté. Permet de sélectionner l'une des options suivantes :

    - **Heures** – Permet d'entrer le nombre d'heures accordé pour l'exécution du processus d'approbation. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Jours** – Permet d'entrer le nombre de jours accordé pour l'exécution du processus d'approbation. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Semaines** – Permet d'entrer le nombre de semaines accordé pour l'exécution du processus d'approbation.
    - **Mois** – Permet de sélectionner le jour et la semaine limites d'exécution du processus d'approbation. Par exemple, vous voudrez peut-être que le processus d'approbation soit exécuté d'ici le vendredi de la troisième semaine du mois.
    - **Années** – Permet de sélectionner la semaine et le mois limites d'exécution du processus d'approbation. Par exemple, vous voudrez peut-être que le processus d'approbation soit exécuté d'ici le vendredi de la troisième semaine de décembre.

4. Si le délai est dépassé, le système agit sur le document. Dans la liste **Action**, sélectionnez l'action que le système doit exécuter.

## <a name="specify-which-actions-are-available-to-the-user"></a>Spécification des actions disponibles pour l'utilisateur

Lorsqu'un document est affecté à un utilisateur pour approbation, ce dernier doit agir sur le document. Procédez comme suit pour indiquer les actions que l'utilisateur peut exécuter sur le document soumis.

1. Dans le volet gauche, cliquez sur **Paramètres avancés**.
2. Activez la case à cocher **Approuver** si l'utilisateur peut approuver le document.
3. Activez la case à cocher **Rejeter** si l'utilisateur peut rejeter le document.
4. Activez la case à cocher **Demander une modification** si l'utilisateur peut demander des modifications du document.
5. Activez la case à cocher **Déléguer** si l'utilisateur peut affecter le document à un autre utilisateur pour approbation.

> [!NOTE]
> La case à cocher **Activer des actions à partir de la liste de travail dans Enterprise Portal** a été supprimée.

## <a name="configure-the-approval-steps"></a>Configuration des étapes d'approbation

Un processus d'approbation comprend plusieurs étapes. Procédez comme suit pour ajouter des étapes au processus d'approbation et les configurer.

1. Dans l'éditeur de workflow, double-cliquez sur le processus d'approbation. L'éditeur de workflow affiche les étapes du processus d'approbation.
2. Pour ajouter une étape d'approbation, faites glisser l'étape de la zone **Éléments du workflow** sur le canevas.
3. Pour configurer une étape d'approbation, voir [Configurer une étape d'approbation](configure-approval-step-workflow.md).
