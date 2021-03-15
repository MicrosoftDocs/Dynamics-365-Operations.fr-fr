---
title: Cartes d’achat
description: Cette rubrique explique comment configurer et suivre les transactions de carte d’achat.
author: velofog
manager: AnnBe
ms.date: 09/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.search.industry: public sector
ms.author: roschlom
ms.search.validFrom: 2019-9-03
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: ac705f318b06919c14fc436e4caa2f1a706bd1ba
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987991"
---
# <a name="purchasing-cards"></a>Cartes d’achat

[!include [banner](../includes/banner.md)]


Les organismes utilisent des cartes d’achat afin que les employés puissent acheter des biens et services sans utiliser le processus de demande d’achat standard. Les pages et les champs liés aux cartes d’achat fournissent un mécanisme de suivi des achats. Chaque achat effectué par un employé à l’aide d’une carte d’achat est enregistré sur une facture fournisseur. Toutefois, la facture n’est pas réglée à l’aide d’un chèque ou d’un paiement électronique au fournisseur qui a fourni des biens ou services. Au lieu de cela, chaque facture de ce type est associée à une autre facture fournisseur créée pour payer le fournisseur qui fournit les services de cartes d’achat (c’est-à-dire, l’établissement financier). Les achats de carte sont payés lorsque le solde dû au fournisseur de services de cartes d’achat est payé chaque mois.

## <a name="enable-purchasing-card-pages-and-fields"></a>Activer les pages et champs des cartes d’achat

1. Allez dans **Comptabilité fournisseur** \> **Paramètres** \> **Paramètres de la comptabilité fournisseur**.
2. Dans l’onglet **Facture**, définissez l’option **Activer les cartes d’achat** sur **Oui**.

## <a name="enter-purchasing-card-records-for-employees"></a>Entrez les enregistrements des cartes d’achat pour les employés

Vous devez entrer des informations sur les cartes d’achat émises aux employés afin de pouvoir acheter des biens ou services. Cette information apparaît sur les factures fournisseur. Lorsqu’une carte d’achat est ajoutée à un compte bancaire, les factures fournisseur peuvent identifier la carte de crédit comme valide pendant le traitement de facture.

1. Accédez à **Gestion de la trésorerie et de la banque** \> **Commun** \> **Comptes bancaires**.
2. Dans la page de liste, sélectionnez le compte bancaire du fournisseur de services de carte d’achat.
3. Dans le volet Actions, sous l’onglet **Paramétrage**, sélectionnez **Cartes d’achat**.
4. Dans la page **Carte d’achat bancaire**, sélectionnez **Nouveau** pour créer un enregistrement de carte d’achat.
5. Entrez les informations suivantes sur la carte d’achat :

    - Dans le champ **Numéro de référence de la carte d’achat**, entrez le numéro de référence de la carte de crédit. Par exemple, entrez les quatre derniers chiffres.

        > [!NOTE]
        > Après avoir enregistré le numéro de référence de la carte d’achat, vous ne pouvez pas le modifier.

    - Dans le champ **Nom du titulaire de la carte**, entrez le nom du détenteur de la carte tel qu’il apparaît sur la carte d’achat.
    - Dans le champ **Employé**, sélectionnez l’employé pour lequel la carte est émise.
    - Facultatif : Dans le champ **Début de validité**, entrez la date à laquelle la carte est émise à l’employé.
    - Facultatif : Dans le champ **Date d’expiration**, entrez la date à laquelle la carte expire.
    - Facultatif : Dans le champ **Limite de crédit**, entrez le montant maximal pouvant être payé par la carte.

## <a name="set-up-a-posting-definition-for-vendor-invoices-that-track-employee-purchases"></a>Paramétrez une définition de validation pour les factures fournisseur qui suivent les achats des employés

Vous devez créer une définition de validation pour les factures fournisseur entrées pour enregistrer les achats effectués à l’aide d’une carte d’achat. Lorsque ces factures sont enregistrées, des écritures d’équilibrage de la dépense sont créées dans la comptabilité. Lorsqu’une facture fournisseur est réglée, elle est déplacée vers l’historique, mais un paiement au fournisseur n’est pas généré. Vous utilisez cette définition de validation lorsque vous importez des factures à partir d’un fichier externe et lorsque vous entrez manuellement les factures fournisseur pour les achats des employés.

Facultatif : Vous pouvez définir la définition de validation afin qu’elle soit utilisé par défaut lorsque vous créez des factures fournisseur pour enregistrer des transactions de carte d’achat.

1. Allez dans **Comptabilité fournisseur** \> **Paramètres** \> **Paramètres de la comptabilité fournisseur**.
2. Dans l’onglet **Facture**, dans le champ **Définition de validation par défaut pour l’enregistrement d’achat**, sélectionnez la définition de validation à utiliser comme définition de validation par défaut.

## <a name="overview-processing-invoices-for-purchasing-card-transactions"></a>Vue d’ensemble : Traitement des factures pour les transactions de carte d’achat

Après avoir paramétré votre système pour les cartes d’achat, vous pouvez créer une facture pour un fournisseur, ou un établissement financier, qui fournit des services de carte d’achat. Vous pouvez également créer d’autres factures pour suivre les achats effectués par les titulaires de cartes. Après avoir reçu le relevé mensuel de carte d’achat de votre établissement financier, vous pouvez le distribuer aux employés ayant effectué des achats au cours de la période de facturation. Généralement, les employés vérifient les transactions, et fournissent des reçus ou des factures qui justifient leurs achats.

1. Créez d’une facture fournisseur pour payer le fournisseur de services de carte d’achat. Vous allez générer un chèque pour cette facture fournisseur afin de payer le solde sur le relevé de carte d’achat.
2. Créez d’autres factures fournisseur pour enregistrer les achats effectués par les titulaires de cartes.

> [!NOTE]
> Généralement, vous pouvez utiliser les entités de données de facture fournisseur pour publier des données de facture fournisseur dans le système.

## <a name="create-a-vendor-invoice-for-a-purchasing-card-statement"></a>Créer une facture fournisseur pour un relevé de carte d’achat

Cette procédure vous permet de créer une facture fournisseur pour enregistrer le solde de relevé périodique pour un relevé de carte d’achat reçu d’un fournisseur de services de carte d’achat.

1. Accédez à **Comptabilité fournisseur** \> **Commun** \> **Factures fournisseur** \> **Factures fournisseur en cours**.
2. Dans le volet Actions, sélectionnez **Facture** \> **Facture fournisseur**.
3. Dans la page **Facture fournisseur**, dans le champ **Compte de facturation**, entrez le numéro de compte du fournisseur qui a envoyé le relevé de carte d’achat.
4. Entrez le numéro de la facture dans le champ **Numéro**.
5. Dans la zone de grille **Lignes**, sélectionnez **Ajouter une ligne**, puis entrez les informations sur la ligne.
6. Pour spécifier des informations complémentaires concernant la ligne, sélectionnez l’organisateur **Détails sur le ligne** et entrez les informations.
7. Sélectionnez **Finances** pour ajouter ou modifier les informations de répartition financière pour la ligne de facture.
8. Dans le volet Actions, sélectionnez **En-tête** pour entrer des informations supplémentaires pour l’en-tête de facture.
9. Dans le volet Actions, sous l’onglet **Général**, dans le champ **Facture de la carte d’achat**, sélectionnez **Règlement du solde** pour spécifier que vous réglez le solde de la carte d’achat de votre organisme.
10. Facultatif : Envoyez la facture au système de workflow pour révision et approbation, puis validez la facture.

    > [!NOTE]
    > Avant de créer une Facture de carte d’achat, vous devez valider la facture de règlement du solde au fournisseur de services de carte d’achat. Toutes les factures de carte d’achat sont contrôlées par rapport à cette facture.

11. Pour enregistrer la facture sans la valider, fermez la page. Vous pouvez afficher la facture sur la page de liste **Factures fournisseur en attente**.

## <a name="create-a-vendor-invoice-to-record-a-purchasing-card-transaction"></a>Créer une facture fournisseur pour enregistrer une transaction de carte d’achat

La procédure suivante vous permet de créer une facture fournisseur pour enregistrer un achat qui a été exécuté à l’aide d’une carte d’achat. Cette facture sera réglée, mais non payée, au fournisseur qui a fourni les biens ou services achetés.

> [!NOTE]
> La facture pour le relevé qui est défini comme la facture de règlement du solde doit être validée dans le compte fournisseur avant de créer une Facture de carte d’achat.

1. Accédez à **Comptabilité fournisseur** \> **Commun** \> **Factures fournisseur** \> **Factures fournisseur en cours**.
2. Dans le volet Actions, sélectionnez **Facture** \> **Facture fournisseur**.
3. Dans la page **Facture fournisseur**, dans le champ **Compte de facturation**, entrez le numéro de compte du fournisseur qui a envoyé la facture pour es biens et services.
4. Entrez le numéro de la facture dans le champ **Numéro**.
5. Dans le volet Actions, sélectionnez **En-tête** pour entrer des informations supplémentaires pour l’en-tête de facture.
6. Dans le champ **Facture de la carte d’achat**, sélectionnez **Enregistrer l’achat** comme type de transaction de carte d’achat pour laquelle vous entrez la facture.

    > [!NOTE]
    > Une valeur du **Règlement du solde** indique que la facture règlera un solde dû au fournisseur de services de carte d’achat. Une valeur **S. o.** indique que la facture n’implique pas de carte d’achat.

7. Dans l’organisateur **Paramétrage**, dans le champ **Définition de validation**, sélectionnez la définition de validation de la carte d’achat si une valeur par défaut n’a pas été sélectionnée sur la page **Paramètres de la comptabilité fournisseur**.

    > [!NOTE]
    > La définition de validation sélectionnée doit être paramétrée pour enregistrer l’achat, mais pas pour valider dans la Comptabilité fournisseur. Sinon, un paiement sera réalisé au fournisseur qui a fourni les biens ou services qui ont été obtenus via la carte d’achat.

8. Dans l’organisateur **Paiement**, affichez ou entrez des informations sur la carte d’achat utilisée pour effectuer l’achat :

    - Dans le champ **Numéro de référence de la carte d’achat**, entrez le numéro de référence de la carte.
    - Affichez le nom de la banque qui a émis la carte. Cette valeur s’affiche après avoir entré le numéro de référence.
    - Affichez le nom du détenteur de la carte. Cette valeur est basée sur le numéro de référence entré.
    - Dans le champ **Compte**, entrez le numéro de compte du fournisseur qui fournit les services de carte d’achat.
    - Affichez le nom du fournisseur de services de carte d’achat. Cette valeur est basée sur le numéro de compte entré.
    - Dans le champ **Facture de la carte d’achat**, entrez le numéro de facture fournisseur de la Facture de règlement du solde créée pour payer le relevé de la carte d’achat incluant cet achat. Ce champ doit être défini sur le numéro de la facture validée désignée comme la Facture de règlement du solde. Ce numéro de facture apparaît dans la liste si la facture a été marquée de la manière appropriée.

9. Dans le volet Actions, sélectionnez **Affichage des lignes** pour entrer des informations sur le montant de l’achat.
10. Dans la zone de grille **Lignes**, sélectionnez **Ajouter une ligne**, et entrez les informations sur la ligne.
11. Pour spécifier des informations complémentaires concernant la ligne, sélectionnez l’organisateur **Détails sur le ligne** et entrez les informations.
12. Facultatif : Envoyez la facture au système de workflow pour révision et approbation, puis validez la facture.
13. Pour enregistrer la facture sans la valider, fermez la page. Vous pouvez afficher la facture sur la page de liste **Factures fournisseur en attente**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]