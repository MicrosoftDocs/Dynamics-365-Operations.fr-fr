---
title: Réponse aux questions des fournisseurs sur les appels d'offre
description: Les fournisseurs qui ont des questions sur un appel d'offre peuvent les soumettre et lire les réponses dans la page **Collaboration du fournisseur**.
author: velofog
manager: tfehr
ms.date: 01/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-alpavk
ms.search.validFrom: 2020-1-22
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 3aecd924ee47a0a722d0a62f6b96453011d94b87
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207822"
---
# <a name="responding-to-vendor-questions-on-request-for-quotations"></a>Réponse aux questions des fournisseurs sur les appels d'offre

[!include [banner](../includes/banner.md)]

Si votre agence a envoyé un appel d'offre, les fournisseurs ont parfois des questions concernant la demande. Les fournisseurs qui ont des questions sur un appel d'offre peuvent les soumettre et lire les réponses dans la page **Collaboration du fournisseur** si vous rendez cette page disponible. Si les questions des fournisseurs sont acceptées, **Questions et réponses** est disponible dans la page **Offre pour un appel d'offre** sur **Collaboration du fournisseur** et pour votre agence via la page **Appel d'offre**, **Questions et réponses**. 

Les utilisateurs peuvent publier plusieurs fois les réponses aux questions des fournisseurs. Les fournisseurs ne peuvent plus publier les questions après la sélection d'un fournisseur et l'attribution de l'appel d'offre ou si la date limite pour les questions est atteinte.

## <a name="setting-up-for-vendor-questions"></a>Configuration pour les questions des fournisseurs
Lors de la création d'un appel d'offre, vous déterminez si les fournisseurs peuvent poser des questions sur l'appel d'offre.
1. Accédez à **Approvisionnements > Appels d'offre**, puis cliquez sur **Nouveau > Appel d'offre**. 
2. Dans la page **Nouvel appel d'offre**, **En-tête** pour définir les champs **Options des questions des fournisseurs** pour autoriser les questions avant une certaine date.
- Définissez l'option **Autoriser la question du fournisseur** sur **Oui** pour que les fournisseurs puissent saisir des questions. Les utilisateurs peuvent saisir et répondre aux questions et désigner les questions fréquemment posées à publier pour les fournisseurs lorsque l'appel d'offre est envoyé aux fournisseurs.
3. Facultatif : dans le champ **Date limite**, définissez la date de fin de soumission des questions. Si aucune date limite n'est saisie, les questions sont acceptées tant que l'appel d'offre est ouvert et accepte les offres.
4. Cliquez sur **Enregistrer** pour enregistrer l'appel d'offre.
5. Cliquez sur **Envoyer** pour envoyer l'appel d'offre aux fournisseurs.

## <a name="entering-and-replying-to-vendor-questions"></a>Saisie et réponse aux questions des fournisseurs
Les fournisseurs saisissez des questions dans la page **Collaboration du fournisseur > Offre d'appel d'offre**, organisateur **Questions du fournisseur**. Seuls le fournisseur et les utilisateurs affichent la question.

## <a name="entering-a-vendor-question"></a>Saisie d'une question de fournisseur
1. Dans la collaboration du fournisseur, à la page **Offre d'appel d'offre**, cliquez sur **Questions et réponses**, puis cliquez sur **+ Poser une question**.

[Remarque !] Sinon, un utilisateur peut saisir les questions pour un fournisseur sur la page **Appel d'offre** en cliquant sur **Gérer les réponses**, **Modifier la réponse à l'appel d'offres**, puis en cliquant sur **Questions et réponses**.

2. Sur le champ **Question**, saisissez le texte de la question.
3. Cliquez sur **Soumettre**. Répétez les étapes 1 à 3 pour ajouter une question.
4. Une fois terminé, cliquez sur **Enregistrer** pour enregistrer vos questions.

## <a name="replying-to-a-single-vendor"></a>Répondre à un seul fournisseur
Seuls le fournisseur et les utilisateurs affichent la question et la réponse.
1. Dans la page **Appel d'offre**, cliquez sur **Questions et réponses** pour afficher la page **Questions et réponses**.
2. Cliquez sur **Modifier**
1. Saisissez le texte dans le champ **Réponse** pour répondre à la question du vendeur.
2. Cochez la case **Réponse directe**.
3. Cliquez sur **Enregistrer** pour enregistrer vos réponses.
4. Cliquez sur **Envoyer les réponses** pour envoyer les réponses au fournisseur.

## <a name="replying-to-all-vendors"></a>Répondre à tous les fournisseurs
Si vous recevez la même question de plusieurs fournisseurs, vous pouvez regrouper les questions et répondre en une seule fois. Tous les fournisseurs reçoivent une notification lorsque les questions fréquemment posées et les réponses sont publiées. Les fournisseurs et toute personne ayant accès à l'appel d'offre peuvent consulter le résumé des questions et des réponses.

1. Dans la page **Appel d'offre**, cliquez sur **Questions et réponses** pour afficher la page **Questions et réponses**.
2. Cliquez sur **Modifier**.
3. Choisissez un code pour la question courante, comme la lettre « a ».
4. Pour chaque ligne qui pose une question similaire, saisissez le code dans le champ **Code du groupe**. Par exemple, pour chaque ligne demandant la couleur de l'article, saisissez « a ».
5. Choisissez l'une des lignes avec la valeur de code, puis saisissez la question et répondez comme vous le souhaitez dans le résumé disponible dès la publication des questions et des réponses (champs **Question du groupe, Réponse du groupe**).
6. Facultatif : vous pouvez cochez la case **Réponse directe** pour envoyer les réponses uniquement aux fournisseurs sélectionnés.
7. Cliquez sur **Enregistrer** pour enregistrer vos réponses.
8. Facultatif : vous pouvez rétablir les questions et réponses aux valeurs publiées précédemment si vous voulez annuler vos modifications.
9. Cliquez sur **Envoyer les réponses** pour envoyer les réponses aux fournisseurs.

## <a name="changing-rfq-to-allow-or-disallow-questions"></a>Modification de l'appel d'offre pour autoriser ou interdire les questions
Vous pouvez apporter des modifications pour autoriser ou interdire les questions aux appels d'offres jusqu'à ce que l'appel d'offres soit attribué. Vous pouvez également prolonger ou raccourcir le délai dans lequel les fournisseurs peuvent soumettre des questions.
Pour les appels d'offres publiés, vous devez modifier un appel d'offre pour autoriser ou interdire les questions des fournisseurs, ou ajuster le délai pour les questions. 
