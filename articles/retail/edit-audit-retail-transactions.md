---
title: Modifier et auditer les transactions du magasin de vente au détail
description: Cette rubrique décrit la fonctionnalité de modification et d'audit des transactions du magasin de vente au détail.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: f53573b8afb2003f6796930f5877185e533a4715
ms.sourcegitcommit: 92322167f57b66d2accc134aaf862e6b9931ec94
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2019
ms.locfileid: "2693064"
---
# <a name="edit-and-audit-retail-store-transactions"></a>Modifier et auditer les transactions du magasin de vente au détail

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

Les clients Dynamics 365 Retail utilisent des applications internes ainsi que des applications POS tierces. Avec l'application POS interne, les transactions du magasin de vente au détail sont extraites dans Retail Headquarters depuis les canaux via un processus de traitement par lots. Avec les applications tierces, les transactions sont extraites dans Retail Headquarters par intégration. Dans les deux cas, une fois que les transactions sont extraites dans Retail Headquarters, un processus de vérification de la cohérence doit être exécuté avec plusieurs validations des transactions afin que seules les transactions correctement validées soient extraites dans le relevé à valider dans Retail Headquarters. 

Les transactions de vente au détail ne sont pas validées pour plusieurs raisons. Par exemple, un bogue dans le code d'intégration ou un bogue dans l'application POS peut entraîner des données incohérentes, ou une erreur de l'utilisateur, comme la suppression d'un produit après sa synchronisation avec le canal ou la clôture d'une période fiscale sans valider les transactions de vente au détail pour cette période, peut entraîner des données incohérentes.

Ces transactions sont marquées et exclues des relevés, mais elles peuvent perturber le processus quotidien de validation des ventes au détail quotidiennes dans les finances.

Dans Retail, vous pouvez modifier les transactions de vente au détail spécifiques qui n'ont pas été validées tout en conservant l'audit de toutes les modifications. 

## <a name="edit-and-audit-transactions"></a>Modifier et auditer des transactions

Dans Retail version 10.0.5, les transactions au comptant sans livraison comme les ventes et les retours sont les seules transactions pouvant être modifiées. La modification des commandes client ou des commandes en ligne n'est pas prise en charge. Dans Retail version 10.0.6 et plus, la modification des transactions de gestion des disponibilités est également prise en charge.

1. Installez le complément Dynamics Excel.

2. Accédez à l'espace de travail **Finances du magasin de vente au détail**. La vignette **Échecs de validation de transaction** offre une vue préfiltrée du formulaire Transaction de vente au détail pour lequel une ou plusieurs règles de validation ont échoué.
 
3. Ouvrez le formulaire. Cliquez sur l'enregistrement qui n'a pas été validé, cliquez sur **Complément Office**, puis cliquez sur **Modifier la transaction sélectionnée**. Un fichier Excel avec les détails de la transaction sélectionnée s'ouvre, avec les feuilles de calcul suivantes :

    - Lignes : cette feuille de calcul contient les lignes d'en-tête et de produit et les données associées pour la transaction.
    - Paiements : cette feuille de calcul contient les détails des lignes de paiement pour la transaction.
    - Remises : cette feuille de calcul contient les détails de la remise pour la transaction.
    - Taxes : cette feuille de calcul contient les détails de la taxe pour la transaction.
    - Frais : cette feuille de calcul contient les détails des frais pour la transaction.

4. Dans le fichier Excel, modifiez les champs appropriés, puis chargez les données dans Retail Headquarters en utilisant la fonctionnalité de publication du complément Dynamics Excel. Une fois publiées, les modifications sont répercutées dans le système. Lors de la publication, aucune validation n'est exécutée sur les modifications effectuées par les utilisateurs.

5. Une piste d'audit complète des modifications est disponible en cliquant sur **Afficher la piste d'audit** dans l'en-tête **Transaction de vente au détail** pour les modifications au niveau de l'en-tête et dans la section et l'enregistrement appropriés dans la page de transaction appropriée. Par exemple, toutes les modifications relatives aux lignes de vente sont visibles dans la page **Transactions de vente**, les modifications relatives aux paiements sont visibles dans la page **Transactions de paiement**, etc. Les détails d'audit conservés pour les modifications se présentent comme suit.

   - Date et heure de modification
   - Champ 
   - Ancienne valeur
   - Nouvelle valeur
   - Modifié par

6. Une fois les modifications effectuées et publiées, réexécutez l'option **Valider les transactions en magasin** pour valider que les modifications effectuées sont cohérentes et valides.

> [!NOTE]
> Vous pouvez uniquement modifier les transactions qui n'ont pas été validées. Si vous souhaitez modifier les transactions qui ont été validées, modifiez le statut de validation de la transaction à modifier en **Erreur** ou **Aucun** pour pouvoir la modifier. 


## <a name="bulk-edit-transactions"></a>Modifier des transactions en bloc

Dans Retail version 10.0.6 et plus, l'option de modification en bloc des transactions de vente au détail au niveau du relevé est prise en charge. 

1. Utilisez le complément Excel pour ouvrir un relevé contenant des transactions à modifier en utilisant les étapes 1 à 3 ci-dessus.

2. Choisissez l'une des options ci-dessous.

    - **Modifier les transactions au comptant sans livraison**. Cette option permet de modifier toutes les transactions au comptant sans livraison contenues dans le relevé. Les feuilles de calcul Excel suivantes sont disponibles.
    
       - **Transaction** : cette feuille de calcul contient toutes les informations au niveau de l'en-tête pour les transactions de vente.
       - **Transaction de vente** : cette feuille de calcul contient toutes les informations au niveau des lignes pour les transactions de vente.
       - **Transactions de paiement** : cette feuille de calcul contient toutes les informations sur les lignes de paiement pour les transactions de vente.
       - **Transactions de remise** : cette feuille de calcul contient toutes les informations sur les lignes de remise pour les transactions de vente.
       - **Transactions de taxe** : cette feuille de calcul contient toutes les informations sur les lignes de taxe pour les transactions de vente.
       - **Transactions de frais** : cette feuille de calcul contient toutes les informations sur les lignes de frais pour les transactions de vente.

    - **Modifier les transactions de gestion des disponibilités**. Cette option permet de modifier toutes les transactions de gestion des disponibilités contenues dans le relevé. Les feuilles de calcul Excel suivantes sont disponibles.
     
       - **Transaction** : cette feuille de calcul contient toutes les informations au niveau de l'en-tête pour les transactions de gestion des disponibilités.
       - **Transactions de mode de paiement en banque** : cette feuille de calcul contient tous les détails des transactions de remise en banque.
       - **Transactions de paiements remises en coffre-fort** : cette feuille de calcul contient tous les détails des transactions de paiement remises en coffre-fort.
       - **Comptage de caisse** : cette feuille de calcul contient tous les détails des transactions de comptage de caisse.
       - **Transaction de revenus/dépenses** : cette feuille de calcul contient tous les détails de la ligne de transaction de revenus/dépenses.
       - **Transactions de paiement** : cette feuille de calcul contient toutes les informations de paiement pour l'opération **Payer la facture** ainsi que la transaction de revenus/dépenses.

3.  Les validations ne sont pas exécutées lorsque vous publiez des transactions modifiées en bloc. Vous devez vous assurer que toutes vos modifications sont correctes et que la fidélité des données dans les feuilles de calcul est maintenue. Par exemple, si vous souhaitez modifier la date de transaction pour gérer les scénarios où la période fiscale ou d'inventaire des transactions de vente au détail en cours est clôturée, vous devez modifier la date sur toutes les feuilles de calcul Excel contenant la colonne **Date d'activité**. Pour valider les transactions après les avoir modifiées, vous pouvez utiliser **Revalider les transactions** dans la page **Relevés de vente au détail**.
