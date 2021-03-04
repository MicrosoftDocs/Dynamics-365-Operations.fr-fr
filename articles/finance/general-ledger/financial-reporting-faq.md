---
title: FAQ sur Financial Reporting
description: Cette rubrique répertorie les questions relatives aux états financiers qui ont été posées par d’autres utilisateurs.
author: jiwo
manager: tfehr
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3f9381f5b656d0cc0b46c8828b2ef9d024e296b0
ms.sourcegitcommit: 14785208d84b2c1efd30f140c52df35a2ccd1577
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/27/2021
ms.locfileid: "5070215"
---
# <a name="financial-reporting-faq"></a>FAQ sur Financial Reporting 

Cette rubrique répertorie les questions relatives aux états financiers qui ont été posées par d’autres utilisateurs. 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>Comment restreindre l’accès à un état à l’aide de la sécurité de l’organigramme ?

Scénario : La société de démonstration USMF a un état Bilan et elle ne souhaite pas que tous les utilisateurs de Financial Reporting puissent l’afficher dans D365. Solution : Vous pouvez utiliser la sécurité de l’organigramme pour restreindre l’accès à un seul état afin que seuls certains utilisateurs puissent y accéder. 

1.  Connectez-vous à Financial Reporter Report Designer

2.  Créer une définition d’organigramme (Fichier | Nouveau | Définition d’organigramme) a.    Double-cliquez sur la ligne **Synthèse** dans la colonne **Sécurité d’unité**.
  i.    Cliquez sur Utilisateurs et groupes.  
          1. Sélectionnez le groupe ou le/les utilisateurs qui souhaitent accéder à ce rapport. 
          
[![écran de l’utilisateur](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)

[![écran de sécurité](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)

  b.    Cliquez sur **Enregistrer**.
  
[![bouton Enregistrer](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)

3.  Dans votre définition d’état, ajoutez votre nouvelle définition d’organigramme

[![formulaire de définition d’organigramme](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)

A.  Dans la définition d’organigramme, cliquez sur Paramètres et sous « Sélection d’unité organisationnelle », cochez « Inclure toutes les unités »

[![formulaire de sélection de l’unité organisationnelle](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)

**Avant :** [![capture d’écran avant](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)

**Après :** [![capture d’écran après](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)

Remarque : le message ci-dessus s’affiche car l’utilisateur n’a pas accès à cet état après avoir appliqué la Sécurité d’unité



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a>Comment déterminer quels comptes ne correspondent pas à mes soldes dans D365 ?

Lorsqu’un état ne correspond pas à vos attentes dans D365, voici quelques étapes à suivre pour identifier les comptes et les écarts qui posent problème. 

### <a name="in-financial-reporter-report-designer"></a>Dans Financial Reporter Report Designer

1.  Créez une définition de ligne a.    Cliquez sur Modifier | Insérer des lignes à partir de dimensions i.  Sélectionner MainAccount [![Écran Sélectionner compte principal_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)
    
    ii. Cliquez sur Ok b.    Enregistrez la définition de ligne

2.  Créer une nouvelle définition de colonne     [![Créer une nouvelle définition de colonne](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)

3.  Créez une définition d’état a.    Cliquez sur Paramètres et décochez [![Formulaire de paramètres](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)
   
4.  Générez l’état. 

5.  Exportez l’état vers Excel.

### <a name="in-d365"></a>Dans D365 : 
1.  Cliquez sur Comptabilité | Recherches et états | Balance comptable a.    Paramètres i.  Date de début : Début de l’exercice ii. À ce jour : Date à laquelle vous avez généré l’état pour iii.    Ensemble de dimensions financières « Compte principal défini » [![Formulaire de compte principal](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)
      
  b.    Cliquez sur Calculer

2.  Exporter l’état vers Excel

Vous devriez maintenant pouvoir copier les données de l’état Excel États financiers et de l’état Balance comptable D365 et comparer les colonnes « Solde de clôture ».


[!INCLUDE[footer-include](../../includes/footer-banner.md)]