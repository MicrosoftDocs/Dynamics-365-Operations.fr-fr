---
title: Liste des fonctionnalités de taxe vide dans les paramètres de calcul de la taxe
description: Cette rubrique explique comment résoudre un problème où la liste des fonctionnalités de taxe sur la page Paramètres de calcul des taxes est vide.
author: wangchen
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 5b87499042c9c4bfe76e182b170adf4f1cfeac4b
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388570"
---
# <a name="empty-tax-feature-list-in-tax-calculation-parameters"></a>Liste des fonctionnalités de taxe vide dans les paramètres de calcul de la taxe

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="symptom"></a>Problème

Vous avez publié une fonctionnalité dans Regulatory Configuration Service (RCS), afin de pouvoir l’utiliser dans Microsoft Dynamics 365 Finance. Cependant, lorsque vous ouvrez Finances, accédez à **Taxe** \> **Installer** \> **Paramétrage des taxes** \> **Paramètres de calcul des taxes**, et essayez de sélectionner une valeur dans le champ **Nom de paramétrage de la fonctionnalité**, la liste de valeurs est vide.

## <a name="reason"></a>Motif

Ce problème se produit généralement parce que votre environnement Finances et votre environnement RCS ne se trouvent pas sous le même client.

### <a name="rcs-tenant"></a>Client RCS

Procédez comme suit pour trouver l’ID de votre client RCS.

1. Copiez l’URL RCS complète. Par exemple, l’URL peut être `https://rcs-rts-sf-ed22b5aeea8-int-westus2.configure.global.int.dynamics.com/namespaces/817ff7a0-0d77-4aba-9360-3c9749e2c5de/?cmp=dat&mi=RCSFeatureDomainsWorkspace`.
2. Ouvrez une fenêtre de navigateur InPrivate, collez l’URL RCS dans la barre d’adresse, puis sélectionnez **Entrer**. Vous êtes dirigé vers la page de connexion, où vous pouvez trouver l’ID client RCS. Par exemple, si l’URL de la page de connexion est `https://login.microsoftonline.com/d335a570-a05b-4bc5-8eb3-c42c65f9560d`, l’ID client est l’information qui apparaît après `https://login.microsoftonline.com/` ou **d335a570-a05b-4bc5-8eb3-c42c65f9560d**.

### <a name="finance-environment-tenant-id"></a>ID client d’environnement Finance

Pour trouver l’ID client pour votre environnement Finances, suivez les mêmes étapes que vous avez suivies pour trouver le client RCS. Cependant, copiez et collez l’URL complète de votre environnement Finances au lieu de l’URL RCS complète.

## <a name="resolution"></a>Résolution

Si les ID des deux locataires diffèrent, vous rencontrez le problème décrit dans cette rubrique. S’ils sont identiques, vous rencontrez un problème sans rapport. Dans ce cas, nous vous recommandons de contacter le support Microsoft.

### <a name="solution-1"></a>Solution 1

Connectez votre environnement RCS au même client auquel votre environnement Finances est connecté. Ensuite, créez et publiez la fonctionnalité de taxe.

### <a name="solution-2"></a>Solution 2

Partagez la fonctionnalité de taxe avec le client Finances dans RCS.

1. Dans RCS, accédez à **Fonctionnalités de mondialisation** \> **Calcul des taxes**.
2. Sélectionnez la fonctionnalité à partager, puis, sur l’onglet **Organisations**, sélectionnez **Partager avec**.
3. Dans le champ **Nom du domaine d’organisation**, entrez un nom pour le fichier. Par exemple, entrez **contoso.onmicrosoft.com**.
4. Sélectionnez **Partager**.

![Boîte de dialogue déroulante Partager avec l’organisation externe.](media/ShareTaxFeature.png)
