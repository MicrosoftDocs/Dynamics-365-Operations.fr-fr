---
title: Planifier la capacité de charge de travail
description: Cette rubrique explique comment paramétrer et planifier la capacité de charge de travail pour les collaborateurs d'un entrepôt ou pour un entrepôt entier.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd4225d9e7ad65939c57cb770ba521377c87dea3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217262"
---
# <a name="schedule-workload-capacity"></a>Planifier la capacité de charge de travail

[!include[banner](../includes/banner.md)]

Vous pouvez programmer la capacité de la charge de travail pour les entrepôts, et vous pouvez également prévoir les charges de travail actuelles et futures pour les collaborateurs des entrepôts individuels. Vous pouvez prévoir la charge de travail pour l'ensemble de l'entrepôt, ou vous pouvez prévoir la charge de travail séparément pour les charges de travail entrantes et sortantes.

Pour prévoir la charge de travail sortante pour les entrepôts sélectionnés, les données du calcul PDP/MRP doivent être disponibles pour ces entrepôts. Pour plus d'informations, voir [Vue d'ensemble des plans généraux](../master-planning/master-plans.md).

## <a name="schedule-and-view-workloads-for-a-warehouse"></a>Planification et affichage des charges de travail pour un entrepôt

Pour planifier la capacité de la charge de travail d'un entrepôt, vous devez créer un paramétrage de charge de travail pour un ou plusieurs entrepôts, puis associer ce paramétrage à un plan général. Dans le paramétrage de la capacité de la charge de travail, vous pouvez définir des limites pour le poids ou le volume des transactions entrantes et sortantes. Vous pouvez également créer plusieurs paramétrages pour chaque entrepôt, puis associer le paramétrage à des plans généraux individuels. Vous pouvez par exemple utiliser cette approche pour répondre aux modifications saisonnières du personnel.

Si les collaborateurs d'un entrepôt utilisent des transactions à la fois pour les charges de travail entrantes et sortantes, vous pouvez configurer le paramétrage de la capacité de l'entrepôt de façon à ce que la charge de travail soit projetée dans une vue combinée.

Pour planifier et afficher les charges de travail pour les entrepôts, procédez comme suit :

1. Créez un paramétrage de la capacité de la charge de travail et définissez des limites de capacité de la charge de travail pour un ou plusieurs entrepôts.
2. Associez le paramétrage de la capacité de la charge de travail à un plan général pour créer des projections de charge de travail et spécifier la durée pendant laquelle celles-ci s'appliquent.

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a>Création d'un paramétrage de la capacité de la charge de travail pour un entrepôt

1. Sélectionnez **Gestion des stocks** \> **Paramétrage** \> **Surveillance de l'entrepôt** \> **Capacité de la charge de travail**.
2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un paramétrage de la capacité de charge de travail.
3. Dans l'organisateur **Entrepôts**, sélectionnez **Nouveau** puis entrez les valeurs sur la ligne pour associer un entrepôt au paramétrage de la capacité de la charge de travail.
4. Activez la case à cocher **Combinaison des charges de travail entrante et sortante** si l'état **Capacité de la charge de travail** doit afficher la charge de travail totale pour les transactions entrantes et sortantes sur une seule vue.
5. Dans l'organisateur **Types de transactions**, sélectionnez les types de transactions entrantes et sortantes auxquels les limites de charge de travail s'appliquent.

    > [!NOTE]
    > Vous devez sélectionner au moins un type de transaction pour la charge de travail entrante et la charge de travail sortante.

#### <a name="define-limits-for-volume-or-weight"></a>Définir des limites pour le volume ou le poids

Vous pouvez paramétrer des limites pour le volume ou le poids selon la limitation appropriée pour le personnel de l'entrepôt. Les limites que vous spécifiez sont incluses dans la projection de la capacité de la charge de travail que vous pouvez afficher dans l'état **Capacité de la charge de travail**.

Le volume standard d'un article en stock et le poids d'un article en stock doivent être spécifiés pour tous les produits pour pouvoir projeter des informations sur le volume et le poids des articles. Les champs requis sont disponibles dans les groupes de champs suivants de l'organisateur **Gérer le stock** de la page **Détails des produits lancés** :

- Traitement
- Dimensions physiques
- Mesures pondérales

Si ces informations ne sont pas spécifiées correctement, vous recevez un message lors de la génération de l'état **Capacité de la charge de travail**. Depuis l'état, vous pouvez ensuite effectuer un zoom avant afin d'identifier les informations manquantes requises pour la projection de la future charge de travail.

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a>Association d'un paramétrage de la capacité de la charge de travail à un plan général

1. Sélectionnez **Gestion des stocks** \> **Périodique** \> **Programmer la charge de travail**.
2. Dans le champ **Plans généraux**, sélectionnez le plan général à utiliser pour les projections de charge de travail.
3. Dans le champ **Nombre de jours**, spécifiez le nombre de jours couvert par la projection de charge de travail.
4. Dans le champ **Charge de travail**, sélectionnez le paramétrage de charge de travail à associer au plan général.

### <a name="view-workload-capacity"></a>Affichage de la capacité de la charge de travail

1. Sélectionnez **Gestion des stocks** \> **Recherches et états** \> **États sur le stock physique** \> **Capacité de la charge de travail**.
2. Dans le champ **Nombre de colonnes**, spécifiez le nombre de colonnes à afficher dans l'état.
3. Dans le champ **Type de commande**, sélectionnez **Prévu et confirmé**, **Prévu** ou **Confirmé** pour indiquer le type de commandes à projeter dans l'état.
4. Dans le champ **Type de charge**, sélectionnez un type de charge pour spécifier si la capacité de la charge de travail est projetée pour le volume ou le poids.
5. Dans le champ **Capacité de la charge de travail**, sélectionnez un paramétrage pour la capacité de la charge de travail.
