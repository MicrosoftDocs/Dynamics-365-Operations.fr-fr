---
title: Canada GST/GIFT (HST Internet File Transfer)
description: Cet article décrit la configuration et utiliser la fonctionnalité de transfert de fichiers via Internet Canada GST/GIFT (HST Internet File Transfer).
author: ericwang
manager: Ann Beebe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GST/HST, GIFT
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Canada
ms.author: kfend
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 829e13bd4bd111d8a5f8b534c9f6ab589f24d74f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4984890"
---
# <a name="canada-gsthst-internet-file-transfer"></a>Canada GST/GIFT (HST Internet File Transfer) 

[!include [banner](../includes/banner.md)]

Les contribuables canadiens utilisent le formulaire GST 34 pour remplir manuellement les déclarations fiscales sur les biens et services ou de taxe harmonisée (GST/HST) et pour effectuer les paiements auprès de l’Agence du revenu du Canada (ARC). Toutefois, cette dernière leur permet de remplir les déclarations et de verser les taxes calculées sur les immobilisations acquises par voie électronique. Vous pouvez remplir les déclarations GST/HST par voie électronique à l’aide de l’une des méthodes suivantes :

  - transfert de fichiers via Internet : service Web de déclaration qui permet aux contribuables de remplir leurs déclarations directement via Internet ;

  - échange de données informatisé (EDI) : méthode de transfert de données qui permet aux contribuables de remplir leurs déclarations directement auprès de l’ARC ou d’un fournisseur de services tiers ;

  - GST/HST Internet File Transfer (GIFT) : outil de téléchargement qui permet d’envoyer des fichiers texte au site Web de l’ARC à des fins de déclarations GST/HST et de règlement des paiements.

Avant de générer un fichier GIFT, vous devez configurer le code identification du logiciel, le code taxe et le groupe de taxe. 

Les procédures suivantes permettent d’entrer des informations sur l’entité juridique, le code taxe et les groupes de taxe pour GIFT, ainsi que de créer des entrées de taxe pour les taxes sur l’acquisition.

## <a name="set-up-legal-entities-for-gift"></a>Paramétrage d’entités juridiques pour GIFT

Lorsque vous envoyez une requête de transfert de fichiers via Internet à l’ARC, celle-ci fournit un code identification du logiciel, composé de deux caractères alphabétiques et de six caractères numériques. Vous devez entrer correctement ce code identification dans l’écran **Entités juridiques** pour traiter vos déclarations.

1.  Cliquez sur **Administration d’organisation** \> **Paramétrage** \> **Organisation** \> **Entités juridiques**.

2.  Cliquez sur l’organisateur **Génération d’état statutaire**, puis dans le champ **Numéro d’enregistrement**, entrez le numéro d’enregistrement fourni par l’ARC lors de votre enregistrement à des fins de déclaration GST/HST.

3.  Dans le champ **Code identification du logiciel**, entrez AX030003 pour transférer les déclarations.

4.  Cliquez sur **Identificateurs du compte** pour ouvrir l’écran **Identificateurs du compte**.

5.  Sous l’onglet **Vue d’ensemble**, dans le champ **Identificateur du programme**, sélectionnez **GST/HST**.

6.  Dans le champ **Numéro de référence**, entrez le numéro de référence fourni par l’ARC.

7.  Fermez les écrans pour enregistrer vos modifications.

## <a name="set-up-tax-codes-for-gift"></a>Définition des codes taxe pour GIFT

L’écran **Codes taxe** permet de définir des codes taxe pour calculer le montant des taxes GST/HST pour le fichier GIFT.

1.  Cliquez sur **Comptabilité** \> **Paramétrage** \> **Taxe** \> **Codes de taxe**.

2.  Appuyez sur Ctrl+N pour créer un code taxe.

3.  Dans le champ **Code de taxe**, entrez un code, tel que GST/HST, puis entrez des informations générales sur le code taxe.

4.  Cliquez sur l’onglet **Calcul** et entrez les détails du calcul du montant des taxes GST/HST.

5.  Cliquez sur **Valeurs** pour ouvrir l’écran **Valeurs**. Entrez les dates auxquelles le code taxe prend effet.

6.  Dans le champ **Valeur**, entrez le pourcentage utilisé pour le calcul.

7.  Fermez les écrans pour enregistrer vos modifications.

## <a name="set-up-tax-groups-for-gift"></a>Paramétrage des groupes de taxe pour GIFT

Utilisez l’écran **Groupes de taxe** pour configurer les groupes de taxe. Vous pouvez affecter des groupes de taxe à des sociétés et les taxes sont calculées en fonction des codes taxe en vigueur au moment de l’exécution des transactions.

1.  Cliquez sur **Comptabilité** \> **Paramétrage** \> **Taxe** \> **Groupes de taxe**.

2.  Appuyez sur Ctrl+N pour créer un groupe de taxe.

3.  Dans le champ **Code de groupe de taxe**, entrez un nom, tel que GST/HST, puis entrez des informations générales sur le groupe de taxe.

4.  Cliquez sur l’onglet **Configuration**, puis dans le champ **Code de taxe**, sélectionnez un code taxe à ajouter au groupe de taxe.

5.  Fermez l’écran pour enregistrer vos modifications.

## <a name="generate-a-gift-file"></a>Génération d’un fichier GIFT

Vous pouvez générer un fichier GST/GIFT (HST Internet File Transfer) de déclaration de taxe sur les biens et services ou de taxe harmonisée et charger celui-ci sur le site de l’Agence du revenu du Canada (ARC) afin de remplir vos déclarations GST/HST et effectuer des paiements.

1. Cliquez sur **Comptabilité générale** > **Périodique** > **GST/GIFT (HST Internet File Transfer)**.

2. Dans les champs **Date de début** et **Date de fin**, entrez les dates de début et de fin de la période de déclaration.

3. Dans le champ **Nom du fichier**, sélectionnez le chemin et saisissez le nom du fichier d’exportation de l’état Déclaration européenne de services.

    Note

   Pour faciliter l’identification, utilisez le format GSTAAAAMMJJ.tax (GST, suivi de la date de déclaration, puis de l’extension .tax) ; par exemple : GST20100728.tax.

4. Cliquez sur **OK** pour exporter le fichier GIFT vers le chemin spécifié.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]