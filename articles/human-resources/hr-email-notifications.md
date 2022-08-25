---
title: Notification d'avantages par e-mail
description: Cet article fournit une vue d’ensemble de la caractéristique de notification par e-mail de gestion des avantages dans Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/01/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d550cbb2f639535dbb43765c9fb0632a514fbe8c
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229911"
---
# <a name="benefits-email-notification"></a>Notification d'avantages par e-mail

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [banner](../includes/preview-banner.md)]

La caractéristique de notification par e-mail permet d’envoyer des notifications et des rappels par e-mail aux employés dans les scénarios suivants :

- Inscription du nouvel employé
- Inscription en cours
- Événements de vie admissibles

Vous pouvez créer et définir plusieurs modèles d’e-mail et envoyer les notifications à l’aide de la page **Gestion des avantages** et **Avantages Worker** . Vous pouvez également suivre l’historique des notifications/rappels.

## <a name="set-up-human-resources-shared-parameters"></a>Définir les paramètres partagés de ressources humaines

Sur la page **Paramètres partagés des ressources humaines**, vous pouvez créer des modèles d’e-mail d’avantage pour différents types de communication qui sont envoyés aux employés ou aux groupes d’employés.

## <a name="create-a-new-email-id-template"></a>Créer un nouveau modèle d'identifiant e-mail

Pour créer un nouveau modèle d’identifiant e-mail, suivez ces étapes.

1. Accédez à **Modèles d'e-mail du système**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Identifiant d'e-mail**, entrez un nom.
4. Définissez les autres champs selon vos besoins.
5. Sélectionnez **Message électronique** pour télécharger le modèle.
6. Sur la page **Paramètres partagés des ressources humaines**, sélectionnez le nouveau modèle sous **Modèles de système**, et déplacez-le sous **Modèles d’avantages**.

## <a name="send-email-to-employees"></a>Envoyer un e-mail à des employés

Pour envoyer un e-mail à un nouvel employé qui n’a pas encore commencé, suivez ces étapes.

1. Ouvrez l’espace de travail **Gestion des avantages** .
2. Sélectionnez la vignette du groupe d’employés auquel vous souhaitez envoyer l’e-mail.
3. Sélectionnez **Envoyer un e-mail**.
4. Sélectionnez les employés auxquels vous souhaitez envoyer l’e-mail.
5. Sélectionnez **Envoyer un e-mail**.
6. Sélectionnez le modèle que vous désirez utiliser.
7. Sélectionnez **OK** pour envoyer l'e-mail.

    Vous pouvez consulter le message électronique et le statut de la page **Avantage Worker** de l’employé ou en sélectionnant **Historique des e-mails des avantages** dans la section **Liens** de l'espace de travail de la **Gestion des avantages**. Vous pouvez également envoyer l’e-mail à partir de la page **Plan d’avantages Worker** .

8. Pour afficher l’historique des e-mails relatifs aux avantages, dans l'espace de travail **Gestion des avantages**, dans la section **Liens**, sélectionnez **Historique des e-mails relatifs aux avantages**.
9. Afficher l’historique complet des e-mails pour les e-mails relatifs aux avantages qui ont été envoyés. Pour revoir le contenu de l’e-mail, sélectionnez **Voir le message**.
10. Sélectionnez **Worker**.
11. Sur la page **Plan des avantages Worker**, vous pouvez envoyer des e-mails et afficher l’historique des e-mails relatifs aux avantages.

L'espace de travail **Gestion des avantages** comprend différentes vignettes. Vous pouvez envoyer des e-mails en sélectionnant le modèle associé. Si les e-mails d’inscription des nouveaux employés ont été envoyés, sélectionnez la vignette **Nouvelle embauche non commencée**, et ensuite sélectionnez le lien **Envoyer un rappel**. Vous pouvez sélectionner un modèle de rappel et définir le titre de la notification comme un premier, deuxième ou troisième rappel.
