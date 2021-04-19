---
title: Ajustements de limite de crédit
description: Cette rubrique explique comment paramétrer et ajouter des ajustements de limite de crédit.
author: mikefalkner
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: b1669029f28cef924170b47340567af49525e1b7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835362"
---
# <a name="credit-limit-adjustments"></a>Ajustements de limite de crédit 

[!include [banner](../includes/banner.md)]

Les ajustements de limite de crédit permettent aux gestionnaires de crédit de mettre à jour les limites de crédit et les dates d’expiration d’un seul client, d’un groupe de clients ou de tous les clients via un processus de validation. Vous pouvez ajouter des entrées d’ajustement de limite de crédit pour mettre à jour les clients et les groupes de crédit client, ou vous pouvez les utiliser pour calculer des limites de crédit automatiques. Les entrées peuvent ensuite être examinées, envoyées pour approbation via un workflow et validées sur les comptes clients.

## <a name="set-up-credit-limit-adjustments"></a>Paramétrer des ajustements de limite de crédit

Vous pouvez créer des écritures dans le journal d’ajustement de limite de crédit à la page **Ajustement de limite de crédit** (**Gestion de crédit \> Ajustements de limite de crédit \> Ajustements de limite de crédit**).

1. Sélectionnez **Nouveau**. Un nouveau groupe d’entrées est créé avec un numéro d’ajustement de limite de crédit.
2. Sélectionnez le type d’ajustement de limite de crédit :

    - Sélectionnez **Limite de crédit** pour modifier la limite de crédit du client.
    - Sélectionnez **Limite de crédit temporaire** pour créer une limite de crédit temporaire au lieu de modifier la limite de crédit actuelle du client. Les limites de crédit temporaires remplacent la limite de crédit d’un client pour une période définie. Après cette période, la limite de crédit du client est utilisée à nouveau.
3. Entrez une description. 

Si la case **Validée** est cochée, les limites de crédit ont été appliquées. Le champ **Statut d’approbation** indique l’état du workflow du journal. Un workflow est optionnel.

### <a name="add-credit-limit-adjustments"></a>Ajouter des ajustements de limite de crédit

Pour ajouter manuellement des ajustements de limite de crédit, sélectionnez **Lignes**, puis suivez ces étapes.

1. Pour ajouter un ajustement de limite de crédit pour un client, utilisez le menu **Ajustements clients**. Pour ajouter une limite de crédit pour un groupe de crédit client, sélectionnez **Ajustements du groupe de crédit client**.
2. Saisissez un compte client pour le compte client de facturation qui doit être mis à jour avec la nouvelle limite de crédit. Si vous avez sélectionné **Ajustements du groupe de crédit client** à l’étape 1, entrez le groupe de crédits client. Vous ne pouvez pas saisir à la fois un compte client et un ID de groupe de crédits client sur la même ligne de journal.

    La limite de crédit actuelle s’affiche et le nom apparaît automatiquement.

3. Entrez la nouvelle limite de crédit qui devrait remplacer la limite de crédit actuelle lorsque la saisie de limite de crédit est validée.
4. Entrez une date pour définir la nouvelle date d’expiration de la limite de crédit client. Vous devez entrer une date d’expiration de limite de crédit lorsque vous créez un ajustement de limite de crédit.

Le champ **Statut d’approbation** indique l’état du workflow de la ligne journal.

Si vous souhaitez que les ajustements de limite de crédit soient générés automatiquement, vous pouvez utiliser le menu **Générer** dans le volet Actions.
 
### <a name="add-temporary-credit-limit-adjustments"></a>Ajouter des ajustements de limite de crédit temporaires

Pour ajouter manuellement des ajustements de limite de crédit temporaires, suivez les étapes des lignes de journal.

1. Pour ajouter un ajustement de limite de crédit pour un client, utilisez le menu **Ajustements clients**. Pour ajouter une limite de crédit pour un groupe de crédit client, sélectionnez **Ajustements du groupe de crédit client**.
2. Saisissez un compte client pour le compte client de facturation qui doit être mis à jour avec la nouvelle limite de crédit. Si vous avez sélectionné **Ajustements du groupe de crédit client** à l’étape 1, entrez le groupe de crédits client. Vous ne pouvez pas saisir à la fois un compte client et un ID de groupe de crédits client sur la même ligne de journal.

    Si une limite de crédit temporaire active ou future existe déjà, la limite de crédit temporaire actuelle et les plages de dates apparaissent pour chaque limite de crédit temporaire. Le nom apparaît automatiquement.

3. Entrez la nouvelle limite de crédit qui devrait remplacer la limite de crédit actuelle.
4. Dans les champs **Nouvelle date de début** et **Nouvelle date de fin**, définissez la période de validité de la limite de crédit avancée. Vous devez entrer des dates d’expiration de limite de crédit lorsque vous créez un journal d’ajustement de limite de crédit.

Le champ **Statut d’approbation** indique l’état du workflow de la ligne journal.

## <a name="generate-credit-limit-adjustments"></a>Générer des ajustements de limite de crédit

Vous pouvez également faire ajuster automatiquement les limites de crédit. Dans le volet Actions, sélectionnez **Générer** puis l’une des options suivantes :

- D’un client existant
- Du groupe de créditS client existant
- Limites de crédit automatiques

### <a name="from-existing-customer"></a>D’un client existant

Vous pouvez créer des lignes de journal à partir de clients existants. Lorsque vous sélectionnez **Générer \> D’un client existant**, une boîte de dialogue apparaît dans laquelle vous pouvez fournir des critères de sélection des clients et de calcul des nouvelles limites.

1. Entrez une valeur d’ajustement pour ajouter ou soustraire un montant de la limite de crédit. Saisissez une valeur négative pour diminuer la limite de crédit actuelle ou une valeur positive pour l’augmenter.
2. Dans le **Type de valeur**, sélectionnez comment la valeur que vous avez entrée à l’étape 1 doit être utilisée pour calculer la nouvelle limite de crédit :

    - Sélectionnez **Valeur fixe** pour modifier la limite de crédit d’un montant.
    - Sélectionnez **Pourcentage** pour modifier la limite de crédit d’un pourcentage.

3. Entrez une valeur utilisée pour arrondir la limite de crédit calculée. Par exemple, entrez **10,00** pour arrondir la limite de crédit aux 10,00 devises les plus proches.
4. Paramétrez le champ **Type d’arrondi** pour spécifier si le reste doit être arrondi vers le haut ou vers le bas.
5. Sélectionnez la méthode utilisée pour ajuster les dates.

    - Si vous sélectionnez **Absolu**, vous pouvez saisir des dates qui définissent la plage de dates pour les limites de crédit.
    - Si vous sélectionnez **Relatif**, vous pouvez saisir des dates de décalage pour la plage. La plage de dates actuelle pour la limite de crédit sera ajustée par la compensation.

6. Utilisez le raccourci **Enregistrements à inclure** pour filtrer la liste des clients inclus. Si vous n’incluez pas de filtres, des entrées de limite de crédit seront générées pour tous les clients.
7. Sélectionnez **OK** pour créer les entrées d’ajustement de limite de crédit.

### <a name="from-existing-customer-credit-group"></a>Du groupe de créditS client existant

Vous pouvez créer des lignes de journal à partir de groupes de crédits de clients existants. Lorsque vous sélectionnez **Générer \> D’un groupe de crédit de client existant**, une boîte de dialogue apparaît dans laquelle vous pouvez fournir des critères de sélection des groupes de crédit clients et de calcul des nouvelles limites. Les critères sont les mêmes que ceux utilisés pour créer des lignes de journal à partir de clients existants. Consultez les étapes de la section précédente.

### <a name="automatic-credit-limits"></a>Limites de crédit automatiques

Vous pouvez créer des limites de crédit automatiques pour définir et mettre à jour les limites de crédit client. Les limites de crédit automatiques sont créées pour un groupe de risque et elles sont basées sur des valeurs spécifiques utilisées dans les groupes de notation. Vous pouvez utiliser ces limites de crédit automatiques pour générer des entrées de limite de crédit. Si un client a été affecté à un groupe de risque spécifique et que les informations de crédit du client correspondent aux critères d’une limite de crédit automatique, une entrée d’ajustement de limite de crédit est créée.

#### <a name="create-automatic-credit-limits"></a>Créer des limites de crédit automatiques

Vous créez des limites de crédit automatiques à l’aide d’ajustements de limite de crédit. Lorsque vous sélectionnez **Générer \> Limites de crédit automatiques**, une boîte de dialogue s’affiche dans laquelle vous pouvez définir une date d’expiration pour les nouvelles limites de crédit qui seront créées en fonction des groupes de risques auxquels les clients sont affectés. Lorsque vous avez terminé, sélectionnez **OK** pour créer les lignes d’ajustement de limite de crédit.

### <a name="post-adjustments"></a>Valider des ajustements

Après avoir créé des lignes d’ajustement de limite de crédit, vous pouvez utiliser le bouton **Valider** dans le volet Actions pour publier les entrées et mettre à jour les limites de crédit client. Cependant, si vous avez configuré un workflow, vous devez sélectionner **Workflow \> Soumettre** dans le volet Actions pour soumettre le journal pour approbation.

### <a name="credit-limit-adjustments-workflows"></a>Workflows d’ajustements de limite de crédit

Les workflow d’**Ajustements de limite de crédit** peuvent être utilisés pour envoyer des ajustements de limite de crédit via un processus d’approbation de workflow. Vous pouvez créer deux workflows sur la page **Gestion de crédit worfklow** (**Gestion de crédit \> Paramétrer \> Gestion de crédit worfklow**) :

- **Ajustements de limite de crédit** – Ce workflow peut être utilisé pour approuver des entrées au niveau de l’en-tête.
- **Ligne d’ajustement de limite de crédit** – Ce workflow peut être utilisé pour approuver les entrées d’ajustement afin que les entrées puissent être approuvées par différentes personnes, en fonction des critères du workflow.

> [!NOTE]
> Lorsque vous créez le workflow **Ajustements de limite de crédit**, vous pouvez le paramétrer pour que les ajustements soient automatiquement validés une fois les lignes approuvées. Incluez simplement la tâche **Valider le journal automatiquement** dans le workflow.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]