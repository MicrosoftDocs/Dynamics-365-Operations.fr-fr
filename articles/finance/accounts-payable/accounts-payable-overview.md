---
title: Vue d’ensemble de la configuration du module Comptabilité fournisseur
description: Cet article décrit les pages que vous utilisez pour paramétrer les fonctionnalités de base et facultatives pour la Comptabilité fournisseur. Il décrit également les étapes de paramétrage que vous devez effectuer avant de commencer à configurer la Comptabilité fournisseur.
author: abruer
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable, DeliveryReason, DeliveryTerms, DestinationCode
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "24671"
- intro-internal
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bce5da0c9593bcfcfb9589f8fe7e09b8acd63726
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906530"
---
# <a name="configure-accounts-payable-overview"></a>Vue d’ensemble de la configuration du module Comptabilité fournisseur

[!include [banner](../includes/banner.md)]

Cet article décrit les pages que vous utilisez pour paramétrer les fonctionnalités de base et facultatives pour la Comptabilité fournisseur. Il décrit également les étapes de paramétrage que vous devez effectuer avant de commencer à configurer la Comptabilité fournisseur.

## <a name="prerequisites-for-accounts-payable-setup"></a>Conditions préalables à la configuration du module Comptabilité fournisseur

Avant d’être en mesure de configurer le module Comptabilité fournisseur, vous devez effectuer les procédures de paramétrage suivantes :

-   En comptabilité :
    -   Pour utiliser des journaux des paiements, vous devez d’abord les paramétrer.
    -   Si vous prévoyez d’effectuer des ajustements du taux de change, paramétrez les codes devise sur la page **Devises**, paramétrez les **types de taux de change** sur la page Types de taux de change, et paramétrez les taux de change des devises sur la page **Taux de change des devises**.
-   Dans le module Gestion de la trésorerie et de la banque, paramétrez les comptes bancaires à utiliser avec des modes de paiement.

## <a name="setup-pages-for-accounts-payable"></a>Configuration des pages pour le module Comptabilité fournisseur

Les pages suivantes permettent de paramétrer les fonctionnalités de base du module Comptabilité fournisseur pour chaque entité juridique. Elles sont répertoriées dans l’ordre de paramétrage recommandé. Pour simplifier le processus de paramétrage, vous pouvez créer des modèles à partir des premiers enregistrements que vous créez. Dans un modèle, les valeurs sont généralement entrées dans de nombreux champs de sorte à refléter les fonctionnalités que l’organisation veut mettre en œuvre pour un type de fournisseur particulier.
1.  Sur la page **Conditions de paiement**, définissez les conditions de paiement à attribuer aux commandes client, aux commandes fournisseur, aux clients et aux fournisseurs et qui déterminent les dates d’échéance des factures. Pour plus d’informations, voir [Définir les commissions de paiement fournisseur](tasks/define-vendor-payment-fees.md).
2.  Sur la page **Modes de paiement - fournisseurs**, créez et tenez à jour les informations sur la manière dont l’organisation paie ses fournisseurs.
3.  Sur la page **Groupes de fournisseurs**, créez et tenez à jour les groupes de fournisseurs qui partagent des paramètres importants pour la validation, le règlement et le paiement, la génération d’états et les prévisions.
4.  Sur la page **Profils de validation fournisseur**, définissez comment les transactions fournisseur sont validés dans la comptabilité.
5.  Sur la page **Paramètres de la comptabilité fournisseur**, définissez des paramètres par défaut qui sont appliqués si aucun paramétrage plus spécifique n’est spécifié, des paramètres pour différents types de fonctionnalités et les diverses souches de numéros pour la comptabilité fournisseur.
6.  Sur la page **Paramétrage d’écran**, définissez le format de différents documents liés aux fournisseurs et utilisés dans l’organisation pour le suivi des réceptions des fournisseurs et pour entrer les motifs du flux de paiements adressés aux fournisseurs.
7.  Sur la page **Fournisseurs**, créez et tenez à jour les comptes fournisseur, ainsi que les administrations fiscales auxquelles votre organisation déclare les taxes.

## <a name="optional-setup-pages-for-accounts-payable"></a>Paramétrage facultatif de pages pour le module Comptabilité fournisseur
Outre les fonctionnalités de base, le module Comptabilité fournisseur est doté d’autres fonctionnalités que vous pouvez paramétrer.

Les pages à paramétrer supplémentaires sont organisés selon leur fonction.

**Stratégies**
-   Sur la page **Stratégie de facture fournisseur**, paramétrez les stratégies de facture fournisseur.

**Rapprochement de factures**

-   Sur la page **Tolérances de totaux de facture**, paramétrez les tolérances pour les totaux de facture.
-   Sur la page **Stratégie de rapprochement**, paramétrez des stratégies de rapprochement à deux et à trois facteurs.
-   Sur la page **Tolérances de prix**, paramétrez les tolérances pour les prix unitaires.
-   Sur la page **Groupes de tolérance de prix d’article**, paramétrez des groupes de tolérance pour le prix des articles.
-   Sur la page **Groupes de tolérance de prix de fournisseurs**, paramétrez des groupes de tolérance pour les prix des fournisseurs.
-   Sur la page **Tolérances en termes de frais**, paramétrez les tolérances pour les frais.

**Workflow**

-   Sur la page **Workflows de la comptabilité fournisseur**, paramétrez les configurations de workflow pour les approbations de journaux et les demandes d’achat.

**Motifs**

-   Sur la page **Motifs de fournisseur**, paramétrez les codes motif.

**Frais**

-   Sur la page **Code frais**, paramétrez les codes pour les frais utilisés dans les commandes fournisseur.
-   Sur la page **Groupe de frais fournisseur**, créez et tenez à jour les groupes de frais pour les fournisseurs.
-   Sur la page **Groupes de frais sur article**, créez et tenez à jour les groupes de frais pour les articles.
-   Sur la page **Frais auto.**, définissez les frais qui sont automatiquement affectés à des commandes.

**Articles supplémentaires**

-   Sur la page **Groupes d’articles supplémentaires – Fournisseur**, créez et tenez à jour des groupes d’articles supplémentaires pour les fournisseurs.
-   Sur la page **Groupes d’articles supplémentaires – Stock**, créez et tenez à jour des groupes d’articles supplémentaires pour les articles.

**Distribution**

-   Sur la page **Conditions de livraison**, créez et tenez à jour les conditions de transfert d’un article d’un vendeur vers un acheteur.
-   Sur la page **Modes de livraison**, créez et tenez à jour les modes de transport utilisés pour la livraison d’une commande du vendeur à l’acheteur..
-   Sur la page **Codes destination**, créez et tenez à jour des identificateurs et des descriptions pour les destinations de livraison.

**Écrans**

-   Sur la page **Textes standard**, créez le texte standard qui s’affiche sur diverses pages.
-   Sur la page **Paramètres de tri d’écran**, paramétrez l’ordre de tri pour les demandes, les listes de réception, les bons de livraison et les factures.
-   Sur la page **Paramétrage de la gestion de l’impression**, paramétrez les informations de gestion d’impression pour les originaux et les copies des pages.

**Paiements**

-   Sur la page **Escomptes de règlement**, paramétrez et gérez les conditions d’obtention d’escomptes de règlement. Les codes escompte de règlement sont associés aux fournisseurs et appliqués aux commandes fournisseur.
-   Sur la page **Echéanciers de paiement**, paramétrez les échéanciers de paiement utilisés pour gérer les paiements par versement des fournisseurs.
-   Sur la page **Jours de paiement**, définissez les jours de paiement utilisés pour le calcul des dates d’échéance et spécifiez les jours de paiement pour un jour spécifique de la semaine ou du mois.
-   Sur la page **Frais de paiement**, créez et tenez à jour les frais de paiement associés aux fournisseurs.
-   Sur la page **Instructions de paiement**, créez et tenez à jour les instructions de paiement.

**Statistiques**

-   Sur la page **Définitions des plages âgées**, paramétrez des intervalles définis par l’utilisateur, permettant d’analyser la distribution par exigibilité des comptes fournisseur.
-   Sur la page **Activité**, créez les codes activité affectés aux fournisseurs.

**Taxe sur les honoraires**

-   Sur la page **Champs de déclaration des honoraires**, vérifiez et tenez à jour les montants minimaux à déclarer à l’IRS (Internal Revenue Service), selon les dernières recommandations de l’administration fiscale.

## <a name="optional-setup-for-other-modules"></a>**Paramétrage facultatif pour d’autres modules**
**Administration d’organisation**

-   Sur la page **Souches de numéros**, paramétrez des groupes de souches de numéros pour les numéros de facture.
-   Sur les pages suivantes, paramétrez les informations d’adresse :
    -   **Configuration de l’adresse**
    -   **Codes NAF**
    -   **Importer des codes postaux**

**Comptabilité**

-   Sur la page **Dimensions financières**, paramétrez les dimensions financières.
-   Sur les pages suivantes, paramétrez les informations fiscales :
    -   **Codes taxe**
    -   **Groupes de taxe**
    -   **Groupes de taxe d’article**
    -   **Groupe de comptes**
    -   **Codes d’exonération fiscale**
    -   **Juridictions fiscales**
    -   **Administrations fiscales**
    -   **Périodes de règlement fiscal**

**Gestion de la trésorerie et de la banque**

-   Sur la page **Codes objectif de paiement**, paramétrez le **code objet de la Banque centrale**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
