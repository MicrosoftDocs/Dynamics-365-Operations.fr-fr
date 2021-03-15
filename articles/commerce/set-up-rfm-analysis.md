---
title: Paramétrer l'analyse RFM (récence, fréquence et valeur monétaire)
description: Cette rubrique décrit comment paramétrer une analyse RFM (récence, fréquence et valeur monétaire) de vos clients.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRRFMDefinition
audience: Application User
ms.reviewer: josaw
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 7a216b237052e084e7efac2580bf5ff9846d3127
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985664"
---
# <a name="set-up-recency-frequency-and-monetary-rfm-analysis"></a>Paramétrer l'analyse RFM (récence, fréquence et valeur monétaire)

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment paramétrer une analyse RFM (récence, fréquence et valeur monétaire) de vos clients.

L'analyse RFM (récence, fréquence et valeur monétaire) est un outil marketing que votre organisation peut utiliser pour évaluer les données générées par les achats client. Après avoir paramétré l'analyse RFM, les clients se voient attribuer un score RFM calculé lorsqu'ils effectuent des achats. Le score RFM peut être une évaluation à trois chiffres ou un nombre entier, selon la façon dont votre organisation a configuré l'analyse RFM. Voici comment l'évaluation fonctionne si votre organisation utilise une évaluation à trois chiffres du score :

- Le premier chiffre est l'évaluation de la récence du client (si le client a récemment effectué un achat dans votre organisation).
- Le deuxième chiffre est une évaluation de la fréquence du client (fréquence à laquelle le client effectue des achats auprès de votre organisation).
- Le troisième chiffre est une évaluation de la valeur monétaire du client (montant que le client dépense lorsqu'il effectue des achats auprès de votre organisation).

Par exemple, votre organisation a défini les évaluations sur une échelle de 1 à 5, dans laquelle 5 correspond au classement le plus élevé. Dans ce cas, une notation client de 535 vous indique les informations suivantes sur le client :

- **Score de récence de 5** – Le client a récemment effectué un achat.
- **Score de fréquence de 3** – Le client achète des produits à votre organisation à une fréquence modérée.
- **Score monétaire de 5** – Lorsque le client effectue un achat, il dépense une quantité importante d'argent.

Si votre organisation utilise un nombre entier pour le score, les classements individuels sont additionnés. Pour le même exemple, le client a un score de 13 (5 + 3 + 5).

## <a name="set-up-rfm-analysis-for-the-customers-in-your-organization"></a>Paramétrer l'analyse RFM pour les clients de votre organisation

1. Accédez à **Centre d'appels** \> **Périodique** \> **Analyse RFM**.
2. Sur la page **Analyse RFM**, sélectionnez **Nouveau**. Dans le champ **Définition FRM**, entrez un nom pour la définition RFM. Par exemple, vous pouvez appeler la définition RFM-A.
3. Entrez les dates de début et de fin de cette définition RFM.
4. Dans l'organisateur **Général**, procédez comme suit :

    - Si chaque section du score RFM doit contenir un nombre égal de clients, activez la case à cocher **Distribution égale**.
    - Activez la case à cocher **Ajouter des scores** pour additionner les trois scores. Par exemple, le client aurait un score RFM de 13 au lieu de 535.
    - Activez la case à cocher **Enregistrer l'historique** pour exiger que le système enregistre les données statistiques des clients afin que les données puissent être utilisées pour calculer le score RFM.

5. Dans l'organisateur **Récence**, procédez comme suit :

    - Dans le champ **Dvisions**, entrez le nombre de divisions ou de groupes qui seront utilisés pour calculer le score de récence des clients. Par exemple, si vous avez 100 clients, une division de 5 signifie qu'il y a 20 clients pour chaque score. Les 20 clients qui ont effectué des achats le plus récemment ont un score de récence de 5. Les 20 clients suivants ont un score de récence de 4, etc. Si vous avez 50 clients, 10 clients ont un score de récence de 5, 10 ont un score de récence de 4, etc.
    - Dans le champ **Priorité**, sélectionnez l'importance du paramètre de récence par rapport aux autres paramètres lorsque le score RFM est calculé pour un client. Par exemple, vous pouvez accorder plus d'importance au score de récence qu'au score monétaire.
    - Dans le champ **Multiplicateur**, entrez la valeur par laquelle multiplier le score de récence. Si vous n'entrez pas de valeur, le score ne sera pas multiplié.
    - Dans le champ **Période**, sélectionnez la période pendant laquelle le score de récence est calculé. Par exemple, par semaine ou par mois.

6. Dans l'organisateur **Fréquence**, procédez comme suit :

    - Dans le champ **Divisions**, entrez le nombre de divisions ou de groupes qui seront utilisés pour calculer le score de fréquence des clients.
    - Dans le champ **Priorité**, sélectionnez l'importance du paramètre de fréquence par rapport aux autres paramètres lorsque le score RFM est calculé pour un client.
    - Dans le champ **Multiplicateur**, entrez la valeur par laquelle multiplier le score de fréquence. Si vous n'entrez pas de valeur, le score ne sera pas multiplié.

7. Dans l'organisateur **Monétaire**, procédez comme suit :

    - Dans le champ **Divisions**, entrez le nombre de divisions ou de groupes qui seront utilisés pour calculer le score monétaire des clients.
    - Dans le champ **Priorité**, sélectionnez l'importance du paramètre monétaire par rapport aux autres paramètres lorsque le score RFM est calculé pour un client.
    - Dans le champ **Multiplicateur**, entrez la valeur par laquelle multiplier le score monétaire. Si vous n'entrez pas de valeur, le score ne sera pas multiplié.
    - Dans le champ **Brut/net**, indiquez si le score monétaire du client doit être calculé à l'aide du montant net ou brut des factures.
    - Si les montants des retours client doivent être soustraits du calcul du total des factures du client, activez la case à cocher **Soustraire les retours**.

## <a name="view-a-customers-rfm-score"></a>Affichage du score RFM d'un client

Suivez cette procédure pour afficher le score RFM d'un client.

1. Accédez à **Centre d'appels** \> **Journaux** \> **Service client**.
2. Sur la page **Service client**, dans le volet **Service client**, dans les champs de recherche, sélectionnez le type de mot clé de recherche et entrez le texte de recherche.
3. Sélectionnez **Rechercher**.
4. Sur la page **Recherche du client**, sélectionnez l'enregistrement client souhaité, puis cliquez sur **Sélectionner le client**.

Le score RFM s'affiche dans le groupe **Historique des commandes** à droite de la page **Service client**.

## <a name="view-or-clear-the-history-of-an-rfm-analysis-record"></a>Affichage ou suppression de l'historique d'un enregistrement d'analyse RFM

Cette procédure permet d'afficher ou de supprimer l'historique d'un enregistrement d'analyse RFM.

1. Accédez à **Centre d'appels** \> **Périodique** \> **Analyse RFM**.
2. Sur la page **Analyse RFM**, sélectionnez l'enregistrement à afficher.
3. Pour afficher l'historique de l'enregistrement, sélectionnez l'organisateur **Historique**.
4. Pour effacer l'historique de l'enregistrement, sélectionnez **Effacer l'historique**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]