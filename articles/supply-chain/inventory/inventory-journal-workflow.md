---
title: Workflows d’approbation du journal de stock
description: Cette rubrique décrit comment paramétrer et utiliser des workflows d’approbation du journal de stock pour différents types de transactions de stock physique. Les workflows du journal de stock aident à garantir que seuls les journaux de stock approuvés peuvent être validés sur les transactions.
author: yufeihuang
ms.date: 07/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTableWorkflowDropDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-07-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: fd73c515c653de9160301e069fb25d995db40741
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778303"
---
# <a name="inventory-journal-approval-workflows"></a>Workflows d’approbation du journal de stock

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment paramétrer et utiliser des workflows d’approbation du journal de stock pour différents types de transactions de stock physique, tels que les sorties et les réceptions, les mouvements de stock, les nomenclatures et le rapprochement du stock physique. Les workflows du journal de stock aident à garantir que seuls les journaux de stock approuvés peuvent être validés sur les transactions.

> [!NOTE]
> Les workflows d’approbation du journal de stock s’appliquent uniquement aux transactions enregistrées à l’aide du module Gestion des stocks. Ils ne fonctionnent pas avec les journaux de stock déclenchés à partir du module Gestion des entrepôts.

## <a name="turn-on-the-inventory-journal-approval-workflows-feature"></a>Activer la fonctionnalité de workflows d’approbation du journal de stock

À compter de la version 10.0.21 de Supply Chain Management, cette fonctionnalité sera activée par défaut. Les administrateurs peuvent utiliser la page [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer ou la désactiver au besoin. La fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des stocks et des entrepôts*
- **Nom de la fonctionnalité :** *Workflow d’approbation du journal de stock*

## <a name="create-your-inventory-journal-approval-workflows"></a>Créer vos workflows d’approbation du journal de stock

Pour paramétrer cette fonctionnalité, vous devez créer un workflow pour chacun des types de journaux de stock que vous souhaitez contrôler. Comme différents types de journaux de stock peuvent avoir des hiérarchies d’approbation et des étapes de workflow différentes, vous pouvez configurer des workflows individuels pour chaque type de journal de stock.

Les workflows prennent en charge le contrôle de version et chacun a un ID de workflow et une version active. Vous pouvez choisir d’activer chaque nouvelle version de workflow dès sa création ou de la conserver inactive. Si différents workflows sont nécessaires pour le même type de journal, créez plusieurs workflows pour ce type de journal, puis affectez chacun d’eux à un nom de journal différent qui utilise ce type.

Pour créer vos workflows d’approbation du journal de stock :

1. Allez dans **Gestion des stocks \> Paramétrage \> Workflows de gestion des stocks**.
1. Sélectionnez **Nouveau** dans le volet Actions.
1. Choisissez le type de journal de stock pour lequel vous souhaitez paramétrer un workflow :
    - **Journal d’inventaire de balise de stock**
    - **Journal des modifications de propriété du stock**
    - **Journal des mouvements de stock**
    - **Journal de transfert de stock**
    - **Journal d’inventaire de stock**
    - **Journal de nomenclature de stock**
    - **Journal d’ajustement du stock**

    ![Boîte de dialogue Créer un workflow.](media/journal-workflow-create-workflow.png "Boîte de dialogue Créer un workflow")

1. L’application Éditeur de workflow se lance sur votre ordinateur. (Vous pouvez être invité à approuver cette action.) Utilisez-la pour concevoir votre workflow selon vos besoins. Pour plus d’informations sur l’utilisation de l’éditeur de workflow, voir [Vue d’ensemble du système de workflow](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).
1. Après avoir enregistré et fermé l’application Éditeur de workflow, vous devez choisir d’activer cette version de workflow ou de la conserver comme inactive.

> [!NOTE]
> Les workflows fournissent le contrôle de version, ce qui signifie que vous pouvez afficher une liste des versions que vous avez créées et choisir celle active. Pour afficher la liste des versions disponibles et choisir celle à activer, sélectionnez un workflow répertorié dans la page **Workflows de gestion des stocks**. Dans le volet Actions, ouvrez l’onglet **Workflow** et sélectionnez **Versions**. Une seule version peut être active à la fois pour chaque ID de workflow.

## <a name="assign-approval-workflows-to-inventory-journal-names"></a>Affecter des workflows d’approbation à des noms de journal de stock

L’étape suivante consiste à affecter un workflow du journal de stock à chaque nom de journal de stock. Pour chaque type de journal de stock, vous pouvez configurer plusieurs noms de journal de stock.

Pour associer un workflow du journal de stock à un nom de journal de stock :

1. Allez dans **Gestion des stocks \> Paramétrage \> Noms de journal \> Stock**.
1. Sélectionnez un nom de journal dans la colonne de liste pour ouvrir sa page de paramètres.
1. Dans l’organisateur **Général**, définissez l’option **Workflow d’approbation** sur **Oui**. Si vous êtes invité à approuver l’action, cliquez sur **Oui**.

    ![Affecter un workflow à un nom de journal.](media/journal-workflow-journal-name.png "Affecter un workflow à un nom de journal")

1. Ouvrez la liste déroulante **Workflow** et sélectionnez le workflow approprié. La liste affiche chaque workflow actif que vous avez créé à l’aide de l’application Éditeur de workflow.

## <a name="create-an-inventory-journal-and-send-it-for-approval"></a>Créer un journal de stock et l’envoyer pour approbation

Après avoir associé un nom de journal de stock à son workflow d’approbation du journal de stock correspondant, vous pourrez créer des journaux de stock qui utilisent ce nom, puis envoyer ces journaux pour approbation à l’aide de ce workflow. Vous ne pourrez pas valider le journal de stock tant qu’il n’aura pas été approuvé par les approbateurs configurés dans le workflow.

1. Dans le volet de navigation, développez **Gestion des stocks \> Entrées de journal \> Articles**, puis sélectionnez un type de journal de stock.
1. Sélectionnez **Nouveau** pour créer un journal du type sélectionné.
1. La boîte de dialogue **Créer un journal de stock** s’ouvre. Complétez le formulaire selon les besoins, puis cliquez sur **OK** pour enregistrer le journal.
1. Complétez le journal selon les besoins.
1. Lorsque vous créez ou ouvrez un journal de stock auquel est associé un workflow d’approbation, le bouton **Workflow** est actif dans le volet Actions. Lorsque vous êtes prêt à soumettre le journal pour approbation, cliquez sur le bouton **Workflow** pour ouvrir une boîte de dialogue déroulante, puis sélectionnez **Soumettre**. La demande d’approbation est ensuite envoyée à l’approbateur approprié, qui en est informé à l’aide de la méthode de notification configurée pour le workflow.

    ![Soumettre un journal pour approbation.](media/journal-workflow-inventory-journal.png "Soumettre un journal pour approbation")

Pour rappeler une demande d’approbation, ouvrez le journal approprié, cliquez sur le bouton **Workflow**, puis sélectionnez **Rappeler**. Le workflow est alors réinitialisé.

Une fois que votre journal aura été approuvé, vous pourrez le valider. Pour valider le journal, sélectionnez **Valider** dans le volet Actions. Si le bouton **Valider** n’est pas actif, le journal n’a pas encore été approuvé.

## <a name="respond-to-an-inventory-journal-approval-request"></a>Répondre à une demande d’approbation du journal de stock

Si vous êtes un approbateur, vous devez recevoir un message chaque fois que votre approbation est nécessaire (comme configuré dans le workflow approprié). Vous pouvez ensuite approuver ou rejeter une demande d’approbation de journal en procédant comme suit :

1. Dans le volet de navigation, développez **Gestion des stocks \> Entrées de journal \> Articles**, puis sélectionnez un type de journal de stock.
1. Ouvrez le journal approprié et passez-le en revue.
1. Cliquez sur le bouton **Workflow** dans le volet Actions pour ouvrir une boîte de dialogue déroulante. Sélectionnez l’une des options suivantes :
    - **Approuver** : pour approuver la demande.
    - **Rejeter** : pour rejeter la demande.
    - **Autre \> Demander une modification** : pour envoyer un message au demandeur lui demandant de modifier quelque chose de spécifique, puis soumettre la demande à nouveau.
    - **Autre \> Déléguer** : pour déléguer l’approbation à un autre utilisateur.
    - **Autre \> Rappeler** : pour rappeler la demande d’approbation (réinitialise le workflow).
    - **Autre \> Historique du workflow** : pour afficher l’historique de ce workflow d’approbation jusqu’à présent.

## <a name="review-the-approval-history"></a>Consulter l’historique d’approbation

Comme pour les autres types de workflows, vous pouvez utiliser la page **Historique du workflow** pour afficher l’historique du workflow d’approbation de n’importe quel journal.

Pour consulter l’historique du workflow d’un journal :

1. Dans le volet de navigation, développez **Gestion des stocks \> Entrées de journal \> Articles**, puis sélectionnez un type de journal de stock.
1. Ouvrez le journal approprié.
1. Cliquez sur le bouton **Workflow** dans le volet Actions pour ouvrir une boîte de dialogue déroulante. Sélectionnez **Historique du workflow**. Pour plus d’informations, voir [Afficher l’historique du worklow](../../fin-ops-core/fin-ops/organization-administration/tasks/view-workflow-history.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]