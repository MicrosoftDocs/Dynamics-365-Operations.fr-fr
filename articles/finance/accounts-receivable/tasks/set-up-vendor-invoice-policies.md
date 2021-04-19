---
title: Paramétrer des stratégies de facture fournisseur
description: Cette rubrique explique comment paramétrer des politiques de facturation fournisseur.
author: ShivamPandey-msft
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c088f6e3fea7c218cfd2108d0f279bccf1292772
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816194"
---
# <a name="set-up-vendor-invoice-policies"></a>Paramétrer des stratégies de facture fournisseur

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment paramétrer des politiques de facturation fournisseur. Les stratégies de facture fournisseur sont exécutées lorsque vous validez une facture fournisseur à l’aide de la page Facture fournisseur et lorsque vous ouvrez la page Violations de stratégie de la facture fournisseur. Vous pouvez également configurer le workflow de facture fournisseur de manière à exécuter des stratégies de facture fournisseur chaque fois que vous envoyez une facture dans le workflow. 

- Les stratégies de facture fournisseur ne s’appliquent pas aux factures créées dans le registre des factures ou dans le journal des factures.  
- Le contrôle du rapprochement de factures ne fait pas appel aux stratégies de facture fournisseur. Au lieu de cela, il est paramétré sur la page Paramètres de la comptabilité fournisseur.  
- La société fictive USMF sert d’exemple dans cet enregistrement. Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable. Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Préparation de la création des stratégies de facture fournisseur
1. Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage > Paramètres de la comptabilité fournisseur**.
2. Sélectionnez l’onglet **Contrôle de la facture**.
3. Activez ou désactivez la case à cocher **Mettre à jour automatiquement le statut d’en-tête des factures**.
4. Cliquez sur **OK**.
5. Sélectionnez une option dans le champ **Valider la facture avec les non-correspondances**.
6. Fermez la page.
7. Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage de la stratégie > Stratégies de facture fournisseur**.
8. Sélectionnez **Paramètres**.
9. Sélectionnez **Ajouter**.
10. Fermez la page pour revenir à la page d’accueil.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Création de types de règles de stratégie pour les factures fournisseur
1. Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage de la stratégie > Types de règles de stratégies de facture fournisseur**.
2. Sélectionnez **Nouveau**.
3. Tapez des valeurs dans les champs **Nom de la règle** et **Description**.
4. Dans le champ **Nom de la requête**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche, puis sélectionnez l’enregistrement souhaité.
5. Sélectionnez **Enregistrer**.
6. Fermez la page pour revenir à la page d’accueil.

## <a name="define-a-vendor-invoice-policy"></a>Définition d’une stratégie de facture fournisseur
1. Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage de la stratégie > Stratégies de facture fournisseur**.
2. Sélectionnez **Nouveau**.
3. Tapez des valeurs dans les champs **Nom** et **Description**.
4. Développez ou réduisez la section **Organisations de stratégie**.
5. Dans l’arborescence, sélectionnez **Contoso Entertainment System USA**.
6. Sélectionnez **Ajouter**.
7. Développez ou réduisez la section **Règles de stratégie**.
8. Sélectionnez **Créer une règle de stratégie**.
9. Tapez une valeur dans le champ **Description de la règle de stratégie**.
10. Sélectionnez **Filtrer**.
11. Sélectionnez **Ajouter**. Sélectionnez l’enregistrement souhaité.
12. Dans les champs **Table**, **Table dérivée** et **Champ**, sélectionnez ou entrez des options dans les menus déroulants.
13. Fermez la page.
14. Tapez une valeur dans le champ **Critères**.
15. Cliquez sur **OK**.
16. Cliquez sur **OK**.
17. Fermez les pages pour revenir à la page d’accueil.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]