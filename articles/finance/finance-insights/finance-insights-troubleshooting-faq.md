---
title: Résoudre les problèmes de configuration de Finance Insights
description: Cet article répertorie les problèmes qui peuvent survenir lorsque vous utilisez les fonctionnalités de Finance Insights. Il explique également comment résoudre ces problèmes.
author: panolte
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 331c714663d212471b72f1558e6183452ef7f394
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573166"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Résoudre les problèmes de configuration de Finance Insights

[!include [banner](../includes/banner.md)]

Cet article répertorie les problèmes qui peuvent survenir lorsque vous utilisez les fonctionnalités de Finance Insights. Il explique également comment résoudre ces problèmes.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>Symptôme : Pourquoi ne puis-je pas mapper la colonne de destination du modèle d’intégration de données de paiement avec les informations de paiement du client ?

### <a name="resolution"></a>Résolution

Vous utilisez peut-être un modèle pour une version antérieure. Avant la sortie de la version 10.0.17, les clients de version préliminaire configuraient le Modèle d’intégration de données (DI) **Résultats des analyses de paiement client (CDS à Fin and Ops)** en utilisant l’entité **Résultat de la prédiction de paiement (aperçu)**. Après une mise à niveau vers 10.0.17 et versions ultérieures, vous devez utiliser le modèle DI **Résultats des analyses de paiement client (CDS à Fin and Ops)** pour terminer le mappage. Vous ne pourrez peut-être pas mapper la colonne de destination du modèle DI tant que la liste des entités de gestion des données n’est pas actualisée et que l’entité **Résultat de la prédiction de paiement** y apparaît. Pour actualiser la liste des entités et afficher le résultat de la prévision de paiement, vous devrez effectuer les étapes dans Microsoft Dynamics 365 Finance et Dataverse (anciennement connu sous le nom de portail d’administration Common Data Service \[CDS\]).

### <a name="in-finance"></a>Dans Finance

Suivez ces étapes dans Finance après la mise à niveau.

1. Allez dans **Administration système \> Espaces de travail \> Gestion des données**.
2. Dans l’espace de travail **Gestion des données**, sélectionnez la vignette **Paramètres du cadre**.
3. Sur la page **Paramètres du cadre d’import/export de données**, sélectionnez **Paramètres d’entité**, puis sélectionnez **Actualiser la liste des entités**.
4. Fermez la page **Paramètres du cadre d’import/export de données**.
5. Dans l’espace de travail **Gestion des données**, sélectionnez la vignette **Entités de données**.
6. Recherchez "Résultat de la prédiction de paiement". Vérifiez que l’entité **Résultat de la prédiction de paiement** n’est pas la version préliminaire. Le nom de la version préliminaire se termine par "(version préliminaire) ». Si vous ne voyez que la version d’aperçu de l’entité, contactez le support Microsoft.

### <a name="in-dataverse"></a>Dans Dataverse

Suivez ces étapes dans le [centre d’administration Power Platform](https://admin.powerplatform.microsoft.com/environments) pour mettre à jour vos projets d’intégration de données.

1. Si vous utilisez une version d’aperçu de Finance Insights, supprimez le projet DI associé au modèle **Résultats des informations sur les paiements des clients (CDS à Fin and Ops)**.
2. Suivez les étapes de [création d’un projet d’intégrateur de données](create-data-integrate-project.md). Utilisez le modèle **Résultats des analyses de paiement client (CDS à Fin and Ops 10.0.17 et version ultérieure)**.

## <a name="symptom-when-i-try-to-open-ai-builder-by-using-the-links-on-the-customer-payment-predictions-setup-page-why-do-i-receive-the-following-error-message-sorry-theres-been-a-disconnect"></a>Symptôme : Lorsque j’essaie d’ouvrir AI Builder à l’aide des liens de la page de configuration des prédictions de paiement des clients, pourquoi le message d’erreur suivant s’affiche-t-il : « Désolé, vous avez été déconnecté » ?

### <a name="resolution"></a>Résolution

Les utilisateurs de Dynamics 365 Finance doivent disposer d’un compte d’utilisateur Microsoft Power Apps pour l’environnement, et ce compte d’utilisateur doit avoir le rôle de personnalisateur du système. L’administrateur système Microsoft Power Apps peut créer le compte d’utilisateur et attribuer le rôle. Vous pouvez ensuite accéder à <https://make.preview.powerapps.com/>, vous connecter à l’aide de ce compte d’utilisateur et réessayer les liens.

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>Symptôme : Pourquoi l’onglet Prévision de trésorerie dans l’espace de travail Prévision de flux de trésorerie n’affiche-t-il aucune donnée ?

### <a name="resolution"></a>Résolution

La fonction de prévision des flux de trésorerie dans Gestion de trésorerie et des banques et la fonction Prévisions de flux de trésorerie dans Finance Insights doivent être configurées et activées pour afficher correctement les données dans l’espace de travail **Prévision de trésorerie**.

Tout d’abord, configurez et activez les comptes de prévision des flux de trésorerie et de liquidité. Pour plus d’informations, voir [Prévision de la trésorerie](../cash-bank-management/cash-flow-forecasting.md). Si cette configuration est terminée, mais que vous ne voyez pas les résultats escomptés, consultez [Résoudre les problèmes de configuration des prévisions de trésorerie](../cash-bank-management/cash-flow-forecasting-tsg.md) pour plus d’informations.

Ensuite, confirmez que la fonctionnalité Prévisions de flux de trésorerie dans Finance insights (**Trésorerie et gestion bancaire \> Configuration \> Finance Insights \> Prévisions de trésorerie**) a été activée et que la formation du modèle IA est terminée. Si la formation n’est pas terminée, sélectionnez **Prévoir maintenant** pour démarrer le processus de formation du modèle.

## <a name="symptom-why-isnt-the-install-a-new-add-in-button-visible-in-microsoft-dynamics-lifecycle-services"></a>Symptôme : Pourquoi le bouton Installer un nouveau complément n’est-il pas visible dans Microsoft Dynamics Lifecycle Services ?

### <a name="resolution"></a>Résolution

Tout d’abord, vérifiez que le rôle **Gestionnaire de l’environnement** ou **Propriétaire du projet** est bien attribué à l’utilisateur connecté dans le champ **Rôle de sécurité du projet** dans Microsoft Dynamics Lifecycle Services (LCS). L’installation des nouveaux compléments nécessite l’un de ces rôles de sécurité de projet.

Si le bon rôle de sécurité du projet vous est attribué, vous devrez peut-être actualiser la fenêtre de votre navigateur pour voir le bouton **Installer un nouveau complément**.

## <a name="symptom-the-finance-insights-add-in-doesnt-seem-to-be-installing-why-is-that"></a>Symptôme : le complément Finance Insights ne semble pas s’installer. Pourquoi ?

### <a name="resolution"></a>Résolution

Les étapes suivantes doivent avoir été effectuées.

- Vérifiez que vous disposez d’un accès **Administrateur système** et **Personnalisateur de système** dans le centre d’administration Power Portal.
- Vérifiquez qu’une licence Dynamics 365 Finance ou équivalente est appliquée à l’utilisateur qui installe le complément.
- Vérifiez que l’application Azure AD est bien enregistrée dans Azure AD : 

    | Application                  | ID d’application           |
    | ---------------------------- | ---------------- |
    | CDS Microservices ERP Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 | 
  
    Pour vérifier que l’application est enregistrée dans Azure AD, vérifiez la liste **Toutes les applications**. Pour obtenir plus de détails, consultez [Afficher les applications d’entreprise](/azure/active-directory/manage-apps/view-applications-portal).
  
    Si l’application n’est pas enregistrée dans Azure AD, contactez le support.

## <a name="symptom-error-we-didnt-find-any-data-for-the-selected-filter-range-please-select-a-different-filter-range-and-try-again"></a>Symptôme : Erreur : « Nous n’avons trouvé aucune donnée pour la plage de filtres sélectionnée. Veuillez sélectionner une autre plage de filtres et réessayer. » 

### <a name="resolution"></a>Résolution

Vérifiez la configuration de l’intégrateur de données pour valider qu’il fonctionne comme prévu et met à jour les données d’AI Builder dans Finance.  
Pour plus d’informations, voir [Créer un projet d’intégration de données](../finance-insights/create-data-integrate-project.md).

## <a name="symptom-customer-payment-prediction-training-failed-and-the-ai-builder-error-states-prediction-should-have-only-2-distinct-outcome-values-to-train-the-model-map-to-two-outcomes-and-retrain-training-report-issue-isnotminrequireddistinctnonnullvalues"></a>Symptôme : la formation de prédiction de paiement client a échoué et l’erreur AI Builder indique : « La prédiction ne doit avoir que 2 valeurs de résultat distinctes pour entraîner le modèle. Mapper sur deux résultats et recycler », « Problème de rapport de formation : IsNotMinRequiredDistinctNonNullValues ».

### <a name="resolution"></a>Résolution

Cette erreur indique qu’il n’y a pas assez de transactions historiques au cours de la dernière année qui représentent chaque catégorie décrite dans les catégories **À temps**, **En retard** et **Très en retard**. Pour résoudre cette erreur, ajustez la période de transaction **Très en retard**. Si ajuster la période de transaction **Très en retard** ne corrige pas l’erreur, **Prédictions de paiement client** n’est pas la meilleure solution à utiliser, car elle nécessite des données dans chaque catégorie à des fins de formation.

Pour plus d’informations sur la façon d’ajuster les catégories **À temps**, **En retard** et **Très en retard**, consultez la rubrique [Activer les prédictions de paiement des clients](../finance-insights/enable-cust-paymnt-prediction.md).

## <a name="symptom-model-training-failed"></a>Symptôme : Échec de la formation du modèle

### <a name="resolution"></a>Résolution

La formation du modèle **Prévisions de flux de trésorerie** nécessite des données contenant au moins 100 transactions s’étalant sur plus d’un an. Nous vous recommandons d’avoir au moins deux ans de données avec plus de 1 000 transactions.

La fonctionnalité **Prédictions de paiement client** nécessite plus de 100 transactions au cours des six à neuf mois précédents. Les transactions peuvent inclure des factures financières, des commandes client et des paiements client. Ces données doivent être réparties sur les paramètres **À temps**, **En retard** et **Très tard** définis sur la page **Configuration**.    

La fonctionnalité **Proposition de budget** nécessite un minimum de trois années de budget ou de données réelles. Cette solution utilise trois à dix années de données dans les projections. Plus de trois ans donneront de meilleurs résultats. Les données elles-mêmes fonctionnent mieux lorsqu’il y a une variation dans les valeurs. Si les données contiennent toutes des données constantes, telles qu’une dépense de location, la formation peut échouer car l’absence de variation n’exige pas que l’IA projette les montants.

## <a name="symptom-error-message-states-that-the-table-with-name-msdyn_paypredpredictionresultentities-does-not-exist-the-remote-server-returned-an-error-404-not-found"></a>Symptôme : un message d’erreur indique que la "table avec le nom, ’msdyn_paypredpredictionresultentities’ n’existe pas. Le serveur distant a renvoyé une erreur : (404) Not Found…"

### <a name="resolution"></a>Résolution

L’environnement a atteint la limite de table maximale de Data Lake Services. Pour plus d’informations sur la limite, consultez la section **Activer les modifications de données en temps quasi réel** de l’article [Présentation de l’exportation vers Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/Azure-Data-Lake-GA-version-overview.md).
