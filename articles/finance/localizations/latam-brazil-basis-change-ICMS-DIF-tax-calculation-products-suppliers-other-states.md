---
title: Changement de base dans les calculs de taxe ICMS-DIF pour les produits provenant de fournisseurs d’autres états
description: Cette rubrique décrit la configuration des calculs du type de taxe ICMS-DIF lorsqu’un document fiscal est reçu dans l’État brésilien de Rio Grande do Sul (RS) ou de São Paulo (SP).
author: Kai-Cloud
ms.date: 1/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 63e3cbaaf77456b55f08ea91831ba9d49cb57185
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689154"
---
# <a name="basis-change-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Changement de base dans les calculs de taxe ICMS-DIF pour les produits provenant de fournisseurs d’autres états

Cette rubrique décrit la configuration des calculs du type de taxe **ICMS-DIF** lorsqu’un document fiscal est reçu dans l’État brésilien de Rio Grande do Sul (RS) ou de São Paulo (SP).

Selon la définition de la loi de l’État, l’Imposto sobre Circulação de Mercadorias e Serviços (ICMS) collecté doit suivre cette règle :

*ICMS à collecter* = ([(*Montant de l’opération* – *ICMS de la source*) ÷ (1 – *% ICMS interne*)] × *% ICMS interne*) – *Montant ICMS de la source*

## <a name="example"></a>Exemple

Une entreprise brésilienne située dans l’État RS reçoit un document fiscal pour un achat auprès d’un fournisseur dans l’État SP. L’entreprise doit collecter la différence de pourcentage de l’ICMS entre l’état RS (18 %) et l’état SP (12 %). Cependant, la base doit être calculée selon la règle précédente.

- **Montant de l’opération :** 1 000,00 réals brésiliens (1 000,00 R$)
- **ICMS inter-états :** 120,00 R$
- **Pourcentage ICMS dans l’état RS :** 18 pour cent
- **ICMS à collecter dans l’état RS :** (\[(1 000 – 120) ÷ (1 – 0,18)\] × 0,18) – 120 = 73,17 R$ 

## <a name="resolution"></a>Résolution

Pour calculer l’ICMS différentiel (ICMS-DIF) selon les règles de l’état RS, vous devez paramétrer des codes taxe et un groupe de taxes de la manière suivante :

1. Créez un code taxe pour recevoir l’ICMS de 12 % (pour l’autre État). Ce code est utilisé pour enregistrer le montant de la taxe à recevoir du fournisseur.
2. Créez un code taxe pour collecter l’ICMS-DIF. Ce code taxe doit avoir un pourcentage de 18 % (pour votre propre état) pour définir la différence entre 18 % et 12 %. Définissez le type de taxe sur **ICMS-DIF**. Ce code taxe doit être défini de la manière suivante dans les paramètres de calcul :

    - Dans le champ **Origine**, sélectionnez **Pourcentage ou montant brut**.
    - Dans le champ **Base marginale**, sélectionnez **Montant net par ligne** ou **Montant net du solde de la facture**.
    - Définissez le code fiscal pour qu’il ait une valeur fiscale de **3**. De cette manière, la transaction de régularisation sera automatiquement créée lorsque le module **Registres fiscaux** sera activé.
    - Dans la configuration du groupe de taxes, sélectionnez l’option **Utiliser la taxe** pour le code taxe **ICMS-DIF**.
