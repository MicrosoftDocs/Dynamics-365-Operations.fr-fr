---
title: Canada GST/GIFT (HST Internet File Transfer)
description: Cette rubrique explique comment configurer et utiliser la fonction GIFT (Internet File Transfer) sur les biens et services ou de taxe harmonisée (GST/HST) du Canada.
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
ms.openlocfilehash: bfe7793e3367a2b30e8cb2db16c09cf9fff0fba2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968343"
---
# <a name="canada-gsthst-internet-file-transfer-gift"></a>Canada GST/GIFT (HST Internet File Transfer)

[!include [banner](../includes/banner.md)]

Les contribuables canadiens utilisent le formulaire GST 34 pour remplir manuellement les déclarations fiscales sur les biens et services ou de taxe harmonisée (GST/HST) et pour effectuer les paiements auprès de l’Agence du revenu du Canada (ARC). Toutefois, cette dernière leur permet de remplir électroniquement les déclarations et de verser les taxes calculées sur les immobilisations acquises par voie électronique. Vous pouvez remplir électroniquement les déclarations GST/HST par voie électronique à l’aide de l’une des méthodes suivantes :

- **Transfert de fichiers via Internet** : service Internet de déclaration qui permet aux contribuables de remplir leurs déclarations directement via Internet.
- **Échange de données informatisé (EDI)**  : méthode de transfert de données qui permet aux contribuables de remplir leurs déclarations directement auprès de l’ARC ou d’un fournisseur de services tiers.
- **GST/HST Internet File Transfer (GIFT)**  : outil de téléchargement qui permet aux contribuables d’envoyer des fichiers texte au site Web de l’ARC à des fins de déclarations GST/HST et de règlement des paiements.

Avant de générer un fichier GIFT, vous devez configurer le code identification du logiciel, le code taxe et le groupe de taxe.

Les procédures suivantes permettent d’entrer des informations sur l’entité juridique, le code taxe et les groupes de taxe pour GIFT, ainsi que de créer des entrées de taxe réglée pour les taxes sur l’acquisition.

## <a name="set-up-legal-entities-for-gift"></a>Paramétrage d’entités juridiques pour GIFT

Lorsque vous envoyez une requête de transfert de fichiers via Internet à l’ARC, celle-ci fournit un code identification du logiciel, composé de deux caractères alphabétiques et de six caractères numériques. Pour traiter vos déclarations, vous devez entrer correctement ce code identification sur la page **Entités juridiques**.

1. Accédez à **Administration d’organisation** \> **Paramétrage** \> **Organisation** \> **Entités juridiques**.
2. Sur l’organisateur **Génération d’état statutaire**, puis dans le champ **Numéro d’enregistrement**, entrez le numéro d’enregistrement fourni par l’ARC lors de votre enregistrement à des fins de déclaration GST/HST.
3. Dans le champ **Code identification du logiciel**, entrez **AX030003** pour transférer les déclarations.
4. Sélectionnez **Identificateurs du compte** pour ouvrir la page **Identificateurs du compte**.
5. Sous l’onglet **Vue d’ensemble**, dans le champ **Identificateur du programme**, sélectionnez **GST/HST**.
6. Dans le champ **Numéro de référence**, entrez le numéro de référence fourni par l’ARC.
7. Fermez les pages pour enregistrer vos modifications.

## <a name="set-up-tax-codes-for-gift"></a>Définition des codes taxe pour GIFT

La page **Codes taxe** permet de définir des codes taxe pour calculer le montant des taxes GST/HST pour le fichier GIFT.

1. Accédez à **Comptabilité** \> **Paramétrage** \> **Taxe** \> **Codes de taxe**.
2. Appuyez sur **Ctrl+N** pour créer un code taxe.
3. Dans le champ **Code de taxe**, entrez un code, tel que **GST/HST**, puis entrez des informations générales sur le code taxe.
4. Cliquez sur l’onglet **Calcul** et entrez les détails du calcul du montant des taxes GST/HST.
5. Sélectionnez **Valeurs** pour ouvrir la page **Valeurs**.
6. Entrez les dates auxquelles le code taxe prend effet.
7. Dans le champ **Valeur**, entrez le pourcentage utilisé pour le calcul.
8. Fermez les pages pour enregistrer vos modifications.

## <a name="set-up-tax-groups-for-gift"></a>Paramétrage des groupes de taxe pour GIFT

Utilisez la page **Groupes de taxe** pour configurer les groupes de taxe. Vous pouvez affecter des groupes de taxe aux sociétés. Les taxes seront ensuite calculées en fonction des codes taxe en vigueur au moment de l’exécution des transactions.

1. Accédez à **Comptabilité** \> **Paramétrage** \> **Taxe** \> **Groupes de taxe**.
2. Appuyez sur **Ctrl+N** pour créer un groupe de taxe.
3. Dans le champ **Code de groupe de taxe**, entrez un nom, tel que **GST/HST**, puis entrez des informations générales sur le groupe de taxe.
4. Sur l’onglet **Configuration**, puis dans le champ **Code de taxe**, sélectionnez un code taxe à ajouter au groupe de taxe.
5. Fermez la page pour enregistrer vos modifications.

## <a name="generate-a-gift-file"></a>Génération d’un fichier GIFT

Pour faire vos déclarations GST/HST et effectuer les paiements, vous pouvez générer un fichier GIFT et le télécharger le site Web de l’ARC.

1. Accédez à **Comptabilité générale** \> **Périodique** \> **GST/HST Internet File Transfer (GIFT)**.
2. Dans les champs **Date de début** et **Date de fin**, entrez les dates de début et de fin de la période de déclaration.
3. Dans le champ **Nom du fichier**, sélectionnez le chemin et saisissez le nom du fichier d’exportation de l’état Déclaration européenne de services.

    > [!NOTE]
    > Pour faciliter l’identification du fichier GIFT, utilisez le format *GSTAAAAMMJJ.tax* pour le nom de fichier. (Autrement dit, entrez **GST** suivi de la date de déclaration, puis ajoutez l’extension de nom de fichier **.tax** .) Par exemple, si la date de génération d’états est le 28 juillet 2010, entrez **GST20100728.tax** comme nom du fichier GIFT.

4. Sélectionnez **OK** pour exporter le fichier GIFT vers le chemin spécifié.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]