---
title: Configurer des décisions manuelles dans un workflow
description: Cette rubrique explique comment configurer les différentes propriétés d’une décision manuelle.
author: ChrisGarty
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d54c010c8fe0d8ca6cc8129948392fb56ef85283
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065653"
---
# <a name="configure-manual-decisions-in-a-workflow"></a>Configurer des décisions manuelles dans un workflow

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Cette rubrique explique comment configurer les différentes propriétés d’une décision manuelle.

Pour configurer une décision manuelle, dans l’éditeur de workflow, cliquez avec le bouton droit sur la décision manuelle, puis cliquez sur **Propriétés** pour ouvrir la page **Propriétés**. Suivez ensuite les procédures suivantes pour configurer les propriétés de la décision manuelle.

## <a name="name-the-decision"></a>Saisie d’un nom pour la décision

Procédez comme suit pour entrer un nom pour la décision manuelle.

1. Dans le volet gauche, cliquez sur **Paramètres de base**.
2. Entrez un nom unique pour la décision manuelle dans le champ **Nom**.

## <a name="enter-a-subject-line-and-instructions"></a>Saisie d’une ligne d’objet et des instructions

Vous devez fournir une ligne d’objet et des instructions aux utilisateurs affectés à la décision manuelle. Par exemple, si vous configurez une décision pour des demandes d’achat, l’utilisateur concerné par cette décision voit la ligne d’objet et les instructions dans la page **Demandes d’achat**. La ligne d’objet figure dans une barre de message de la page. L’utilisateur peut ensuite cliquer sur l’icône de la barre des messages pour afficher les instructions. Procédez comme suit pour entrer une ligne d’objet et des instructions.

1. Dans le volet gauche, cliquez sur **Paramètres de base**.
2. Entrez la ligne d’objet dans l’onglet **Instructions**, dans le champ **Objet de l’article de travail**.
3. Si vous souhaitez personnaliser la ligne, vous pouvez insérer des espaces réservés. Ils sont remplacés par les données appropriées lorsque la ligne d’objet s’affiche pour les utilisateurs. Pour insérer un espace réservé, procédez comme suit :

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
6. Pour personnaliser les instructions, vous pouvez insérer des espaces réservés. Ils sont remplacés par les données appropriées lorsque les instructions apparaissent aux utilisateurs. Pour insérer un espace réservé, procédez comme suit :

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

## <a name="specify-the-possible-outcomes-of-a-decision"></a>Indication des résultats possibles d’une décision

En général, quand un document est affecté à un décideur lorsque ce dernier doit répondre à une question. Le plus souvent, la réponse à la question est **Oui** ou **Non** ou **Vrai** ou **Faux**. Procédez comme suit pour indiquer les résultats possibles de la décision manuelle.

1. Dans le volet gauche, cliquez sur **Paramètres de base**.
2. Entrez le nom du résultat ou de l’option dans l’onglet **Résultats**, dans le champ **Résultat 1**.
3. Suivez les étapes suivantes pour ajouter une traduction du résultat.

    1. Cliquez sur **Traductions**.
    2. Dans la page qui s’affiche, cliquez sur **Ajouter**.
    3. Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.
    4. Entrez le texte dans le champ **Texte traduit**.
    5. Cliquez sur **Fermer**.

4. Dans le champ **Résultat 2**, entrez le nom du résultat ou de l’option.
5. Suivez les étapes suivantes pour ajouter une traduction du résultat.

    1. Cliquez sur **Traductions**.
    2. Dans la page qui s’affiche, cliquez sur **Ajouter**.
    3. Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.
    4. Entrez le texte dans le champ **Texte traduit**.
    5. Cliquez sur **Fermer**.

## <a name="specify-when-notifications-are-sent"></a>Spécification du moment où les notifications sont envoyées

Vous pouvez envoyer des notifications aux personnes lorsqu’une décision doit être prise, déléguée ou réaffectée. Procédez comme suit pour indiquer quand les notifications sont envoyées, et à qui.

1. Dans le volet gauche, cliquez sur **Notifications**.
2. Activez la case à cocher en regard des événements pour lesquels les notifications doivent être envoyées.

    - **\[Choix 1\]** – L’utilisateur affecté a choisi **\[Choix 1\]**.
    - **\[Choix 2\]** – L’utilisateur affecté a choisi **\[Choix 2\]**.
    - **Déléguer** – L’utilisateur affecté a affecté la décision à un autre utilisateur.
    - **Réaffecter** – L’utilisateur affecté n’a pas pris la décision dans le délai imparti.

3. Sélectionnez la ligne pour un événement sélectionné à l’étape 2.
4. Entrez le texte de la notification dans la zone de texte de l’onglet **Texte de notification**.
5. Pour personnaliser la notification, vous pouvez insérer des espaces réservés. Ils sont remplacés par les données appropriées lorsque la notification s’affiche pour les utilisateurs. Pour insérer un espace réservé, procédez comme suit :

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
    <li>Dans la liste <strong>Participant</strong>, sélectionnez le groupe ou le rôle auquel envoyer les notifications.</li>
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

## <a name="assign-a-decision"></a>Affectation d’une décision

Procédez comme suit pour indiquer à qui affecter une décision manuelle.

1. Dans le volet gauche, cliquez sur **Affectation**.
2. Sous l’onglet **Type d’affectation**, sélectionnez l’une des options du tableau suivant et suivez les étapes supplémentaires concernant l’option avant de passer à l’étape 3.

    <table>
    <thead>
    <tr>
    <th>Option</th>
    <th>Utilisateurs à qui la décision est affectée</th>
    <th>Étapes supplémentaires</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Participant</td>
    <td>Utilisateurs affectés à un groupe ou à un rôle spécifique</td>
    <td>
    <ol>
    <li>Après avoir sélectionné <strong>Participant</strong>, sous l’onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel affecter la décision.</li>
    <li>Dans la liste <strong>Participant</strong>, sélectionnez le type de groupe ou de rôle auquel affecter la décision.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Hiérarchie</td>
    <td>Utilisateurs d’une hiérarchie organisationnelle spécifique</td>
    <td>
    <ol>
    <li>Après avoir sélectionné <strong>Hiérarchie</strong>, sous l’onglet <strong>Sélection de hiérarchie</strong>, dans la liste <strong>Type de hiérarchie</strong>, sélectionnez le type de hiérarchie auquel affecter la décision.</li>
    <li>Le système doit extraire un ensemble de noms d’utilisateurs de la hiérarchie. Ces noms représentent les utilisateurs à qui la décision peut être affectée. Pour indiquer le point de départ et le point final de l’ensemble de noms d’utilisateurs extraits par le système, procédez comme suit : <ol>
    <li>Pour spécifier le point de départ, sélectionnez une personne dans la liste <strong>Commencer à</strong>.</li>
    <li>pour indiquer le point final, cliquez sur <strong>Ajouter une condition</strong>. Entrez ensuite une condition pour indiquer où le système arrête l’extraction de noms dans la hiérarchie.</li>
    </ol>
    </li>
    <li>Sous l’onglet <strong>Options de la hiérarchie</strong>, spécifiez les utilisateurs de la sélection auxquels affecter la décision : <ul>
    <li><strong>Affecter à tous les utilisateurs récupérés</strong> – La décision est affectée à tous les utilisateurs de la sélection.</li>
    <li><strong>Affecter uniquement au dernier utilisateur récupéré</strong> – La décision est affectée uniquement au dernier utilisateur de la sélection.</li>
    <li><strong>Exclure les utilisateurs à la condition suivante</strong> – La décision n’est affectée à aucun des utilisateurs de la sélection qui remplissent une condition. Cliquez sur <strong>Ajouter une condition</strong> pour spécifier la condition.</li>
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
    <li>La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs. Sélectionnez les utilisateurs à qui vous souhaitez affecter la décision, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. Sous l’onglet **Limite de temps**, dans le champ **Durée**, indiquez le délai accordé à l’utilisateur pour prendre la décision. Permet de sélectionner l’une des options suivantes :

    - **Heures** – Permet d’entrer le nombre d’heures accordées à l’utilisateur pour prendre la décision. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Jours** – Permet d’entrer le nombre de jours accordés à l’utilisateur pour prendre la décision. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Semaines** – Permet d’entrer le nombre de semaines accordées à l’utilisateur pour prendre la décision.
    - **Mois** – Permet de sélectionner le jour et la semaine où l’utilisateur doit prendre la décision. Vous voudrez peut-être que l’utilisateur prenne la décision d’ici le vendredi de la troisième semaine du mois.
    - **Années** – Permet de sélectionner le jour, la semaine et le mois où l’utilisateur doit prendre la décision. Vous voudrez peut-être que l’utilisateur prenne la décision d’ici le vendredi de la troisième semaine du mois de décembre.

    Si l’utilisateur ne prend pas la décision dans le délai imparti, la décision est en retard. Une décision en retard est réaffectée, conformément aux options que vous sélectionnez dans la zone **Escalade** de cette page.

## <a name="specify-what-happens-when-a-decision-is-overdue"></a>Spécification des conséquences du retard d’une décision

Si un utilisateur ne prend pas la décision dans le délai imparti, la décision est en retard. Une décision en retard peut être affectée à un échelon supérieur ou affectée automatiquement à un autre utilisateur. Procédez comme suit pour réaffecter la décision en retard.

1. Dans le volet gauche, cliquez sur **Escalade**.
2. Activez la case à cocher **Utiliser le chemin de réaffectation** pour créer un chemin de réaffectation. Le système affecte automatiquement la décision aux utilisateurs répertoriés dans le chemin de réaffectation. Le tableau suivant présente un exemple de chemin de réaffectation.

    | Séquence | Chemin de réaffectation            |
    |----------|----------------------------|
    | 1        | Affecter à : Donna           |
    | 2        | Affecter à : Erin            |
    | 3        | Action finale : \[Choix 1\] |

    Dans cet exemple, le système affecte la décision en retard à Donna. Si celle-ci ne prend pas la décision dans le délai imparti, le système affecte la décision à Erin. Si celle-ci ne prend pas la décision dans le délai imparti, le système sélectionne le **\[Choix 1\]** comme décision.

3. Pour ajouter un utilisateur dans le chemin de réaffectation, cliquez sur **Ajouter une réaffectation**. Sélectionnez l’une des options du tableau suivant et suivez les étapes supplémentaires concernant l’option avant de passer à l’étape 4.

    <table>
    <thead>
    <tr>
    <th>Option</th>
    <th>Utilisateurs à qui la décision est affectée</th>
    <th>Étapes supplémentaires</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Hiérarchie</td>
    <td>Utilisateurs d’une hiérarchie organisationnelle spécifique</td>
    <td>
    <ol>
    <li>Après avoir sélectionné <strong>Hiérarchie</strong>, sous l’onglet <strong>Sélection de hiérarchie</strong>, dans la liste <strong>Type de hiérarchie</strong>, sélectionnez le type de hiérarchie à laquelle réaffecter la décision.</li>
    <li>Le système doit extraire un ensemble de noms d’utilisateurs de la hiérarchie. Ces noms représentent les utilisateurs à qui la décision peut être réaffectée. Pour indiquer le point de départ et le point final de l’ensemble de noms d’utilisateurs extraits par le système, procédez comme suit : <ol>
    <li>Pour spécifier le point de départ, sélectionnez une personne dans la liste <strong>Commencer à</strong>.</li>
    <li>pour indiquer le point final, cliquez sur <strong>Ajouter une condition</strong>. Entrez ensuite une condition pour indiquer où le système arrête l’extraction de noms dans la hiérarchie.</li>
    </ol>
    </li>
    <li>Sous l’onglet <strong>Options de la hiérarchie</strong>, indiquez les utilisateurs de la sélection à qui la décision est réaffecté : <ul>
    <li><strong>Affecter à tous les utilisateurs récupérés</strong> – La décision est réaffecté à tous les utilisateurs de la sélection.</li>
    <li><strong>Affecter uniquement au dernier utilisateur récupéré</strong> – La décision est réaffecté uniquement au dernier utilisateur de la sélection.</li>
    <li><strong>Exclure les utilisateurs à la condition suivante</strong> – La décision n’est réaffectée à aucun des utilisateurs de la sélection qui remplissent une condition. Cliquez sur <strong>Ajouter une condition</strong> pour spécifier la condition.</li>
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
    <li>La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs. Sélectionnez les utilisateurs à qui réaffecter la décision, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. Sous l’onglet **Limite de temps**, dans le champ **Durée**, indiquez le délai accordé à l’utilisateur pour prendre la décision. Permet de sélectionner l’une des options suivantes :

    - **Heures** – Permet d’entrer le nombre d’heures accordées à l’utilisateur pour prendre la décision. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Jours** – Permet d’entrer le nombre de jours accordés à l’utilisateur pour prendre la décision. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Semaines** – Permet d’entrer le nombre de semaines accordées à l’utilisateur pour prendre la décision.
    - **Mois** – Permet de sélectionner le jour et la semaine où l’utilisateur doit prendre la décision. Vous voudrez peut-être que l’utilisateur prenne la décision d’ici le vendredi de la troisième semaine du mois.
    - **Années** – Permet de sélectionner le jour, la semaine et le mois où l’utilisateur doit prendre la décision. Vous voudrez peut-être que l’utilisateur prenne la décision d’ici le vendredi de la troisième semaine du mois de décembre.

5. Répétez les étapes 3 à 4 pour chaque utilisateur à ajouter au chemin de réaffectation. Vous pouvez modifier l’ordre des utilisateurs.
6. Si les utilisateurs du chemin de réaffectation ne prennent pas la décision dans le délai imparti, le système prend la décision. Pour indiquer l’option exécutée par le système, sélectionnez la ligne **Action**, puis sélectionnez une option sous l’onglet **Terminer l’action**.

## <a name="set-a-time-limit"></a>Définition d’un délai limite

Si la décision doit être prise dans un certain délai, procédez comme suit.

> [!NOTE]
> Les options sélectionnées dans cette procédure remplacent celles sélectionnées dans les zones **Affectation** et **Escalade** de la page.

1. Dans le volet gauche, cliquez sur **Paramètres avancés**.
2. Activez la case à cocher **Définir une limite de temps pour l’élément de workflow**.
3. Dans le champ **Durée**, spécifiez quand la décision doit être prise. Permet de sélectionner l’une des options suivantes :

    - **Heures** – Permet d’entrer le nombre d’heures. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Jours** – Permet d’entrer le nombre de jours. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    - **Semaines** – Permet d’entrer le nombre de semaines.
    - **Mois** – Permet de sélectionner le jour et la semaine où prendre la décision. Par exemple, vous pouvez décider que la décision soit prise d’ici le vendredi de la troisième semaine du mois.
    - **Années** – Permet de sélectionner le jour, la semaine et le mois limites pour prendre la décision. Par exemple, vous pouvez décider que la décision soit prise d’ici le vendredi de la troisième semaine de décembre.

4. Si le délai est dépassé, le système prend la décision. Dans la liste **Action**, sélectionnez l’option que le système doit sélectionner.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]