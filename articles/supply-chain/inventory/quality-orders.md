---
title: Ordres de qualité
description: Cette rubrique décrit comment créer manuellement ou automatiquement des ordres de qualité et comment les utiliser pour effectuer des inspections et enregistrer les résultats des tests dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 964f8a37ac9471b2eb6c9ec01fc0322a43cfea11
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022178"
---
# <a name="quality-orders"></a>Ordres de qualité

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment créer manuellement ou automatiquement des ordres de qualité et comment les utiliser pour effectuer des inspections et enregistrer les résultats des tests dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="automatically-created-quality-orders"></a>Ordres de qualité créés automatiquement

Vous pouvez configurer le système pour qu'il crée automatiquement des ordres de qualité, en fonction des règles d'échantillonnage des articles. Pour plus d'informations, consultez [Échantillonnage d’articles de gestion de la qualité](quality-item-sampling.md).

## <a name="manually-create-quality-orders"></a><a name="manual-quality-orders"></a>Créer des ordres de qualité manuellement

Pour créer un ordre de qualité manuellement, procédez comme suit :

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.
1. Sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Ordres de qualité**, dans le champ **Type de référence**, sélectionnez la référence de stock à laquelle votre commande de qualité sera liée. Pour obtenir une description des types de référence pouvant être sélectionnés, reportez-vous à la section [Types de référence d'ordre de qualité](#ref-types) plus loin dans cette rubrique.

    > [!NOTE]
    > Le stock lié à la référence sélectionnée doit être disponible. Si aucun stock n'est disponible pour la combinaison du type de référence, de la quantité et des dimensions de stock que vous sélectionnez, vous recevrez un message d'erreur.

1. Suivez l’une des procédures suivantes, selon la valeur que vous avez sélectionnée dans le champ **Type de référence** :

    - Si vous avez sélectionné **Stock**, aucune information de référence supplémentaire n’est nécessaire.
    - Si vous avez sélectionné **Vente** ou **Achat**, spécifiez les informations suivantes :

        - **Sélection de compte** – Référencez le numéro du client ou du fournisseur.
        - **Numéro de référence** - Référencez le numéro de la commande fournisseur ou client.
        - **Lot de référence** - Référencez la ligne de commande client ou la ligne de commande fournisseur spécifique.

    - Si vous avez sélectionné **Production**, **Contrôle**, ou alors **Production de coproduits**, dans le champ **Numéro de référence**, référencez le numéro d'ordre de fabrication, de lot de commandes et d'ordre de contrôle.
    - Si vous avez sélectionné **Opération de gamme**, spécifiez les informations suivantes :

        - **Numéro de référence** - Référencez le numéro du lot de commandes ou d'ordre de fabrication.
        - **N° opér.** - Référencez le numéro d'opération de gamme spécifique.
        - **Opération** – Référencez l'opération de gamme spécifique.
        - **Ressource** - Référencez la ressource spécifique qui doit être utilisée avec l'opération de gamme.

1. Dans le champ **Groupe de test**, sélectionnez le groupe de tests devant être exécutés.
1. Dans le champ **Quantité**, entrez la quantité d'articles devant être testés.
1. Dans la section **Dimensions de stock**, entrez les dimensions de stock supplémentaires requises pour l'article sélectionné.
1. Cliquez sur **OK**.

Une fois l'ordre de qualité créé, vous pouvez commencer à inspecter le stock et enregistrer les résultats des tests. Pour plus d'informations sur l'enregistrement et la validation des résultats de test, voir [Inspecter la qualité des marchandises](tasks/inspect-quality-goods.md).

## <a name="quality-order-reference-types"></a><a name="ref-types"></a>Types de référence d'ordre de qualité

Les ordres de qualité sont utilisés pour suivre les détails des inspections et des résultats de test pour un stock spécifique dans votre entrepôt. Un ordre de qualité doit inclure une référence qui représente la source du stock qui est testé. Les ordres de qualité peuvent être liés aux types de référence suivants :

- **Stock** - Ce type de référence indique que vous inspectez le stock disponible. Les inspections de ce type sont généralement aléatoires ou non planifiées et sont effectuées lorsqu'un magasinier identifie un problème.
- **Ventes** - Ce type de référence indique que vous inspectez le stock lié à une commande client spécifique. Les inspections de ce type sont généralement liées aux spécifications du client ou à la génération d'un certificat d'analyse (CoA) qui doit être fourni à un client dans le cadre d'un envoi. (Un CoA est parfois également appelé certificat de conformité \[CoC\].)
- **Achat** - Ce type de référence indique que vous inspectez le stock lié à une commande fournisseur spécifique. Les inspections de ce type sont souvent utilisées pour inspecter les marchandises entrantes avant qu'elles ne soient mises en stock ou consommées dans les processus de production.
- **Fabrication** - Ce type de référence indique que vous inspectez le stock lié à une ordre de fabrication spécifique. Les inspections de ce type sont souvent utilisées pour inspecter les produits finis avant qu'ils ne soient mises en stock.
- **Contrôle** - Ce type de référence indique que vous inspectez le stock lié à un ordre de contrôle spécifique. Les ordres de contrôle représentent un type d'ordre spécial qui suit les stocks dans un entrepôt séparé ou une zone séparée de votre entrepôt. Les inspections de ce type sont souvent utilisées pour inspecter les marchandises qu'un client a renvoyées ou qui ont été mises en quarantaine pour une analyse plus approfondie. Les ordres de contrôle peuvent être générés à partir des ordres de qualité. Ils peuvent aussi être générés à partir d'autres sources, puis les ordres de qualité peuvent être liés aux ordres de contrôle.
- **Opération de gamme** - Ce type de référence indique que vous inspectez le stock lié à une étape spécifique de la gamme pour un ordre de fabrication. Les inspections de ce type sont généralement utilisées pour analyser le travail en cours (WIP) d'un produit avant qu'il ne passe à l'étape suivante du processus de fabrication.
- **Production de coproduits** - Ce type de référence indique que vous inspectez le stock lié à un coproduit d'un ordre de fabrication. Les inspections de ce type sont généralement utilisées pour inspecter le coproduit d'une commande par lots avant que le coproduit ne soit ajouté au stock.

## <a name="view-and-create-quality-orders-from-various-parts-of-the-system"></a>Afficher et créer des ordres de qualité à partir de différentes parties du système

Les ordres de qualité peuvent être créés manuellement. Ils peuvent également être créés automatiquement en fonction des associations de qualité que vous définissez. Pour plus d'informations sur la création et la gestion de la création automatique d'ordres de qualité, voir [Associations de qualité](quality-associations.md).

Vous pouvez utiliser la page d'ordre de qualité pour créer manuellement un nouvel ordre de qualité ou afficher l'état d'un ordre de qualité lié à un autre enregistrement. Il existe plusieurs façons d'accéder à la page de commande de qualité.

### <a name="from-the-quality-orders-page"></a>Depuis la page Ordres de qualité

Pour créer manuellement des ordres de qualité et afficher ceux existants, accédez à **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**. Les sections restantes de cette rubrique fournissent plus d'informations sur la façon de travailler avec la page **Ordres de qualité**.

### <a name="from-sales-orders"></a>À partir des commandes client

Pour travailler avec des ordres de qualité liés à vos commandes client, accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**, puis suivez l'une de ces étapes :

- Ouvrez une commande client ou sélectionnez-la dans la grille. Ensuite, dans le volet Actions, sur l'onglet **Prélever et emballer**, dans le groupe **Gestion de la qualité**, sélectionnez **Ordres de qualité** pour ouvrir la page **Ordres de qualité**. Là, vous pouvez afficher, créer ou mettre à jour les ordres de qualité liés à la commande client.
- Ouvrez une commande client, puis, sur l'onglet **En-tête**, sélectionnez le raccourci **Général**. Le champ **Statut de l'ordre de qualité** affiche le statut global de tous les ordres de qualité liés à la commande client.
- Ouvrez une commande client, puis, sur l'onglet **Lignes**, sélectionnez le raccourci **Lignes de commande client**. La colonne **Statut de l'ordre de qualité** affiche le statut de chaque ligne de la commande client.

### <a name="from-purchase-orders"></a>À partir des commandes fournisseur

Pour travailler avec des ordres de qualité liés à vos commandes fournisseur, accédez à **Approvisionnement et sources \> Commandes fournisseur \> Toutes les Commandes fournisseur**, puis suivez l'une de ces étapes :

- Ouvrez une commande fournisseur ou sélectionnez-la dans la grille. Ensuite, dans le volet Actions, sur l'onglet **Recevoir**, dans le groupe **Gestion de la qualité**, sélectionnez **Ordres de qualité** pour ouvrir la page **Ordres de qualité**. Là, vous pouvez afficher, créer ou mettre à jour les ordres de qualité liés à la commande fournisseur.
- Ouvrez une commande fournisseur, puis, sur l'onglet **En-tête**, sélectionnez le raccourci **Général**. Le champ **Statut de l'ordre de qualité** affiche le statut global de tous les ordres de qualité liés à la commande fournisseur.
- Ouvrez une commande fournisseur, puis, sur l'onglet **Lignes**, sélectionnez le raccourci **Lignes de commande fournisseur**. La colonne **Statut de l'ordre de qualité** affiche le statut de chaque ligne de la commande fournisseur.

### <a name="from-production-orders"></a>À partir des ordres de fabrication

Pour travailler avec des ordres de qualité liés à vos ordres de fabrication, accédez à **Contrôle de la production \> Ordres de fabrication \> Tous les ordres de fabrication**, puis suivez l'une de ces étapes :

- Ouvrez un ordre de fabrication ou sélectionnez-le dans la grille. Ensuite, dans le volet Actions, sur l'onglet **Afficher**, dans le groupe **Gérer la qualité**, sélectionnez **Ordres de qualité** pour ouvrir la page **Ordres de qualité**. Là, vous pouvez afficher, créer ou mettre à jour les ordres de qualité liés à l'ordre de fabrication.
- Ouvrez un ordre de fabrication ou sélectionnez-le dans la grille. Puis, dans le volet Actions, sous l’onglet **Ordre de fabrication**, dans le groupe **Détails de la production**, sélectionnez **Gamme** pour ouvrir la page **Gamme de production**. Pour afficher les ordres de qualité liés à une opération de gamme, procédez comme suit :

    - Sélectionnez l'opération de gamme cible dans la grille. Ensuite, dans le volet Actions, sélectionnez **Recherches \> Ordres de qualité**.
    - Sélectionnez la valeur dans le champ **Au n° opér.** pour que l'opération de gamme cible ouvre la page de détails **Gamme de production**. Sur le raccourci **Général**, le champ **Statut de l'ordre de qualité** affiche le statut des ordres de qualité liés à l'opération de gamme.

- Ouvrez un ordre de fabrication et sélectionnez le raccourci **Général**. Le champ **Statut de l'ordre de qualité** affiche le statut des ordres de qualité liés à l'ordre de fabrication.

### <a name="from-quarantine-orders"></a>À partir des ordres de contrôle

Pour travailler avec des ordres de qualité liés à vos ordres de contrôle, accédez à **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de contrôle**, puis suivez l'une de ces étapes :

- Passez en revue les valeurs de la colonne **Statut de l'ordre de qualité**. De cette façon, vous pouvez connaître l'état général de tous les ordres de qualité liés à chaque ordre de contrôle dans la grille.
- Sélectionnez un ordre de contrôle dans la grille, puis, dans le volet Actions, sélectionnez **Ordres de qualité** pour afficher, créer ou mettre à jour les ordres de qualité liés à l'ordre de contrôle.

## <a name="advanced-actions-for-quality-orders"></a>Actions avancées pour les ordres de qualité

Vous pouvez effectuer plusieurs actions sur les ordres de qualité pour gérer le statut, générer des documents et demander des détails supplémentaires.

### <a name="reopen-a-quality-order"></a>Rouvrir un ordre de qualité

Par défaut, vous ne pouvez plus modifier ou mettre à jour un ordre de qualité une fois qu'il a été validé et que les tests ont été réussis. Cependant, dans certains cas, vous devrez peut-être rouvrir un ordre de qualité une fois celui-ci terminé.

Pour rouvrir un ordre de qualité, procédez comme suit :

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.
1. Ouvrez un ordre de qualité validé ou sélectionnez-le dans la grille.
1. Dans le volet Actions, sélectionnez **Rouvrir l'ordre de qualité**.

### <a name="create-a-certificate-of-analysis-for-a-quality-order"></a>Créer un certificat d'analyse pour un ordre de qualité

Un CoA est un rapport généré par l'équipe d'assurance qualité d'une organisation. Il valide la conformité d'un produit à des réglementations ou des exigences spécifiques. Vos clients ou les organismes de réglementation de votre pays peuvent nécessiter des certificats d'authenticité. Ils peuvent également être nécessaires en fonction de votre secteur d'activité et du type de produits que vous manipulez, achetez, produisez ou vendez.

Supply Chain Management vous permet de générer un CoA à partir d'un ordre de qualité. L'état va inclure les résultats de tous les tests sur l'ordre de qualité où l'option **État du certificat d'analyse** est définie sur *Oui*. Cette option peut être définie par défaut, en fonction du test que vous définissez sur la page **Tests**. Cependant, vous pouvez remplacer le paramètre sur des tests spécifiques pour un ordre de qualité spécifique.

Pour générer un CoA pour un ordre de qualité, procédez comme suit :

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.
1. Sélectionnez l'ordre de qualité pour lequel vous souhaitez créer un CoA.
1. Dans le volet Actions, sélectionnez **Recherches \> Certificat d'analyse**.
1. Dans la page **Certificat d'analyse**, dans le volet Actions, sélectionnez **Nouveau**.
1. Facultatif : dans le champ **Contact**, sélectionnez la personne à contacter à qui le certificat doit être adressé.
1. Dans le volet Actions, sélectionnez **Imprimer**.
1. Dans la boîte de dialogue **Certificat d'analyse**, définissez comment le rapport doit être imprimé. Puis cliquez sur **OK** pour imprimer le rapport sur une imprimante, à l'écran, dans un fichier ou par courrier électronique.
1. Fermez les pages.

### <a name="block-or-unblock-inventory-for-a-quality-order"></a>Bloquer ou débloquer le stock pour un ordre de qualité

Lorsqu'un ordre de qualité est automatiquement généré à partir d'une association de qualité, l'échantillonnage d'article affecté à l'association de qualité peut être configuré pour bloquer la quantité totale de stock de la référence en cours de test. Pour plus d'informations sur les échantillonnages des éléments, consultez [Échantillonnage d’articles de gestion de la qualité](quality-item-sampling.md).

Si vous n'utilisez pas le blocage complet ou si vous créez manuellement un ordre de qualité, le système crée automatiquement un enregistrement de blocage de stock pour la quantité de l'article qui est testé sur l'ordre de qualité. Dans l'enregistrement créé sur la page **Blocage du stock**, le champ **Type de blocage du stock** est défini sur *Ordre de qualité*.

Pour afficher et modifier le blocage du stock pour un ordre de qualité sélectionné sur la page **Blocage du stock**, sélectionnez **Recherches \> Blocage du stock** dans le volet Actions. Pour plus d’informations, voir [Blocage du stock](inventory-blocking.md).

### <a name="inquire-about-the-details-of-a-quality-order"></a>Se renseigner sur les détails d'un ordre de qualité

Utilisez les boutons suivants dans le volet Actions de la page **Ordres de qualité** pour afficher plus d'informations sur un ordre de qualité :

- **Recherches \> Détails du travail** – Ouvrez une page où vous pouvez voir le travail d'entrepôt lié à l'ordre de qualité.
- **Recherches \> Non-conformités** – Ouvrez une page où vous pouvez visualiser les non-conformités liées à l'ordre de qualité.
- **Stock** – Les commandes de ce menu sont communes à toutes les transactions de stock. Vous pouvez les utiliser pour afficher ou mettre à jour des détails tels que les transactions, le stock disponible, les réservations et le marquage.

### <a name="create-cases-related-to-quality-orders"></a>Créer des dossiers liés à des ordres de qualité

Vous pouvez créer des dossiers liés à des ordres de qualité. De cette façon, vous pouvez suivre les détails des problèmes et travailler à une résolution. Vous pouvez ensuite utiliser les fonctionnalités de flux de travail de la gestion des dossiers pour acheminer un dossier via un processus métier prédéfini afin d'obtenir des approbations supplémentaires ou obtenir plus d'informations sur un problème spécifique. Vous pouvez également utiliser la fonctionnalité des articles de base de connaissances pour créer une base de connaissances de solutions aux problèmes courants.

## <a name="case-management-examples-for-quality-management"></a>Exemples de gestion des dossiers pour la gestion de la qualité

### <a name="example-1"></a>Exemple 1

Vous travaillez pour une entreprise de fabrication qui doit respecter des réglementations strictes liées à la production de produits réglementés tels que les aliments. Les ordres de qualité sont utilisés pour enregistrer et suivre les détails sur la qualité des articles tout au long du processus de production. Si un ordre de qualité échoue à des tests spécifiques, il peut y avoir un problème avec l'équipement. Les dossiers sont utilisés pour suivre un processus métier et transmettre le problème aux ingénieurs appropriés afin que la cause première puisse être déterminée. Pour faciliter le suivi des processus métier, l'entreprise conserve une base de connaissances sur les problèmes courants liés aux commandes de qualité et aux problèmes d'équipement.

### <a name="example-2"></a>Exemple 2

Vous travaillez pour une société de distribution qui expédie des produits qui peuvent être personnalisés en fonction du pays auquel ils sont destinés. Certains clients ont des spécifications strictes qui doivent être respectées. Ils sont sinon soumis à des frais et des retours ou des rétrofacturations. Vous utilisez les ordres de qualité pour suivre les détails de chaque test et les résultats qui correspondent aux exigences du client. Les dossiers sont utilisés pour examiner et approuver les détails de la CoA avant que le document ne soit généré et joint avec d'autres documents d'expédition.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Processus de gestion de la qualité](quality-management-processes.md)
- [Test de qualité](quality-tests.md)
- [Groupes de tests de qualité](quality-test-groups.md)
- [Associations de qualité](quality-associations.md)
- [Processus de gestion de la qualité](quality-management-processes.md)
- [Activer la gestion de la qualité et de la non-conformité](enable-quality-management.md)
- [Gestion de la qualité pour les processus d'entrepôt](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
