---
title: Prévision de flux de trésorerie (version préliminaire)
description: Cette rubrique décrit la fonctionnalité de prévision des flux de trésorerie.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 64935db3b50e7598f2076ecbec72aba020d4f908
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186538"
---
# <a name="cash-flow-forecast-preview"></a>Prévision de flux de trésorerie (version préliminaire)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Le flux de trésorerie est essentiel à toute entreprise. Même les entreprises rentables peuvent être confrontées à l’insolvabilité si elles ne maintiennent pas les flux de trésorerie nécessaires pour répondre aux besoins immédiats. La capacité de prévision des flux de trésorerie dans les informations financières peut aider les entreprises à surveiller et à gérer efficacement leurs soldes de trésorerie. Cette fonctionnalité utilise l’apprentissage automatique pour aider les entreprises à prévoir les flux de trésorerie avec plus de précision qu’auparavant. Elle peut également aider les responsables à prendre des décisions qui optimisent les opportunités selon l’emplacement actuel de leurs disponibilités. 

Pour la plupart des entreprises, la gestion des flux de trésorerie et l’exécution de la prévision des flux de trésorerie sont un processus fastidieux, répétitif et manuel. La plupart des entreprises comptent sur les solutions Microsoft Excel qui ont des degrés de complexité variables. Les défis liés à la prévision précise des flux de trésorerie sont les suivants :

- Les données ne sont pas disponibles pour les décideurs, car elles sont dispersées à plusieurs endroits, notamment : 
  - Le système de comptabilité ou de planification des ressources d’entreprise
  - Logiciel de planification financière
  - Excel
  - Applications logicielles supplémentaires 
- Les prévisions sont basées sur des connaissances internes en « silos » au sein de chaque domaine ou service.
- Mesurer l’exactitude de la prévision des flux de trésorerie après la réalisation des états financiers est incertain et difficile.
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a>Détails de la capacité de prévision des flux de trésorerie
La fonction de prévision des flux de trésorerie comprend les fonctionnalités suivantes. 

- Facilite l’intégration des données de flux de trésorerie provenant de systèmes externes vers Dynamics 365 Finance. Les prévisions de flux de trésorerie peuvent également utiliser l’infrastructure d’importation-exportation des données. Cette infrastructure facilite l’intégration à Excel OData. Vous pouvez également combiner des données provenant de plusieurs sources pour créer une solution complète de flux de trésorerie. 

- Introduit un emplacement intelligent des disponibilités. L’emplacement des disponibilités est créée en fonction du comportement de paiement du client pour prédire quand une entreprise peut s’attendre à ce que de l’argent arrive sur ses comptes. Elle analyse également les modèles historiques de paiement des fournisseurs, afin de prédire quand les futures factures et commandes seront probablement payées. 

- Introduit la prévision intelligente des flux de trésorerie pour les prévisions à long terme, en utilisant la prévision de séries chronologiques grâce à une intégration automatisée avec AI Builder.

- Offre la possibilité d’enregistrer un emplacement ou des prévisions de flux de trésorerie spécifiques, de les modifier, puis de comparer et de mesurer facilement les performances des prévisions avec les données financières réelles.

- Active l’analyse hypothétique via la comparaison de clichés. Par exemple, vous pouvez créer plusieurs instantanés qui représentent les vues optimistes, pessimistes et les plus réalistes de votre flux de trésorerie, puis comparer et afficher les différences.

- Permet d’afficher les prévisions de flux de trésorerie dans plusieurs devises, à travers les entités juridiques, et de filtrer et d’afficher les flux de trésorerie liés à un compte bancaire. 

- Vous permet de filtrer et d’afficher les comptes bancaires liés aux dimensions financières.

La fonctionnalité de prévision de flux de trésorerie dans Dynamics 365 Finance permettra à votre organisation de transformer une projection de flux de trésorerie fastidieuse, complexe, mais répétitive en un processus simple et automatisé. L’automatisation des aspects les plus fastidieux de la prévision des flux de trésorerie vous permet de vous concentrer sur la prise de décision critique pour obtenir les résultats commerciaux souhaités.

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a>Configuration des dimensions pour la prévision des flux de trésorerie
Un nouvel onglet sur la page **Configuration des prévisions de flux de trésorerie** vous permet de contrôler les dimensions financières à utiliser pour le filtrage dans l’espace de travail **Prévision des flux de trésorerie**. Cet onglet n’apparaîtra que lorsque la fonction de prévision des flux de trésorerie est activée. 

Sur l’onglet **Dimensions**, choisissez dans la liste des dimensions à utiliser pour le filtrage et utilisez les touches fléchées pour les déplacer vers la colonne de droite. Seules deux dimensions peuvent être sélectionnées pour filtrer les données de prévision des flux de trésorerie. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
