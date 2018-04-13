--- 
title: Entrer et comparer des appels d'offre et octroyer des contrats
description: "Cette procédure décrit comment entrer des réponses à un appel d'offre, marquer et comparer les offres, puis attribuer une offre à l'un des fournisseurs."
author: mkirknel
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5dea9d7bfb1bf7b11f6c49cccaab1b73d4e58d16
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Entrer et comparer des appels d'offre et octroyer des contrats

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment entrer des réponses à un appel d'offre, marquer et comparer les offres, puis attribuer une offre à l'un des fournisseurs. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF. Avant de commencer, vous devez avoir un appel d'offre avec deux lignes qui a été envoyé au moins à deux fournisseurs. Vous pouvez exécuter la procédure « Création d'une demande de devis » comme étape préliminaire pour créer cela. Vous devez avoir paramétré les critères d'attribution de score pour pouvoir exécuter cette procédure.


## <a name="enter-a-reply-from-a-vendor"></a>Entrer la réponse d'un fournisseur
1. Accédez à Approvisionnements > Demandes de devis > Toutes les demandes de devis
2. Sélectionnez un appel d'offre ayant le statut Envoyé, puis cliquez sur le lien sur le numéro de dossier de l'appel d'offre.
    * L'appel d'offre aurait dû être envoyé à au moins à 2 fournisseurs.  
3. Cliquez sur l'en-tête pour accéder à la liste des fournisseurs.
4. Sélectionnez le fournisseur pour lequel vous souhaitez entrer une réponse dans l'appel d'offre.
5. Cliquez sur Entrer une réponse.
6. Cliquez sur Répondre dans le volet Actions.
7. Cliquez sur Copier des données dans la réponse.
    * Cette action copiera les données sélectionnées, par exemple, la quantité du dossier d'appel d'offre est copiée dans la réponse d'appel d'offre. Vous pouvez également ignorer cette action et remplir tous les champs manuellement lorsque vous modifiez la réponse.  
8. Cliquez sur Modifier.
9. Entrez un nombre dans le champ Prix unitaire.
10. Choisissez l'autre ligne de devis.
11. Entrez un nombre dans le champ Prix unitaire.

## <a name="score-the-bid"></a>Attribuer un score à l'offre
1. Cliquez sur l'en-tête pour accéder à l'attribution de score de l'offre.
2. Développez la section Attribution de score de l'offre.
3. Entrez un nombre pour l'un des critères d'attribution de score dans le champ Score.
    * Si vous passez la souris sur l'un des critères d'attribution de score, une info-bulle indique la plage dans laquelle vous devez marquer les points. Dans cette démonstration vous pouvez ajouter un nombre compris entre 1 et 5 à n'importe lequel des critères.  
4. Sélectionnez un autre critère d'attribution de score.
5. Entrez un nombre dans le champ Score.
6. Développez la section Questionnaires.
    * Si l'appel d'offre a un questionnaire qui a été soumis aux fournisseurs, vous pouvez entrer leurs réponses dans la section questionnaire.  
7. Fermez la page.

## <a name="enter-a-reply-for-another-vendor"></a>Entrer une réponse pour un autre fournisseur
1. Sélectionnez le fournisseur suivant en désactivant le fournisseur pour lequel vous venez d'entrer la réponse, puis en sélectionnant la ligne du fournisseur suivant.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Cliquez sur Entrer une réponse.
4. Cliquez sur Copier des données dans la réponse.
5. Cliquez sur Modifier.
6. Entrez un nombre dans le champ Prix unitaire.
7. Choisissez l'autre ligne de devis.
8. Entrez un nombre dans le champ Prix unitaire.

## <a name="score-the-second-bid"></a>Attribuer un score à la deuxième offre
1. Cliquez sur l'en-tête pour accéder à l'attribution de score de l'offre.
2. Entrez un nombre dans le champ Score.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Entrez un nombre dans le champ Score.

## <a name="compare-the-replies"></a>Comparer les réponses
1. Cliquez sur Général dans le volet Actions.
2. Cliquez sur Comparer les réponses.
3. Entrez un nombre dans le champ Rang.
    * Cette page affiche les offres avec l'en-tête et les lignes, et le score total au niveau de l'en-tête. Vous pouvez comparer les lignes en effectuant un tri dans la grille afin que les lignes comparables soient les unes à côté des autres. Les informations incluent également : Quantité : Quantité faisant l'objet d'un devis d'un fournisseur. Celle-ci peut ne pas être égale à la quantité indiquée dans l'appel d'offre.   Montant HT : Prix du devis d'un fournisseur, après soustraction de toutes les remises pour les articles de la ligne.   Écart : Nombre de jours d'écart entre la date de livraison de l'en-tête ou la ligne de l'offre et la date de livraison de l'en-tête ou la ligne de l'appel d'offre.   Vous pouvez entrer un classement pour chaque offre.  
4. Sélectionnez la ligne d'en-tête de l'autre offre que vous souhaitez classer.
5. Entrez un nombre dans le champ Rang.
6. Cliquez sur Enregistrer.

## <a name="reject-a-bid"></a>Rejeter une offre
1. Sélectionnez la ligne d'en-tête de l'autre offre que vous souhaitez rejeter.
    * Vous pouvez uniquement accepter, rejeter ou retourner une offre ou des lignes d'une offre à la fois.  
2. Cochez la case Marquer.
    * Si vous activez la case à cocher Marquer dans l'en-tête de l'offre, toutes les lignes sont également marquées. Vous pouvez également choisir de marquer un sous-ensemble des lignes dans l'offre pour les refuser ou les recevoir. Il est possible d'accepter l'offre d'un fournisseur pour certaines lignes d'un appel d'offre, puis d'attribuer d'autres lignes d'appel d'offre à un autre fournisseur, toutefois, vous devez procéder en 2 étapes, une offre à la fois. Si d'autres lignes sont présentes, vous pouvez uniquement accepter la ligne d'offre d'origine ou sa remplaçante, mais pas les deux.  
3. Cliquez sur Rejeter.
4. Cliquez sur Paramètres pour ouvrir la boîte de dialogue.
5. Saisissez ou sélectionnez une valeur dans le champ Motif du refus.
    * Le motif du rejet sera stocké dans la réponse.  
6. Cliquez sur OK.
7. Cliquez sur OK.
8. Fermez la page.
9. Fermez la page.
10. Actualisez la page.

## <a name="accept-a-bid"></a>Accepter une offre
1. Sélectionnez l'offre à accepter, puis cliquez sur le lien dans le champ Appel d'offre.
2. Cliquez sur Répondre dans le volet Actions.
3. Cliquez sur Accepter.
    * Si vous avez marqué des lignes spécifiques et pas d'autres, l'action d'acceptation va inclure seulement les lignes marquées. Si vous souhaitez accepter toutes les lignes de l'offre, vous ne devez pas marquer de lignes.  
4. Cliquez sur Paramètres pour ouvrir la boîte de dialogue.
    * Cela vous permet d'enregistrer un motif d'acceptation de l'offre. Le motif sera stocké dans l'offre.  
5. Saisissez ou sélectionnez une valeur dans le champ Motif d'acceptation.
6. Cliquez sur OK.
7. Cliquez sur OK.
    * Lorsque vous cliquez sur OK, cela génère une commande fournisseur basée sur les lignes incluses dans l'acceptation d'appel d'offre. S'il existe d'autres offres qui n'ont pas été traitées (acceptées, rejetées ou retournées), alors le système vous invite à rejeter les offres restantes.  

## <a name="view-the-purchase-order-thats-been-generated"></a>Afficher la commande fournisseur générée
1. Cliquez sur Général dans le volet Actions.
2. Cliquez sur Commande fournisseur.
    * Ici vous pouvez voir la commande fournisseur générée lorsque vous avez accepté l'offre.  
3. Fermez la page.
4. Fermez la page.
5. Fermez la page.
6. Fermez la page.


