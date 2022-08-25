---
title: Changement de base dans les calculs de taxe ICMS-DIF pour les produits provenant de fournisseurs d’autres états
description: Cet article décrit la configuration des calculs du type de taxe ICMS-DIF lorsqu’un document fiscal est reçu dans l’État brésilien de Rio Grande do Sul (RS) ou de São Paulo (SP).
author: Kai-Cloud
ms.date: 06/21/2022
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
ms.openlocfilehash: 1bd9982a3804778a27203b4311682ee8bc3c4841
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218647"
---
# <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Changement de base (double base) dans les calculs de taxe ICMS-DIF pour les produits provenant de fournisseurs d’autres états

Cet article décrit la configuration des calculs du type de taxe **ICMS-DIF** lorsqu’un document fiscal est reçu dans l’État brésilien de Rio Grande do Sul (RS) ou de São Paulo (SP).

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
    - Dans le champ **Base marginale**, sélectionnez **Montant net par ligne**.
    - Définissez le code fiscal pour qu’il ait une valeur fiscale de **3**. De cette manière, la transaction de régularisation sera automatiquement créée lorsque le module **Registres fiscaux** sera activé.
    - Dans la configuration du groupe de taxes, sélectionnez l’option **Utiliser la taxe** pour le code taxe **ICMS-DIF**.

### <a name="use-the-delta-tax-rate-in-the-configuration-of-dual-base-icms-dif-sales-tax-codes"></a>Utilisez le taux de taxe delta dans la configuration des codes de taxe de vente base double ICMS-DIF

Lorsque les réglages décrits précédemment sont utilisés, le code de taxe de vente **ICMS-DIF** sera calculé dans la règle de double base. Cependant, le taux d’imposition nominal devient 18 %, ce qui diffère du taux de 6 % dans la règle de base simple. Cette différence entraîne des problèmes d’incohérence dans les documents fiscaux et les déclarations fiscales. À partir de Microsoft Dynamics 365 Finance version 10.0.29, vous pouvez activer la fonctionnalité **Configurer le taux de taxe delta dans le code de taxe ICMS-DIF pour le cas de base double (Brésil)** dans **Gestion de fonctionnalité** pour supprimer l’incohérence.

- En plus de suivre les étapes de la section précédente, sélectionnez le code de taxe de vente **ICMS 12** dans le champ **Taxe de vente sur la taxe de vente**.
- Définissez le taux d’imposition du code de taxe de vente **ICMS-DIF** à 18 pour cent. Le champ **Pourcentage/Montant** indiquera un taux d’imposition nominal de 6 pour cent.

> [!NOTE]
> Les codes de taxe de vente de **ICMS-DIF** et **ICMS 12** doivent être attribués dans le même groupe de taxe de vente.

## <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-to-non-taxpayer-consumers-difal-in-other-states"></a>Changement de base (double base) dans les calculs de taxe ICMS-DIF pour les produits destinés aux consommateurs non-contribuables (DIFAL) dans d’autres états

Activez la fonctionnalité **Calcul de base double pour ICMS-DIFAL dans les opérations de vente** (Brésil) dans **Gestion des fonctionnalités** pour soutenir le changement de base ICMS-DIF sur les échanges avec les consommateurs non contribuables d’un autre État. L’exemple de code de taxe de vente ICMS-DIF entre en vigueur dans les transactions de commande client et de facture financière.

Activez la fonctionnalité **Calcul à double base pour ICMS-DIFAL pour les cas IPI** (Brésil)dans **Gestion des fonctionnalités** pour prendre en charge les scénarios dans lesquels le commerce avec des consommateurs non-contribuables d’un autre État est également passible d’Imposto sobre Produtos Industrializados (IPI). Le montant de la taxe du code de taxe de vente IPI sera reconnu et appliqué dans l’assiette fiscale ICMS-DIFAL.

- Sur l’en-tête de la commande client ou de la facture financière, sur **Informations fiscales** raccourci, l'option **Utilisateur final** doit être définie sur **Oui**.
- Sur l’en-tête de la commande client ou de la facture fournisseur, sur **Informations fiscales** raccourci, l'option **Utilisation et consommation** doit être définie sur **Oui**.
