---
title: Vue d’ensemble de la solution Invoice capture
description: Cet article fournit des informations sur la solution Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76441220b93744527f412110db536601a2fa1dd9
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691161"
---
# <a name="invoice-capture-solution"></a>Solution Invoice capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cet article fournit des informations sur la solution Invoice capture qui crée automatiquement des factures fournisseur à partir d’images de factures numériques.

Le service Comptabilité fournisseur gère et traite les factures pour les marchandises et les services reçus. La comptabilité fournisseur vérifie les données sur les factures fournisseur pour les raisons suivantes :

- Pour éviter des efforts supplémentaires si des ajustements ou des corrections sont requis pendant la clôture de la période
- Pour payer les factures fournisseur en temps opportun et empêcher toute perte financière en raison d’une erreur ou d‘une fraude

La reconnaissance optique de caractères (OCR) est devenue largement utilisée par différents secteurs depuis ces dernières années. Il est maintenant courant que les textes imprimés soient numérisés, afin qu’ils puissent être édités électroniquement, recherchés, stockés de manière plus compacte et affichés en ligne. Le texte numérique peut être utilisé dans des processus automatiques tels que l’informatique cognitive, la traduction automatique, la synthèse vocale, les données clés et l’exploration de texte.

L’évolution de la technologie de l’intelligence artificielle (IA) a permis aux solutions OCR modernes de lire différents formats de factures de différents fournisseurs sans nécessiter beaucoup d’intervention humaine. De plus en plus d’entreprises reconnaissent qu’elles peuvent économiser des efforts et améliorer la précision en traitant les factures via l’automatisation au lieu de procéder à un traitement manuel.

## <a name="system-landscape"></a>Paysage système

L’illustration suivante présente les principaux composants et étapes de la solution Invoice capture.

[![Composants et étapes de la solution Invoice capture.](./media/Invoice-capture2.png)](./media/Invoice-capture2.png)

## <a name="required-roles"></a>Rôles obligatoires

Le tableau suivant présente les rôles requis pour configurer et utiliser la solution Invoice capture.

| Rôle          | Actions | Systèmes | Noms de rôle |
|---------------|---------|---------|-----------|
| Administrateur | <ul><li>Paramétrez des environnements dans Microsoft Power Platform.</li><li>Déployez des solutions dans Microsoft Power Platform.</li><li>Configurez les connexions entre Dynamics 365 et AI Builder.</li><li>Paramétrez les emplacements Azure Data Lake Storage.</li></ul> | <ul><li>Dynamics 365</li><li>Microsoft Power Platform</li><li>Azure Data Lake Storage</li></ul> | <ul><li>Administrateur Dynamics 365</li><li>Administrateur Power Platform</li><li>Propriétaire des données de l’objet blob de stockage</li></ul> |
| Créateur d’IA      | <ul><li>Maintenez les flux.</li><li>Créez des modèles IA personnalisés.</li></ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Créateurs citoyens</li></ul> |
| Assistant comptabilité fournisseur      | <ul><li>Examinez et prenez des mesures dans la zone de préparation des factures fournisseur.</li><ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Nouveau rôle d’assistant comptabilité fournisseur dans Power Platform</li></ul> |
| Assistant comptabilité fournisseur      | <ul><li>Effectuer les opérations quotidiennes en tant qu’assistant comptabilité fournisseur.</li><li>Accédez à la zone de préparation de la facture fournisseur.</li></ul> | <ul><li>Dynamics 365</li></ul> | <ul><li>Commis à la comptabilité fournisseur</li></ul> |
  
Pour plus d’informations sur l’installation d’Invoice capture, voir [Installer Invoice capture](../accounts-payable/install-invoice-capture.md).  
