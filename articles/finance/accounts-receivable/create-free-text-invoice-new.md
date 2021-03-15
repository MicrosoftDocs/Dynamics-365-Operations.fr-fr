---
title: Créer une facture financière
description: Cette rubrique explique comment créer des factures financières.
author: mikefalkner
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 726d4979059417871a00626c55da32fa4286cb53
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991115"
---
# <a name="create-a-free-text-invoice"></a>Créer une facture financière

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment créer des factures financières. Pour la procédure, utilisez la société fictive **USMF**.

## <a name="create-a-free-text-invoice"></a>Créer une facture financière

1. Allez dans **Comptabilité client (ou Registre des ventes) \> Factures \> Toutes factures financières**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Compte client**, sélectionnez une valeur.

    * Par défaut, le compte sélectionné comme compte client est utilisé comme compte de facturation.
    * Si la facture n’est pas validée, le statut comptable commence par **En cours**.
    * Le numéro de facture sera affecté lors de la validation de la facture.
    * Si vous utilisez des mandats SEPA (Espace unique de paiement en euros), le mandat de débit direct est automatiquement entré lorsque vous sélectionnez le compte client.

4. Dans le champ **Description**, entrez une valeur.
5. Dans le champ **Compte principal**, spécifiez un numéro de compte sans dimensions. Vous entrerez des dimensions plus loin dans cette rubrique.

    Vous pouvez également entrer un ou plusieurs caractères pour le compte principal et utiliser la fonction de recherche pour trouver le compte.

6. Sélectionnez l’organisateur **Détails de ligne** pour ajouter des dimensions au compte principal.
7. Sélectionnez l’onglet **Ligne de dimension financière**.

    * Les dimensions concernent la ligne sélectionnée uniquement.
    * Le groupe de taxe est renseigné à partir du client. Si le client n’a pas de groupe de taxe, celui du compte principal est utilisé.
    * Le groupe de taxe d’article est renseigné à partir du compte principal. Si le compte principal n’a pas de groupe de taxe d’article, celui spécifié dans les paramètres de taxe du module Comptabilité est utilisé.

8. Facultatif : dans le champ **Quantité**, entrez un nombre.
9. Facultatif : dans le champ **Prix unitaire**, entrez un nombre.

    Le montant est calculé comme suit : quantité multipliée par prix unitaire. Toutefois, vous pouvez remplacer ce calcul en entrant un montant.

10. Sélectionnez **Taxe** pour afficher la taxe calculée pour la facture.

    Vous pouvez afficher les montants de taxe sur cette page ou remplacer les montants sous l’onglet **Ajustement**.

11. Sélectionnez **OK**.
12. Sélectionnez **Frais** pour ajouter des frais à la facture.
13. Dans le champ **Code frais**, entrez une valeur.
14. Dans le champ **Valeur des frais**, entrez un nombre.
15. Fermez la page.
16. Sélectionnez **Totaux** pour afficher un résumé des détails et des totaux de la facture.
17. Sélectionnez **Fermer**.
18. Sélectionnez **Valider** pour valider la facture. Vous aurez toujours la possibilité d’annuler l’opération avant de la valider réellement.

    * Vous pouvez modifier l’échéance d’impression de la facture. Sélectionnez **Actuel** pour imprimer chaque facture dès qu’elle est mise à jour. Sélectionnez **Après** pour imprimer toutes les factures une fois qu’elles ont été mises à jour.
    * Pour modifier la façon dont la limite de crédit du client est vérifiée avant la validation de la facture, modifiez la valeur dans le champ **Type de limite de crédit**.
    * Pour imprimer la facture, définissez l’option sur **Oui**.
    * Pour valider la facture, définissez l’option sur **Oui**. Vous pouvez imprimer la facture sans la valider.

19. Sélectionnez **OK**.

## <a name="copy-lines"></a>Copier lignes
Pour copier des lignes d’une facture financière, sélectionnez une ou plusieurs lignes, puis sélectionnez **Copier les lignes sélectionnées**. Vous pouvez spécifier le nombre de copies à effectuer, et vous pouvez également copier des notes et des pièces jointes. Vous pouvez copier les répartitions ou les recréer lors de la validation.

Après avoir copié des lignes, vous pouvez modifier les informations si nécessaire.

## <a name="create-a-free-text-invoice-from-a-template"></a>Créer une facture financière à partir d’un modèle
Vous pouvez créer une facture financière à partir d’un modèle. Lorsque vous sélectionnez **Nouveau à partir d’un modèle** sous l’onglet **Facture**, vous pouvez sélectionner un nom de modèle et le compte client pour la nouvelle facture financière. Les valeurs par défaut telles que les conditions de paiement et le mode de paiement peuvent être automatiquement renseignées à partir du client, ou vous pouvez utiliser les valeurs enregistrées dans le modèle.

Une facture financière est créée et vous pouvez modifier les valeurs si nécessaire.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]