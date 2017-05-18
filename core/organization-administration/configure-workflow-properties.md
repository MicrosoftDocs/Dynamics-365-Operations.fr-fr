---
title: "Configuration des propriétés d&quot;un workflow"
description: "Cette rubrique explique comment configurer les différentes propriétés d&quot;un workflow."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 6c44ba2771bab0bc428c0c348a6c34c2deb0be26
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="configure-the-properties-of-a-workflow"></a>Configuration des propriétés d'un workflow

[!include[banner](../includes/banner.md)]


Cette rubrique explique comment configurer les différentes propriétés d'un workflow.

Pour configurer les propriétés d'un workflow, ouvrez ce dernier dans l'éditeur de workflow. Cliquez sur le canevas de l'éditeur de workflow, puis sur **Propriétés** pour ouvrir la page **Propriétés**. Vous pouvez ensuite suivre les procédures suivantes permettant de configurer les différentes propriétés du workflow.

## <a name="name-the-workflow"></a>Saisie d'un nom pour le workflow
Procédez comme suit pour entrer un nom pour le workflow.

1.  Dans le volet gauche, cliquez sur **Paramètres de base**.
2.  Dans le champ **Nom**, entrez un nom unique pour le workflow. Si vous créez un workflow de demande d'achat pour chaque pays ou région dans lequel vous travaillez, vous pouvez nommer un workflow de demande d'achat **Demandes d'achat Danemark** ou **Demandes d'achat Espagne**.

## <a name="specify-the-workflow-owner"></a>Spécification du propriétaire du workflow
Le propriétaire du workflow est la personne qui le gère et le tient à jour. Les étapes suivantes permettent de spécifier le propriétaire du workflow.

1.  Dans le volet gauche, cliquez sur **Paramètres de base**.
2.  Dans la liste **Propriétaire**, sélectionnez le nom de la personne chargée de gérer ce workflow.

## <a name="select-an-email-template"></a>Sélection d'un modèle d'e-mail
Pour sélectionner le modèle d'e-mail qui permettra de générer les messages de notification de ce workflow, exécutez les procédures suivantes.

1.  Dans le volet gauche, cliquez sur **Paramètres de base**.
2.  Sélectionnez le modèle dans la liste **Modèles d'e-mail pour les notifications de workflow**.

## <a name="enter-instructions-for-users"></a>Saisie d'instructions pour les utilisateurs
Vous pouvez fournir des instructions pour les utilisateurs qui soumettent des documents pour traitement et approbation. Ils sont également considérés comme des *expéditeurs*. Par exemple, supposez que vous créez un workflow de demande d'achat et que vous entrez des instructions. Ces instructions peuvent ensuite être affichées par les utilisateurs qui entrent les demandes d'achat dans la page **Demandes d'achat**. Pour afficher les instructions, l'expéditeur doit cliquer sur l'icône dans la barre des messages du workflow. Procédez comme suit pour entrer des instructions pour les utilisateurs.

1.  Dans le volet gauche, cliquez sur **Paramètres de base**.
2.  Entrez les instructions dans le champ **Instructions de soumission**.
3.  Pour personnaliser les instructions, vous pouvez insérer des espaces réservés. Ils sont remplacés par les données appropriées lorsque les instructions apparaissent aux utilisateurs. Pour insérer un espace réservé, procédez comme suit :
    1.  Cliquez sur le champ **Instructions de soumission** pour spécifier l'endroit où l'espace réservé doit apparaître.
    2.  Cliquez sur **Insérer un espace réservé**.
    3.  Dans la liste qui s'affiche, sélectionnez l'espace réservé que vous souhaitez insérer.
    4.  Cliquez sur **Insérer**

4.  Suivez les étapes suivantes pour ajouter une traduction des instructions.
    1.  Cliquez sur **Traductions**.
    2.  Dans la page qui s'affiche, cliquez sur **Ajouter**.
    3.  Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.
    4.  Entrez le texte dans le champ **Texte traduit**.
    5.  Pour personnaliser le texte, vous pouvez insérer des espaces réservés. Pour obtenir des instructions sur l'ajout d'un espace réservé, voir l'étape 3.
    6.  Cliquez sur **Fermer**.

## <a name="specify-when-this-workflow-is-used"></a>Spécification du moment où le workflow est utilisé
Vous pouvez créer plusieurs workflows basés sur le même type. Par exemple, vous pouvez créer un workflow de demande d'achat pour chaque pays ou région dans lequel vous travaillez, comme Demandes d'achat Danemark et Demandes d'achat Espagne. Si plusieurs workflows sont basés sur le même type, vous devez spécifier le moment où chaque workflow est utilisé. Dans l'exemple précédent, vous devez spécifier les conditions suivantes :

-   Demandes d'achat Danemark doit être utilisé lorsque : le pays/région = DK
-   Demandes d'achat Espagne doit être utilisé lorsque : le pays/région = ES

Procédez comme suite pour spécifier quand le workflow que vous configurez est utilisé.

1.  Dans le volet gauche, cliquez sur **Activation**.
2.  Activez la case à cocher **Définir les conditions d'exécution de ce workflow**.
3.  Cliquez sur **Ajouter**.
4.  Permet d'entrer une condition.
5.  Entrez des conditions supplémentaires, si nécessaire.
6.  Pour vérifier que les conditions que vous avez entrées sont correctement configurées, procédez comme suit :
    1.  Cliquez sur **Tester**.
    2.  Sur la page **Condition de workflow de test**, sélectionnez un enregistrement dans la zone **Contrôler la condition**.
    3.  Cliquez sur **Tester**. Le système évalue l'enregistrement pour déterminer s'il répond aux conditions que vous avez spécifiées. Si vous créez un workflow de demande d'achat pour l'Espagne, la zone **Contrôler la condition** de la page affiche la liste de demandes d'achat. Lorsque vous cliquez sur **Test**, le système évalue la demande d'achat sélectionnée pour déterminer si le pays/la région est l'Espagne (ES).
    4.  Cliquez sur **OK** ou sur **Annuler** pour revenir à la page **Propriétés**.

## <a name="specify-when-notifications-are-sent"></a>Spécification du moment où les notifications sont envoyées
Lorsqu'un document est soumis pour traitement, une instance de workflow est créée. Vous pouvez envoyer des notifications aux utilisateurs lorsque les instances de workflow qui sont basées sur ce workflow sont initiées, terminées, interrompues ou bloquées en raison d'une erreur. Procédez comme suit pour spécifier quand les notifications sont envoyées.

1.  Dans le volet gauche, cliquez sur **Notifications**.
2.  Activez la case à cocher correspondant à chaque événement qui doit déclencher des notifications :
    -   **Commencé** - Permet d'envoyer des notifications lorsqu'une instance de workflow démarre.
    -   **Bloqué** - Permet d'envoyer des notifications lorsqu'une instance de workflow est bloquée en raison d'une erreur.
    -   **Terminée** - Permet d'envoyer des notifications lorsqu'une instance de workflow est terminée.
    -   **Irrécupérable** - Permet d'envoyer des notifications lorsqu'une instance de workflow est bloquée en raison d'une erreur irrécupérable.
    -   **Terminé** - Permet d'envoyer des notifications lorsqu'une instance de workflow est terminée.

3.  Sélectionnez la ligne pour un événement sélectionné à l'étape 2.
4.  Entrez le texte de la notification dans l'onglet **Texte de notification**.
5.  Pour personnaliser le texte, vous pouvez insérer des espaces réservés. Ils sont remplacés par les données appropriées lorsque le texte apparait aux utilisateurs. Pour insérer un espace réservé, procédez comme suit :
    1.  Cliquez dans le champ pour spécifier l'endroit où l'espace réservé doit apparaître.
    2.  Cliquez sur **Insérer un espace réservé**.
    3.  Dans la liste qui s'affiche, sélectionnez l'espace réservé que vous souhaitez insérer.
    4.  Cliquez sur **Insérer**

6.  Suivez les étapes suivantes pour ajouter une traduction du texte.
    1.  Cliquez sur **Traductions**.
    2.  Dans la page qui s'affiche, cliquez sur **Ajouter**.
    3.  Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.
    4.  Entrez le texte dans le champ **Texte traduit**.
    5.  Pour personnaliser le texte, vous pouvez insérer des espaces réservés. Pour obtenir des instructions sur l'ajout d'un espace réservé, voir l'étape 5.
    6.  Cliquez sur **Fermer**.

7.  Sous l'onglet **Destinataire**, utilisez les options suivantes pour spécifier qui doit recevoir les notifications.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Option</th>
    <th>Les notifications sont envoyées aux utilisateurs.</th>
    <th>Pour envoyer des notifications, procédez comme suit</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Participant</td>
    <td>Utilisateurs affectés à un groupe ou à un rôle spécifique</td>
    <td><ol>
    <li>Sous l'onglet <strong>Destinataire</strong>, cliquez sur <strong>Participant</strong>.</li>
    <li>Sous l'onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</li>
    <li>Dans la liste <strong>Participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Utilisateur du workflow</td>
    <td>Utilisateurs participant à ce workflow</td>
    <td><ol>
    <li>Sous l'onglet <strong>Destinataire</strong>, cliquez sur <strong>Utilisateur du workflow</strong>.</li>
    <li>Sous l'onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un participant à ce workflow.</li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Utilisateur</td>
    <td>Utilisateurs Dynamics 365 for Operations spécifiques</td>
    <td><ol>
    <li>Sous l'onglet <strong>Destinataire</strong>, cliquez sur <strong>Utilisateur</strong>.</li>
    <li>Sous l'onglet <strong>Utilisateur</strong>, la liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs Dynamics 365 for Operations. Sélectionnez les utilisateurs à qui envoyer les notifications, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  Répétez les étapes 3 à 7 pour chaque événement que vous avez sélectionné à l'étape 2.

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a>Entrez des commentaires sur les modifications apportées au workflow.
Pour entrer des commentaires sur les modifications que vous avez apportées à ce workflow, procédez comme suit.

1.  Dans le volet gauche, cliquez sur **Remarques**.
2.  Entrez vos commentaires dans le champ **Entrer des commentaires sur le workflow**.
3.  Relisez vos commentaires. Une fois les commentaires entrés, il n'est plus possible de les modifier.
4.  Cliquez sur **Ajouter** pour ajouter vos commentaires dans la zone **Historique des commentaires**.





