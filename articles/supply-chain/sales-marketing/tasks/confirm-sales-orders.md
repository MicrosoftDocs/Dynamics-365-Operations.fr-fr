---
title: Confirmer les commandes client
description: Cette procédure illustre comment confirmer des commandes client.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, CustConfirmJournal, SysQueryForm, SysQueryFieldLookUp, SysLookup, SalesParmIdLookup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db475cf967bebec2d442aaa864800d920cf0ab81
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "323983"
---
# <a name="confirm-sales-orders"></a>Confirmer les commandes client

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure illustre comment confirmer des commandes client. Vous découvrirez comment confirmer une seule commande et comment confirmer plusieurs commandes à la fois. Ces tâches sont généralement effectuées par un préparateur de commandes client. Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Avant de commencer, assurez-vous qu'il existe plusieurs commandes client en cours pour le même client. Si vous utilisez USMF, vous pouvez utiliser le client US-027.


## <a name="confirm-a-single-sales-order"></a>Confirmer une seule commande client
1. Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.
2. Dans la liste, localisez et sélectionnez la commande que vous voulez confirmer.
3. Cliquez sur le lien sur le numéro de commande client pour ouvrir la commande sélectionnée.
4. Cliquez sur Vendre dans le volet Actions.
5. Cliquez sur Confirmer la commande client.
6. Développez ou réduisez la section Paramètres.
    * Veillez à ce que le champ Validation Oui soit actif.  
7. Définissez l'option Impression de la confirmation sur Oui.
    * Le champ Vérifier la limite de crédit, spécifie la méthode utilisée pour calculer le crédit restant d'un client. Par défaut, il est copié à partir de la page Paramètres de la comptabilité client. Si vous souhaitez ignorer la vérification de la limite de crédit lors de la confirmation d'une commande client spécifique, définissez la limite de crédit de chèque sur Aucune. Toutefois, vous devez être conscient que même avec ce champ est défini sur Aucune, la vérification de la limite de crédit est toujours effectuée si l'option Limite de crédit obligatoire est activée dans les données principales du client.  
8. Cliquez sur OK.
9. Cliquez sur Oui.
10. Fermez la page.
11. Dans le volet Actions, cliquez sur Options.
12. Cliquez sur Changer de vue.
13. Cliquez sur Vue de l'en-tête.
    * Lorsqu'une commande est confirmée, le statut du document est défini sur Confirmation.  
14. Cliquez sur Vendre dans le volet Actions.
15. Cliquez sur Confirmation de commande client.
16. Fermez la page.

## <a name="confirm-multiple-sales-orders-at-once"></a>Confirmer plusieurs commandes client simultanément
1. Accédez à Ventes et marketing > Commandes client > Confirmation de commande > Confirmer la commande client.
2. Cliquez sur Sélectionner.
3. Dans la liste de l'onglet Plage, localisez et sélectionnez l'enregistrement qui fait référence au champ Compte client.
4. Dans le champ Critères, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, localisez et sélectionnez le compte client qui a plusieurs commandes que vous souhaitez confirmer simultanément.
    * Si vous utilisez USMF, vous pouvez sélectionner le compte US-027.  
6. Cliquez sur OK.
    * L'onglet Vue d'ensemble affiche la liste des commandes qui correspondent aux critères de requête. Ceux-ci sont inclus dans la confirmation.  
    * Le champ Mise à jour récapitulative pour spécifie le paramètre par lequel plusieurs commandes doivent être synthétisées dans un document de confirmation. Par défaut, l'option est copiée à partir des valeurs par défaut pour le paramètre de mise à jour récapitulative sur la page Paramètres de la comptabilité client.  
7. Dans le champ Mise à jour récapitulative, sélectionnez « Commande ».
    * Les paramètres minimaux requis pour créer des mises à jour récapitulatives sont Compte de facturation et Devise. Cela signifie que les mises à jour récapitulatives présentant des comptes de facturation et des devises différents ne sont pas autorisées. Les paramètres supplémentaires peuvent être paramétrées dans la page Paramètres de mise à jour récapitulative qui est accessible à partir de la page Paramètres de la comptabilité client.  
8. Dans le champ Commande client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, sélectionnez le numéro de la commande qui servira de commande récapitulative.
10. Cliquez sur Organiser.
11. Cliquez sur OK.
12. Cliquez sur OK.

