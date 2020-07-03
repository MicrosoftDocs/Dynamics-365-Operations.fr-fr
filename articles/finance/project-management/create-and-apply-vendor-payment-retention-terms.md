---
title: Créer et appliquer des conditions de rétention de paiement fournisseur
description: Cette rubrique fournit des informations sur le paramétrage et le maintien à jour des conditions de rétention des paiements fournisseur.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410221"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a>Créer et appliquer des conditions de rétention de paiement fournisseur

[!include [banner](../includes/banner.md)] 

La configuration des conditions de rétention des paiements fournisseur pour un projet est utile lorsque votre organisation souhaite retenir une partie des paiements effectués à un fournisseur. Par exemple, lorsque vous souhaitez reporter le paiement à un fournisseur jusqu'à ce que les produits livrés répondent à vos attentes. Les conditions de rétention des paiements fournisseur peuvent être stipulées au moment de la négociation d'un contrat avec le fournisseur.

## <a name="create-vendor-payment-retention-terms"></a>Créer des conditions de rétention de paiement fournisseur

Vous pouvez entrer le pourcentage du paiement fournisseur à retenir et le pourcentage des montants retenus précédemment à débloquer. Les montants sont automatiquement retenus sur les factures fournisseur jusqu'à ce que le contrat atteigne le niveau d'achèvement désigné. Une fois les conditions de rétention définies pour un fournisseur, vous pouvez les appliquer à n'importe quel projet concernant ce fournisseur.

Procédez comme suit pour paramétrer et tenir à jour les conditions de rétention des paiements fournisseur. 

1. Accédez à **Gestion de projet et comptabilité** > **Rétention** > **Conditions de rétention des paiements fournisseur**.
2. Sélectionnez **Nouveau** pour ajouter de nouvelles conditions de rétention fournisseur. La valeur de l'**ID de règle** des nouvelles conditions est entrée automatiquement. 
3. Entrez une brève description dans le champ **Description** et, dans le raccourci **Conditions**, sélectionnez **Ajouter une ligne** pour saisir des valeurs de condition pour les éléments suivants :

   - **Pourcentage d'unités livrées** : entrez un pourcentage d'achèvement pour la condition. Les montants sont automatiquement retenus sur les factures fournisseur jusqu'à ce que l'état d'avancement du projet soit égal au pourcentage spécifié. Par exemple, si vous entrez 50,00, les paiements sont retenus tant que le projet n'est pas terminé à 50 %.
   - **Pourcentage à retenir** : entrez le pourcentage du montant de la facture fournisseur à retenir. Par exemple, si vous entrez 10,00 dans ce champ, 10 % du montant de la facture fournisseur sera retenu jusqu'à ce que le projet atteigne le pourcentage d'achèvement sélectionné dans le champ **Pourcentage d'unités livrées**.
   - **Pourcentage à débloquer** : sélectionnez **Ajouter une ligne** le pourcentage des montants précédemment retenus à débloquer au niveau d'achèvement sélectionné.

> [!NOTE]
> Si vous avez plusieurs jalons pour différents niveaux d'achèvement du projet, entrez une ligne de conditions de rétention fournisseur distincte pour chaque règle de rétention. Chaque ligne peut préciser un pourcentage différent à retenir ou à débloquer pour chaque niveau d'achèvement de projet désigné.

Une fois les conditions de rétention définies pour un fournisseur, vous pouvez les appliquer à un projet.

## <a name="apply-vendor-retention-terms-to-a-project"></a>Appliquer les conditions de rétention de paiement fournisseur à un projet

1. Accédez à **Gestion de projet et comptabilité** > **Projets** > **Tous les projets** et ouvrez un projet à partir de la page de liste des projets.
2. Dans l'organisateur **Accords fournisseur**, cliquez sur **Ajouter une ligne**.
3. Dans le champ **Code compte**, sélectionnez l'une des options suivantes : 

   - **Tableau** : Les conditions de rétention fournisseur s'appliquent à un seul fournisseur.
   - **Groupe** : Les conditions de rétention fournisseur s'appliquent à tous les fournisseurs du groupe de fournisseurs.
   - **Tous** : Les conditions de rétention fournisseur s'appliquent à tous les fournisseurs.

4. Dans le champ **Fournisseur/Groupe de fournisseurs**, sélectionnez le fournisseur ou le groupe de fournisseurs auxquels les conditions de rétention fournisseur s'appliquent. Si vous avez sélectionné **Tous** à l'étape précédente, ce champ n'est pas disponible.
5. Dans le champ **Conditions de rétention fournisseur**, sélectionnez les conditions de rétention que vous avez créées dans la procédure précédente.
6. Si le projet a également une clause Payer quand payé paramétrée pour le fournisseur, entrez le pourcentage seuil du projet dans le champ **Pourcentage minimal de mise en œuvre de la clause Payer quand payé**.

Les conditions de rétention fournisseur sont également affichées dans les commandes fournisseur créées pour le fournisseur.
