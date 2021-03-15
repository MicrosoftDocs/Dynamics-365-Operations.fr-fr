---
title: Rapprocher un compte bancaire
description: Cette rubrique décrit la procédure de rapprochement d’un compte bancaire.
author: panolte
manager: AnnBe
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1abc86aa5c3863eba34f726b543792408a542383
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976364"
---
# <a name="reconcile-a-bank-account"></a>Rapprocher un compte bancaire

[!include[banner](../includes/banner.md)]

Lorsque vous recevez un relevé bancaire, vous devez périodiquement rapprocher les transactions bancaires de l’entité juridique avec les transactions du relevé bancaire.

Vous ne pouvez pas rapprocher un relevé bancaire avec un compte bancaire si des chèques ou des paiements de bordereau de remise répertoriés sur le relevé présentent le statut **Annulation en attente**. Lorsqu’un préposé valide ou rejette une contrepassation de chèque ou l’annulation d’un paiement de bordereau de remise, le statut n’est plus **Annulation en attente** et vous pouvez rapprocher le compte bancaire.

1.  Accédez à **Gestion de la trésorerie et de la banque** \> **Comptes bancaires** \> **Comptes bancaires**. Sélectionnez le compte bancaire à rapprocher avec le relevé bancaire et sélectionnez **Rapprocher** > **Rapprochement de compte**.

2.  Entrez des informations dans les champs **Date de relevé bancaire** et **Relevé bancaire**. Dans le champ **Solde de fin**, vous pouvez entrer le solde du compte bancaire tel qu’il apparaît sur le relevé bancaire.

3.  Sélectionnez **Transactions** pour ouvrir la page **Rapprochement de compte**.

4.  Pour chaque transaction incluse dans le relevé bancaire, activez la case à cocher **Compensé** si le montant dans Dynamics 365 Finance correspond au montant du relevé bancaire. Vous pouvez également entrer ou modifier la valeur du champ **Type de transaction bancaire**. Cette valeur de champ est importante pour vos statistiques de transactions bancaires et pour certains états.
    

    > [!NOTE]
    > <P>N’activez pas la case à cocher <STRONG>Compensé</STRONG> pour les transactions qui ne sont pas incluses dans le relevé bancaire. Ces transactions continueront de figurer dans cette page jusqu’à ce qu’elles soient rapprochées avec un prochain relevé bancaire.</P>
    > <P>La case à cocher <STRONG>Compensé</STRONG> n’est pas disponible si la transaction présente le statut <STRONG>Annulation en attente</STRONG>. Les transactions peuvent présenter ce statut si Finance est paramétré de sorte à exiger que les contrepassations ou les annulations soient envoyées pour vérification avant d’être validées. Lorsqu’un réviseur valide ou rejette la contrepassation ou l’annulation, le statut n’est plus <STRONG>Annulation en attente</STRONG> et vous pouvez rapprocher le compte bancaire avec le relevé bancaire.</P>

    
    Pour activer la case à cocher **Compensé** pour un intervalle de chèques entièrement affichés sur le relevé bancaire, sélectionnez **Marquer l’intervalle de chèques**, puis indiquez l’intervalle.

5.  Si le montant d’une transaction de compte bancaire ne correspond pas au montant de la transaction sur le relevé bancaire, entrez le montant de la correction dans le champ **Montant de la correction**.
    

    > [!NOTE]
    > <P>Si la période fiscale de la transaction à corriger est clôturée, le champ <STRONG>Montant de la correction</STRONG> ne peut pas être utilisé. Créez à la place une ligne qui a une date de transaction dans une période fiscale en cours pour la correction. Dans ce cas, vous devez ajouter les dimensions financières qui étaient utilisées sur la transaction d’origine, de même que le compte principal.</P>



6.  Créez des transactions pour les entrées, telles que des frais ou des intérêts, qui figurent sur le relevé de compte bancaire, mais ne sont pas enregistrées dans Finance. Entrez le **Type de transaction bancaire** et les dimensions financières appropriées.

7.  Comme les transactions du relevé de compte bancaire sont marquées comme **Compensées**, le montant dans le champ **Non rapproché**, qui est recalculé continuellement au fur et à mesure de vos changements, s’approche de zéro. Lorsqu’il atteint zéro, sélectionnez **Rapprocher le compte** pour valider le rapprochement ainsi que les transactions et les corrections que vous avez créées.
    
    Lorsque le rapprochement est validé, les transactions incluses ne peuvent plus être modifiées ni corrigées et elles n’apparaîtront plus dans aucun rapprochement de compte.

8.  Pour afficher les transactions bancaires qui ne sont pas encore rapprochées, utilisez l’état **Transactions bancaires non rapprochées**. Pour afficher le relevé d’un compte bancaire, utilisez l’état **Relevé bancaire**.

## <a name="cancel-bank-statement-reconciliation"></a>Annuler le rapprochement de relevé bancaire 

La fonctionnalité Annuler le rapprochement de relevé de bancaire vous permet d’annuler le rapprochement de relevé bancaire. Pour utiliser cette fonctionnalité, activez la fonctionnalité **Annuler le rapprochement de relevé bancaire** dans l’espace de travail **Gestion des fonctions**. Vous devez également activer le paramètre **Autoriser la modification du relevé bancaire**. Pour ce faire, accédez à **Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque > Rapprochement bancaire**.
 
Les rapprochements de relevé bancaire ne peuvent être annulés que dans l’ordre chronologique dans lequel ils ont été entrés. Lorsqu’un rapprochement de relevé bancaire est annulé, de nouvelles transactions et corrections seront contrepassées et toutes les autres transactions seront marquées comme non rapprochées.
 
Pour annuler le rapprochement de relevé bancaire, sélectionnez le relevé bancaire et sélectionnez **Relevé bancaire > Annuler le rapprochement bancaire**. Dans la page **Annuler le rapprochement bancaire**, renseignez les champs **Code motif**, **Commentaire du motif** et **Date d’annulation**. Sélectionnez **OK** pour démarrer l’annulation. Notez que la date d’annulation du relevé bancaire doit être égale ou postérieure à la date du relevé bancaire. Une fois le rapprochement de relevé de bancaire annulé, le champ **Date d’annulation** du relevé bancaire sera mis à jour avec la **Date d’annulation** fournie. Sélectionnez le bouton **Transactions** pour afficher les transactions pour lesquelles le rapprochement a été annulé.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]