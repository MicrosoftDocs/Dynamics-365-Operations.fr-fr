---
title: Confirmer les commandes client
description: Cette procédure illustre comment confirmer des commandes client.
author: omulvad
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, CustConfirmJournal, SysQueryForm, SysQueryFieldLookUp, SysLookup, SalesParmIdLookup, SalesUnconfirmedOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ac5217ecd74e3a8d4dd6a82112788a7aaba4698857cd5854eed1f8c91aa97e73
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779156"
---
# <a name="confirm-sales-orders"></a>Confirmer les commandes client

[!include [banner](../../includes/banner.md)]

Cette procédure illustre comment confirmer des commandes client. Vous découvrirez comment confirmer une seule commande et comment confirmer plusieurs commandes à la fois. Ces tâches sont généralement effectuées par un préparateur de commandes client. Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Avant de commencer, assurez-vous qu’il existe plusieurs commandes client en cours pour le même client. Si vous utilisez USMF, vous pouvez utiliser le client US-027.


## <a name="confirm-a-single-sales-order"></a>Confirmer une seule commande client
1. Accédez à **Volet de navigation > Modules > Ventes et marketing > Commandes client > Toutes les commandes client**.
2. Dans la liste, localisez et sélectionnez la commande que vous voulez confirmer.
3. Cliquez sur le lien sur le numéro de commande client pour ouvrir la commande sélectionnée.
4. Dans le volet **Action**, cliquez sur **Vendre**.
5. Cliquez sur **Confirmer la commande client**.
6. Développez la section **Paramètres**. Veillez à ce que l’option **Validation** soit définie sur Oui.  
7. Définissez l’option **Impression de la confirmation** sur Oui. Le champ **Vérifier la limite de crédit** spécifie la méthode utilisée pour calculer le crédit restant d’un client. Par défaut, il est copié à partir de la page Paramètres de la comptabilité client. Si vous souhaitez ignorer la vérification de la limite de crédit lors de la confirmation d’une commande client spécifique, définissez l’option **Vérifier la limite de crédit** sur Aucune. Toutefois, vous devez être conscient que même avec ce champ est défini sur Aucune, la vérification de la limite de crédit est toujours effectuée si l’option **Limite de crédit obligatoire** est activée dans les données principales du client. 
8. Cliquez sur **OK**.
9. Cliquez sur **Oui**.
10. Fermez la page.
11. Dans le **volet Actions**, cliquez sur **Options**.
12. Cliquez sur **Changer de vue**.
13. Cliquez sur **Vue de l’en-tête**. Lorsqu’une commande est confirmée, le champ **Statut du document** est défini sur Confirmation. 
14. Dans le volet **Action**, cliquez sur **Vendre**.
15. Cliquez sur **Confirmation de commande client**.
16. Fermez la page.

## <a name="confirm-multiple-sales-orders-at-once"></a>Confirmer plusieurs commandes client simultanément
1. Accédez à **Ventes et marketing > Commandes client > Confirmation de commande > Confirmer la commande client**.
2. Cliquez sur **Sélectionner**.
3. Dans la liste de l’onglet **Plage**, localisez et sélectionnez l’enregistrement qui fait référence au champ **Compte client**.
4. Dans le champ **Critères**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, localisez et sélectionnez le compte client qui a plusieurs commandes que vous souhaitez confirmer simultanément. Si vous utilisez USMF, vous pouvez sélectionner le compte US-027.  
6. Cliquez sur **OK**.
    - L’onglet **Vue d’ensemble** affiche la liste des commandes qui correspondent aux critères de requête. Ceux-ci sont inclus dans la confirmation.  
    - Le champ **Mise à jour récapitulative pour** dans la section **Paramètres** spécifie le paramètre par lequel plusieurs commandes doivent être synthétisées dans un document de confirmation. Par défaut, l’option est copiée à partir des **Valeurs par défaut pour le paramètre de mise à jour récapitulative** sur la page **Paramètres de la comptabilité client**.  
7. Dans le champ **Mise à jour récapitulative**, sélectionnez « Commande ». Les paramètres minimaux requis pour créer des mises à jour récapitulatives sont **Compte de facturation** et **Devise**. Cela signifie que les mises à jour récapitulatives présentant des comptes de facturation et des devises différents ne sont pas autorisées. Des paramètres supplémentaires peuvent être configurés sur la page **Paramètres de mise à jour récapitulative** qui est accessible à partir de la page **Paramètres de la comptabilité client**. 
8. Dans le champ **Commande client**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, sélectionnez le numéro de la commande qui servira de commande récapitulative.
10. Cliquez sur **Organiser**.
11. Cliquez sur **OK**.
12. Cliquez sur **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]