---
title: Résoudre les problèmes de configuration de Finance Insights
description: Cette rubrique répertorie les problèmes qui peuvent survenir lorsque vous utilisez les fonctionnalités de Finance Insights. Il explique également comment résoudre ces problèmes.
author: panolte
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 68115d484abcdc3c37357ae441e9f9ccb5212659
ms.sourcegitcommit: 6a9f068b59b62c95a507d1cc18b23f9fd80a859b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2021
ms.locfileid: "7827051"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Résoudre les problèmes de configuration de Finance Insights

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique répertorie les problèmes qui peuvent survenir lorsque vous utilisez les fonctionnalités de Finance Insights. Il explique également comment résoudre ces problèmes.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>Symptôme : Pourquoi ne puis-je pas mapper la colonne de destination du modèle d’intégration de données de paiement avec les informations de paiement du client ?

### <a name="resolution"></a>Résolution

Vous utilisez peut-être un modèle pour une version antérieure. Avant la sortie de la version 10.0.17, les clients de version préliminaire configuraient le Modèle d’intégration de données (DI) **Résultats des analyses de paiement client (CDS à Fin and Ops)** en utilisant l’entité **Résultat de la prédiction de paiement (aperçu)**. Après une mise à niveau vers 10.0.17 et versions ultérieures, vous devez utiliser le modèle DI **Résultats des analyses de paiement client (CDS à Fin and Ops)** pour terminer le mappage. Vous ne pourrez peut-être pas mapper la colonne de destination du modèle DI tant que la liste des entités de gestion des données n’est pas actualisée et que l’entité **Résultat de la prédiction de paiement** y apparaît. Pour actualiser la liste des entités et afficher le résultat de la prévision de paiement, vous devrez effectuer les étapes dans Microsoft Dynamics 365 Finance et Dataverse (anciennement connu sous le nom de portail d’administration Common Data Service\[CDS\]).

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

  | Demande                  | ID d’application           |
  | ---------------------------- | ---------------- |
  | CDS Microservices ERP Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 | 
  
