---
title: "Configurer une étape d&quot;approbation dans un workflow"
description: "Cette rubrique explique comment configurer les propriétés d&quot;une étape d&quot;approbation."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1924562f866ecdbb6fa6d3d0a9dc7627387f2d6a
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="configure-an-approval-step-in-a-workflow"></a>Configurer une étape d'approbation dans un workflow

[!include[banner](../includes/banner.md)]


Cette rubrique explique comment configurer les propriétés d'une étape d'approbation.

Pour configurer une étape d'approbation, dans l'éditeur de workflow, cliquez avec le bouton droit sur l'étape d'approbation, puis cliquez sur **Propriétés** pour ouvrir la page **Propriétés**. Suivez ensuite les procédures suivantes permettent de configurer les propriétés de l'étape d'approbation.

## <a name="name-the-step"></a>Saisie d'un nom pour l'étape
Procédez comme suit pour entrer un nom pour l'étape d'approbation.

1.  Dans le volet gauche, cliquez sur **Paramètres de base**.
2.  Dans le champ **Nom**, entrez un nom unique pour l'étape d'approbation.

## <a name="enter-a-subject-line-and-instructions"></a>Saisie d'une ligne d'objet et des instructions
Vous devez fournir une ligne d'objet et des instructions aux utilisateurs affectés à l'étape d'approbation. Par exemple, si vous configurez une étape d'approbation pour des demandes d'achat, l'utilisateur concerné par cette étape voit la ligne d'objet et les instructions sur la page **Demandes d'achat**. La ligne d'objet figure dans une barre de message de la page. L'utilisateur peut ensuite cliquer sur l'icône de la barre des messages pour afficher les instructions. Procédez comme suit pour entrer une ligne d'objet et des instructions.

1.  Dans le volet gauche, cliquez sur **Paramètres de base**.
2.  Entrez la ligne d'objet dans le champ **Objet de l'article de travail**.
3.  Si vous souhaitez personnaliser la ligne, vous pouvez insérer des espaces réservés. Ils sont remplacés par les données appropriées lorsque la ligne d'objet s'affiche pour les utilisateurs. Pour insérer un espace réservé, procédez comme suit :
    1.  Dans la zone de texte, cliquez pour spécifier l'endroit où l'espace réservé doit figurer.
    2.  Cliquez sur **Insérer un espace réservé**.
    3.  Dans la liste qui s'affiche, sélectionnez l'espace réservé que vous souhaitez insérer.
    4.  Cliquez sur **Insérer**

4.  Suivez les étapes suivantes pour ajouter une traduction de la ligne d'objet.
    1.  Cliquez sur **Traductions**.
    2.  Dans la page qui s'affiche, cliquez sur **Ajouter**.
    3.  Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.
    4.  Entrez le texte dans le champ **Texte traduit**.
    5.  Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l'étape 3.
    6.  Cliquez sur **Fermer**.

5.  Entrez les instructions dans le champ **Instructions de l'élément de travail**.
6.  Pour personnaliser les instructions, vous pouvez insérer des espaces réservés. Ils sont remplacés par les données appropriées lorsque les instructions apparaissent aux utilisateurs. Pour insérer un espace réservé, procédez comme suit :
    1.  Dans la zone de texte, cliquez pour spécifier l'endroit où l'espace réservé doit figurer.
    2.  Cliquez sur **Insérer un espace réservé**.
    3.  Dans la liste qui s'affiche, sélectionnez l'espace réservé que vous souhaitez insérer.
    4.  Cliquez sur **Insérer**

7.  Suivez les étapes suivantes pour ajouter une traduction des instructions.
    1.  Cliquez sur **Traductions**.
    2.  Dans la page qui s'affiche, cliquez sur **Ajouter**.
    3.  Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.
    4.  Entrez le texte dans le champ **Texte traduit**.
    5.  Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l'étape 6.
    6.  Cliquez sur **Fermer**.

## <a name="assign-the-approval-step"></a>Affectation de l'étape d'approbation
Procédez comme suit pour indiquer à qui affecter la tâche d'approbation.

1.  Dans le volet gauche, cliquez sur **Affectation**.
2.  Sous l'onglet **Type d'affectation**, sélectionnez l'une des options du tableau suivant et suivez les étapes supplémentaires concernant l'option avant de passer à l'étape 3.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Option</th>
    <th>Utilisateurs à qui l'étape d'approbation est affectée</th>
    <th>Étapes supplémentaires</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Participant</td>
    <td>Utilisateurs affectés à un groupe ou à un rôle spécifique</td>
    <td><ol>
    <li>Après avoir sélectionné <strong>Participant</strong>, sous l'onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel affecter l'étape.</li>
    <li>Dans la liste <strong>Participant</strong>, sélectionnez le groupe ou le rôle auquel vous souhaitez affecter l'étape.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Hiérarchie</td>
    <td>Utilisateurs d'une hiérarchie organisationnelle spécifique</td>
    <td><ol>
    <li>Après avoir sélectionné <strong>Hiérarchie</strong>, sous l'onglet <strong>Sélection de hiérarchie</strong>, dans la liste <strong>Type de hiérarchie</strong>, sélectionnez le type de hiérarchie auquel affecter l'étape.</li>
    <li>Le système doit extraire un ensemble de noms d'utilisateurs de la hiérarchie. Ces noms représentent les utilisateurs à qui l'étape peut être affectée. Pour indiquer le point de départ et le point final de l'ensemble de noms d'utilisateurs extraits par le système, procédez comme suit : <ol>
    <li>Pour spécifier le point de départ, sélectionnez une personne dans la liste <strong>Commencer à</strong>.</li>
    <li>pour indiquer le point final, cliquez sur <strong>Ajouter une condition</strong>. Entrez ensuite une condition pour indiquer où le système arrête l'extraction de noms dans la hiérarchie.</li>
    </ol></li>
    <li>Sous l'onglet <strong>Options de la hiérarchie</strong>, spécifiez les utilisateurs de la sélection auxquels affecter l'étape : <ul>
    <li><strong>Affecter à tous les utilisateurs récupérés</strong> – L'étape est affectée à tous les utilisateurs de la sélection.</li>
    <li><strong>Affecter uniquement au dernier utilisateur récupéré</strong> – L'étape est affectée uniquement au dernier utilisateur de la sélection.</li>
    <li><strong>Exclure les utilisateurs à la condition suivante</strong> – L'étape n'est affectée à aucun des utilisateurs de la sélection qui remplissent une condition. Cliquez sur <strong>Ajouter une condition</strong> pour spécifier la condition.</li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Utilisateur du workflow</td>
    <td>Utilisateurs du workflow actuel</td>
    <td><ul>
    <li>Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l'onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</li>
    </ul></td>
    </tr>
    <tr class="even">
    <td>Utilisateur</td>
    <td>Utilisateurs Microsoft Dynamics 365 for Operations spécifiques</td>
    <td><ol>
    <li>Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l'onglet <strong>Utilisateur</strong>.</li>
    <li>La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs Dynamics 365 for Operations. Sélectionnez les utilisateurs à qui vous souhaitez affecter l'étape, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

3.  Sous l'onglet **Limite de temps**, dans le champ **Durée**, indiquez le délai accordé à l'utilisateur pour traiter les documents qui atteignent cette étape d'approbation ou pour y répondre. Permet de sélectionner l'une des options suivantes :
    -   **Heures** – Entrez le nombre d'heures accordé à l'utilisateur pour répondre. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    -   **Jours** – Entrez le nombre de jours accordé à l'utilisateur pour répondre. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    -   **Semaines** – Entrez le nombre de semaines accordé à l'utilisateur pour répondre.
    -   **Mois** – Sélectionnez le jour et la semaine où l'utilisateur doit répondre. Par exemple, vous pouvez souhaiter que l'utilisateur réponde avant le vendredi de la troisième semaine du mois.
    -   **Années** – Sélectionnez le jour et le mois limites où l'utilisateur doit répondre. Par exemple, vous pouvez souhaiter que l'utilisateur réponde avant le vendredi de la troisième semaine du mois de décembre.

    Si l'utilisateur ne traite pas le document dans le délai imparti, le document est en retard. Un document en retard est réaffecté, conformément aux options que vous sélectionnez dans la zone **Escalade** de cette page.
4.  Si vous avez affecté l'étape d'approbation à plusieurs utilisateurs ou à un groupe d'utilisateurs, cliquez sur l'onglet **Stratégie d'achèvement**, puis sélectionnez l'une des options suivantes :
    -   **Un seul approbateur** – L'action appliquée au document est déterminée par la première personne qui répond. Par exemple, Sam a soumis un état de dépenses de USD 15 000. L'état de dépenses est actuellement affecté à Sue, Jo et Bill. Si Sue est la première à répondre au document, l'action qu'elle effectue est appliquée au document. Si Sue rejette le document, il est rejeté et renvoyé à Sam. Si Sue approuve le document, il est envoyé à Ann pour approbation. ![Workflow avec un processus d'approbation](./media/workflow_multipleusersinstep.gif)
    -   **La majorité des approbateurs** – L'action appliquée au document est déterminée lorsque la majorité des approbateurs ont répondu. Par exemple, Sam a soumis un état de dépenses de USD 15 000. L'état de dépenses est actuellement affecté à Sue, Jo et Bill. Si Sue et Jo sont les deux premiers approbateurs à répondre, l'action qu'ils effectuent est appliquée au document.
        -   Si Sue approuve le document, mais que Jo le rejette, le document est rejeté et renvoyé à Sam.
        -   Si Sue et Jo approuvent le document, il est envoyé à Ann pour approbation.
    -   **Pourcentage d'approbateurs** – L'action appliquée au document est déterminée lorsqu'un pourcentage spécifique d'approbateurs a répondu. Par exemple, Sam a soumis un état de dépenses de USD 15 000. L'état de dépenses est actuellement affecté à Sue, Jo et Bill, et vous avez entré le pourcentage **50**. Si Sue et Jo sont les deux premiers approbateurs à répondre, l'action qu'ils effectuent est appliquée au document, car ils répondent à la condition qui stipule 50 % d'approbateurs.
        -   Si Sue approuve le document, mais que Jo le rejette, le document est rejeté et renvoyé à Sam.
        -   Si Sue et Jo approuvent le document, il est envoyé à Ann pour approbation.
    -   **Tous les approbateurs** – Tous les approbateurs doivent approuver le document. Sinon, le workflow ne peut pas continuer. Par exemple, Sam a soumis un état de dépenses de 15 000 EUR. L'état de dépenses est actuellement affecté à Sue, Jo et Bill. Si Sue et Jo approuvent le document, mais que Bill le rejette, le document est rejeté et renvoyé à Sam. Si Sue, Jo et Bill approuvent le document, il est envoyé à Ann pour approbation.

## <a name="specify-when-the-approval-step-is-required"></a>Indication du moment où l'étape d'approbation est requise
Vous pouvez indiquer quand l'étape d'approbation est requise. L'étape d'approbation peut être requise tout le temps ou uniquement sous certaines conditions.

### <a name="the-approval-step-is-always-required"></a>L'étape d'approbation est toujours requise

Si l'étape d'approbation est toujours requise, procédez comme suit.

1.  Dans le volet gauche, cliquez sur **Condition**.
2.  Sélectionnez l'option **Toujours exécuter cette étape**.

### <a name="the-approval-step-is-required-in-specific-conditions"></a>L'étape d'approbation est requise sous certaines conditions

L'étape d'approbation que vous configurez peut être requise uniquement sous certaines conditions. Par exemple, si vous configurez une étape d'approbation pour un workflow de demande d'achat, vous voudrez peut-être que cette étape ne soit réalisée que si le montant de la demande d'achat est supérieur à 10 000 EUR. Procédez comme suit pour indiquer quand l'étape d'approbation est requise.

1.  Dans le volet gauche, cliquez sur **Condition**.
2.  Sélectionnez l'option **Exécuter cette étape uniquement si la condition suivante est remplie**.
3.  Permet d'entrer une condition.
4.  Entrez des conditions supplémentaires, si nécessaire.
5.  Pour vérifier que les conditions que vous avez entrées sont correctement configurées, procédez comme suit :
    1.  Cliquez sur **Tester**.
    2.  Sur la page **Condition de workflow de test**, sélectionnez un enregistrement dans la zone **Contrôler la condition**.
    3.  Cliquez sur **Tester**. Le système évalue l'enregistrement pour déterminer s'il répond aux conditions que vous avez spécifiées.
    4.  Cliquez sur **OK** ou sur **Annuler** pour revenir à la page **Propriétés**.

## <a name="specify-what-happens-when-the-document-is-overdue"></a>Spécification des conséquences du retard du document
Si un utilisateur ne traite pas un document dans le délai imparti, le document est en retard. Un document en retard peut être réaffecté ou affecté automatiquement à un autre utilisateur pour approbation. Procédez comme suit pour réaffecter le document en retard.

1.  Dans le volet gauche, cliquez sur **Escalade**.
2.  Activez la case à cocher **Utiliser le chemin de réaffectation** pour créer un chemin de réaffectation. Le système affecte automatiquement le document aux utilisateurs répertoriés dans le chemin de réaffectation. Le tableau suivant présente un exemple de chemin de réaffectation.
    | Séquence | Chemin de réaffectation      |
    |----------|----------------------|
    | 1        | Affecter à : Donna     |
    | 2        | Affecter à : Erin      |
    | 3        | Action finale : Rejeter |

    Dans cet exemple, le système affecte le document en retard à Donna. Si celle-ci ne répond pas dans le délai imparti, le système affecte le document à Erin. Si celle-ci ne répond pas dans le délai imparti, le système rejette le document.
3.  Pour ajouter un utilisateur dans le chemin de réaffectation, cliquez sur **Ajouter une réaffectation**. Sous l'onglet **Type d'affectation**, sélectionnez l'une des options du tableau suivant et suivez les étapes supplémentaires concernant l'option avant de passer à l'étape 4.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Option</th>
    <th>Utilisateurs à qui le document est affecté</th>
    <th>Étapes supplémentaires</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Hiérarchie</td>
    <td>Utilisateurs d'une hiérarchie organisationnelle spécifique</td>
    <td><ol>
    <li>Après avoir sélectionné <strong>Hiérarchie</strong>, sous l'onglet <strong>Sélection de hiérarchie</strong>, dans la liste <strong>Type de hiérarchie</strong>, sélectionnez le type de hiérarchie à laquelle réaffecter le document.</li>
    <li>Le système doit extraire un ensemble de noms d'utilisateurs de la hiérarchie. Ces noms représentent les utilisateurs à qui le document peut être réaffecté. Pour indiquer le point de départ et le point final de l'ensemble de noms d'utilisateurs extraits par le système, procédez comme suit : <ol>
    <li>Pour spécifier le point de départ, sélectionnez une personne dans la liste <strong>Commencer à</strong>.</li>
    <li>pour indiquer le point final, cliquez sur <strong>Ajouter une condition</strong>. Entrez ensuite une condition pour indiquer où le système arrête l'extraction de noms dans la hiérarchie.</li>
    </ol></li>
    <li>Sous l'onglet <strong>Options de la hiérarchie</strong>, indiquez les utilisateurs de la sélection à qui le document est réaffecté : <ul>
    <li><strong>Affecter à tous les utilisateurs récupérés</strong> – Le document est réaffecté à tous les utilisateurs de la sélection.</li>
    <li><strong>Affecter uniquement au dernier utilisateur récupéré</strong> – Le document est réaffecté uniquement au dernier utilisateur de la sélection.</li>
    <li><strong>Exclure les utilisateurs à la condition suivante</strong> – Le document n'est affecté à aucun des utilisateurs de la sélection qui remplissent une condition. Cliquez sur <strong>Ajouter une condition</strong> pour spécifier la condition.</li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Utilisateur du workflow</td>
    <td>Utilisateurs du workflow actuel</td>
    <td><ul>
    <li>Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l'onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td>Utilisateur</td>
    <td>Utilisateurs Dynamics 365 for Operations spécifiques</td>
    <td><ol>
    <li>Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l'onglet <strong>Utilisateur</strong>.</li>
    <li>La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs Dynamics 365 for Operations. Sélectionnez les utilisateurs à qui réaffecter le document, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

4.  Sous l'onglet **Limite de temps**, dans le champ **Durée**, indiquez le délai accordé à l'utilisateur pour traiter les documents qui atteignent cette étape d'approbation ou pour y répondre. Permet de sélectionner l'une des options suivantes :
    -   **Heures** – Entrez le nombre d'heures accordé à l'utilisateur pour répondre. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    -   **Jours** – Entrez le nombre de jours accordé à l'utilisateur pour répondre. Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.
    -   **Semaines** – Entrez le nombre de semaines accordé à l'utilisateur pour répondre.
    -   **Mois** – Sélectionnez le jour et la semaine où l'utilisateur doit répondre. Par exemple, vous pouvez souhaiter que l'utilisateur réponde avant le vendredi de la troisième semaine du mois.
    -   **Années** – Sélectionnez le jour et le mois limites où l'utilisateur doit répondre. Par exemple, vous pouvez souhaiter que l'utilisateur réponde avant le vendredi de la troisième semaine du mois de décembre.

5.  Répétez les étapes 3 à 4 pour chaque utilisateur à ajouter au chemin de réaffectation. Vous pouvez modifier l'ordre des utilisateurs.
6.  Si les utilisateurs du chemin de réaffectation ne répondent pas dans le délai imparti, le système traite automatiquement le document. Pour indiquer l'action exécutée par le système, sélectionnez la ligne **Action**, puis sélectionnez une action sous l'onglet **Terminer l'action**.





