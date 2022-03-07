---
title: Paramétrez et exécutez le traitement pour appeler format d'exportation d'ER pour générer un état d'Excel
description: Cette rubrique fournit un exemple qui montre comment configurer et utiliser des messages électroniques.
author: liza-golub
ms.date: 07/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 25721f1b79d8f0fbf8ca2112ed21fa2d8cd0bc84
ms.sourcegitcommit: 73d320d2103f2b0c6ecbb2b9df746469bc544ea2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2021
ms.locfileid: "6433783"
---
# <a name="set-up-and-run-processing-to-call-a-simple-exporting-er-format-to-generate-an-excel-report"></a>Paramétrez et exécutez le traitement pour appeler format d'exportation d'ER pour générer un état d'Excel

[!include [banner](../includes/banner.md)]

Après avoir créé votre format d’ER, l’avoir mappé à des sources de données, et l’avoir terminé, vous pouvez l’exécuter à partir de l’espace de travail **Gestion des états électroniques**. Une fois l'état généré, vous pouvez enregistrer localement.

Pour contrôler les aspects suivants du processus de gestion d’états, paramétrez le traitement par messagerie électronique :

- Enregistrez les informations sur l’utilisateur ayant généré l’état.
- Enregistrez les informations sur le moment de génération de l’état.
- Enregistrez les états générés pour les périodes précédentes.

L'exemple suivant indique comment paramétrer la messagerie électronique pour générer un état basé sur un format d’exportation ER pour Microsoft Excel. Si vous souhaitez suivre cet exemple, le format d’exportation Excel des états électroniques doit déjà être créé, mappé sur des sources de données, et être terminé. En outre, une souche de numéros doit déjà être paramétrée pour les messages électroniques.

Lorsque vous créez le traitement, il est utile de commencer par définir les actions et les statuts de traitement à paramétrer. L’illustration suivante présente à quoi ce traitement ressemble pour cet exemple.

![Schéma du traitement](media/processing-scheme.png)

## <a name="create-message-statuses"></a>Créer des statuts de message

1. Accédez à **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Statuts de message**.
2. Créez les statuts de message suivants :

    - Nouveau
    - Préparé
    - Généré

    ![Statuts du message](media/message-statuses.png)

3. Sur la ligne du statut **Nouveau**, activez la case à cocher **Autoriser la suppression** pour permettre aux utilisateurs de supprimer les messages avec ce statut.

## <a name="create-additional-fields"></a>Créer des champs supplémentaires

1. Accédez à **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Champs supplémentaires**.
2. Ajouter un champ supplémentaire et ses valeurs.
3. Définissez l’option **Modification utilisateur** sur **Oui** de permettre aux utilisateurs de modifier le champ.

![Champs supplémentaires](media/additional-fields.png)

## <a name="create-message-processing-actions"></a>Créer des actions de traitement des messages

Pour cet exemple, vous allez créer les actions de traitement des messages suivantes :

- **Créer un message**
- **Mettre à jour sur Préparé**
- **Générer un état**
- **Mettre à jour sur le statut initial** (facultatif)

Pour créer les actions, procédez comme suit.

1. Accédez à **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Actions de traitement du message**.
2. Créez une action nommée **Créer un message**. Sur l’organisateur **Général**, dans le champ **Type d’action**, sélectionnez **Créer un message**.
3. Créez une action nommée **Mettre à jour sur Préparé**, puis définissez les champs suivants :

    - Sur l’organisateur **Général**, dans le champ **Type d’action**, sélectionnez **Traitement utilisateur au niveau du message**.
    - Sur l’organisateur **Statuts initiaux**, dans le champ **Statut du message**, sélectionnez **Nouveau**.
    - Sur l’organisateur **Statuts de résultat**, dans le champ **Statut du message**, sélectionnez **Préparé**. Dans le champ **Type de réponse**, entrez **Exécution réussie**.

4. Créez une action nommée **Générer un état**, puis définissez les champs suivants :

    - Sur l’organisateur **Général**, dans le champ **Type d’action**, sélectionnez **Exportation de la gestion des états électroniques**. Dans le champ **Mise en correspondance des formats**, sélectionnez le format d’exportation ER. Les options sont **Excel**, **XML**, **JSON**, **Texte**, et **Autre**.
    - Sur l’organisateur **Statuts initiaux**, dans le champ **Statut du message**, sélectionnez **Préparé**.
    - Sur l’organisateur **Statuts de résultat**, dans le champ **Statut du message**, sélectionnez **Généré**. Dans le champ **Type de réponse**, entrez **Exécution réussie**.

    ![Générer une action d’état](media/generate-report-action.png)

5. Facultatif : Pour permettre aux utilisateurs de regénérer un état plusieurs fois, créez une action nommée **Mettre à jour sur le statut initial** et définissez les champs suivants :

    - Sur l’organisateur **Général**, dans le champ **Type d’action**, sélectionnez **Traitement utilisateur au niveau du message**.
    - Sur l’organisateur **Statuts initiaux**, dans le champ **Statut du message**, sélectionnez **Généré**.
    - Dans l’organisateur **Statuts de résultat**, ajoutez une ligne distincte pour les deux statuts de message (**Préparé** et **Nouveau**). Pour les deux lignes, définissez le champ **Type de réponse** sur **Avec succès**.

## <a name="electronic-message-processing"></a>Traitement du message électronique

Pour cet exemple, toutes les actions doivent être paramétrées de manière à ce que elles s’exécutent séparément. On suppose que chaque action est lancée par l’utilisateur.

1. Accédez à **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Traitement du message électronique**.
2. Ajoutez un enregistrement pour votre traitement, puis ajoutez toutes les actions définies précédemment et un champ supplémentaire.
3. Facultatif : dans l’organisateur **Rôles de sécurité**, définissez des rôles de sécurité pour votre traitement afin de limiter l’accès à l’état spécifique.
4. Accédez à **Taxe** \> **Recherches et états** \> **Messages électroniques** \> **Messages électroniques**.
5. Sélectionnez **Nouveau** pour créer un message. À ce stade, vous pouvez ajouter des dates et une description. Vous pouvez également mettre à jour la valeur du champ supplémentaire au besoin.

    ![Créer un message électronique](media/create-electronic-message.png)

    La grille sur l’organisateur **Journal des actions** est renseignée automatiquement avec un journal de toutes les actions effectuées sur le message.

    Vous pouvez désormais supprimer ou mettre à jour le statut du message. 

6. Pour mettre à jour le statut de message, sélectionnez **Mettre à jour le statut**. Dans le champ **Nouveau statut**, sélectionnez **Préparé**, puis sélectionnez **Ajouter**.

    ![Mettre à jour le statut du message](media/update-status.png)

    L'état du message est mis à jour sur **Préparé**.

7. Générez l'état en sélectionnant **Générer l'état**.

    L’état est généré, et le statut du message et le journal des actions sont mis à jour.

8. Pour afficher l’état généré, sélectionnez le bouton **Pièce jointe** (le symbole du trombone) dans le coin supérieur droit de la page.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
