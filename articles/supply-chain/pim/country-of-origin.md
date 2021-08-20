---
title: Pays d’origine
description: De nombreuses organisations délivrent des certificats à leurs fournisseurs pour garantir que les produits répondent à des normes de certification spécifiques. Ces certificats dépendent souvent du pays d’origine. Cette rubrique fournit des informations sur la fonction du pays d’origine, qui vous permet de lier un produit à son pays d’origine et de suivre ses certifications de produit.
author: dasani-madipalli
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: fde4211e4449c28eda8ac7a23ddfc346d2c7e8359d9e473821bdefe76db65616
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739776"
---
# <a name="country-of-origin"></a>Pays d’origine

[!include [banner](../includes/banner.md)]

De nombreuses organisations délivrent des certificats à leurs fournisseurs pour garantir que les produits répondent à des normes de certification spécifiques. Ces certificats dépendent souvent du pays d’origine. La fonction du pays d’origine vous permet de lier un produit à son pays d’origine et de suivre ses certifications de produit.

## <a name="turn-on-the-country-of-origin-feature"></a>Activer la fonction du pays d’origine

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des informations sur les produits*
- **Nom de la fonctionnalité :** *Fonctionnalité de gestion du pays d’origine*

## <a name="configure-source-and-destination-countries"></a>Configurer les pays source et de destination

Avant d’émettre un certificat pour un produit, vous devez lier le produit à son pays de destination et à son pays d’origine.

1. Accédez à **Gestion des informations sur les produits \> Paramétrage \> Conformité des produits \> Pays d’origine \> Règles du pays d’origine**.
2. Sélectionnez une configuration de pays existante à modifier ou sélectionnez **Nouveau** dans le volet Actions pour créer une nouvelle configuration de pays.
3. Définissez les valeurs suivantes pour le pays sélectionné ou le nouveau pays.

    | Champ | Description |
    |---|---|
    | numéro d’article | Permet de sélectionner le numéro d’article du produit. |
    | Pays de destination | Sélectionnez le pays vers lequel vous envoyez le produit. |
    | Pays d’origine | Sélectionnez le pays à partir duquel vous expédiez le produit. |

Le but de cette configuration est de vous aider à générer un rapport de nomenclature (BOM) dans lequel vous pouvez inclure le pays d’origine de chaque pièce pour laquelle les pays d’origine et de destination sont spécifiés. Ce rapport vous permet d’obtenir une image globale de l’origine de vos pièces et de leur destination.

## <a name="keep-track-of-vendor-certificates"></a>Garder la trace des certificats des fournisseurs

Vous pouvez utiliser la page **Certificats de fournisseur du pays d’origine** pour garder une trace des certificats que vous délivrez aux fournisseurs.

Vous devez décider quels documents de certificat vous émettrez et comment vous les transmettrez aux clients. Cette fonctionnalité vous aide à garder une trace de vos certificats. Elle vous permet également de choisir si les numéros de certificat pertinents apparaissent sur les factures, les bons de livraison et/ou les confirmations de commande.

Pour paramétrer des informations de certificat, procédez comme suit :

1. Accédez à **Gestion des informations sur les produits \> Paramétrage \> Conformité des produits \> Pays d’origine \> Certificats fournisseur du pays d’origine**.
2. Sélectionnez une configuration de certificat existante à modifier ou sélectionnez **Nouveau** dans le volet Actions pour créer une nouvelle configuration de certificat.
3. Définissez les paramètres suivants pour le certificat sélectionné ou le nouveau certificat.

    | Champ | Description |
    |---|---|
    | Compte fournisseur | Sélectionnez le fournisseur pour lequel vous avez émis le certificat. |
    | numéro d’article | Sélectionnez l’article pour lequel vous avez émis le certificat. |
    | Pays/région | Le pays ou la région de destination où vous devez utiliser ce certificat. |
    | Numéro de certificat | Saisissez le numéro d’identification du certificat que vous avez émis. |
    | Effective | Sélectionnez la date de début de validité du certificat.|
    | Expiration | Sélectionnez la date de fin de validité du certificat. |
    | Imprimer sur la facture | Cochez cette case pour imprimer le numéro de certificat sur les factures adressées au pays spécifié pendant la plage de dates spécifiée. |
    | Imprimer sur le bon de livraison | Cochez cette case pour imprimer le numéro de certificat sur les bons de livraison adressés au pays spécifié pendant la plage de dates spécifiée. |
    | Imprimer sur la commande client | Cochez cette case pour imprimer le numéro de certificat sur les commandes client adressées au pays spécifié pendant la plage de dates spécifiée. |

## <a name="include-the-country-of-origin-on-bom-reports"></a>Inclure le pays d’origine dans les rapports de nomenclature

Lorsque vous générez un rapport de nomenclature, vous pouvez inclure le pays d’origine de chaque pièce pour laquelle vous avez spécifié les pays d’origine et de destination dans la page **Règles du pays d’origine**.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez ou créez un produit pour ouvrir sa page **Détails des produits lancés**.
1. Dans le volet Actions, sous l’onglet **Ingénieur**, dans le groupe **Nomenclature**, sélectionnez **Concepteur**.
1. Sur la page qui s’affiche, dans le volet Actions,, sélectionnez **Nomenclature \> Imprimer**.
1. Dans la boîte de dialogue **Lignes de nomenclature**, définissez le champ **Pays de destination** comme le pays de destination que vous souhaitez afficher sur votre rapport.
1. Cliquez sur **OK**.

Un rapport contenant des informations sur le pays d’origine de chaque pièce est généré et affiché. Voici un exemple de rapport.

![Rapport de pays d’origine.](media/country-of-origin-report.png "Rapport de pays d’origine")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]