---
title: "Convertir des devises comptables ou de déclaration"
description: 
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 78223
ms.assetid: 31c56f9a-9c64-40a2-90e3-1969a760614b
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4f5dae90c5fcaaa52a7087d7c20b2de343b7da0
ms.openlocfilehash: c738207f3088da151ec2317ce2b445f83278ec79
ms.contentlocale: fr-fr
ms.lasthandoff: 08/01/2017

---

# <a name="convert-accounting-or-reporting-currencies"></a>Convertir des devises comptables ou de déclaration

[!include[banner](../includes/banner.md)]


Une société qui doit modifier sa devise comptable ou sa devise de déclaration a deux options. La première option est de créer une société et de répartir à zéro. La deuxième option est d'exécuter le processus de conversion des devises comptables et de déclaration. Il s'agit d'un processus très long qui modifie chaque transaction dans le système. Des paramétrages sont également nécessaires avant d'exécuter le processus.

## <a name="preparing-the-legal-entity-for-currency-conversion"></a>Préparation de l'entité juridique pour la conversion de devise
Avant de pouvoir convertir la devise de l'entité juridique, vous devez rétablir tous les montants de réévaluation des comptes en devises pour les comptes client et fournisseur, puis clôturer les exercices précédents. Vous devez également préparer les bases de données pour la conversion, puis apporter les modifications nécessaires au compte de l'entité juridique qui subit la conversion de devise. Après avoir effectué une conversion de devise, vous devez exécuter des procédures supplémentaires. Vous devez rapprocher les différences d'arrondi des montants convertis, recalculer les statistiques commerciales, journaliser les écritures comptables, limiter l'accès à l'outil de conversion et réévaluer les montants en devise étrangère pour les comptes client et fournisseur.

## <a name="setting-up-accounts-for-automatic-transactions"></a>Paramétrage des comptes pour les transactions automatiques
Lors du processus de conversion de devise, les profits ou pertes ou les différences minimes sont validés dans les comptes définis dans la page **Comptes pour transactions automatiques**. Les comptes principaux doivent être affectés aux types de transaction suivants avant l'exécution du processus de conversion :

-   Profit de conversion en devise comptable
-   Perte de conversion en devise comptable
-   Différence minime dans la devise comptable
-   Différence minime en devise de déclaration
-   Résultat de fin d'exercice

## <a name="posting-rounding-differences-and-sum-recalculations"></a>Validation des différences d'arrondi et recalcul de la somme
Les informations suivantes indiquent les scénarios dans lesquels des différences d'arrondi peuvent se produire :

-   Si le prix des produits est mis à 0 (zéro), un état est généré. Celui-ci indique le numéro de produit, le type de module, le prix avant la conversion et l'unité.
-   Les différences d'arrondi entre la taxe et la comptabilité sont validées dans le journal des opérations diverses.
-   Les montants de réévaluation des comptes en devises sont recalculés, ainsi que les montants des transactions client et fournisseur.
-   Des enregistrements de règlement client et fournisseur sont créés pour les différences d'arrondi pour chaque transaction client et fournisseur.
-   Les différences d'arrondi des clients et des fournisseurs sont validées dans le journal des opérations diverses.
-   Les montants des coûts réglés et d'ajustement de coûts des mouvements de stock clôturés sont recalculés.
-   Les différences d'arrondi du module Gestion des stocks sont validées dans le journal des opérations diverses.
-   Le stock disponible est recalculé.
-   Les montants totaux des journaux comptables sont recalculés.
-   Les feuilles d'ajustements de comptabilité sont recalculées.
-   Les soldes comptables sont recalculés.
-   Les différences d'arrondi du module Comptabilité sont validées dans le journal des opérations diverses.
-   Les écritures comptables d'ouverture sont recalculées.
-   Le montant final des soldes comptables est calculé.

Si vous effectuez un conversion vers une nouvelle devise comptable, et qu'une erreur survient lors du nouveau calcul des montants totaux ou de la validation des différences d'arrondi, vous devez fermer la page **Conversion de devise comptable**. Les montants totaux sont ensuite recalculés, et les différences d'arrondi sont validées.

## <a name="processing-the-currency-conversion"></a>Traitement de la conversion de devise
Lorsque vous démarrez le processus de conversion de devise, tous les utilisateurs doivent être déconnectés du système. Vous devez définir la nouvelle devise comptable ou de déclaration ainsi que les taux de change. Lorsque vous cliquez sur **OK**, le processus s'exécute et met à jour chaque transaction dans le système. La conversion de devise est un processus très long. À la fin du processus, la devise comptable ou de déclaration est mise à jour dans la page **Comptabilité**.

## <a name="completing-the-currency-conversion"></a>Finalisation de la conversion de devise
Après la conversion de devise, vous devez générer tous les états de rapprochement afin de garantir l'exactitude de tous les montants convertis.

-   Si la conversion de la devise comptable entraîne des différences d'arrondi, celles-ci ne sont pas validées à l'aide du N° document dans lequel elles ont été détectées, mais à l'aide du N° document entré pour les validations de conversion. Après la conversion, tous les états contrôlés par document et date incluent ces différences d'arrondi. Ce comportement est normal et peut être ignoré.
-   Si les états de rapprochement client et fournisseur affichent une différence dans la ligne de total, et qu'aucune différence n'existait avant la conversion, cette différence doit être validée. Le compte est le compte collectif pour les clients et les fournisseurs. Le compte de contrepartie est le compte général pour les pertes ou les profits de conversion.

Lorsque tous les journaux des écritures comptables ont été supprimés, vous pouvez journaliser les écritures comptables. Cliquez sur **Comptabilité** &gt; **Périodique** &gt; **Journaux** &gt; **Journalisation**. Vous pouvez réévaluer les montants en devise étrangère après la conversion de devise, si la réévaluation est requise. Pour réévaluer les montants en devise étrangère, sélectionnez **Standard** dans la page **Méthode** pour la réévaluation.

Pour plus d'informations, voir [Journaliser les entrées de journal validées](tasks/journalize-posted-journal-entries.md).


