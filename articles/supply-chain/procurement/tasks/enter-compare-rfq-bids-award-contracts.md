---
title: Entrer et comparer des devis d'appels d'offre et octroyer des contrats
description: Cette rubrique explique comment entrer des réponses à un appel d'offre, marquer et comparer les offres, puis attribuer le contrat à l'un des fournisseurs.
author: RichardLuan
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchRFQCaseTable, PurchRFQReplyTable, PurchRFQCompare, PurchRFQEditLines, PurchRFQEditLinesParameters, PurchTable, PurchTablePart, PurchRFQCompareLinePrices, PurchRFQCompareRFQ
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f14b95a71397bf5879c97654620e1d4c22a1149
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016676"
---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Entrer et comparer des devis d'appels d'offre et octroyer des contrats

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment entrer des réponses à un appel d'offre, marquer et comparer les offres, puis attribuer le contrat à l'un des fournisseurs. Vous pouvez utiliser cette procédure dans les données fictives de la société **USMF**.

Avant de commencer cette procédure, vous devez avoir un appel d'offre avec deux lignes et qui a été envoyé au moins à deux fournisseurs. Pour créer cet appel d'offre, suivez la procédure [Créer un appel d'offre](create-request-quotation.md). Des critères d'attribution de score doivent également avoir été paramétrés pour pouvoir exécuter cette procédure.

Vous pouvez entrer l'offre comme fournisseur ou professionnel des approvisionnements. Pour plus d'informations, voir [Paramétrer et mettre à jour la collaboration fournisseur](../set-up-maintain-vendor-collaboration.md).

## <a name="enter-a-reply-as-a-vendor"></a>Entrer la réponse en tant que fournisseur

1. Sur le tableau de bord, sélectionnez **Offre du fournisseur**.
2. Dans la liste **Nouvelles invitations à une offre**, recherchez un appel d'offre qui vient juste d'être envoyé. Sélectionnez l'appel d'offre pour examiner ce qui a été demandé.
3. Sélectionnez **Pièces jointes à l'appel d'offre** pour examiner les pièces jointes ayant été ajoutées.
4. Sélectionnez **Offre** pour rendre les champs modifiables. Notez que le champ **Progression de l'offre** est défini sur **Le fournisseur effectue une mise à jour**.
5. Sur l'en-tête et les lignes, entrez les valeurs de la réponse à l'offre.
6. Si des pièces jointes doivent être ajoutées à l'offre, sélectionnez **Pièces jointes à l'offre**.
7. Sélectionnez l'organisateur **Instructions de soumission** pour afficher si des documents sont requis.
8. Sélectionnez l'organisateur **Avenants** pour afficher si l'appel d'offre a été modifié.
9. Sélectionnez l'organisateur **Questionnaire**. Tous les questionnaires qui apparaissent ici doivent être remplis.
10. Sélectionnez l'organisateur **Détails de la ligne** pour afficher des informations supplémentaires sur la ligne.
11. Sélectionnez **Réinitialiser à partir de l'appel d'offre** uniquement si vous devez réinitialisé les valeurs entrées dans les valeurs d'appel d'offre d'origine.
12. Vous pouvez enregistrer l'offre à tout moment et effectuer un traitement supplémentaire ultérieurement, avant que la date et l'heure d'expiration se soient écoulées. Dans ce cas, vous pouvez trouver l'offre dans la liste **Offres en cours** dans l'espace de travail **Offre du fournisseur**.
13. Lorsque l'offre est prête à être soumise, sélectionnez **Soumettre**. Si vous ne souhaitez pas faire d'offre, sélectionnez **Refuser**. Les offres envoyées sont disponibles dans la liste **Offres envoyées** de l'espace de travail **Offre du fournisseur**.  
14. Une fois l'offre soumise, vous pouvez la rappeler à tout moment avant la date et l'heure d'expiration. Notez que lorsqu'une offre est rappelée, elle n'est pas traitée comme soumise. Lorsque l'offre est acceptée ou refusée par département d'approvisionnement, elle apparaît dans **Offres attribuées** ou **Offres perdues** dans l'espace de travail **Offre du fournisseur**.  

## <a name="enter-a-reply-from-a-vendor-as-a-procurement-professional"></a>Entrer une réponse d'un fournisseur en tant professionnel de l'approvisionnement

1. Assurez-vous que l'autorisation de modifier les offres du fournisseur est paramétrée. Accédez à **Approvisionnements \> Paramétrage \> Paramètres d'approvisionnements**. Dans l'onglet **Appels d'offre**, définissez l'option **L'acheteur peut modifier l'offre des fournisseurs** sur **Oui**.
2. Accédez à **Approvisionnements \> Appels d'offre \> Toutes les demandes de devis**.
3. Sélectionnez un appel d'offre ayant le statut **Envoyé**, puis sélectionnez le lien dans le champ **Dossier d'appel d'offre**.
4. Sélectionnez **Gérer les réponses**. La page qui apparaît présente un appel d'offre pour chaque fournisseur invité à faire une offre.
5. Sélectionnez un appel d'offre qui n'a pas reçu de réponse. (Le champ **Progression de la réponse** devrait être défini sur **Non commencé**.)
6. Sélectionnez **Modifier \> Modifier la réponse à l'appel d'offre**. La page **Modifier la réponse** s'affiche. En tant que professionnel des approvisionnements, vous pouvez désormais entrer la réponse au nom du fournisseur. Notez que le champ **Progression de l'offre** est défini sur **L'acheteur effectue une mise à jour**.  
7. Entrez les données de l'offre. Lorsque vous avez terminé, sélectionnez **Soumettre**.

## <a name="score-the-bids"></a>Attribuer un score aux offres

1. Dans la page **Toutes les demandes de devis**, sélectionnez le dossier d'appel d'offre auquel vous souhaitez attribuer des points pour les réponses.
2. Sélectionnez **Gérer les réponses**.
3. Sélectionnez la réponse à laquelle attribuer des points.
4. Sélectionnez **En-tête** afin de pouvoir afficher les points obtenus par l'offre.
5. Sur l'organisateur **Attribution de score de l'offre**, entrez un nombre dans le champ **Score** pour l'un des critères d'attribution de score. Si vous passez la souris sur l'un des critères d'attribution de score, une info-bulle indique la plage dans laquelle doit se trouver le score. Dans cette démonstration, vous pouvez entrer un nombre compris entre 1 et 5 à n'importe lequel des critères d'attribution de score.  
6. Répétez l'étape 5 pour un autre critère d'attribution de score.
7. Si le dossier d'appel d'offre a un questionnaire qui a été soumis aux fournisseurs, vous pouvez entrer leurs réponses sur l'organisateur **Questionnaires**.
8. Fermez la page.
9. Répétez les étapes 1 à 8 pour toutes les autres offres.

## <a name="compare-the-replies"></a>Comparer les réponses

1. Dans le volet Actions, sous l'onglet **Général**, sélectionnez **Comparer les réponses**.
2. Dans le champ **Rang**, entrez un nombre.  
    - Cette page affiche les offres avec les informations d'en-tête et de ligne, ainsi que le score total au niveau de l'en-tête. Vous pouvez comparer les lignes en effectuant un tri dans la grille afin que les lignes comparables soient les unes à côté des autres. Les informations suivantes sont également incluses :
    - **Quantité** – Quantité ayant fait l'objet du devis du fournisseur. Cette quantité peut ne pas être égale à la quantité indiquée dans l'appel d'offre.
    - **Montant net** – Prix du devis du fournisseur pour les articles de la ligne, après soustraction de toutes les remises.
    - **Écart** – Nombre de jours d'écart entre la date de livraison de l'en-tête ou la ligne de l'offre et la date de livraison de l'en-tête ou la ligne de l'appel d'offre. Vous pouvez entrer un classement pour chaque offre.  
3. Sélectionnez la ligne d'en-tête de l'autre offre que vous souhaitez classer.
4. Dans le champ **Rang**, entrez un nombre.
5. Sélectionnez **Enregistrer**.

## <a name="reject-a-bid"></a>Rejeter une offre

1. Sélectionnez la ligne d'en-tête de l'autre offre que vous souhaitez rejeter. Vous pouvez accepter, rejeter ou retourner uniquement une offre ou les lignes d'une offre à la fois.
2. Activez la case à cocher **Marquer**.  
    - Si vous activez la case à cocher **Marquer** dans l'en-tête de l'offre, toutes les lignes sont également marquées. Pour rejeter ou accepter uniquement certaines lignes sous l'offre, vous pouvez marquer juste ces lignes. De plus, vous pouvez accepter l'offre d'un fournisseur pour certaines lignes d'un appel d'offre, puis attribuer d'autres lignes d'appel d'offre à un autre fournisseur. Toutefois, vous devez effectuer une offre à la fois.  
    - Si d'autres lignes sont présentes, vous pouvez accepter la ligne d'offre d'origine ou sa remplaçante, mais pas les deux.  
3. Sélectionnez **Refuser**.
4. Sélectionnez **Paramètres**, puis, dans le champ **Motif du refus**, entrez ou sélectionnez le motif du refus de l'offre. Le motif est enregistré dans la réponse.  
5. Cliquez sur **OK**.
6. Cliquez sur **OK**.

## <a name="accept-a-bid"></a>Accepter une offre

1. Sélectionnez l'offre à accepter, puis le lien dans le champ **Appel d'offre**. Si vous êtes sur la page **Comparer les réponses aux appels d'offre**, l'offre en surbrillance est l'offre que le système prendra en compte pendant l'action Accepter. Vous pouvez accepter les lignes d'une seule offre à la fois.  
2. Dans le volet Actions, sélectionnez **Répondre**.
3. Sélectionner **Accepter**. Si vous avez marqué uniquement des lignes spécifiques, l'action Accepter inclut uniquement ces lignes. Si vous souhaitez accepter toutes les lignes de l'offre, vous n'avez pas besoin de marquer les lignes.  
4. Sélectionnez **Paramètres**, puis, dans le champ **Motif d'acceptation**, entrez ou sélectionnez le motif de l'acceptation de l'offre. Le motif est enregistré dans l'offre.  
5. Cliquez sur **OK**.
6. Cliquez sur **OK**. Lorsque vous sélectionnez **OK**, une commande fournisseur est générée sur la base sur les lignes incluses dans l'acceptation d'appel d'offre. S'il existe d'autres offres qui n'ont pas été traitées (acceptées, rejetées ou retournées), le système vous invite à les rejeter.  

## <a name="view-the-purchase-order-that-is-generated"></a>Afficher la commande fournisseur générée

Dans le volet Actions, sous l'onglet **Général**, sélectionnez **Commande fournisseur**. La page qui s'affiche indique la commande fournisseur générée lorsque vous avez accepté l'offre.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]