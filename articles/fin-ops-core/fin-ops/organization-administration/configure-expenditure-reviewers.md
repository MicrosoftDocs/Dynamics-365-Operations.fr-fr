---
title: Configurer les réviseurs de dépenses
description: Cette rubrique explique comment utiliser les réviseurs de dépenses pour sélectionner dynamiquement l'utilisateur auquel une tâche de flux de travail, une approbation ou une décision manuelle est affectée.
author: rachel-profitt
ms.date: 06/25/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2021-06-24
ms.openlocfilehash: ceb0a60ccf3d1c989d8663e933faaa5e430d314695e20990c9086cd1b8325ff1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773725"
---
# <a name="configure-expenditure-reviewers"></a>Configurer les réviseurs de dépenses
[!include[banner](../includes/banner.md)]

Vous pouvez paramétrer des réviseurs de dépenses dynamiques pour acheminer les dépenses à des fins de révision en fonction de l'utilisateur affecté à un rôle de projet ou de la dimension financière dans laquelle la dépense est facturée. Le processus de workflow utilise le rôle de projet ou le propriétaire de dimension financière spécifié pour déterminer vers quelle personne acheminer la dépense.

Vous pouvez définir une ou plusieurs configurations de réviseurs de dépenses, puis sélectionner une configuration lorsque vous créez un flux de travail. Vous pouvez configurer les valeurs de réviseurs de dépenses pour toutes les entités juridiques de votre organisation. Après avoir défini les configurations de réviseurs de dépenses, vous affectez une configuration. Les réviseurs de dépenses peuvent être affectés aux tâches de flux de travail, aux approbations et aux décisions manuelles.

> [!NOTE]
> Bien que les réviseurs de dépenses ne soient pas obligatoires, ils peuvent aider à simplifier la configuration de votre flux de travail. Par exemple, vous n'avez pas besoin de créer une décision conditionnelle pour vérifier chaque dimension de centre de coûts, puis de créer un autre élément pour affecter l'approbation ou la tâche à un utilisateur spécifique ou à des groupes d'utilisateurs. Au lieu de cela, vous pouvez configurer le propriétaire de la dimension de centre de coûts et utiliser un réviseur de dépenses pour sélectionner dynamiquement le bon utilisateur. Ainsi, lorsque la propriété ou l'affectation des centres de coûts change, il vous suffit de mettre à jour le champ **Propriétaire** pour la dimension financière.

## <a name="types-of-expenditure-reviewers"></a>Types de réviseurs de dépenses

Tous les flux de travail ne prennent pas en charge le concept de réviseurs de dépenses. Par défaut, vous pouvez configurer des réviseurs de dépenses pour les demandes d'achat, les bons de commande, les factures fournisseur et les états de dépenses. Chacun de ces types de flux de travail nécessite que vous configuriez les réviseurs de dépenses sur une page distincte spécifique à la fonctionnalité et au module. Pour chaque document pris en charge, les réviseurs de dépenses peuvent être utilisés avec des flux de travail au niveau de l'en-tête ou des flux de travail au niveau de la ligne.

Le tableau suivant indique où vous devez configurer un réviseur de dépenses pour chaque document pris en charge.

| Document | Chemin de navigation |
|----------|-----------------|
| États de dépenses | Gestion des dépenses \> Installer \> Stratégies \> Réviseurs de dépenses |
| Commandes fournisseur | Approvisionnements \> Installer \> Stratégies \> Réviseurs de dépenses des commandes fournisseur |
| Demandes d'achat | Approvisionnements \> Installer \> Stratégies \> Réviseurs de dépenses des demandes d'achat |
| Factures fournisseur | Allez dans Comptabilité fournisseur \> Paramétrage de la stratégie \> Réviseurs de dépenses des factures fournisseur |

## <a name="expenditure-reviewer-assignments"></a>Affectations du réviseur de dépenses

Deux types d'affectations sont disponibles pour chaque réviseur de dépenses : *répartitions du projet* et *répartitions de l'organisation*. Pour une distribution de projet, vous pouvez choisir entre les autorités de projet et les dimensions financières. Pour une distribution d'organisation, vous pouvez sélectionner des dimensions financières.

Les autorités de projet comprennent le chef de projet, le contrôleur de projet et le responsable des ventes du projet. Vous définissez ces autorités directement sur votre projet, en sélectionnant un travailleur dans les champs appropriés.

Les dimensions financières sont contrôlées par les structures de compte dans chaque entité juridique. Pour chaque entité juridique, vous pouvez sélectionner les dimensions financières qui seront utilisées avec le réviseur de dépenses. Les dimensions peuvent provenir soit du projet (dans ce cas, vous sélectionnez les dimensions sous l'onglet **Répartition du projet**) ou le document (dans ce cas, vous sélectionnez les dimensions sous l'onglet **Répartition des organisations**). Dans le champ **Propriétaire** sur la page **Valeurs des dimensions financières**, vous pouvez sélectionner le travailleur pour chaque dimension financière.

## <a name="example-1-expenditure-reviewers-based-on-organization-distributions"></a>Exemple 1 : réviseurs de dépenses basés sur les répartitions des organisations

Vous travaillez pour Contoso Appliances, et votre organisation compte six départements et 10 centres de coûts. Lorsqu'une nouvelle demande d'achat est soumise, l'approbation doit d'abord provenir du responsable du service puis du responsable du centre de coûts.

Pour cet exemple, vous configurez deux *réviseurs de dépenses de demandes d'achat* :

- Pour le premier réviseur, vous nommez le service, puis sélectionnez la dimension financière du **Service** sous l'onglet **Distributions de l'organisation**. 
- Pour le deuxième réviseur, vous nommez le centre de coût, puis sélectionnez la dimension financière du **Centre de coût** sous l'onglet **Distributions de l'organisation**.

Lorsque vous configurez le flux de travail, vous créez deux étapes d'approbation. La première concerne le département, et la seconde le centre de coût. Pour chaque élément d'approbation, vous sélectionnez **Participant** dans le champ **Type d'affectation** sous l'onglet **Basé sur les rôles**, vous sélectionnez **Participants aux dépenses** dans le champ **Type de participant**, puis vous sélectionnez le participant approprié dans le champ **Participant**.

Lors de la création de la demande d'achat, les dimensions financières du département et du centre de coût sont affectées aux lignes de la demande d'achat. Lorsque le flux de travail est soumis, le système évalue d'abord le service sur la demande d'achat et affecte l'élément d'approbation à l'utilisateur qui est lié au travailleur que vous avez sélectionné pour le service. Une fois la première étape d'approbation accomplie, le système évalue la seconde étape d'approbation et affecte le second élément d'approbation à l'utilisateur qui est lié au travailleur que vous avez sélectionné pour le centre de coût.

## <a name="example-2-expenditure-reviewers-based-on-project-distributions"></a>Exemple 2 : réviseurs de dépenses basés sur les répartitions de projets

Vous travaillez pour la division services de Contoso Appliances. L'organisation exige que le chef de projet pour chaque commande fournisseur approuve la dépense. De plus, le responsable du centre de coût du projet doit l'approuver. Les approbations peuvent être faites en même temps. Dans tous les cas, les deux utilisateurs doivent approuver la commande fournisseur avant que le flux de travail puisse continuer.

Pour cet exemple, vous créez un *réviseur de dépenses pour les bons de commande* nommé **Chef de projet et centre de coût**. Vous cochez la case **Chef de projet** et définissez l'option **Dimension du centre de coûts** sur **Oui** sous l'onglet **Répartitions du projet** de la page **Réviseur des dépenses des bons de commande**. Dans le cadre de la configuration, vous devez vous assurer que le **Chef de projet** est défini pour tous les projets et qu'un propriétaire est spécifié pour tous les centres de coût sur la page **Valeurs de la dimension financière**.

Lorsque vous configurez le flux de travail, vous avez besoin d'un élément d'approbation. Vous sélectionnez **Participant** dans le champ **Type d'affectation**. Puis, sous l'onglet **Basé sur les rôles**, vous sélectionnez **Participants aux dépenses** dans le champ **Type de participant** et sélectionnez le chef de projet et le centre de coûts dans le champ **Participant**. Pour vous assurer que le flux de travail ne peut pas continuer tant que le chef de projet et le propriétaire du centre de coût n'ont pas approuvé le flux de travail, vous définissez le champ **Stratégie d'achèvement** sur **Tous les approbateurs**.

Lorsque le bon de commande est créé, le champ **Projet** doit être spécifié. Si vous n'avez pas besoin d'un projet pour tous vos bons de commande, vous devez ajouter une décision conditionnelle à votre flux de travail pour rechercher un projet avant l'exécution de l'étape d'approbation. Le système évalue ensuite le projet spécifié pour la commande d'achat et affecte l'élément d'approbation à l'utilisateur qui est lié au travailleur dans le champ **Chef de projet**. De plus, le système crée une tâche et l'affecte à l'utilisateur qui est lié au travailleur que vous sélectionnez dans le champ **Propriétaire** pour le centre de coûts du projet. Notez que cet exemple utilise le centre de coût du projet, et non le centre de coûts de la commande d'achat.

## <a name="set-up-expenditure-reviewers"></a>Paramétrage de réviseurs de dépenses

Cet exemple montre comment configurer un réviseur de dépenses de demandes d'achat. Pour configurer d'autres types de réviseurs de dépenses, remplacez le chemin de navigation à l'étape 1 par le chemin approprié du tableau de la section [Types d'examinateurs des dépenses](configure-expenditure-reviewers.md#types-of-expenditure-reviewers) un peu plus haut dans ce sujet.

1. Accédez à **Approvisionnements \> Installer \> Stratégies \> Réviseurs de dépenses des demandes d'achat**.
2. Sur la page **Réviseurs des dépenses de demande d'achat**, sélectionnez **Nouveau**.
3. Dans le champ **Nom**, saisissez un nom pour la configuration du réviseur des dépenses, tel que **centre de coût**.
4. Sur le raccourci **Réviseurs des dépenses par entité juridique**, sélectionnez l'entité légale à configurer.
5. Pour une distribution de projet, cochez la case de chaque responsable de projet, puis sélectionnez **Oui** pour chaque dimension financière que vous souhaitez activer. 
6. Pour une distribution de l'organisation, sous l'onglet **Répartition des organisations**, sélectionnez **Oui** pour chaque dimension financière que vous souhaitez activer.
7. Répétez les étapes 4 à 6 pour chaque entité juridique supplémentaire.

## <a name="assign-owners-to-financial-dimensions"></a>Affecter des propriétaires aux dimensions financières

Pour affecter un propriétaire à une dimension financière, procédez comme suit.

1. Accédez à **Comptabilité \> Plan de comptes \> Dimensions \> Dimensions financières**.
2. Dans la liste, sélectionnez la dimension financière à laquelle affecter des propriétaires.
3. Sélectionner **Valeurs de dimension**.
4. Sélectionnez **Éditer** pour apporter des modifications aux valeurs de dimension.
5. Dans la liste, sélectionnez la valeur de dimension à laquelle affecter un propriétaire.
6. Dans le champ **Propriétaire**, sélectionnez le travailleur auquel affecter la valeur de dimension.

## <a name="configure-project-distributions"></a>Configurer les distributions de projet

Pour affecter des autorités de projet à un projet, procédez comme suit.

1. Accédez à **Gestion et comptabilité des projets \> Projets \> Tous les projets**.
2. Sélectionnez le projet auquel affecter des autorités.
3. Sélectionnez **Éditer** pour apporter des modifications au projet.
4. Sous le raccourci **Général**, dans la section **Responsable**, sélectionnez un travailleur pour les champs **Directeur commercial**, **Chef de projet** et **Contrôleur de projet** au besoin.
5. Sous le raccourci **Dimensions financières**, sélectionnez les dimensions financières requises pour votre projet.

## <a name="assign-expenditure-reviewers-to-a-workflow-task"></a>Affectation de réviseurs de dépenses à une tâche de flux de travail

Cet exemple montre comment configurer un flux de travail de demande d'achat afin qu'il utilise un réviseur de dépenses de demande d'achat. Pour configurer d'autres types de flux de travail, la page du flux de travail que vous devez ouvrir à l'étape 1 peut se trouver dans le module **Gestion des dépenses** ou **Comptabilité fournisseur** au lieu du module **Approvisionnements**.

Pour affecter des réviseurs de dépenses de demandes d'achat à une tâche de flux de travail, procédez comme suit.

1. Accédez à **Approvisionnements\> Configuration \> Workflows d’approvisionnements**.
2. Appuyez deux fois (ou double-cliquez) sur un flux de travail existant ou créez un nouveau flux de travail.
3. Dans l'éditeur de flux de travail, dans le volet **Flux de travail**, sélectionnez la tâche à laquelle affecter la configuration du réviseur des dépenses. Dans le **volet Actions**, dans le groupe **Montrer**, sélectionnez **Propriétés**.
4. Dans le volet gauche de la page **Propriétés**, sélectionnez **Affectation**.
5. Dans l’onglet **Type d’affectation**, sélectionnez **Participant**.
6. Sous l'onglet **Basé sur les rôles**, dans le champ **Type de participant**, sélectionnez **Participants aux dépenses**. Puis, dans le champ **Participant**, sélectionnez la configuration de réviseurs de dépenses à utiliser pour la tâche de workflow.
