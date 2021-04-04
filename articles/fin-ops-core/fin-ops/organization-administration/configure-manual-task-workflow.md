---
title: Configurer des tâches manuelles dans un workflow
description: Cette rubrique explique comment configurer les propriétés d’une tâche manuelle.
author: ChrisGarty
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee759cbf51555a32045e74f40138a04f330d7eb2
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559471"
---
# <a name="configure-manual-tasks-in-a-workflow"></a>Configurer des tâches manuelles dans un workflow

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer les propriétés d’une tâche manuelle.

Pour configurer une tâche manuelle, dans l’éditeur de workflow, cliquez avec le bouton droit sur la tâche, puis cliquez sur **Propriétés** pour ouvrir l’écran **Propriétés**. Suivez ensuite les procédures suivantes pour configurer les propriétés de la tâche manuelle.

## <a name="name-the-task"></a>Saisie d’un nom pour la tâche

Procédez comme suit pour entrer un nom pour la tâche manuelle.

1. Dans le volet gauche, cliquez sur **Paramètres de base**.
2. Entrez un nom unique pour la tâche dans le champ **Nom**.

## <a name="enter-a-subject-line-and-instructions"></a>Saisie d’une ligne d’objet et des instructions

Vous devez fournir une ligne d’objet et des instructions aux utilisateurs affectés à la tâche. Par exemple, si vous configurez une tâche pour des demandes d’achat, l’utilisateur concerné par cette tâche voit la ligne d’objet et les instructions dans la page **Demandes d’achat**. La ligne d’objet figure dans une barre de message de la page. L’utilisateur peut ensuite cliquer sur l’icône de la barre des messages pour afficher les instructions. Procédez comme suit pour entrer une ligne d’objet et des instructions.

1. Dans le volet gauche, cliquez sur **Paramètres de base**.
2. Entrez la ligne d’objet dans le champ **Objet de l’article de travail**.
3. Si vous souhaitez personnaliser la ligne, vous pouvez insérer des espaces réservés. Ils sont remplacés par les données appropriées lorsque la ligne d’objet s’affiche pour les utilisateurs. Pour insérer un espace réservé, procédez comme suit :

    1. Dans la zone de texte, cliquez pour spécifier l’endroit où l’espace réservé doit figurer.
    2. Cliquez sur **Insérer un espace réservé**.
    3. Dans la liste qui s’affiche, sélectionnez l’espace réservé que vous souhaitez insérer.
    4. Cliquez sur **Insérer**

4. Suivez les étapes suivantes pour ajouter une traduction de la ligne d’objet.

    1. Cliquez sur **Traductions**.
    2. Dans la page qui s’affiche, cliquez sur **Ajouter**.
    3. Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.
    4. Entrez le texte dans le champ **Texte traduit**.
    5. Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l’étape 3.
    6. Cliquez sur **Fermer**.

5. Entrez les instructions dans le champ **Instructions de l’élément de travail**.
6. Pour personnaliser les instructions, vous pouvez insérer des espaces réservés. Ils sont remplacés par les données appropriées lorsque les instructions apparaissent aux utilisateurs. Pour insérer un espace réservé, procédez comme suit :

    1. Dans la zone de texte, cliquez pour spécifier l’endroit où l’espace réservé doit figurer.
    2. Cliquez sur **Insérer un espace réservé**.
    3. Dans la liste qui s’affiche, sélectionnez l’espace réservé que vous souhaitez insérer.
    4. Cliquez sur **Insérer**

7. Suivez les étapes suivantes pour ajouter une traduction des instructions.

    1. Cliquez sur **Traductions**.
    2. Dans la page qui s’affiche, cliquez sur **Ajouter**.
    3. Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.
    4. Entrez le texte dans le champ **Texte traduit**.
    5. Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l’étape 6.
    6. Cliquez sur **Fermer**.

## <a name="assign-the-task"></a>Affectation de la tâche

Procédez comme suit pour indiquer à qui affecter la tâche manuelle.

1. Dans le volet gauche, cliquez sur **Affectation**.
2. Sous l’onglet **Type d’affectation**, sélectionnez l’une des options du tableau suivant et suivez les étapes supplémentaires concernant l’option avant de passer à l’étape 3.

    <table>
    <thead>
    <tr>
    <th>Option</th>
    <th>Utilisateurs à qui la tâche est affectée</th>
    <th>Étapes supplémentaires</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Participant</td>
    <td>Utilisateurs affectés à un groupe ou à un rôle spécifique</td>
    <td>
    <ol>
    <li>Après avoir sélectionné <strong>Participant</strong>, sous l’onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel affecter la tâche.</li>
    <li>Dans la liste <strong>Participant</strong>, sélectionnez le groupe ou le rôle auquel affecter la tâche.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Hiérarchie</td>
    <td>Utilisateurs d’une hiérarchie organisationnelle spécifique</td>
    <td>
    <ol>
    <li>Après avoir sélectionné <strong>Hiérarchie</strong>, sous l’onglet <strong>Sélection de hiérarchie</strong>, dans la liste <strong>Type de hiérarchie</strong>, sélectionnez le type de hiérarchie auquel affecter la tâche.</li>
    <li>Le système doit extraire un ensemble de noms d’utilisateurs de la hiérarchie. Ces noms représentent les utilisateurs à qui la tâche peut être affectée. Pour indiquer le point de départ et le point final de l’ensemble de noms d’utilisateurs extraits par le système, procédez comme suit : <ol>
    <li>Pour spécifier le point de départ, sélectionnez une personne dans la liste <strong>Commencer à</strong>.</li>
    <li>pour indiquer le point final, cliquez sur <strong>Ajouter une condition</strong>. Entrez ensuite une condition pour indiquer où le système arrête l’extraction de noms dans la hiérarchie.</li>
    </ol>
    </li>
    <li>Sous l’onglet <strong>Options de la hiérarchie</strong>, spécifiez les utilisateurs de la sélection auxquels affecter la tâche : <ul>
    <li><strong>Affecter à tous les utilisateurs récupérés</strong> – La tâche est affectée à tous les utilisateurs de la sélection.</li>
    <li><strong>Affecter uniquement au dernier utilisateur récupéré</strong> – La tâche est affectée uniquement au dernier utilisateur de la sélection.</li>
    <li><strong>Exclure les utilisateurs à la condition suivante</strong> – La tâche n’est affectée à aucun des utilisateurs de la sélection qui remplissent une condition. Cliquez sur <strong>Ajouter une condition</strong> pour spécifier la condition.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Utilisateur du workflow</td>
    <td>Utilisateurs du workflow actuel</td>
    <td>
    <ul>
    <li>Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l’onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Utilisateur</td>
    <td>Utilisateurs spécifiques</td>
    <td>
    <ol>
    <li>Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l’onglet <strong>Utilisateur</strong>.</li>
    <li>La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs. Sélectionnez les utilisateurs à qui vous souhaitez affecter la tâche, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>File d’attente</td>
    <td>File d’attente des éléments de travail</td>
    <td>
    <ol>
    <li>Après avoir sélectionné <strong>File d’attente</strong>, cliquez sur l’onglet <strong>Basé sur la file d’attente</strong>.</li>
    <li>Pour affecter la tâche à une file d’attente donnée, procédez comme suit : <ol>
    <li>Dans la liste <strong>Type de file d’attente</strong>, sélectionnez <strong>Files d’attente des éléments de travail</strong>.</li>
    <li>Sélectionnez la file d’attente dans la liste <strong>Nom de file d’attente</strong>.</li>
    </ol>
    </li>
    <li>Si une condition détermine la file d’attente à laquelle la tâche est affectée, procédez comme suit : <ol>
    <li>Dans la liste <strong>Type de file d’attente</strong>, sélectionnez <strong>Files d’attente conditionnelles des éléments de travail</strong>.</li>
    <li>Dans la liste <strong>Nom de file d’attente</strong>, sélectionnez <strong>File d’attente conditionnelle</strong>.</li>
    </ol>
    </li>
    </ol>
    <blockquote>[!NOTE] Cette option est utilisée uniquement pour certains workflows, tels que Gestion des dossiers.</blockquote>
    </td>
    </tr>
    </tbody>
    </table>

3. Sous l’onglet **Limite de temps**, dans le champ **Durée**, indiquez le délai accordé à l’utilisateur pour réaliser la tâche. Permet de sélectionner l’une des options suivantes :

    - **Heures** – Permet d’entrer le nombre d’heures accordées à l’utilisateur pour terminer la tâche. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Jours** – Permet d’entrer le nombre de jours accordés à l’utilisateur pour terminer la tâche. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Semaines** – Permet d’entrer le nombre de semaines accordées à l’utilisateur pour terminer la tâche.
    - **Mois** – Permet de sélectionner le jour et la semaine où l’utilisateur doit terminer la tâche. Vous voudrez peut-être que l’utilisateur ait effectué la tâche d’ici le vendredi de la troisième semaine du mois.
    - **Années** – Permet de sélectionner le jour et le mois où l’utilisateur doit terminer la tâche. Vous voudrez peut-être que l’utilisateur ait effectué la tâche d’ici le vendredi de la troisième semaine de décembre.

    Si l’utilisateur ne termine pas la tâche dans le délai imparti, la tâche est en retard. Une tâche en retard peut être réaffectée, conformément aux options que vous sélectionnez dans la zone **Escalade** de cette page.

## <a name="specify-what-happens-when-the-task-is-overdue"></a>Spécification des conséquences du retard de la tâche

Si un utilisateur ne termine pas la tâche manuelle dans le délai imparti, la tâche est en retard. Une tâche en retard peut être affectée à un échelon supérieur ou affectée automatiquement à un autre utilisateur. Procédez comme suit pour réaffecter la tâche en retard.

1. Dans le volet gauche, cliquez sur **Escalade**.
2. Activez la case à cocher **Utiliser le chemin de réaffectation** pour créer un chemin de réaffectation. Le système affecte automatiquement la tâche aux utilisateurs répertoriés dans le chemin de réaffectation. Le tableau suivant présente un exemple de chemin de réaffectation.

    | Séquence | Chemin de réaffectation      |
    |----------|----------------------|
    | 1        | Affecter à : Donna     |
    | 2        | Affecter à : Erin      |
    | 3        | Action finale : Rejeter |

    Dans cet exemple, le système affecte la tâche en retard à Donna. Si celle-ci ne termine pas la tâche dans le délai imparti, le système affecte la tâche à Erin. Si celle-ci ne termine pas la tâche dans le délai imparti, le système rejette le document qui était soumis pour traitement.

3. Pour ajouter un utilisateur dans le chemin de réaffectation, cliquez sur **Ajouter une réaffectation**. Sous l’onglet **Type d’affectation**, sélectionnez l’une des options du tableau suivant et suivez les étapes supplémentaires concernant l’option avant de passer à l’étape 4.

    <table>
    <thead>
    <tr>
    <th>Option</th>
    <th>Utilisateurs à qui la tâche est affectée</th>
    <th>Étapes supplémentaires</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Hiérarchie</td>
    <td>Utilisateurs d’une hiérarchie organisationnelle spécifique</td>
    <td>
    <ol>
    <li>Après avoir sélectionné <strong>Hiérarchie</strong>, sous l’onglet <strong>Sélection de hiérarchie</strong>, dans la liste <strong>Type de hiérarchie</strong>, sélectionnez le type de hiérarchie auquel réaffecter la tâche.</li>
    <li>Le système doit extraire un ensemble de noms d’utilisateurs de la hiérarchie. Ces noms représentent les utilisateurs à qui la tâche peut être réaffectée. Pour indiquer le point de départ et le point final de l’ensemble de noms d’utilisateurs extraits par le système, procédez comme suit : <ol>
    <li>Pour spécifier le point de départ, sélectionnez une personne dans la liste <strong>Commencer à</strong>.</li>
    <li>pour indiquer le point final, cliquez sur <strong>Ajouter une condition</strong>. Entrez ensuite une condition pour indiquer où le système arrête l’extraction de noms dans la hiérarchie.</li>
    </ol>
    </li>
    <li>Sous l’onglet <strong>Options de la hiérarchie</strong>, spécifiez les utilisateurs de la sélection auxquels réaffecter la tâche : <ul>
    <li><strong>Affecter à tous les utilisateurs récupérés</strong> – La tâche est réaffectée à tous les utilisateurs de la sélection.</li>
    <li><strong>Affecter uniquement au dernier utilisateur récupéré</strong> – La tâche est réaffectée uniquement au dernier utilisateur de la sélection.</li>
    <li><strong>Exclure les utilisateurs à la condition suivante</strong> – La tâche n’est réaffectée à aucun des utilisateurs de la sélection qui remplissent une condition. Cliquez sur <strong>Ajouter une condition</strong> pour spécifier la condition.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Utilisateur du workflow</td>
    <td>Utilisateurs du workflow actuel</td>
    <td>
    <ul>
    <li>Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l’onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Utilisateur</td>
    <td>Utilisateurs spécifiques</td>
    <td>
    <ol>
    <li>Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l’onglet <strong>Utilisateur</strong>.</li>
    <li>La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs. Sélectionnez les utilisateurs à qui vous souhaitez réaffecter la tâche, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. Sous l’onglet **Limite de temps**, dans le champ **Durée**, indiquez le délai accordé à l’utilisateur pour réaliser la tâche. Permet de sélectionner l’une des options suivantes :

    - **Heures** – Permet d’entrer le nombre d’heures accordées à l’utilisateur pour terminer la tâche. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Jours** – Permet d’entrer le nombre de jours accordés à l’utilisateur pour terminer la tâche. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Semaines** – Permet d’entrer le nombre de semaines accordées à l’utilisateur pour terminer la tâche.
    - **Mois** – Permet de sélectionner le jour et la semaine où l’utilisateur doit terminer la tâche. Vous voudrez peut-être que l’utilisateur ait effectué la tâche d’ici le vendredi de la troisième semaine du mois.
    - **Années** – Permet de sélectionner le jour et le mois où l’utilisateur doit terminer la tâche. Vous voudrez peut-être que l’utilisateur ait effectué la tâche d’ici le vendredi de la troisième semaine de décembre.

5. Répétez les étapes 3 à 4 pour chaque utilisateur à ajouter au chemin de réaffectation. Vous pouvez modifier l’ordre des utilisateurs.
6. Si les utilisateurs du chemin de réaffectation ne terminent pas la tâche dans le délai imparti, le système agit sur la tâche. Pour indiquer l’action exécutée par le système, sélectionnez la ligne **Action**, puis sélectionnez une action sous l’onglet **Terminer l’action**.

## <a name="specify-when-the-system-automatically-acts-on-the-task"></a>Indication du moment où le système agit automatiquement sur la tâche

Vous pouvez configurer le système pour qu’il agisse sur la tâche manuelle si elle répond à certaines conditions. Supposons qu’une tâche nécessite qu’un membre du département États de dépenses passe en revue les reçus soumis avec un état de dépenses. Selon la stratégie de l’entreprise, cette tâche doit être exécutée si le montant total de l’état de dépense est supérieur à 100 EUR. Dans ce cas, vous pouvez configurer le système de sorte qu’il marque automatiquement la tâche comme **Terminé** lorsque le montant total est inférieur à 100. Procédez comme suit pour indiquer quand le système agit sur la tâche manuelle.

1. Dans le volet gauche, cliquez sur **Actions automatiques**.
2. Activez la case à cocher **Activer les actions automatiques**.
3. Cliquez sur **Ajouter**.
4. Permet d’entrer une condition.
5. Entrez des conditions supplémentaires, si nécessaire.
6. Pour vérifier que les conditions que vous avez entrées sont correctement configurées, procédez comme suit :

    1. Cliquez sur **Tester**.
    2. Sur la page **Condition de workflow de test**, sélectionnez un enregistrement dans la zone **Contrôler la condition**.
    3. Cliquez sur **Tester**. Le système évalue l’enregistrement pour déterminer s’il répond aux conditions que vous avez spécifiées.
    4. Cliquez sur **OK** ou sur **Annuler** pour revenir à la page **Propriétés**.

7. Dans la liste **Action de saisie automatique**, sélectionnez l’action que le système doit appliquer à la tâche.

## <a name="specify-when-notifications-are-sent"></a>Spécification du moment où les notifications sont envoyées

Vous pouvez envoyer des notifications aux personnes lorsqu’une tâche manuelle a été déléguée, réaffectée, terminée ou rejetée, ou encore lorsqu’une modification a été demandée. Procédez comme suit pour indiquer quand les notifications sont envoyées, et à qui.

1. Dans le volet gauche, cliquez sur **Notifications**.
2. Activez la case à cocher en regard des événements pour lesquels les notifications doivent être envoyées.

    - **Déléguer** – La tâche a été affectée à un autre utilisateur.
    - **Réaffecter** – L’utilisateur affecté n’a pas terminé la tâche dans le délai imparti.
    - **Terminé** – L’utilisateur affecté a terminé la tâche.
    - **Rejeter** – L’utilisateur affecté a rejeté le document soumis.
    - **Demander une modification** – L’utilisateur affecté a demandé une modification du document soumis.

3. Sélectionnez la ligne pour un événement sélectionné à l’étape 2.
4. Entrez le texte de la notification dans la zone de texte de l’onglet **Texte de notification**.
5. Pour personnaliser la notification, vous pouvez insérer des espaces réservés. Ils sont remplacés par les informations appropriées lorsque la notification s’affiche pour les utilisateurs. Pour insérer un espace réservé, procédez comme suit :

    1. Dans la zone de texte, cliquez pour spécifier l’endroit où l’espace réservé doit figurer.
    2. Cliquez sur **Insérer un espace réservé**.
    3. Dans la liste qui s’affiche, sélectionnez l’espace réservé que vous souhaitez insérer.
    4. Cliquez sur **Insérer**

6. Suivez les étapes suivantes pour ajouter une traduction de la notification.

    1. Cliquez sur **Traductions**.
    2. Dans la page qui s’affiche, cliquez sur **Ajouter**.
    3. Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.
    4. Entrez le texte dans le champ **Texte traduit**.
    5. Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l’étape 5.
    6. Cliquez sur **Fermer**.

7. Spécifiez à qui les notifications sont envoyées sous l’onglet **Destinataire**. Sélectionnez l’une des options du tableau suivant et suivez les étapes supplémentaires concernant l’option avant de passer à l’étape 8.

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
    <li>Après avoir sélectionné <strong>Participant</strong>, sous l’onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</li>
    <li>Dans la liste <strong>Participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Utilisateur du workflow</td>
    <td>Utilisateurs du workflow actuel</td>
    <td>
    <ul>
    <li>Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l’onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Utilisateur</td>
    <td>Utilisateurs spécifiques</td>
    <td>
    <ol>
    <li>Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l’onglet <strong>Utilisateur</strong>.</li>
    <li>La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs. Sélectionnez les utilisateurs à qui envoyer les notifications, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Répétez les étapes 3 à 7 pour chaque événement que vous avez sélectionné à l’étape 2.

## <a name="set-a-time-limit"></a>Définition d’un délai limite

Si la tâche manuelle doit être exécutée dans un certain délai, procédez comme suit.

> [!NOTE]
> Les options sélectionnées dans cette procédure remplacent celles sélectionnées dans les zones **Affectation** et **Escalade** de la page.

1. Dans le volet gauche, cliquez sur **Paramètres avancés**.
2. Activez la case à cocher **Définir une limite de temps pour l’élément de workflow**.
3. Dans le champ **Durée**, spécifiez quand la tâche doit être exécutée. Permet de sélectionner l’une des options suivantes :

    - **Heures** – Permet d’entrer le nombre d’heures pendant lesquelles cette tâche doit être exécutée. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Jours** – Permet d’entrer le nombre de jours pendant lesquels cette tâche doit être exécutée. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Semaines** – Permet d’entrer le nombre de semaines accordé pour l’exécution de la tâche.
    - **Mois** – Permet de sélectionner le jour et la semaine et le mois limites où la tâche doit être terminée. Par exemple, vous voudrez peut-être que la tâche soit exécutée d’ici le vendredi de la troisième semaine du mois.
    - **Années** – Permet de sélectionner le jour, la semaine et le mois limites où la tâche doit être terminée. Vous voudrez peut-être que la tâche soit exécutée d’ici le vendredi de la troisième semaine de décembre.

4. Si le délai est dépassé, le système agit sur la tâche. Dans la liste **Action**, sélectionnez l’action que le système doit exécuter.

## <a name="specify-which-actions-are-available-to-the-user"></a>Spécification des actions disponibles pour l’utilisateur

Lorsque la tâche manuelle est affectée à un utilisateur, l’utilisateur doit agir sur la tâche. Procédez comme suit pour indiquer les actions que l’utilisateur peut exécuter sur la tâche.

> [!NOTE]
> Les actions disponibles peuvent varier selon la conception de la tâche.

1. Dans le volet gauche, cliquez sur **Paramètres avancés**.
2. Activez la case à cocher **Terminé** si vous voulez que l’utilisateur puisse marquer la tâche comme **Terminé**.
3. Activez la case à cocher **Rejeter** si vous voulez que l’utilisateur puisse rejeter le document envoyé.
4. Activez la case à cocher **Demander une modification** si vous voulez que l’utilisateur puisse demander des modifications du document envoyé.
5. Activez la case à cocher **Déléguer** si vous voulez que l’utilisateur puisse affecter la tâche à un autre utilisateur.
6. Activez la case à cocher **Réaffecter** si vous voulez que l’utilisateur puisse réaffecter la tâche à un autre utilisateur de la file d’attente des éléments de travail.
7. Activez la case à cocher **Lancer** si vous voulez que l’utilisateur puisse réaffecter la tâche à la file d’attente des éléments de travail. Un autre utilisateur peut effectuer la tâche.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]