---
title: "Paramétrage de paiements centralisés"
description: "Cette procédure permet de préparer le traitement des paiements dans une entité juridique au nom d'autres entités juridiques de votre organisation."
author: kweekley
manager: AnnBe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62243
ms.assetid: ffd17b5f-9aea-40e0-be49-d8702f615256
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c91d02bfb5e51a7eb34234abb982242bc9f7610f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-centralized-payments"></a>Paramétrage de paiements centralisés

[!include[banner](../includes/banner.md)]


Cette procédure permet de préparer le traitement des paiements dans une entité juridique au nom d'autres entités juridiques de votre organisation. Avant de commencer, vous devez effectuer les procédures de paramétrage suivantes :

-   Créez les entités juridiques.
-   Paramétrez la comptabilité et les plans de comptes.
-   Définissez les Paramètres d'Achats et les Paramètres de Ventes (en fonction des modules qui utilisent les paiements centralisés).
-   Paramétrez la comptabilité intersociétés.

## <a name="set-up-an-organizational-hierarchy-for-centralized-payments"></a>Paramétrage d'une hiérarchie d'organisation pour les paiements centralisés
Vous devez paramétrer une hiérarchie d'organisation pour les paiements centralisés. La même hiérarchie d'organisation permet de traiter les paiements fournisseur centralisés et les paiements client centralisés. **Remarque :** En ce qui concerne les paiements centralisés, la structure de la hiérarchie n'a pas d'importance. Les entités juridiques de la hiérarchie pourront traiter les paiements au nom des autres entités juridiques de la hiérarchie. Sur la page **Hiérarchies de l'organisation**, vous pouvez créer une hiérarchie d'organisation. Dans le champ **Objectif**, vous devez sélectionner **Paiements centralisés**. 

## <a name="set-up-an-intercompany-account-for-centralized-payments"></a>Paramétrage d'un compte intersociétés pour les paiements centralisés
Lorsque des transactions de paiement de l'entité juridique actuelle sont réglées avec des factures dans d'autres entités juridiques, les transactions d'échéance appropriées sont créées pour chaque entité juridique. Vous devez spécifier l'entité juridique lorsque des montants d'escompte de règlement applicables et des montants de profit réalisé ou de perte réalisée sont validés. Avant de commencer, choisissez l'entité juridique que vous allez utiliser pour traiter les paiements client et fournisseur. Si une entité juridique traite les paiements fournisseur, mais si une autre entité juridique traite les paiements client, vous devrez passer d'une entité à l'autre. Dans la page **Comptabilité intersociétés**, sélectionnez un enregistrement de relation intersociétés pour une entité juridique au nom de laquelle vous traiterez les paiements. 

Dans l'onglet **Paiements centralisés**, choisissez s'il faut valider les escomptes de règlement dans l'entité juridique de paiement (ou une autre transaction qui diminue le solde du compte fournisseur) ou dans l'entité juridique de facturation (ou une autre transaction qui augmente le solde du compte fournisseur). Cette sélection est associée au champ **Administration d'escompte de règlement** des pages **Paramètres d'Achats** et **Paramètres des ventes**. Pour les tolérances de trop-perçus et de différences minimes, utilisez le paramétrage dans l'entité juridique de paiement. Pour les tolérances de moins-perçus et de différences minimes, utilisez le paramétrage dans l'entité juridique de facture.

## <a name="map-vendor-accounts-across-legal-entities"></a>Mappage des comptes fournisseur dans les entités juridiques
Si vous payez un fournisseur à partir d'une entité juridique et si vous souhaitez sélectionner des factures pour ce fournisseur dans d'autres entités juridiques, vous devez vous assurer que les comptes fournisseur correspondants dans chaque entité juridique utilisent le même ID carnet d'adresses. Si vous recevez un paiement d'un client qui paie des factures dans plusieurs entités juridiques, veillez à ce que tous les comptes client correspondants dans chaque entité juridique utilisent le même ID carnet d'adresses.

## <a name="set-up-posting-profiles-for-centralized-payments"></a>Paramétrage des profils de validation pour les paiements centralisés
Lorsque vous créez un paiement dans une entité juridique qui règle les factures dans d'autres entités juridiques, les ID de profil de validation doivent être identiques dans toutes les entités juridiques. Pour garantir une création correcte des paiements, dans chaque entité juridique de la facture, paramétrez un profil de validation correspondant aux profils de validation utilisés dans l'entité juridique de paiement. Passez à la première entité juridique de la facture, puis sur la page **Profils de validation fournisseur**, vous pouvez créer un profil de validation ou en modifier un existant. Les sélections que vous effectuez pour le profil de validation dans l'entité juridique de facture ne doivent pas forcément correspondre au paramétrage du profil de validation dans l'entité juridique de paiement.

## <a name="set-up-methods-of-payment-for-centralized-payments"></a>Paramétrage de modes de paiement pour les paiements centralisés
Lorsque vous créez un paiement dans une entité juridique qui règle les factures dans d'autres entités juridiques, les ID mode de paiement doivent être identiques dans toutes les entités juridiques. Pour garantir la bonne création des paiements, dans chaque entité juridique de facture, paramétrez un mode de paiement correspondant aux modes de paiement utilisés dans l'entité juridique de paiement. Passez à la première entité juridique de facture, puis sur la page **Modes de paiement**, vous pouvez créer un mode de paiement ou modifier un mode de paiement existant. Les sélections que vous effectuez pour le mode de paiement dans l'entité juridique de facture ne doivent pas forcément correspondre au paramétrage du mode de paiement dans l'entité juridique de paiement.

## <a name="set-up-default-descriptions"></a>Paramétrage des descriptions par défaut
Vous pouvez définir des descriptions par défaut pour les N° document de règlement intersociétés. La description par défaut est incluse dans les transactions d'échéance au cours du traitement du règlement de société croisée. Sur la page **Descriptions par défaut**, vous pouvez créer de nouvelles descriptions pour les champs **Règlement client intersociétés** et **Règlement fournisseur intersociétés** en sélectionnant une langue, puis en entrant le texte.




