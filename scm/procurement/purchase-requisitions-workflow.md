---
title: workflow de demande d&quot;achat
description: "Le processus de workflow déplace les demandes d&quot;achat via le processus de révision, depuis le statut initial de Brouillon jusqu&quot;au statut final Approuvé. Lorsqu&quot;une demande d&quot;achat est envoyée pour révision, le processus de workflow démarre. Lorsqu&quot;une demande d&quot;achat est approuvée, une commande fournisseur peut être générée pour les lignes de la demande d&quot;achat et soumise au fournisseur pour honorer une commande."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchReqAuthorization, WorkflowParticipantExpenToken
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2234
ms.assetid: dad3ba5a-2892-45d2-874a-300896f59b34
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 7c5986dbce88a1cb704dddfc2afbcf2ac8c4b0dd
ms.lasthandoff: 03/31/2017


---

# <a name="purchase-requisition-workflow"></a>workflow de demande d'achat

[!include[banner](../includes/banner.md)]


Le processus de workflow déplace les demandes d'achat via le processus de révision, depuis le statut initial de Brouillon jusqu'au statut final Approuvé. Lorsqu'une demande d'achat est envoyée pour révision, le processus de workflow démarre. Lorsqu'une demande d'achat est approuvée, une commande fournisseur peut être générée pour les lignes de la demande d'achat et soumise au fournisseur pour honorer une commande.

Avant qu'une demande d'achat ne puisse être envoyée pour révision, vous devez configurer un workflow. Le processus de workflow peut inclure une ou plusieurs étapes de révision, dans n'importe quel ordre. Il peut également être configuré de manière à ignorer les tâches de révision et à approuver automatiquement la demande d'achat. Vous pouvez configurer le workflow pour acheminer la demande d'achat en tant que document unique, ou vous pouvez acheminer des lignes de demande d'achat individuelles aux réviseurs appropriés. Vous pouvez également créer un scénario dans lequel la demande d'achat est acheminée dans son intégralité vers certains réviseurs, et certaines lignes de demande d'achat sélectionnées vers d'autres réviseurs.  

Si les lignes de la demande d'achat sont révisées individuellement, le processus de révision doit être terminé pour toutes les lignes associées à la demande d'achat pour que le processus de workflow puisse avancer vers la prochaine étape et que le processus de révision de la demande d'achat prise dans son intégralité puisse être exécuté. Lorsque le processus de révision est terminé pour la demande d'achat et toutes ses lignes, le statut global de la demande d'achat est mis à jour sur **Approuvé**.  

Vous pouvez configurer votre workflow pour représenter le processus entreprise des demandes d'achat de votre organisation. Lorsque vous configurez votre processus de workflow de demande d'achat, prenez en compte les questions suivantes :

-   Quelles dépenses doivent être révisées ?
-   Quelles dépenses peuvent être automatiquement approuvées ?
-   Qui doit réviser et approuver les demandes de dépenses ? À quel rôle ces utilisateurs sont-ils affectés ?
-   Quel processus doit être suivi si un réviseur n'est pas disponible ?

Les exemples suivants illustrent deux façons de configurer un workflow pour les demandes d'achat.

## <a name="example-1-route-a-purchase-requisition-as-a-single-document-for-review"></a>Exemple 1 : acheminement d'une demande d'achat prise dans sa globalité pour révision
L'illustration suivante indique le flux d'une demande d'achat dans le processus de révision du workflow en tant que document simple. Les lignes de la demande d'achat ne sont pas acheminées individuellement. Les rôles suivants sont inclus dans le processus de workflow pour cet exemple :

-   **Demandeur** : utilisateur qui demande les articles ou les services. Il peut préparer la demande d'achat, ou un autre travailleur peut la préparer en son nom. Ce travailleur est appelé préparateur. Celui-ci est responsable de la gestion de la demande d'achat via le processus de révision. Seul le préparateur de la demande d'achat peut modifier celle-ci.

**Remarque :** un travailleur doit disposer des autorisations appropriées pour créer une demande d'achat au nom d'une autre personne. Utilisez la page **Autorisation de demande d'achat** pour paramétrer ces autorisations.

-   **Acheteur** : utilisateur qui effectue une révision d'approvisionnement et peut approuver le document.
-   **Responsable du demandeur** : utilisateur qui effectue une révision décisionnelle et peut approuver le document.

![Processus de révision du workflow des demandes d'achat](./media/purchreqworkflowoverview_submission.gif)  
Dans cet exemple, le processus de workflow de la demande d'achat inclut les étapes suivantes :

1.  Le préparateur envoie une demande d'achat pour révision.
2.  L'agent des achats reçoit une notification. La notification demande à l'acheteur de vérifier les informations de la demande d'achat. Si des informations requises manquent, il peut les ajouter ou renvoyer la demande d'achat au préparateur qui s'en chargera. Lorsque toutes les informations requises sont fournies, le traitement de la demande d'achat peut passer à l'étape suivante du processus de révision.
3.  Le responsable du demandeur révise la demande d'achat. La demande d'achat peut être acheminée vers le responsable du demandeur, par exemple, si le montant associé dépasse le plafond des dépenses du demandeur pour les demandes d'achat. Le responsable du demandeur peut approuver ou rejeter la demande d'achat ou la renvoyer au préparateur pour que celui-ci la modifie.

## <a name="example-2-route-the-individual-purchase-requisition-lines-for-review"></a>Exemple 2 : acheminement de lignes de demande d'achat individuelles pour révision
L'illustration suivante indique de quelle manière les lignes de demande d'achat individuelles peuvent être acheminées via un workflow. En général, le processus pour chaque ligne est identique à celui d'une demande d'achat qui est révisée en tant que document unique. Cependant, chaque ligne doit effectuer le processus de workflow individuellement pour que le workflow puisse être terminé pour la demande d'achat dans son intégralité.  

Dans cet exemple, un travailleur entre une demande d'affiches et de t-shirts pour une campagne marketing. Le coût des affiches est divisé entre le département Marketing et le département Ventes. S'il dépasse l'autorité de limite de signature pour les responsables de département, la demande d'achat doit également être révisée par le responsable du groupe.  

Les rôles suivants sont inclus dans le processus de workflow pour cet exemple :

-   **Demandeur** : utilisateur qui demande les articles ou les services. Il peut préparer la demande d'achat, ou un autre travailleur peut la préparer en son nom. Ce travailleur est appelé préparateur. Celui-ci est responsable de la gestion de la demande d'achat via le processus de révision. Seul le préparateur de la demande d'achat peut modifier celle-ci.

**Remarque :** un travailleur doit disposer des autorisations appropriées pour créer une demande d'achat au nom d'une autre personne. Utilisez la page **Autorisation de demande d'achat** pour paramétrer ces autorisations.

-   **Acheteur** : utilisateur qui effectue une révision d'approvisionnement et peut approuver le document.
-   **Responsable du demandeur** : utilisateur qui effectue une révision décisionnelle et peut approuver le document.
-   **Responsable de département** : utilisateur qui effectue une révision des dépenses et peut approuver le document.
-   **Responsable de groupe** : utilisateur qui effectue une révision d'autorité de signature et peut approuver le document.

![Processus de révision du workflow de la ligne de demande d'achat](./media/purchreqlineworkflowoverview.gif)  
Dans cet exemple, le processus de workflow pour les lignes de demande d'achat inclut les étapes suivantes :

1.  Le préparateur envoie une demande d'achat pour révision. Chaque ligne est acheminée vers le réviseur configuré pour la recevoir dans le processus de workflow.
2.  L'agent des achats reçoit une notification. La notification demande à l'acheteur de vérifier les informations de la demande d'achat et des lignes de demande d'achat. Lorsque la demande d’achat est ouverte par l’agent des achats, toutes les lignes sont visibles, mais un indicateur visuel indique quelles lignes ont été envoyées à l’agent des achats pour la révision. Si des informations requises manquent, il peut les ajouter ou renvoyer une ligne de demande d'achat au préparateur qui s'en chargera. Lorsque toutes les informations requises sont fournies, le traitement de la ligne de demande d'achat peut passer à l'étape suivante du processus de révision. Les lignes de demande d'achat peuvent être acheminées via le processus de révision, indépendamment les unes des autres.
3.  Le directeur de ligne du demandeur révise et approuve les lignes de demande d'achat. L'approbation peut être acheminée vers le responsable du demandeur, par exemple, si le montant d'une ligne de demande d'achat dépasse le plafond des dépenses du demandeur pour les lignes de demande d'achat. Le responsable peut approuver ou rejeter les deux lignes de demande d'achat ou une seule d'entre elles.
4.  Le responsable du département Marketing révise les lignes de demande d'achat pour les affiches et les t-shirts. Le responsable du département Ventes révise la ligne de demande d'achat uniquement pour les affiches, car il s'agit du seul coût facturé à ce département.
5.  Le responsable de groupe révise et approuve la ligne de demande d'achat pour les T-shirts uniquement si son approbation est nécessaire car, par exemple, le montant de la ligne de demande d'achat dépasse le plafond autorisé par le responsable de département. Le responsable du groupe ne doit pas approuver la ligne de demande d'achat pour les affiches.

## <a name="configuring-a-workflow-for-purchase-requisitions"></a>Configuration d'un workflow pour les demandes d'achat
Pour acheminer une demande d'achat pour révision, vous devez configurer les processus de workflow de demande d'achat. Ceux-ci contrôlent l'interaction entre l'utilisateur qui a demandé les articles (demandeur) et le réviseur et l'approbateur dans le workflow. L'acheminement de la demande d'achat dépend des conditions spécifiées dans la configuration du workflow. Par exemple, ces conditions déterminent le moment où la demande d'achat doit être transmise, l'utilisateur ou le rôle vers lequel elle doit être transmise et les actions proposées aux utilisateurs.  

Les exemples de cette rubrique décrivent l'acheminement d'une demande d'achat via un workflow en tant que document pris dans son intégralité ou en tant que lignes individuelles de la demande d'achat. Vous pouvez également configurer un workflow pour les demandes d'achat qui reflètent la révision des contrôles internes des demandes d'achat qui est définie pour votre organisation.  

Les participants ou les réviseurs auxquels une tâche est affectée dans un workflow peuvent être membres d'un groupe d'utilisateurs spécifique, des utilisateurs avec un rôle de sécurité spécifique, des utilisateurs associés à l'expéditeur dans une hiérarchie managériale, des utilisateurs nommés ou des utilisateurs ayant des responsabilités de dépense spécifiques.

### <a name="purchase-requisition-expenditure-reviewers"></a>Réviseurs de dépenses de demandes d'achat

Les configurations de réviseurs de dépenses vous permettent d'acheminer dynamiquement les dépenses à des fins de révision en fonction de l'utilisateur affecté à un rôle de projet ou à une dimension financière dans laquelle la dépense est facturée. Le processus de workflow utilise le rôle de projet ou le propriétaire de dimension financière spécifié pour déterminer vers quelle personne acheminer la dépense.  

Vous pouvez définir une ou plusieurs configurations de réviseurs de dépenses, puis sélectionner une configuration lorsque vous créez un workflow. Vous pouvez configurer les valeurs de réviseurs de dépenses pour toutes les entités juridiques de votre organisation. Après avoir défini les configurations de réviseurs de dépenses, vous affectez une configuration à votre tâche de workflow.  

Il n'est pas nécessaire de définir des configurations de réviseurs de dépenses. À la place, vous pouvez affecter des utilisateurs ou des groupes d'utilisateurs spécifiques en tant que réviseurs lorsque vous définissez votre workflow. Cependant, si votre organisation est complexe, les réviseurs de dépenses peuvent accroître l'efficacité de votre processus d'approbation. De même, si vous paramétrez des réviseurs de dépenses, il n'est pas nécessaire de mettre à jour les affectations de réviseurs de workflow chaque fois qu'un réviseur modifie les rôles de tâche.  

Vous pouvez paramétrer les réviseurs de dépenses dans la page **Réviseurs de dépenses de demandes d'achat**. Créez une configuration de réviseurs de dépenses, puis entrez des valeurs pour chaque entité juridique de votre organisation. Pour les demandes affectées à un projet, vous pouvez spécifier le rôle chargé de la révision des demandes : chef de projet, contrôleur de projet ou responsable des ventes du projet. Les dépenses sont acheminées vers l'utilisateur affecté au rôle spécifique. Vous pouvez également les acheminer vers le propriétaire de dimension financière en sélectionnant l'option appropriée sous l'onglet **Distributions de l'organisation**.  

Pour utiliser l'un des réviseurs de dépenses que vous paramétrez dans un workflow, vous devez définir l'option **Type de participant** sur** Participants aux dépenses** dans les propriétés** Affectation** de l'élément de workflow approprié.

<a name="see-also"></a>Voir également :
--------

[Créer un bon de commande pour la consommation (Guide de tâche)](https://ax.help.dynamics.com/en/wiki/create-a-requisition-for-consumption/)

[Defining business process workflows for purchase requisitions](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions) (livre blanc)

[Workflows d'approvisionnements](procurement-sourcing-workflows.md)

[Présentation générale de la demande d'achat](purchase-requisitions-overview.md)




