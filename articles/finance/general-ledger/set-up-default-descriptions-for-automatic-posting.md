---
title: Paramétrage des descriptions par défaut pour la validation automatique
description: Cette rubrique explique comment vous pouvez paramétrer le texte par défaut utilisé pour décrire les écritures comptables validées automatiquement dans la comptabilité. Vous pouvez paramétrer le texte de description par défaut à l’aide de texte libre ou de variables fixes.
author: aprilolson
manager: AnnBe
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f5fc73f636a5cac25c259ce2cbae5c5407dca9b7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443003"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a>Paramétrage des descriptions par défaut pour la validation automatique

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment vous pouvez paramétrer le texte par défaut utilisé pour décrire les écritures comptables validées automatiquement dans la comptabilité. Vous pouvez paramétrer le texte de description par défaut à l’aide de texte libre ou de variables fixes.

> [!NOTE]
> Pour certains types de transactions dans certains pays/régions, vous pouvez également inclure du texte provenant de champs de la base de données de Microsoft Dynamics AX associés à ces types de transactions. Pour obtenir une liste des types de transaction, et les pays et régions, voir la section [(Facultatif) Ajout d’un autre libellé aux descriptions par défaut](#optional-add-other-text-to-default-descriptions) plus loin dans cette rubrique.

## <a name="set-up-default-descriptions"></a>Paramétrage des descriptions par défaut

1. Accédez à **Administration d’organisation** \> **Paramétrage** \> **Descriptions par défaut**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Description**, sélectionnez le type de transaction pour lequel créer une description par défaut.
4. Dans le champ **Langue**, sélectionnez la langue à laquelle cette description s’applique.
5. Dans le champ **Texte**, entrez une description par défaut. Vous pouvez entrer le texte dans le champ, ou utiliser une ou plusieurs des variables de texte libre suivantes :

    - **%1** – Permet d’ajouter la date de transaction.
    - **%2** – Permet d’ajouter un identificateur correspondant au type de document validé dans la comptabilité. Par exemple, pour les types de transactions liés aux factures, la variable **%2** ajoute le numéro de facture.
    - **%3** – Permet d’ajouter un identificateur lié au type de document validé dans la comptabilité. Par exemple, pour les types de transactions liés aux factures, la variable **%3** ajoute le numéro de compte client.

## <a name="optional-add-other-text-to-default-descriptions"></a>(Facultatif) Ajout d’un autre libellé aux descriptions par défaut

Pour certains types de transactions dans certains pays ou régions, les descriptions par défaut peuvent également du texte provenant de champs de vos données associés à ces types de transactions. Les listes suivantes indiquent les types de transactions et les pays et régions pour lesquels cette option est disponible.

**Types de transactions**

Vous pouvez ajouter un autre libellé aux descriptions par défaut pour les types de transactions liés aux types de documents suivants :

- Factures client
- Avoirs du client
- Paiements au comptant du client
- Paiements fournisseur
- Commandes client
- Commandes fournisseur
- Journaux de stock
- Planification
- Immobilisations

**Pays et régions**

Cette option est disponible pour les pays et régions suivants :

- Brésil
- Chine
- République tchèque
- Europe de l’Est
- Hongrie
- Inde
- Japon
- Lituanie
- Lettonie
- Pologne
- Russie

### <a name="add-text-to-default-descriptions"></a>Ajout d’un autre libellé aux descriptions par défaut

Après avoir suivi les étapes de la section [Paramétrage des descriptions par défaut](#set-up-default-descriptions), précédemment dans cette rubrique, procédez comme suit pour ajouter un autre libellé aux descriptions par défaut.

1. Dans l’organisateur **Paramètres**, sélectionnez **Ajouter**.
2. Dans le champ **Table de référence**, sélectionnez la table de base de données à partir de laquelle ajouter des données de paramétrage à la description.
3. Dans le champ **Champ de référence**, sélectionnez le champ à partir duquel ajouter des données de paramétrage à la description.
4. Répétez les étapes 1 à 3 pour ajouter d’autres paramètres.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]