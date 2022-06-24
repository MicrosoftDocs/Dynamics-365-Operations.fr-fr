---
title: Création de codes frais
description: Cet article explique comment configurer les codes de frais pour la comptabilité fournisseur et la comptabilité client.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MarkupTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d65952cb989672e4eac2dd6101ee9c7c9424daed
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8866081"
---
# <a name="create-charges-codes"></a>Création de codes frais

Cet article explique comment configurer les codes de frais pour la comptabilité fournisseur et la comptabilité client. Si votre organisation exige que les montants des ventes ou des achats soient suivis en plus des éléments de ligne sur une commande client ou une commande fournisseur, vous pouvez utiliser des codes de frais à cette fin. Par exemple, vous pouvez payer les frais de transport et d’assurance sur une commande fournisseur, puis ces montants sont détaillés séparément dans la commande fournisseur. Dans ce cas, vous pouvez spécifier si les montants sont validés dans les comptes de dépenses ou s’ils sont ajoutés au coût des articles.

## <a name="set-up-charges-codes-for-accounts-receivable"></a>Paramétrage de codes frais pour la comptabilité client

Pour créer des codes de frais pour la comptabilité client, procédez comme suit.

1. Accédez à **Comptabilité client** &gt; **Paramétrage des frais** &gt; **Code frais**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Code frais**, entrez un code pour les frais.
3. Dans le champ **Description**, entrez la description des frais.
4. Facultatif : dans le champ **Groupe de taxe d’article**, sélectionnez un groupe de taxe d’article.
5. Dans le raccourci **Validation**, indiquez comment débiter et créditer automatiquement les frais.
6. Si vous avez sélectionné **Compte général** comme type de débit ou de crédit, indiquez le type de validation dans les champs **Validation**, et spécifiez le compte principal dans le champ **Compte**.

### <a name="example"></a>Exemple

Votre client paie les frais. Par conséquent, ils sont ajoutés aux totaux des commandes client. Vous devez paramétrer les informations de validation suivantes :

- Dans le champ **Type** de la section **Débit**, sélectionnez **Client/Fournisseur** pour ajouter les frais facturés au compte du client.
- Dans le champ **Type** de la section **Crédit**, sélectionnez **Compte général**. Puis, dans le champ **Compte**, sélectionnez le compte principal pour le produit des frais de facturation.

> [!NOTE]
> Si le type de débit ou de crédit pour le code sélectionné est **Compte général** ou **Article**, vous pouvez saisir une devise différente pour la transaction des frais.

Vous pouvez imprimer le texte relatif aux frais dans la langue affectée au client. Pour spécifier le texte pour le code frais dans d’autres langues, sélectionnez **Traductions**.

## <a name="set-up-charges-codes-for-accounts-payable"></a>Paramétrage de codes frais pour la comptabilité fournisseur

Pour créer des codes de frais pour la comptabilité fournisseur, procédez comme suit.

1. Utilisez l’une des procédures suivantes :

    - Accédez à **Comptabilité fournisseur** &gt; **Paramétrage** **des frais** &gt; **Code frais**.
    - Accédez à **Approvisionnements** &gt; **Paramétrage** &gt; **Frais** &gt; **Code frais**.

2. Cliquez sur **Nouveau**.
3. Dans le champ **Code frais**, entrez un code pour les frais.
3. Dans le champ **Description**, entrez la description des frais.
4. Facultatif : dans le champ **Groupe de taxe d’article**, sélectionnez un groupe de taxe d’article.
5. Facultatif : dans le champ **Montant maximal**, entrez le montant maximal autorisé pour le code frais.

    Ce champ est utilisé pour valider les frais pour les factures fournisseur. Pour activer la validation des frais, cochez la case **Activer le contrôle de rapprochement de factures** dans l’onglet **Validation des factures** de la page **Paramètres de la comptabilité fournisseur**.

    > [!IMPORTANT]
    > Pour valider les frais des factures, vous devez également créer une instance d’un type de règle de stratégie basé sur les frais pour la stratégie de facture fournisseur spécifique.

6. Dans le raccourci **Validation**, indiquez comment débiter et créditer automatiquement les frais.
7. Si vous avez sélectionné **Compte général** comme type de débit ou de crédit, indiquez le type de validation dans les champs **Validation des débits** et **Validation des crédits**, et spécifiez le compte principal dans les champs **Compte à débiter** et **Compte à créditer**.
8. Pour permettre la comparaison des valeurs de frais pour une facture qui contient les frais tirés des lignes ou en-têtes de commandes fournisseur correspondantes, activez la case à cocher **Comparer les valeurs de la commande fournisseur et de la facture**.

### <a name="example"></a>Exemple

Vous pouvez enregistrer les frais comme une dépense dans le cadre du total de la commande fournisseur ou de la facture fournisseur. Procédez comme suit pour paramétrer les informations de validation. 

- Dans le champ **Type** de la section **Crédit**, sélectionnez **Client/Fournisseur** pour ajouter les frais facturés au compte du fournisseur.
- Dans le champ **Type** de la section **Débit**, sélectionnez **Compte général**. Puis, dans le champ **Compte**, sélectionnez le compte principal pour la dépense des frais de facturation.

Suivez ces étapes pour configurer les informations de validation afin que les frais unitaires soient ajoutés au coût de l’article.

- Dans le champ **Type** de la section **Crédit**, sélectionnez **Client/Fournisseur** pour ajouter les frais facturés au compte du fournisseur.
- Dans le champ **Type** de la section **Débit**, sélectionnez **Article** pour ajouter les frais au coût de l’article.

> [!NOTE]
> Vous souhaitez peut-être utiliser une devise différente de celle spécifiée sur la commande fournisseur ou la facture. Il est possible d’entrer une devise différente si le type de débit ou de crédit pour le code frais sélectionné est défini comme **Compte général** ou **Article**.

Vous pouvez imprimer le texte relatif aux frais dans la langue affectée au client. Pour spécifier le texte pour le code frais dans d’autres langues, sélectionnez **Traductions**.
