---
title: Vue d’ensemble du débit direct SEPA
description: L’Espace unique de paiement en euros (SEPA) est défini par la Commission européenne et stipule que tous les paiements électroniques sont considérés comme locaux, quel que soit le pays/la région où la personne, l’entreprise ou l’organisation et la banque sont localisées. Il n’existe aucune différence entre les paiements nationaux et transfrontières. Le SEPA inclut les 28 états membres de l’Union européenne (EU), ainsi que l’Islande, le Liechtenstein, la Norvège, la Suisse, Monaco et San Marin. Le SEPA permet de former un marché unique pour les transactions de paiement dans l’Espace économique européen. Enfin, le SEPA est supposé réduire le nombre de formats de paiement pour les banques, les entreprises et les personnes.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, CustBankAccounts, CustParameters, CustTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 11144
ms.assetid: 3277c9b6-e46e-40c9-aa76-9b0449467842
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf3872a47a92509af5857c0c1aec0d4da4095d19
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835266"
---
# <a name="sepa-direct-debit-overview"></a>Vue d’ensemble du débit direct SEPA

[!include [banner](../includes/banner.md)]

L’Espace unique de paiement en euros (SEPA) est défini par la Commission européenne et stipule que tous les paiements électroniques sont considérés comme locaux, quel que soit le pays/la région où la personne, l’entreprise ou l’organisation et la banque sont localisées. Il n’existe aucune différence entre les paiements nationaux et transfrontières. Le SEPA inclut les 28 états membres de l’Union européenne (EU), ainsi que l’Islande, le Liechtenstein, la Norvège, la Suisse, Monaco et San Marin. Le SEPA permet de former un marché unique pour les transactions de paiement dans l’Espace économique européen. Enfin, le SEPA est supposé réduire le nombre de formats de paiement pour les banques, les entreprises et les personnes.   

<a name="what-is-the-goal-of-sepa-direct-debits"></a>Quel est l’objectif des débits directs SEPA ?
---------------------------------------

Un débit direct SEPA permet à un créditeur d’encaisser des fonds à partir du compte bancaire d’un client, à condition que le client ait signé un mandat au créditeur. Le client signe un mandat qui autorise le créditeur à encaisser un paiement et demande à la banque du client de payer la créance. 

Les débits directs SEPA créent, pour la première fois, un instrument de paiement qui peut être utilisé pour les débits nationaux et transfrontières dans l’ensemble des 32 pays/régions SEPA. 

Deux modèles sont disponibles : le modèle de débit direct SEPA Core et le modèle de débit direct SEPA interentreprise (B2B). Les deux modèles utilisent le même format de fichier.

## <a name="what-is-the-core-direct-debit-scheme"></a>Qu’est-ce que le modèle de débit direct Core ?
Le modèle de débit direct SEPA Core est le modèle de base. Il présente les attributs suivants :
-   Le transfert de fonds est en euros (même si les comptes bancaires contiennent des fonds dans d’autres devises).
-   Le client et le créditeur doivent tous deux détenir un compte auprès d’un organisme de crédit situé dans la zone SEPA.
-   Le client doit accorder un mandat signé au créditeur.
-   Les mandats expirent 36 mois après le dernier encaissement réalisé.
-   Le créditeur doit stocker les mandats tant qu’ils sont valides et au moins 14 mois après le dernier encaissement.
-   Le modèle peut être utilisé pour les recouvrements de débit direct uniques (une fois) ou récurrents.
-   Les clients disposent du droit de recevoir un remboursement « sans poser de question » jusqu’à huit semaines après le débit de leur compte.

## <a name="what-is-the-sepa-business-to-business-b2b-direct-debit-scheme"></a>Qu’est-ce que le modèle de débit direct SEPA interentreprise (B2B) ?
Le modèle de débit direct SEPA B2B s’applique aux transactions d’entreprise à entreprise et se base sur le modèle de débit direct SEPA Core. Les principales différences sont les suivantes :
-   Le modèle de débit direct SEPA B2B n’est pas autorisé lorsque le client est un individu (consommateur).
-   Le client n’est pas autorisé à obtenir le remboursement d’une transaction autorisée.
-   Les banques des clients doivent s’assurer que l’encaissement est autorisé, en comparant l’encaissement et les informations de mandat. Les banques des clients et les clients doivent accepter la vérification qui sera exécutée pour chaque débit direct.
-   Le modèle offre un délai plus court pour présenter les débits directs et réduit la période de retour.

## <a name="can-i-use-the-cor1-scheme-for-direct-debit-mandates"></a>Puis-je utiliser le schéma COR1 pour les mandats de débit direct ?
Oui. Vous pouvez utiliser le modèle COR1 pour des mandats de débit direct SEPA en Autriche, Belgique, Allemagne, France, Italie, Espagne, et aux Pays-Bas. Le schéma prévoit une période de notification préalable plus courte pour le recouvrement de débit direct du créditeur.

## <a name="what-are-international-bank-account-numbers-iban-and-bank-identifier-codes-bic"></a>Que sont les numéros de compte bancaire internationaux (IBAN) et les codes identificateur de banque (Bank Identifier Codes, BIC) ?
Le numéro de compte bancaire international (IBAN) et le code identificateur de banque (BIC) permettent d’identifier n’importe quel compte dans les 32 pays/régions SEPA. Entrez le code BIC dans le champ Code SWIFT et le code IBAN dans le champ IBAN. Les deux champs sont situés dans l’organisateur Identification supplémentaire sous l’onglet Compte en banque de la page Comptes bancaires. Cela vaut pour le compte bancaire du créditeur et celui du client.

## <a name="where-do-i-enter-creditor-identifiers-direct-debit-ids"></a>Où entrer les identificateurs de créditeur (ID de débit direct) ?
Dans le SEPA, chaque créditeur est identifié par un identificateur unique de créditeur. Cet identificateur permet au client et à la banque du client de filtrer chaque débit direct, puis de traiter ou rejeter le débit direct en fonction des instructions du client. Les créditeurs doivent demander cet identificateur à leur banque. Entrez cet identificateur dans le champ ID débit direct du compte bancaire pour l’entité juridique.

## <a name="what-are-mandates"></a>Que sont les mandats ?
Le client signe un mandat qui autorise le créditeur à encaisser un paiement et demande à la banque du client de payer la créance. Le client peut émettre le mandat imprimé ou par voie électronique. Par défaut, le mandat expire 36 mois après le dernier encaissement du débit direct.

## <a name="where-do-i-specify-the-sepa-direct-debit-file-format-iso-20022"></a>Où dois-je spécifier le format de fichier de débit direct SEPA (ISO 20022) ?
Les formats de données SEPA sont basés sur les normes de message ISO 20022. Vous sélectionnerez la case États électroniques génériques et le format de débit direct SEPA comme configuration de format d’exportation lors de la configuration des modes de paiement de la comptabilité client. Vous devez utiliser ce mode de paiement lorsque vous générez un fichier de paiement dans un journal des paiements client.

## <a name="in-what-file-formats-can-i-generate-sepa-direct-debit-payment-files"></a>Dans quels formats de fichier est-ce que je peux générer des fichiers de paiement de débit direct SEPA ?
Vous pouvez générer des fichiers de paiement électronique pour les débits directs SEPA dans les formats suivants :
-   Fichiers de paiement par débit direct SEPA au format de fichier XML PAIN.008.001.02 pour la Belgique, l’Allemagne, l’Espagne, la France, l’Italie, et les Pays-Bas.
-   Fichiers de paiement de débit direct SEPA au format du fichier XML PAIN.008.001.02 pour l’Autriche, et au format du fichier XML PAIN.008.003.02 pour l’Allemagne.

## <a name="how-do-refunds-and-returns-work-with-sepa-direct-debits"></a>Comment les remboursements et les retours fonctionnent-ils avec les débits directs SEPA ?
Dans les deux modèles de débit direct SEPA, les clients ont certains droits de remboursement. Le client peut rappeler toutes les transactions autorisées pendant une période de huit semaines après la date d’échéance sans donner de motif. Dans le cas de transactions non autorisées, la période est étendue à 13 mois après la date d’échéance. Les contrepassations de tous les paiements qui ont été effectuées sont accomplies manuellement à l’aide du bouton Annuler le paiement dans l’écran Transactions client.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]