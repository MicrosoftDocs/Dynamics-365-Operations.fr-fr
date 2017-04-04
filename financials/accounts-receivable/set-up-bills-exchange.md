---
title: "Paramétrage de lettres de change"
description: "Cette rubrique décrit la procédure de paramétrage des lettres de change."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269964
ms.assetid: f2077165-da90-4359-ab12-e05717728dc7
ms.search.region: global
ms.author: abruer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ce2142d946085d8bfc577accf1bb31a89ea29156
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bills-of-exchange"></a>Paramétrage de lettres de change

Cette rubrique décrit la procédure de paramétrage des lettres de change.

Une lettre de change est un ordre écrit ou électronique d'un client spécifiant qu'un tiers, généralement une banque, doit payer un montant défini à la société. Lorsque vous utilisez une lettre de change pour payer une facture de commande client ou une facture financière, vous créditez le compte client. Ce crédit est sécurisé par la lettre de change jusqu'à ce que le client paie cette dernière à la banque. Généralement, vous réglerez la facture avec la lettre de change à la date d'échéance. Lorsque vous recevez une notification de la banque vous informant que la lettre de change a été honorée, vous pouvez la clôturer. Vous pouvez créer une lettre de change via votre banque à l'un des moments suivants :

-   à la date d'échéance. Cette approche est connue comme remise à l'encaissement.
-   Avant la date d'échéance, généralement la date de remise spécifiée dans les conditions de paiement paramétrées pour le client. Lorsque vous validez la transaction, le montant de remise est validé dans un compte de dépense. Le montant restant constitue un passif pour vous, jusqu'à ce que la banque reçoive le paiement du client. Cette approche est connue comme remise à l'escompte.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Paramétrer les profils de validation des lettres de change
Utilisez ** des profils de validation client ** la page permet de paramétrer les profils de validation à utiliser avec les lettres de change, les lettres de change impayées, les remises à l'encaissement, et les remises à l'escompte. Dans ** compte collectif ** le champ, sélectionnez le compte collectif sur lequel valider les montants des lettres de change. Ce compte est débité ou crédité, selon le type de transaction de lettre de change :
-   Pour les lettres de change, ce compte est débité lorsqu'une lettre de change est validée, et qu'elle a crédité lorsqu'une remise à l'escompte ou une remise à l'encaissement est validée.
-   Pour les lettres de change impayées, ce compte est débité lorsqu'une lettre de change impayée est validée.
-   Pour les remises à l'encaissement, ce compte est débité lorsqu'une remise à l'encaissement est validée.
-   Pour les remises à l'escompte, ce compte est débité lorsqu'une remise à l'escompte est validée.

Dans ** compte de règlement ** le champ, sélectionnez le compte de disponibilités pour valider les montants des lettres de change. Ce compte est débité lorsqu'une lettre de change est réglée. Dans ** des acomptes de taxe ** le champ, sélectionnez le compte collectif sur lequel valider les montants des taxes lorsque des lettres de change sont utilisées pour les acomptes. Dans ** des engagements pour le compte de remise ** le champ, sélectionnez le compte sur lequel valider le montant de remise pour les remises à l'escompte sur. Ce compte est crédité lorsqu'une remise à l'escompte est validée.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>Définition des paramètres des ventes pour les lettres de change
Sous ** des paramètres des ventes ** la page, les profils de validation par défaut pour les lettres de change sont entrés sur ** comptabilité et taxe ** l'onglet. Les souches de numéros sont définies sur ** des souches de numéros ** l'onglet.
Paramétrage du nom des journaux des lettres de change
------------------------------------------

Sous ** des noms de journaux ** la page, créez au moins cinq noms de journal à utiliser pour les lettres de change. Voici les types de journaux :
-   ** Lettre de change client ** – Permet de créer un nom de journal pour le journal des lettres de change.
-   ** Lettre de change impayées client ** – Permet de créer un nom de journal pour le journal des lettres de change impayées.
-   ** Le client renouvellement la lettre de change ** – Créer un nom de journal pour le journal de renouvellement des lettres de change.
-   ** Remise en banque client ** – Permet de créer un nom de journal pour le journal des remises.
-   ** Lettre de change de règlement client ** – Permet de créer un nom de journal pour le journal des lettres de change de règlement.

Dans la page de N° document de journal pour chaque journal des lettres de change, entrez les informations sur la lettre de change sur ** lettre de change ** l'onglet. Une fois les lignes de journal des lettres de change soient validées, vous pouvez les afficher dans ** recherche de journal des lettres de change ** la page et ** les statistiques de lettres de change ** la page.
Paramétrage de modes de paiement pour les lettres de change
-----------------------------------------------

Sous ** modes de paiement ** la page, paramétrez au moins un mode de paiement pour les lettres de change. Si vous faites affaires avec plusieurs banques, paramétrez un mode de paiement qui correspond au format de remise à chaque banque demande pour les lettres de change.
Paramétrage des frais de paiement des lettres de change
-----------------------------------------

Les frais de paiement sont les frais associés au processus de collecte des paiements réalisé auprès des clients. Les plusieurs lignes de paramétrage de frais de paiement peuvent être associées chaque frais de paiement. Vous pouvez utiliser des lignes de paramétrage pour contrôler la manière dont les montants par défaut pour les frais de paiement sont calculés. Par exemple, vous pouvez créer des lignes de paramétrage pour les modes de paiement, les spécifications de paiement, les devises et les périodes. Vous pouvez également créer des lignes de paramétrage pour un pourcentage ou un montant basé sur des intervalles en jours. Par exemple, vous pouvez paramétrer un pourcentage d'intérêt basé sur la durée d'un retard de paiement. Si les frais individuels de frais bancaires pour la remise autre type, comme ** collection ** ou ** remise **, paramétrez une ligne distincte de frais de paiement pour chaque type de remise.
Paramétrage des frais de remise pour les fichiers de remise en banque
------------------------------------------------

Sous ** des comptes bancaires ** la page, vous pouvez paramétrer des frais de remise cet les frais bancaires pour chaque fichier de remise généré. Les frais de remise sont validés lorsque la remise a été confirmée et que les montants des frais réalisés sont connus. Les frais de remise diffèrent des frais de paiement, collectés auprès de les clients et associés aux lignes de journal.
Paramétrage des modèles de document des lettres de change
---------------------------------------------

Sous ** des comptes bancaires ** la page, cliquez sur ** paramétrage **, et de spécifier le modèle de document requis pour chaque compte bancaire pour lequel vous allez générer des documents de lettre de change imprimés.
Paramétrage des clients pour les lettres de change
--------------------------------------

Sous ** les clients ** paginez-, pour chaque client qui a accepté de payer à l'aide d'une lettre de change, vous pouvez paramétrer un mode de paiement par défaut pour les lettres de change sur ** des valeurs par défaut de paiement ** l'onglet.




