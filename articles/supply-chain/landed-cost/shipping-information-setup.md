---
title: Paramétrage des informations d’expédition
description: Cette rubrique décrit comment configurer les informations d’expédition pour le module de coût au débarquement.
author: Weijiesa
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 1ee099b923f3e2140f7f6962795fc6b6e87b913a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690300"
---
# <a name="shipping-information-setup"></a>Paramétrage des informations d’expédition

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment configurer les informations d’expédition pour le module de **coût au débarquement**.

## <a name="description-of-goods"></a><a name="description-of-goods"></a>Description des marchandises

Les descriptions de marchandises aident à identifier un voyage, un conteneur d’expédition ou un folio de marchandises et les marchandises qu’il contient. Sélectionnez une description des marchandises sur l’en-tête du conteneur d’expédition ou l’en-tête du folio.

Pour travailler avec des descriptions de marchandises, accédez à **Prix au débarquement \> Configuration des informations d’expédition \> Description des biens**. Là, vous pouvez afficher, ouvrir, créer et supprimer des enregistrements pour les descriptions des marchandises. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Description des marchandises | Entrez un nom / numéro d’identification unique pour le type de marchandises qui utilisera cette description. |
| Description | Saisissez une description du type de marchandises dans cette catégorie. |

## <a name="vessels"></a><a name="vessels"></a>Bateaux

Un navire est le nom unique d’un navire ou d’un navire utilisé par une compagnie maritime ou une agence. Lorsque vous créez un voyage, vous devez toujours sélectionner ou saisir un navire pour celui-ci. Si vous utilisez souvent les mêmes navires, vous pouvez alors rendre plus rapide et plus facile la création d’un voyage en créant un enregistrement de navire pour chacun d’eux, permettant ainsi aux utilisateurs de sélectionner le navire dans une liste plutôt que d’entrer le nom ou le numéro manuellement chaque fois.

Pour travailler avec les navires, accédez à **Coût au débarquement \> Configuration des informations d’expédition \> Navires**. Là, vous pouvez afficher, ouvrir, créer et supprimer des enregistrements pour les navires. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Bateau | Entrez un nom / numéro d’identification unique pour le navire qui sera utilisé pour transporter des marchandises lors d’un voyage. |
| Description | Permet d’entrer une description du navire. En règle générale, cette description identifie le nom du navire et la compagnie maritime / l’agent. |
| Mode de livraison | Sélectionnez le mode de livraison utilisé par le navire (tel que _Air_, _océan_, ou _Train_). |

## <a name="exporters"></a>Exportateurs

Chaque enregistrement d’exportateur identifie un vendeur ou un exportateur qui peut être défini comme le vendeur pour un voyage. L’exportateur peut être associé à un voyage et utilisé pour la déclaration.

Pour travailler avec les exportateurs, accédez à **Coût au débarquement \> Configuration des informations d’expédition \> exportateurs**. Là, vous pouvez afficher, ouvrir, créer et supprimer des enregistrements pour les exportateurs. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Exportateur | Entrez un nom / numéro d’identification unique pour l’exportateur de marchandises qui seront transportées lors d’un voyage. |
| Description | Permet d’entrer une description de l’exportateur. En règle générale, cette description identifie le nom complet de la compagnie maritime / l’agent. |

## <a name="commodity-codes"></a>Codes marchandise

Vous utilisez les codes marchandises pour faciliter l’identification douanière et le calcul des taux de droits pour les marchandises en voyage. Vous pouvez sélectionner des codes marchandises sur la page **Produits lancés**.

Pour travailler avec les codes de marchandise, accédez à **Coût au débarquement \> Configuration des informations d’expédition \> Codes marchandises**. Là, vous pouvez afficher, ouvrir, créer et supprimer des enregistrements pour les codes marchandises. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Code marchandise | Saisissez un code unique pour ce type de produit. |
| Description | Permet d’entrer la description du type de marchandise. |

## <a name="customs-description"></a>Description de la douane

Les descriptions douanières aident à identifier les marchandises à des fins douanières. Vous pouvez sélectionner une description douanière sur la page **Produits lancés** ou sur les lignes de commande fournisseur.

Pour travailler avec des descriptions de douanes, accédez à **Prix au débarquement \> Configuration des informations d’expédition \> Description des douanes**. Là, vous pouvez afficher, ouvrir, créer et supprimer des enregistrements pour les descriptions des douanes. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Description de la douane | Saisissez un code unique pour ce type de classification douanière. Souvent, ce code sera la description officielle fournie par une autorité douanière pour la description et la valeur qualitative des marchandises. |
| Description | Permet d’entrer la description de la classification douanière. |
