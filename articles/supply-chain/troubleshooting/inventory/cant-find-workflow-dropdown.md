---
title: La boîte de dialogue déroulante « Workflow » pour les journaux d’inventaire est introuvable
description: Vous ne trouvez pas la boîte de dialogue déroulante « Workflow » sur la page du journal, ou les opérations de workflow associées ne sont pas disponibles
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8b2772a75c2388f4d78a459f9dfb72ad7c1be4ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476318"
---
# <a name="you-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>La boîte de dialogue déroulante « Workflow » pour les journaux d’inventaire est introuvable

## <a name="symptoms"></a>Symptômes

Vous ne trouvez pas la boîte de dialogue déroulante **Workflow** sur la page du journal, ou les opérations de workflow associées ne sont pas disponibles.

Ce problème peut se produire pour trois raisons, comme décrit dans les sections suivantes.

## <a name="resolution-1"></a>Résolution 1

Si le problème s’applique à tous les utilisateurs, il peut se produire car le workflow d’approbation n’a pas été attribué au nom du journal. Pour régler le problème, procédez comme suit.

1. Allez dans **Gestion des stocks &gt; Paramétrage &gt; Noms de journal &gt; Inventaire**.
1. Dans le volet de liste, sélectionnez un nom de journal pour ouvrir ses paramètres.
1. Dans le raccourci **Général**, définissez l’option **Workflow d’approbation** sur *Oui*. Si vous êtes invité à confirmer la modification, sélectionnez **Oui**.
1. Dans le champ **Workflow**, sélectionnez le workflow que vous souhaitez utiliser pour le nom de journal sélectionné.

## <a name="resolution-2"></a>Résolution 2

Si votre workflow utilise un code personnalisé, des problèmes peuvent se produire après la mise à niveau du système. Par exemple, dans le workflow du journal, le bouton **Envoyer** peut être grisé, vous ne pouvez donc pas le sélectionner pour approuver un envoi.

Si le bouton **Envoyer** est grisé, votre workflow a peut-être été personnalisé, ce qui signifie que la méthode du workflow, `canSubmitToWorkflow()` dans `FormDataUtil`, a été étendue. Pour résoudre ce problème, modifiez la façon dont vous étendez la méthode de `canSubmitToWorkflow()` pour utiliser la structure dans l’exemple suivant.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

## <a name="resolution-3"></a>Résolution 3

Si le problème ne s’applique qu’à quelques utilisateurs spécifiques, ces utilisateurs peuvent ne pas disposer des privilèges de sécurité nécessaires pour exécuter des opérations de workflow sur les journaux d’inventaire. Vérifiez que chaque utilisateur affecté dispose du privilège de sécurité *Tenir à jour le workflow du journal d’inventaire*. Par défaut, ce privilège est attribué à un droit qui porte le même nom, et ce droit est appliqué aux rôles *Magasinier* et *Gestionnaire de l’entrepôt*.
