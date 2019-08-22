---
title: Rechercher/Résoudre les exceptions
description: Les stratégies de facture fournisseur sont exécutées lorsque vous validez une facture fournisseur à l'aide de la page Facture fournisseur et lorsque vous ouvrez la page Violations de stratégie de la facture fournisseur.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2f2e7d401e97aeab9dbc74f65e1a0c03eb0c880
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835404"
---
# <a name="researchresolve-exceptions"></a>Rechercher/Résoudre les exceptions

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les stratégies de facture fournisseur sont exécutées lorsque vous validez une facture fournisseur à l'aide de la page Facture fournisseur et lorsque vous ouvrez la page Violations de stratégie de la facture fournisseur. Vous pouvez également configurer le workflow de facture fournisseur de manière à exécuter des stratégies de facture fournisseur chaque fois que vous envoyez une facture dans le workflow. 

Les stratégies de facture fournisseur ne s'appliquent pas aux factures créées dans le registre des factures ou dans le journal des factures. 

Le contrôle du rapprochement de factures ne fait pas appel aux stratégies de facture fournisseur. Au lieu de cela, il est paramétré sur la page Paramètres de la comptabilité fournisseur.

La société fictive USMF sert d'exemple dans cet enregistrement. Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable. Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Préparation de la création des stratégies de facture fournisseur
1. Accédez à Comptabilité fournisseur > Paramétrage > Paramètres de la comptabilité fournisseur.
2. Cliquez sur l'onglet Contrôle de la facture.
3. Activez ou désactivez la case à cocher Mettre à jour automatiquement le statut d'en-tête des factures.
4. Cliquez sur OK.
5. Sélectionnez une option dans le champ Valider la facture avec les non-correspondances.
6. Fermez la page.
7. Accédez à Comptabilité fournisseur > Paramétrage de la stratégie > Stratégies de facture fournisseur.
8. Cliquez sur Paramètres.
9. Cliquez sur btnAdd.
10. Fermez la page.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Création de types de règles de stratégie pour les factures fournisseur
1. Accédez à Comptabilité fournisseur > Paramétrage de la stratégie > Types de règles de stratégie de facture fournisseur.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom de la règle.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Nom de la requête, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Cliquez sur Enregistrer.
9. Fermez la page.

## <a name="define-a-vendor-invoice-policy"></a>Définition d'une stratégie de facture fournisseur
1. Accédez à Comptabilité fournisseur > Paramétrage de la stratégie > Stratégies de facture fournisseur.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Description, entrez une valeur.
5. Développez ou réduisez la section Organisations de stratégie.
6. Dans l'arborescence, sélectionnez Contoso Entertainment System USA.
7. Cliquez sur Ajouter.
8. Développez ou réduisez la section Règles de stratégie.
9. Cliquez sur Créer une règle de stratégie.
10. Tapez une valeur dans le champ Description de la règle de stratégie.
11. Cliquez sur Filtre.
12. Cliquez sur Ajouter.
13. Dans la liste, marquez la ligne sélectionnée.
14. Dans le champ de table, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
15. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
16. Dans le champ Table dérivée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
17. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
18. Dans le champ Champ, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
19. Tapez une valeur dans le champ Champ.
20. Fermez la page.
21. Tapez une valeur dans le champ Critères.
22. Cliquez sur OK.
23. Cliquez sur OK.
24. Fermez la page.
25. Fermez la page.

