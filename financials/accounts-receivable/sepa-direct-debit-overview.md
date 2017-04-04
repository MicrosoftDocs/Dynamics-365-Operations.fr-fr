---
title: "Vue d&quot;ensemble du débit direct SEPA"
description: "L&quot;Espace unique de paiement en euros (SEPA) est défini par la Commission européenne et stipule que tous les paiements électroniques sont considérés comme locaux, quel que soit le pays/la région où la personne, l&quot;entreprise ou l&quot;organisation et la banque sont localisées. Il n&quot;existe aucune différence entre les paiements nationaux et transfrontières. Le SEPA inclut les 28 états membres de l&quot;Union européenne (EU), ainsi que l&quot;Islande, le Liechtenstein, la Norvège, la Suisse, Monaco et San Marin. Le SEPA permet de former un marché unique pour les transactions de paiement dans l&quot;Espace économique européen. Enfin, le SEPA est supposé réduire le nombre de formats de paiement pour les banques, les entreprises et les personnes."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankAccountTable, CustBankAccounts, CustParameters, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11144
ms.assetid: 3277c9b6-e46e-40c9-aa76-9b0449467842
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 849fea6030c665e1724c3fc8f31353dd4bafed27
ms.lasthandoff: 03/31/2017


---

# <a name="sepa-direct-debit-overview"></a>Vue d'ensemble du débit direct SEPA

L'Espace unique de paiement en euros (SEPA) est défini par la Commission européenne et stipule que tous les paiements électroniques sont considérés comme locaux, quel que soit le pays/la région où la personne, l'entreprise ou l'organisation et la banque sont localisées. Il n'existe aucune différence entre les paiements nationaux et transfrontières. Le SEPA inclut les 28 états membres de l'Union européenne (EU), ainsi que l'Islande, le Liechtenstein, la Norvège, la Suisse, Monaco et San Marin. Le SEPA permet de former un marché unique pour les transactions de paiement dans l'Espace économique européen. Enfin, le SEPA est supposé réduire le nombre de formats de paiement pour les banques, les entreprises et les personnes.   

<a name="what-is-the-goal-of-sepa-direct-debits"></a>Quel est l'objectif des débits SEPA ?
---------------------------------------

Un débit direct SEPA permet à un créditeur pour collecter les fonds le compte bancaire d'un client, à condition que un mandat signé ait été accordé par le client au créditeur. Le client signe un mandat qui autorise le créditeur à encaisser un paiement et demande à la banque du client de payer la créance. 

Les débits directs SEPA créent, pour la première fois, un instrument de paiement qui peut être utilisé pour les débits nationaux et transfrontières dans l'ensemble des 32 pays/régions SEPA. 

Deux modèles sont disponibles : le modèle de débit direct SEPA Core et le modèle de débit direct SEPA interentreprise (B2B). Les deux modèles utilisent le même format de fichier.

## <a name="what-is-the-core-direct-debit-scheme"></a>Qu'est-ce que le modèle de débit direct Core ?
Le modèle de débit direct SEPA Core est le modèle de base. Il présente les attributs suivants :
-   Le transfert de fonds est en euros (même si les comptes bancaires contiennent des fonds dans d'autres devises).
-   Le client et le créditeur doivent tous deux détenir un compte auprès d'un organisme de crédit situé dans la zone SEPA.
-   Le client doit accorder un mandat signé au créditeur.
-   Les mandats expirent 36 mois après le dernier encaissement réalisé.
-   Le créditeur doit stocker les mandats tant qu'ils sont valides et au moins 14 mois après le dernier encaissement.
-   Le modèle peut être utilisé pour les recouvrements de débit direct uniques (une fois) ou récurrents.
-   Les clients disposent du droit de recevoir un remboursement « sans poser de question » jusqu'à huit semaines après le débit de leur compte.

## <a name="what-is-the-sepa-business-to-business-b2b-direct-debit-scheme"></a>Qu'est-ce que le modèle de débit direct SEPA interentreprise (B2B) ?
Le modèle de débit direct SEPA B2B s'applique aux transactions d'entreprise à entreprise et se base sur le modèle de débit direct SEPA Core. Les principales différences sont les suivantes :
-   Le modèle de débit direct SEPA B2B n'est pas autorisé lorsque le client est un individu (consommateur).
-   Le client n'est pas autorisé à obtenir le remboursement d'une transaction autorisée.
-   Les banques des clients doivent s'assurer que l'encaissement est autorisé, en comparant l'encaissement et les informations de mandat. Les banques des clients et les clients doivent accepter la vérification qui sera exécutée pour chaque débit direct.
-   Le modèle offre un délai plus court pour présenter les débits directs et réduit la période de retour.

## <a name="can-i-use-the-cor1-scheme-for-direct-debit-mandates"></a>Puis-je utiliser le schéma COR1 pour les mandats de débit direct ?
Oui. Vous pouvez utiliser le modèle COR1 pour des mandats de débit direct SEPA en Autriche, Belgique, Allemagne, France, Italie, Espagne, et aux Pays-Bas. Le schéma prévoit une période de notification préalable plus courte pour le recouvrement de débit direct du créditeur.

## <a name="what-are-international-bank-account-numbers-iban-and-bank-identifier-codes-bic"></a>Que sont les numéros de compte bancaire internationaux (IBAN) et les codes identificateur de banque (Bank Identifier Codes, BIC) ?
Le numéro de compte bancaire international (IBAN) et le code identificateur de banque (BIC) permettent d'identifier n'importe quel compte dans les 32 pays/régions SEPA. Entrez le BIC dans le champ Code SWIFT et l'IBAN dans le champ IBAN. Les deux champs sont situés dans l'organisateur Identification supplémentaire sous l'onglet Compte en banque de la page Comptes bancaires. Cela vaut pour le compte bancaire du créditeur et celui du client.

## <a name="where-do-i-enter-creditor-identifiers-direct-debit-ids"></a>Où entrer les identificateurs de créditeur (ID de débit direct) ?
Dans le SEPA, chaque créditeur est identifié par un identificateur unique de créditeur. Cet identificateur permet au client et à la banque du client de filtrer chaque débit direct, puis de traiter ou rejeter le débit direct en fonction des instructions du client. Les créditeurs doivent demander cet identificateur à leur banque. Entrez cet identificateur dans le champ ID débit direct du compte bancaire pour l'entité juridique.

## <a name="what-are-mandates"></a>Que sont les mandats ?
Le client signe un mandat qui autorise le créditeur à encaisser un paiement et demande à la banque du client de payer la créance. Le client peut émettre le mandat imprimé ou par voie électronique. Par défaut, le mandat expire 36 mois après le dernier encaissement du débit direct.

## <a name="where-do-i-specify-the-sepa-direct-debit-file-format-iso-20022"></a>Où dois-je spécifier le format de fichier de débit direct SEPA (ISO 20022) ?
Les formats de données SEPA sont basés sur les normes de message ISO 20022. Vous vérifierez la case à cocher électronique générique de génération d'états et sélectionnez le format de débit direct SEPA comme configuration de format d'exportation lorsque vous configurez les modes de paiement des ventes. Vous devez utiliser ce mode de paiement lorsque vous générez un fichier de paiement dans un journal des paiements client.

## <a name="in-what-file-formats-can-i-generate-sepa-direct-debit-payment-files"></a>Dans quels formats de fichier est-ce que je peux générer des fichiers de paiement de débit direct SEPA ?
Vous pouvez générer des fichiers de paiement électronique pour les débits directs SEPA dans les formats suivants :
-   Fichiers de paiement par débit direct SEPA au format de fichier XML PAIN.008.001.02 pour la Belgique, l'Allemagne, l'Espagne, la France, l'Italie, et les Pays-Bas.
-   Fichiers de paiement de débit direct SEPA au format du fichier XML PAIN.008.001.02 pour l'Autriche, et au format du fichier XML PAIN.008.003.02 pour l'Allemagne.

## <a name="how-do-refunds-and-returns-work-with-sepa-direct-debits"></a>Comment les remboursements et les retours fonctionnent-ils avec les débits directs SEPA ?
Dans les deux modèles de débit direct SEPA, les clients ont certains droits de remboursement. Le client peut rappeler toutes les transactions autorisées pendant une période de huit semaines après la date d'échéance sans donner de motif. Dans le cas de transactions non autorisées, la période est étendue à 13 mois après la date d'échéance. Les contrepassations de tous les paiements qui ont été effectuées sont accomplies manuellement à l'aide du bouton Annuler le paiement dans l'écran Transactions client.




