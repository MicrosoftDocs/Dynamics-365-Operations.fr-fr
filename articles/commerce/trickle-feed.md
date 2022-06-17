---
title: Création de commandes basée sur un flux en continu pour les transactions du magasin de vente au détail
description: Cet article décrit la création de commandes basée sur un flux en continu pour les transactions en magasin dans Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 01/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0f0ee361df8c565761e79f5b0ecf519c149f2ec0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873248"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>Création de commandes basée sur un flux en continu pour les transactions du magasin de vente au détail

[!include [banner](includes/banner.md)]

Dans Microsoft Dynamics 365 Commerce version 10.0.5 et versions ultérieures, nous vous recommandons de faire passer tous les processus de validation des relevés aux processus de validation des relevés basés sur un flux en continu. Des performances et des avantages commerciaux importants sont associés à l’utilisation de la fonctionnalité de flux en continu. Les transactions de vente sont traitées tout au long de la journée. Les opérations d’appel d’offres et de gestion de trésorerie sont traitées sur le tableau d’analyse en fin de journée. La fonctionnalité de flux en continu permet le traitement continu des commandes client, des factures et des paiements. Par conséquent, les stocks, les revenus et les paiements sont mis à jour et reconnus en temps quasi réel.

## <a name="use-trickle-feed-based-posting"></a>Utilisation de la validation basée sur un flux en continu

> [!IMPORTANT]
> Avant d’activer la validation basée sur un flux en continu, vous devez vous assurer qu’il n’y a pas de relevés calculés et non validés. Validez tous les relevés avant d’activer la fonctionnalité. Vous pouvez vérifier les relevés ouverts dans l’espace de travail **Finances du magasin**.

Pour activer la validation basée sur un flux en continu des transactions de vente au détail, activez la fonctionnalité **Relevés de vente au détail – Flux en continu** dans l’espace de travail **Gestion des fonctionnalités**. Les relevés sont fractionnés en deux types : relevés transactionnels et tableaux d’analyse.

### <a name="transactional-statements"></a>Relevés transactionnels

Le traitement des relevés transactionnels est conçu pour une exécution à une fréquence élevée au cours de la journée afin que les documents soient créés lorsque les transactions sont chargées dans Commerce Headquarters. Les transactions sont chargées des magasins vers Commerce Headquarters lorsque vous exécutez la **Tâche P**. Vous devez également exécuter la tâche **Valider les transactions en magasin** pour valider les transactions afin que le relevé transactionnel les récupère.

Planifiez les tâches suivantes pour qu’elles s’exécutent à une fréquence élevée :

- Pour calculer un relevé transactionnel, exécutez la tâche **Calculer les relevés transactionnels par lots** (**Retail et Commerce \> IT Retail et Commerce \> Validation du PDV \> Calculer les relevés transactionnels par lots**). Ce travail récupérera toutes les transactions non validées et validées, puis les ajoutera à un nouveau relevé transactionnel.
- Pour valider les relevés transactionnels dans un lot, exécutez la tâche **Valider les relevés transactionnels par lots** (**Retail et Commerce \> IT Retail et Commerce \> Validation du PDV \> Valider les relevés transactionnels par lots**). Cette tâche exécute le processus de validation et crée des commandes client, des factures de vente, des journaux de paiement, des journaux d’escompte et des transactions revenus-dépenses pour les relevés non validés qui ne contiennent aucune erreur. 

### <a name="financial-statements"></a>Tableaux d’analyse

Le traitement du tableau d’analyse est censé être un processus de fin de journée. Ce type de traitement des relevés ne prend en charge que la méthode de clôture **Équipe** et ne prélève que les équipes fermées. Les relevés se limitent au rapprochement financier. Ils créent uniquement les journaux pour les montants de différence entre le montant calculé et le montant de la transaction pour les différents modes de paiement, ainsi que les journaux pour d’autres transactions de gestion des disponibilités.

Les tableaux d’analyse permettent également de vérifier les transactions suivantes : transactions de comptage de caisse, transactions de paiement, transactions de paiement remises en banque et transactions de paiements remises en coffre-fort. La page de détails sur les offres est uniquement visible lorsqu’un tableau d’analyse est sélectionné.

![Image affichant la section des détails sur les offres du formulaire des relevés validés uniquement lorsqu’un tableau d’analyse est sélectionné.](./media/Trickle-feed-posted-statements-transaction-view.png)

Planifiez les heures de début et de fin des tâches de tableau d’analyse suivantes en fonction de la fin de journée prévue :

- Pour calculer un tableau d’analyse, exécutez la tâche **Calculer les tableaux d’analyse par lots** (**Retail et Commerce \> IT Retail et Commerce \> Validation du PDV \> Calculer les tableaux d’analyse par lots**). Cette tâche collecte toutes les transactions financières non validées et les ajouter à un nouveau tableau d’analyse.
- Pour valider des tableaux d’analyse par lots, exécutez la tâche **Valider les tableaux d’analyse par lots** (**Retail et Commerce \> IT Retail et Commerce \> Validation du PDV \> Valider les tableaux d’analyse par lots**).

### <a name="manually-create-statements"></a>Créer manuellement des relevés

Les types Relevé transactionnel et Tableau d’analyse peuvent également être créés manuellement. 

1. Accédez à **Retail et Commerce \> Canaux \> Magasins**, puis sélectionnez **Relevés**. 
2. Sélectionnez **Nouveau**, puis sélectionnez le type de relevé à créer. Les champs de la page **Relevés** affichent les données pertinentes pour le type de relevé sélectionné et les actions sous le champ **Groupe de relevés** de la page affichent les actions pertinentes.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
