---
title: FAQ sur les états financiers
description: Cette rubrique fournit des réponses à certaines questions fréquentes sur les états financiers.
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
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266631"
---
# <a name="financial-reporting-faq"></a>FAQ sur les états financiers

Cette rubrique fournit des réponses aux questions fréquentes sur les états financiers.

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a>Comment restreindre l’accès à un état à l’aide de la sécurité de l’organigramme ?

L’exemple suivant montre comment restreindre l’accès à un état à l’aide de la sécurité de l’organigramme.

La société de démonstration USMF a un état **Bilan** auquel tous les utilisateurs d’états financiers ne devraient pas avoir accès. Vous pouvez utiliser la sécurité de l’organigramme pour restreindre l’accès à un seul état afin que seuls des utilisateurs spécifiques puissent y accéder.

1. Connectez-vous à Financial Reporter Report Designer.
2. Sélectionnez **Fichier \> Nouveau \> Définition d’organigramme** pour créer une nouvelle définition d’organigramme.
3. Appuyez deux fois (ou double-cliquez) sur la ligne **Synthèse** dans la colonne **Sécurité d’unité**.
4. Cliquez sur **Utilisateurs et groupes**.
5. Sélectionnez les utilisateurs ou les groupes qui doivent avoir accès à l’état.
6. Sélectionnez **Enregistrer**.
7. Ajoutez votre nouvelle définition d’organigramme dans la définition d’état.
8. Dans la définition d’organigramme, sélectionnez **Paramètres**. Ensuite, sous **Sélection d’unité organisationnelle**, sélectionnez **Inclure toutes les unités**.

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a>Comment identifier les comptes qui ne correspondent pas à mes soldes ?

Lorsqu’un état contient des soldes qui ne correspondent pas, utilisez les procédures suivantes pour identifier chaque compte et écart.

### <a name="in-financial-reporter-report-designer"></a>Dans Financial Reporter Report Designer

1. Créez une définition de ligne.
2. Sélectionnez **Modifier \> Insérer des lignes à partir de dimensions**.
3. Cliquez sur **MainAccount**.
4. Cliquez sur **OK**.
5. Enregistrez la définition de ligne.
6. Créez une définition de colonne.
7. Créez une définition d’état.
8. Sélectionnez **Paramètres** et décochez cette option.
9. Générez l’état. 
10. Exportez l’état vers Microsoft Excel.

### <a name="in-dynamics-365-finance"></a>Dans Dynamics 365 Finance

1. Allez dans **Comptabilité \> Recherches et états \> Balance comptable**.
2. Définissez les champs suivants :

    - **Date de début** : entrez la date de début de l’exercice.
    - **Date de fin** : entrez la date pour laquelle vous générez l’état.
    - **Dimension financière** : définissez ce champ sur **Compte principal défini**.

3. Sélectionnez **Calculer**.
4. Exportez l’état vers Excel.

Vous devriez maintenant pouvoir copier les données de l’état Excel Financial Reporter et de l’état **Balance comptable** afin de comparer les colonnes **Solde de clôture**.

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a>Lorsque je conçois un état dans Report Designer ou lorsque je génère un état financier, je reçois le message suivant : « Impossible de terminer l’opération en raison d’un problème dans l’infrastructure du fournisseur de données. » Comment dois-je répondre ?

Le message indique qu’un problème s’est produit lorsque le système a tenté de récupérer les métadonnées financières du mini-data warehouse pendant que vous utilisiez les états financiers. Il existe deux manières de répondre à ce problème :

- Vérifiez le statut d’intégration des données en accédant à **Outils \> Statut d’intégration** dans Report Designer. Si l’intégration est incomplète, attendez qu’elle se termine. Ensuite, recommencez ce que vous faisiez lorsque vous avez reçu le message.
- Contactez le support pour identifier et résoudre le problème. Il peut y avoir des données incohérentes dans le système. Les ingénieurs du support peuvent vous aider à identifier ce problème sur le serveur et à rechercher les données spécifiques qui peuvent nécessiter une mise à jour.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
