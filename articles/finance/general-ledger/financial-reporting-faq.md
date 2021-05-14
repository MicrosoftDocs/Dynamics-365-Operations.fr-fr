---
title: FAQ sur les états financiers
description: Cette rubrique répertorie les questions relatives aux états financiers qui ont été posées par d’autres utilisateurs.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923023"
---
# <a name="financial-reporting-faq"></a>FAQ sur les états financiers 

Cette rubrique fournit des réponses aux questions fréquemment posées sur les états financiers. 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>Comment restreindre l’accès à un état à l’aide de la sécurité de l’organigramme ?

L’exemple suivant montre comment restreindre l’accès à un état à l’aide de la sécurité de l’organigramme.

La société de démonstration USMF a un rapport de bilan auquel tous les utilisateurs d’états financiers ne devraient pas avoir accès. Vous pouvez utiliser la sécurité de l’organigramme pour restreindre l’accès à un seul état afin que seuls certains utilisateurs puissent y accéder. Suivez ces étapes pour restreindre l’accès : 

1. Connectez-vous à Financial Reporter Report Designer.
2. Créez une définition d’arborescence. Allez dans **Fichier > Nouveau > Définition d’organigramme**.
3. Double-cliquez sur la ligne **Synthèse** dans la colonne **Sécurité d’unité**.
4. Cliquez sur **Utilisateurs et groupes**.  
5. Sélectionnez les utilisateurs ou les groupes qui doivent accéder à cet état. 
6. Sélectionnez **Enregistrer**.
7. Ajoutez votre nouvelle définition d’organigramme dans la définition d’état.
8. Dans la définition d’organigramme, sélectionnez **Paramètres**. Sous **Sélection d’unité organisationnelle**, sélectionnez **Inclure toutes les unités**.

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a>Comment identifier les comptes qui ne correspondent pas à mes soldes ?

Lorsqu’un état contient des soldes qui ne correspondent pas, voici quelques étapes à suivre pour identifier chacun de ces comptes et les écarts qui posent problème. 

**Financial Reporter Report Designer**
1. Dans Financial Reporter Report Designer, créez une nouvelle définition de ligne. 
2. Cliquez sur **Modifier > Insérer des lignes à partir de dimensions**.
3. Cliquez sur **MainAccount**.  
4. Cliquez sur **OK**.
5. Enregistrez la définition de ligne.
6. Créer une définition de colonne
7. Créez une définition d’état.
8. Sélectionnez **Paramètres** et décochez cette option.  
9. Générez l’état. 
10. Exportez l’état vers Microsoft Excel.

**Dynamics 365 Finance** 
1. Dans Dynamics 365 Finance, allez dans **Comptabilité > Recherches et états > Balance comptable**.
2. Définissez les paramètres suivants :
   - **Date de début** : Saisissez le début de l’année fiscale.
   - **À ce jour** : Saisissez la date pour laquelle vous générez l’état.
   - **Dimension financière** : Définissez ce champ sur **Compte principal défini**.
 3. Sélectionnez **Calculer**.
 4. Exportez l’état vers Microsoft Excel.

Vous devriez maintenant pouvoir copier les données de l’état Excel Financial Reporter et de l’état Balance comptable et comparer les colonnes **Solde de clôture**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]