---
title: Création de commandes basée sur un flux en continu pour les transactions du magasin de vente au détail
description: Cette rubrique décrit la création de commandes basée sur un flux en continu pour les transactions du magasin de vente au détail dans Microsoft Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
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
ms.openlocfilehash: 80233a73dbffc7380503cf03703758b187824c2a
ms.sourcegitcommit: 0262a19e32b2c0c84c731d9f4fbe8ba91822afa3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "2622664"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions-public-preview"></a>Création de commandes basée sur un flux en continu pour les transactions du magasin de vente au détail (préversion publique)

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

Dans Dynamics 365 Retail versions 10.0.4 et antérieures, la validation des relevés de vente au détail est une opération effectuée en fin de journée et toutes les transactions sont validées dans les registres en fin de journée. Les transactions volumineuses doivent ensuite être traitées dans un intervalle de temps limité, ce qui crée parfois une charge, des verrous et des échecs de validation des relevés. Les détaillants ne peuvent pas également constater le produit et les paiements dans leurs registres tout au long de la journée.

Avec la préversion publique de création de commandes basée sur un flux en continu introduite dans Retail version 10.0.5, les transactions sont traitées tout au long de la journée, et seul le rapprochement financier des modes de paiement et d'autres transactions de gestion des disponibilités sont traités en fin de journée. Cette fonctionnalité fractionne la charge de création des commandes client, des factures et des paiements tout au long de la journée, ce qui offre de meilleures performances perçues ainsi que la possibilité de constater le produit et les paiements dans les registres en temps quasi réel. 


## <a name="how-to-use-trickle-feed-based-posting"></a>Utilisation de la validation basée sur un flux en continu
  
1. Pour activer la validation basée sur un flux en continu des transactions au détail, accédez à **Administration du système > Paramétrage > Configuration des licences** et désactivez la clé **Relevés de vente au détail**.

2. Dans la même page, activez la clé de licence **Relevés de vente au détail (flux en continu) – Version préliminaire**. Lorsque vous activez cette clé, assurez-vous qu'aucun relevé n'est en attente de validation. 

> [!Important]
> Avant d'activer la clé de licence **Relevés de vente au détail (flux en continu) – Version préliminaire**, assurez-vous qu'aucun relevé n'est en attente de validation.

3. Le document actuel du relevé est fractionné en deux types différents ; relevé transactionnel et tableau d'analyse.

      - Le relevé transactionnel prélève toutes les transactions de vente au détail non validées et validées et crée des commandes client, des factures client, des journaux de paiement et de remise, ainsi que des transactions de revenus/dépenses à la fréquence que vous configurez. Vous devez configurer ce processus pour qu'il s'exécute à une fréquence élevée afin que les documents soient créés lorsque les transactions de vente au détail sont chargées dans Retail Headquarters via la tâche P. Avec le relevé transactionnel qui crée déjà des commandes client et des factures client, il n'est pas vraiment nécessaire de configurer le traitement par lots **Valider le stock**. Toutefois, vous pouvez toujours l'utiliser pour répondre aux besoins spécifiques de votre entreprise.  
      
     - Le tableau d'analyse est conçu pour être créé en fin de journée et prend uniquement en charge la méthode de clôture **Équipe**. Ce relevé est limité au rapprochement financier et crée uniquement les journaux pour les montants de différence entre le montant calculé et le montant de la transaction pour les différents modes de paiement, ainsi que les journaux pour d'autres transactions de gestion des disponibilités.   

4. Pour calculer le relevé transactionnel, cliquez sur **Vente au détail > Informatique au détail > Validation du PDV > Calculer les relevés transactionnels par lots**. Pour valider les relevés transactionnels par lots, cliquez sur **Vente au détail > Informatique au détail > Validation du PDV > Valider les relevés transactionnels par lots**.

5. Pour calculer le tableau d'analyse, cliquez sur **Vente au détail > Informatique au détail > Validation du PDV > Calculer les tableaux d'analyse par lots**. Pour valider les tableaux d'analyse par lots, cliquez sur **Vente au détail > Informatique au détail > Validation du PDV > Valider les tableaux d'analyse par lots**.

> [!NOTE]
> Les options de menu **Vente au détail > Informatique au détail > Validation du PDV > Calculer les relevés par lots** et **Vente au détail > Informatique au détail > Validation du PDV > Valider les relevés par lots** sont supprimées avec cette nouvelle fonctionnalité.

Sinon, les types Relevé transactionnel et Tableau d'analyse peuvent être créés manuellement. Accédez à **Vente au détail > Canaux > Magasins de vente au détail** et cliquez sur **Relevés de vente au détail**. Cliquez sur **Nouveau**, puis choisissez le type de relevé à créer. Les champs de la page **Relevés de vente au détail** et les actions sous le champ **Groupe de relevés** de la page affichent des données et actions pertinentes selon le type de relevé sélectionné.
