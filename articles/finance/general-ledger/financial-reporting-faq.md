---
title: FAQ sur les états financiers
description: Cette rubrique fournit des réponses à certaines questions fréquentes sur les états financiers.
author: jiwo
ms.date: 07/07/2021
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
ms.openlocfilehash: 3690a541b503281f204221a72bfb5a371984d9e4
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605277"
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

## <a name="how-does-the-selection-of-historical-rate-translation-affect-report-performance"></a>Comment la sélection de la conversion des taux historiques affecte-t-elle les performances des états ?

Le taux historique est généralement utilisé avec les bénéfices non répartis, les immobilisations corporelles et les comptes de capitaux propres. Le taux historique peut être requis, sur la base des directives du Bureau des normes comptables financières (FASB) ou des principes comptables généralement reconnus (PCGR). Pour plus d’informations, consultez [Fonctionnalités de devise dans les états financiers](financial-reporting-currency-capability.md).

## <a name="how-many-types-of-currency-rate-are-there"></a>Combien y a-t-il de types de taux de change ?

Il existe trois types :

- **Taux actuel** – Ce type est généralement utilisé avec les comptes de bilan. Il est généralement connu sous le nom de *Taux de change au comptant* et peut être le taux du dernier jour du mois ou à une autre date prédéterminée.
- **Taux moyen** – Ce type est généralement utilisé avec les comptes de résultat (bénéfice/perte). Vous pouvez configurer le taux moyen pour faire une moyenne simple ou pondérée.
- **Taux historique** – Ce type est généralement utilisé avec les bénéfices non répartis, les immobilisations corporelles et les comptes de capitaux propres. Ces comptes peuvent être requis, selon les directives FASB ou les principes GAAP.

## <a name="how-does-historical-currency-translation-work"></a>Comment fonctionne la conversion historique des devises ?

Les tarifs sont spécifiques à la date de la transaction. Par conséquent, chaque transaction est convertie individuellement, sur la base du taux de change le plus proche.

Pour la conversion historique des devises, les soldes de période précalculés peuvent être utilisés à la place des détails de transaction individuels. Ce comportement diffère du comportement pour la conversion selon le taux en cours.

## <a name="how-does-historical-currency-translation-affect-performance"></a>Comment la conversion historique des devises affecte-t-elle les performances ?

Lorsque les données présentées sur les états sont mises à jour, il peut y avoir un retard car les montants doivent être recalculés en vérifiant les détails de la transaction. Ce délai est déclenché chaque fois que les taux sont mis à jour ou que plusieurs transactions sont affichées. Par exemple, si des milliers de comptes sont configurés pour la conversion historique plusieurs fois par jour, il peut y avoir un délai pouvant aller jusqu’à une heure avant que les données de l’état soient mises à jour. En revanche, s’il y a un plus petit nombre de comptes spécifiques, les délais de traitement des mises à jour des données de l’état peuvent être réduits à quelques minutes ou moins.

De même, lorsque les états sont générés en utilisant la conversion de devise pour les comptes de type historique, il y aura des calculs supplémentaires par transaction. Selon le nombre de comptes, le temps de génération des états peut plus que doubler.

## <a name="what-are-the-estimated-data-mart-integration-intervals"></a>Quels sont les intervalles d’intégration estimés pour le mini-data warehouse ?

Financial Reporter utilise 16 tâches pour copier des données entre Dynamics 365 Finance et la base de données Financial Reporter. Le tableau suivant répertorie ces 16 tâches et indique l’intervalle qui spécifie la fréquence d’exécution de chaque tâche. Les intervalles ne peuvent pas être modifiés.

| Nom                                                       | Intervalle | Unité de temps |
|------------------------------------------------------------|----------|-----------------|
| Catégories de compte AX 2012 vers Catégorie de compte            | 41       | Minutes         |
| Comptes AX 2012 vers Compte                                | 7        | Minutes         |
| Entreprises AX 2012 vers Entreprises                               | 300      | Secondes         |
| Entreprises AX 2012 vers Organisation                          | 23       | Minutes         |
| Combinaisons de dimensions AX 2012 vers Combinaison de dimensions    | 1        | Minutes         |
| Valeurs de dimension AX 2012 vers Valeur de dimension                | 11       | Minutes         |
| Dimensions AX 2012 vers Dimension                            | 31       | Minutes         |
| Taux de change AX 2012 vers Taux de change                    | 17       | Minutes         |
| Exercices AX 2012 vers Exercice                        | 13       | Minutes         |
| Transactions de la comptabilité AX 2012 vers Récapitulatif                | 1        | Minutes         |
| Hiérarchies d’organisation AX 2012 vers Arborescence                   | 3 600    | Secondes         |
| Scénarios AX 2012 vers Scénario                              | 29       | Minutes         |
| Qualificatifs de type de transaction AX 2012 vers Qualificatif de type de récapitulatif | 19       | Minutes         |
| Tâche de maintenance                                           | 1        | Minutes         |
| Définitions d’état MR vers États financiers AX7             | 45       | Secondes         |
| Versions des états MR vers Versions des états financiers AX         | 45       | Secondes         |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
