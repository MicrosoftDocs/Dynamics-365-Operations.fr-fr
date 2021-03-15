---
title: Savoir utiliser les limites de contrôle de disponibilités
description: Cette rubrique explique comment utiliser le contrôle de disponibilités pour définir des limites de transaction lorsqu’il n’y a aucun solde de disponibilités ou qu’une transaction fait chuter le solde des disponibilités sous un montant prédéfini.
author: v-kiarnd
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-kiarnd
ms.search.validFrom: 2019-8-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fbf19d1f9282c1e2a22eded852035d5a3f0f96ef
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971187"
---
# <a name="use-cash-control-limits"></a>Savoir utiliser les limites de contrôle de disponibilités

[!include [banner](../includes/banner.md)]


Cette rubrique explique comment utiliser le contrôle de disponibilités pour définir des limites de transaction lorsqu’il n’y a aucun solde de disponibilités ou qu’une transaction fait chuter le solde des disponibilités sous un montant prédéfini.

Le contrôle de disponibilités permet de définir une limite (seuil) pour empêcher de valider des transactions si aucun solde de disponibilités n’est disponible, ou si une transaction fait chuter le solde sous un montant défini. Le compte défini dans la définition de validation utilisée est évalué lorsque des transactions sont créées, modifiées et validées. Si aucune entrée n’est générée, le compte correspondant est utilisé. Si la validation de la transaction fait chuter le solde du compte de disponibilités associé sous la limite définie, un message d’erreur s’affiche et vous devez modifier le compte pour continuer. .

Vous pouvez autoriser des groupes d’utilisateurs spécifiques à contourner le contrôle de disponibilités. Ensuite, si le solde du compte de disponibilités chute en dessous de la limite définie, des utilisateurs des groupes d’utilisateurs spécifiés reçoivent un message d’avertissement, mais peuvent procéder à la validation de la transaction. Les utilisateurs peuvent contourner le contrôle de disponibilités si la dépense doit être validée avant la réception des fonds, ou lorsqu’un transfert approuvé doit avoir lieu, mais qu’il n’a pas encore été entré ou validé.

La limite de contrôle de disponibilités est comparable au solde de contrôle de disponibilités (le solde du compte de disponibilités moins toutes les factures de Comptabilité fournisseur impayées et validées). Lorsque le solde de contrôle de disponibilités est inférieur à la limite de contrôle de disponibilités, la limite est dépassée.

## <a name="set-up-cash-control"></a>Paramétrer le contrôle des disponibilités

Procédez comme suit pour paramétrer le contrôle des disponibilités et les comptes de contrôle de disponibilités.

1. Accédez à **Comptabilité** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**.
2. Dans le groupe **Validation du contrôle des disponibilités**, dans le champ **Ensemble de dimensions financières**, sélectionnez l’ensemble de dimensions financières à utiliser pour valider les soldes de contrôle des disponibilités.
3. Dans le champ **Contournement du contrôle de disponibilités**, sélectionnez le groupe d’utilisateurs qui peut contourner le contrôle de disponibilités. Les utilisateurs de ce groupe de sécurité pourront ensuite valider les transactions qui dépassent la limite de contrôle de disponibilités.
4. Accédez à **Comptabilité** \> **Paramétrage de la comptabilité** \> **Paramétrage de la validation** \> **Contrôle de disponibilités**.
5. Définissez l’option **Afficher les noms du compte** sur **Oui** pour afficher les noms du compte pour les comptes de disponibilités et les comptes Comptabilité fournisseur que vous entrez dans la grille.
6. Renseignez chaque compte de disponibilités.

Il est recommandé d’ajouter toutes les chaînes de dimension financière pour tous les comptes de disponibilités valides. Vous pouvez ensuite spécifier quels comptes de disponibilités sont soumis à la limite de contrôle de disponibilités.

7. Dans le champ **Compte de disponibilités**, entrez la chaîne de dimension financière du compte de disponibilités. Vous devez entrer les numéros de compte complets.
8. Activez la case à cocher **Participer** pour indiquer que la chaîne de dimension financière du compte de disponibilités est soumise au contrôle de disponibilités. Ces comptes de disponibilités et les comptes Comptabilité fournisseur correspondants sont validés selon les règles de configuration du contrôle de disponibilités.
9. Facultatif : Dans le champ de compte **Comptabilité fournisseur**, entrez la chaîne de dimension financière du compte Comptabilité fournisseur utilisée avec des factures fournisseur. Vous devez entrer un numéro de compte complet.
10. Dans le champ **Seuil**, entrez le montant qui doit rester dans le compte de disponibilités pour effectuer le contrôle. Vous pouvez entrer un nombre négatif si le compte de disponibilités peut être débiteur (autrement dit, si les montants de transaction peuvent être supérieurs au solde du compte).

## <a name="view-accounts-in-cash-control"></a>Afficher les comptes dans le contrôle de disponibilités

Vous pouvez consulter le solde actuel des comptes définis sur la page **Configuration du contrôle de disponibilités**. Accédez à **Comptabilité** \> **Recherches** \> **Recherche de contrôle de disponibilités**.

La recherche couvre les informations suivantes :

- Le solde du compte de disponibilités actuel
- Le solde de toutes les factures Comptabilité fournisseur validées et impayées qui sont appliquées au compte Comptabilité fournisseur correspondant au compte de disponibilités
- Le solde de contrôle de disponibilités ou le solde du compte actuel de disponibilités moins toutes les factures de Comptabilité fournisseur impayées et validées
- La limite de contrôle de disponibilités, afin de pouvoir la comparer au solde de contrôle de disponibilités et déterminer si le paiement des factures de Comptabilité fournisseur fait chuter le solde du compte de disponibilités sous la limite de contrôle de disponibilités

## <a name="process-transactions-by-using-cash-control-validation"></a>Traiter les transactions à l’aide de la validation du contrôle des disponibilités

Les soldes de compte de disponibilités sont validés pour les factures de Comptabilité fournisseur et les écritures comptables avancées. Le montant de la ligne est validé par rapport aux comptes de disponibilités et aux comptes de Comptabilité fournisseur auxquels les répartitions financières de la ligne sont associées.

[!NOTE] Le contrôle budgétaire est distinct du contrôle des disponibilités et peut contenir des erreurs sans lien.

Si la limite de contrôle de disponibilités est dépassée, un message d’erreur s’affiche. L’erreur empêche la poursuite du traitement de la facture sauf si le contournement du contrôle de disponibilités est autorisé.

## <a name="vendor-invoice-workflow"></a>Flux de travail de facture fournisseur

### <a name="the-workflow-is-set-up-for-autoposting"></a>Le workflow est paramétré pour la validation automatique

Lorsque vous utilisez la fonctionnalité de contrôle de disponibilités avec le workflow de facture fournisseur de Comptabilité fournisseur, et que ce workflow est paramétré pour la validation automatique, le système autorise l’utilisateur qui soumet la facture fournisseur à contourner la limite de contrôle de disponibilités au cours de l’étape de validation automatique.

Si la facture dépasse la limite de contrôle de disponibilités, et que l’utilisateur a des privilèges de contournement, la facture est automatiquement validée dans le cadre du processus de workflow. Si l’utilisateur ne dispose pas des autorisations de contournement, un message d’erreur s’affiche dans l’historique du workflow pour la facture fournisseur correspondante. Dans ce cas, la facture peut être correctement traitée lors de la validation uniquement si l’une des conditions suivantes est remplie :

- Un utilisateur disposant de droits de contournement renvoie la facture
- La facture est modifiée afin qu’un autre compte de disponibilités soit utilisé
- Le solde de contrôle de disponibilités est modifié

### <a name="the-workflow-isnt-set-up-for-autoposting"></a>Le workflow n’est pas paramétré pour la validation automatique

Lorsque vous utilisez la fonctionnalité de contrôle de disponibilités avec le workflow de facture fournisseur de Comptabilité fournisseur, et que le workflow n’est pas paramétré pour la validation automatique, un utilisateur disposant des droits de contournement peut envoyer une facture au workflow. La validation du contrôle de disponibilités est effectuée de nouveau lorsque la facture est validée. Cette seconde validation est réalisée car les soldes de disponibilités peuvent varier entre le moment où la facture est soumise au workflow et celui où elle est validée.

Si la facture dépasse la limite de contrôle de disponibilités et que l’utilisateur ne dispose pas des autorisations de priorité, un message d’erreur s’affiche, et la facture ne peut pas être soumise au workflow. Dans ce cas, la facture peut être correctement soumise uniquement si l’une des conditions suivantes est remplie :

- Un utilisateur disposant de droits de contournement renvoie la facture
- La facture est modifiée afin qu’un autre compte de disponibilités soit utilisé
- Le solde de contrôle de disponibilités est modifié


[!INCLUDE[footer-include](../../includes/footer-banner.md)]