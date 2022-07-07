---
title: Prérequis pour générer un fichier d’audit FEC en France
description: Cet article décrit les prérequis à mettre en place avant de pouvoir générer un fichier d’audit conforme au Fichier des écritures comptables (FEC) en France.
author: liza-golub
ms.date: 05/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.author: elgolu
ms.reviewer: kfend
ms.search.region: France
ms.openlocfilehash: a911dbfd1aefcca2a8a07e7028297bf9b5488c70
ms.sourcegitcommit: d9d111d7420ca8f1071689afe38a1ccf4b8051f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2022
ms.locfileid: "9033708"
---
# <a name="prerequisites-to-generate-an-fec-audit-file-in-france"></a>Prérequis pour générer un fichier d’audit FEC en France

Pour générer un fichier d’audit conforme au Fichier des écritures comptables (FEC) dans Microsoft Dynamics 365 Finance, vous devez configurer les conditions préalables suivantes dans l’entité juridique à partir de laquelle le FEC sera généré.

- Définir les souches des N° documents. Chaque souche de N° de justificatif doit contenir une partie du texte considérée comme une valeur pour le champ **JournalCode** dans l’état Audit FEC. Par exemple, définissez la souche de N° de justificatif pour les journaux de facture fournisseur comme  **FRSIFACF-\#\#\#\#\#\#\#\#** pour obtenir la valeur **FRSIFACF** dans le champ **JournalCode** dans le fichier FEC.

- Le champ **Continu** doit être défini sur **Oui** pour les séquences de numéros utilisées pour les numéros de facture et pour les transactions du compte général pour les pièces justificatives. Ce paramètre contient l’article 100 du BOI-CF-IOR-60-40-20. La numérotation dans le champ **EcritureNum** doit augmenter avec le temps et ne doit inclure aucune interruption. La numérotation doit être soit unique dans tout le fichier, soit spécifique à chaque journal. (Le texte original français indique, "La numérotation dans le champ" EcritureNum "doit être avancé dans le temps et ne pas comporter de rupture. Cette numérotation peut être unique sur l’ensemble du fichier ou être propre à chaque journal. "). Pour plus d’informations sur la configuration et l’utilisation des numéros chronologiques pour les factures et les bons, voir [Numéros chronologiques des factures et des bons](emea-fra-chronological-invoices-vouchers.md).
- La valeur du champ **Nombre limité d’exercices ouverts** dans **Paramètres du compte général** ne doit pas être plus de **2**. Ce champ limite le nombre total d’exercices pouvant être ouverts simultanément. L’article 921-4 du plan comptable général (Principes généraux) stipule qu’une procédure de clôture doit être exécutée au plus tard à la fin de la période suivante.
- Le plan comptable utilisé par l’entité juridique à partir de laquelle le FEC est généré doit être conforme au plan comptable standard de la France (Livre des procédures fiscales, article A47 A-1, chapitre VII : "Le numéro de compte, dont les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français"). Seuls les comptes principaux commençant par **1**, **2**, **3**, **4**, **5**, **6** ou **7** doivent être inclus dans le FEC.
- Utilisez un profil de validation pour tous les comptes de solde client et fournisseur. Ces comptes principaux commencent par **41** et **40**. Le paramètre **Ne pas autoriser la saisie manuelle** doit être activé pour eux.
- Stocker tous les documents sources des transactions du compte général pendant la période requise par les obligations comptables de la France.
- Les documents comptables soumis au FEC doivent être validés en EURO et en français. 

> [!NOTE]
> En France, les modifications de la description des comptes principaux et des journaux validés ne sont pas autorisées.
>
> L’utilisation de la fonctionnalité [Un bon](../general-ledger/one-voucher.md) introduit une limitation des rapports FEC pour certains scénarios soumis à FEC. Plus précisément, un scénario de relevé bancaire doit être validé en utilisant différentes pièces justificatives pour les transactions qui ont des comptes de contrepartie différents. Nous vous recommandons de définir le paramètre **Autoriser plusieurs transactions dans un seul bon** sur la page **Paramètres du grand livre** sur **Non** dans votre entité juridique si vous publiez des transactions qui font partie du rapport FEC. 
