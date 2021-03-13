---
title: Paramétrer des codes motif
description: Dynamics 365 Human Resources utilise des codes de motif pour expliquer pourquoi les avantages d'un employé changent.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae82c8312d344f5380adec8413766304681a0a05
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112501"
---
# <a name="set-up-reason-codes"></a>Paramétrer des codes motif

Dynamics 365 Human Resources utilise des codes de motif pour expliquer pourquoi les avantages d'un employé changent.

> [!NOTE]
> Depuis janvier 2021, les codes motif migrent vers l'espace de travail **Gestion du personnel** au lieu de l'espace de travail **Gestion des avantages**. Pour plus d'informations, voir [Migrer manuellement les codes motif vers la gestion du personnel](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).

## <a name="create-reason-codes"></a>Créer des codes motifs

1. Dans l'espace de travail **Gestion du personnel** (ou l'espace de travail **Gestion des avantages** si vos codes motifs n'ont pas encore migré), sélectionnez **Liens**, puis **Codes motifs**.

2. Sélectionnez **Nouveau**.

3. Spécifiez les valeurs des champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Code motif** | Nom unique pour identifier la raison pour laquelle un employé modifierait la souscription à un régime de prestations. |
   | **Description** | Description du code motif. |

4. Sous **Scénarios applicables**, définissez **Gestion des avantages** sur **Oui**. (Ne s'applique pas si vos codes motif n'ont pas encore migré vers l'espace de travail **Gestion du personnel**.)

5. Sélectionnez **Enregistrer**.

## <a name="manually-migrate-reason-codes-to-personnel-management"></a>Migrer manuellement les codes motif vers Gestion du personnel

En janvier 2021, les codes motif ont migré vers l'espace de travail **Gestion du personnel** au lieu de l'espace de travail **Gestion des avantages**. La plupart des données de code motif migreront automatiquement dans votre environnement. Il est possible que certaines données de code motif ne migrent pas. Par exemple, les codes motif ont désormais un maximum de 15 caractères, de sorte que ceux de plus de 15 caractères ne migreront pas automatiquement.

Vous verrez une bannière sur la page **Liens** de l'espace de travail **Gestion des avantages** vous informant de la migration et indiquant si des codes motif n'ont pas migré.

1. Sélectionnez **Codes motif** pour plus de détails sur l'état de la migration.

   [![Codes motif](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)

2. Sélectionnez un code motif dont la migration a échoué.

   [![Statut de migration du code motif](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)

3. Sélectionnez **Migrer le code motif**.

   [![Migrer le code motif](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)

4. Dans le volet **Bénéficier de la migration du code motif**, vous avez deux options pour mapper à un code motif de gestion du personnel :

   - Pour utiliser un code motif existant dans la gestion du personnel, choisissez-en un dans le menu déroulant **Utiliser le code motif existant**.
     > [!NOTE]
     > Vous ne pouvez utiliser un code motif existant dans Gestion du personnel que si un autre code motif de Gestion des avantages n'y a pas déjà été migré.
   - Pour créer un nouveau code motif dans la gestion du personnel, saisissez-en un nouveau dans **Nouveau code motif**, puis entrez une description dans **Nouvelle description**.

   [![Mettre en correspondance vers un code motif de Gestion du personnel](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)

Une fois les codes motif migrés vers Gestion du personnel, l'option permettant de les utiliser dans Gestion des avantages est automatiquement définie sur **Oui**.

[![Utiliser le code motif dans Gestion des avantages](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)