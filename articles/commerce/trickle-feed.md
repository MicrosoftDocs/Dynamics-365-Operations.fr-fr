---
title: Création de commandes basée sur un flux en continu pour les transactions du magasin de vente au détail
description: Cette rubrique décrit la création de commandes basée sur un flux en continu pour les transactions en magasin dans Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 09/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 79f99b9b401de3e3bcca6ec5a13a3b4f7bad6f8c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459024"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>Création de commandes basée sur un flux en continu pour les transactions du magasin de vente au détail

[!include [banner](includes/banner.md)]

Dans Dynamics 365 Retail versions 10.0.4 et antérieures, la validation des relevés est une opération effectuée en fin de journée et toutes les transactions sont validées dans les registres en fin de journée. Les transactions volumineuses doivent ensuite être traitées dans un intervalle de temps limité, ce qui crée parfois une charge, des verrous et des échecs de validation des relevés. Les détaillants ne peuvent pas non plus constater le produit et les paiements dans leurs registres tout au long de la journée.

Avec la création de commandes basée sur un flux en continu introduite dans Retail version 10.0.5, les transactions sont traitées tout au long de la journée, et seul le rapprochement financier des modes de paiement et d’autres transactions de gestion des disponibilités sont traités en fin de journée. Cette fonctionnalité fractionne la charge de création des commandes client, des factures et des paiements tout au long de la journée, ce qui offre de meilleures performances perçues ainsi que la possibilité de constater le produit et les paiements dans les registres en temps quasi réel. 


## <a name="how-to-use-trickle-feed-based-posting"></a>Utilisation de la validation basée sur un flux en continu
  
1. Pour activer la validation basée sur un flux en continu des transactions de vente au détail, activez la fonctionnalité nommée **Relevés de vente au détail – Flux en continu** à l’aide de la gestion des fonctionnalités.

    > [!IMPORTANT]
    > Avant d’activer cette fonctionnalité, assurez-vous qu’aucun relevé n’est en attente de validation.

2. Le document actuel du relevé est fractionné en deux types : relevé transactionnel et tableau d’analyse.

      - Le relevé transactionnel prélève toutes les transactions non validées et validées et crée des commandes client, des factures client, des journaux de paiement et de remise, ainsi que des transactions de revenus/dépenses à la fréquence que vous configurez. Vous devez configurer ce processus pour qu’il s’exécute à une fréquence élevée afin que les documents soient créés lorsque les transactions sont chargées dans Headquarters via la tâche P. Avec le relevé transactionnel qui crée déjà des commandes client et des factures client, il n’est pas vraiment nécessaire de configurer le traitement par lots **Valider le stock**. Toutefois, vous pouvez toujours l’utiliser pour répondre aux besoins spécifiques de votre entreprise.  
      
     - Le tableau d’analyse est conçu pour être créé en fin de journée et prend uniquement en charge la méthode de clôture **Équipe**. Ce relevé est limité au rapprochement financier et crée uniquement les journaux pour les montants de différence entre le montant calculé et le montant de la transaction pour les différents modes de paiement, ainsi que les journaux pour d’autres transactions de gestion des disponibilités.   

3. Pour calculer le relevé transactionnel, accédez à **Retail et Commerce > IT Retail et Commerce > Validation du PDV > Calculer les relevés transactionnels par lots**. Pour valider les relevés transactionnels par lots, accédez à **Retail et Commerce > IT Retail et Commerce > Validation du PDV > Valider les relevés transactionnels par lots**.

4. Pour calculer le tableau d’analyse, accédez à **Retail et Commerce > IT Retail et Commerce > Validation du PDV > Calculer les tableaux d’analyse par lots**. Pour valider les tableaux d’analyse par lots, accédez à **Retail et Commerce > IT Retail et Commerce > Validation du PDV > Valider les tableaux d’analyse par lots**.

> [!NOTE]
> Les options de menu **Retail et Commerce > IT vente au détail et commerce > Validation du PDV > Calculer les relevés par lots** et **Retail et Commerce > IT vente au détail et commerce > Validation du PDV > Valider les relevés par lots** sont supprimées avec cette nouvelle fonctionnalité.

Sinon, les types Relevé transactionnel et Tableau d’analyse peuvent être créés manuellement. Accédez à **Retail et Commerce > Canaux > Magasins** et cliquez sur **Relevés**. Cliquez sur **Nouveau**, puis choisissez le type de relevé à créer. Les champs de la page **Relevés** et les actions sous le champ **Groupe de relevés** de la page affichent des données et actions pertinentes selon le type de relevé sélectionné.
