---
title: Gérer les modifications apportées aux produits d’ingénierie
description: Cet article fournit des informations sur la gestion des modifications d’ingénierie. La gestion des modifications techniques fournit des processus structurés pour gérer les modifications apportées aux produits d’ingénierie, depuis la proposition, la demande et la réalisation de modifications, jusqu’à l’examen et l’approbation des modifications, l’évaluation de leur impact sur les transactions existantes et leur suivi.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcmRequestSelection,EngChgEcmRequestProducts,EngChgEcmRequestPriorityChart,EngChgEcmRequestListPage,EngChgEcmRequestFilteredPart,EngChgEcmRequestDetails,EngChgEcmReason,EngChgEcmProjTableInformation,EngChgEcmProductRoute,EngChgEcmProductRelease,EngChgEcmProductPreview, EngChgEcmWhereUsed, EngChgEcmInventTrans,EngChgEcmHeaderSelection,EngChgEcmHeaderPreviewPart,EngChgEcmHeaderFilteredPart,EngChgEcmHeaderDetails, EngChgCaseWhereUsedAnalysis, EngChgCaseValidatorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 6c578609a64c21a33f10b64a1d77f006b45bac41
ms.sourcegitcommit: 229ea085cf35579a2631ea1e5fc2c602fa47e3f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2022
ms.locfileid: "9714734"
---
# <a name="manage-changes-to-engineering-products"></a>Gérer les modifications apportées aux produits d’ingénierie

[!include [banner](../includes/banner.md)]

La gestion des changements d’ingénierie fournit des processus structurés pour gérer les changements des produits d’ingénierie. Vous pouvez utiliser le processus de *demande de modification technique* pour proposer et demander des modifications, puis utiliser le processus d’*ordre de modification technique* pour effectuer ces changements. Les utilisateurs peuvent créer des demandes de modification d’ingénierie ou des ordres de modification d’ingénierie, puis un processus est mis en place pour les examiner et les approuver, évaluer leur impact sur les transactions existantes et en assurer le suivi.

## <a name="engineering-change-requests"></a>Demandes de modification d’ingénierie

Le processus de demande de modification technique vous permet de capturer les demandes de modification de tous les services concernés de votre entreprise. Peu importe que vous travailliez en tant qu’ingénieur ou dans le service de fabrication, d’approvisionnement, d’entrepôt ou de vente : n’importe qui peut utiliser une demande de modification technique pour demander une modification. Ce changement peut être une idée pour un nouveau produit, un problème que vous avez découvert pendant que vous travailliez avec un produit existant, une suggestion pour améliorer un produit existant ou autre chose.

Une fois que quelqu’un a soumis une demande de modification, le processus d’*examen et d’approbation* est géré par un workflow qui identifie la personne qui doit approuver la modification (par exemple, le propriétaire du produit).

Pour configurer un workflow pour les ordres de modification technique ou les demandes de modification technique, accédez à **Gestion du changement d’ingénierie \> Workflows d’ingénierie**. Sélectionnez **Nouveau**, indiquez si le workflow sera utilisé pour examiner les ordres de modification technique ou les demandes de modification technique, puis configurez le workflow.

Pour plus d’informations sur l’utilisation des workflows, voir [Vue d’ensemble du système des workflows](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md). Pour plus d’informations sur les propriétaires de produits, voir [Propriétaires de produits](product-owner.md).

### <a name="create-a-new-engineering-change-request"></a>Créer une demande de modification d’ingénierie

Pour créer une demande de modification technique, suivez l’une de ces étapes.

- Aller à **Gestion du changement d’ingénierie \> Commun \> Gestion du changement d’ingénierie \> Demandes de changement d’ingénierie**, puis sélectionnez **Nouveau** sur le volet Actions.
- Ouvrez la page **Détails du produit** pour un produit d’ingénierie existant. Ensuite, sur le volet Action, sous l’onglet **Ingénieur**, dans le groupe **Gestion du changement d’ingénierie**, sélectionnez **Demande de changement d’ingénierie \> Nouvelle demande de changement d’ingénierie**.

Une nouvelle demande de modification est créée. Vous pouvez maintenant définir les champs sur chaque raccourci comme décrit dans les sous-sections suivantes.

#### <a name="general-fasttab"></a>Organisateur Général

Le raccourci **Général** vous permet de fournir une description de base de la demande de modification. Le tableau suivant décrit les champs disponibles sur ce raccourci.

| Champ | Description |
|---|---|
| Demande de modification | Permet d’entrer un nom pour la demande de modification d’ingénierie. |
| Titre | Saisissez un texte décrivant ou identifiant brièvement les modifications de la demande. |
| Priorité | Sélectionnez une valeur pour indiquer la priorité de la modification. Vous pouvez personnaliser les valeurs disponibles pour votre entreprise, selon vos besoins. (Pour plus d’informations, consultez [Établir des valeurs communes pour la gestion du changement d’ingénierie](engineering-change-management-setup.md) .) |
| Catégorie | Sélectionnez une valeur pour décrire le type de modification que vous demandez. Vous pouvez personnaliser les valeurs disponibles pour votre entreprise, selon vos besoins. (Pour plus d’informations, consultez [Établir des valeurs communes pour la gestion du changement d’ingénierie](engineering-change-management-setup.md) .) |
| Gravité | Sélectionnez une valeur pour indiquer la gravité du problème qui doit être résolu en implémentant la demande. Vous pouvez personnaliser les valeurs disponibles pour votre entreprise, selon vos besoins. (Pour plus d’informations, consultez [Établir des valeurs communes pour la gestion du changement d’ingénierie](engineering-change-management-setup.md) .) |
| Demandé par | Nom de l’utilisateur ayant créé la demande. |
| Sur | La date de création de la demande. |
| Statut | Statut de la demande. Lorsqu’une demande est créée pour la première fois, le statut est *Créé*. Lorsque la demande est approuvée, le statut passe à *Approuvé*. Si une demande de modification associée a été créée pour la demande, le statut passe à *Suivi*. |
| Ordre de modification | Le numéro d’ordre de modification, si la demande de modification a été suivie via un ordre de modification. |

#### <a name="information-fasttab"></a>Raccourci Informations

Le raccourci **Information** vous permet d’ajouter plus d’informations sur la demande.

Pour ajouter une ligne à la grille, sélectionnez **Nouveau** dans la barre d’outils au-dessus de la grille, puis sélectionnez l’une des options suivantes :

- **Fichier** – Charger un fichier.
- **Image** – Charger un fichier image.
- **Remarque** – Saisissez une note directement dans la grille.
- **URL** – Saisissez une URL directement dans la grille.

Le tableau suivant décrit les champs disponibles sur chaque ligne.

| Champ | Description |
|---|---|
| Date et heure de création | Date et heure de création de la ligne. |
| Type | Le type d’informations pour lesquelles la ligne a été créée (fichier, image, note ou URL). |
| Description | Entrez la description de la ligne. |
| Restriction | Valeur qui indique si les informations ajoutées proviennent d’une source interne ou externe. |
| Lié | Une case cochée indique que la ligne comprend une pièce jointe (fichier ou image). Pour télécharger la pièce jointe, sélectionnez la ligne, puis sélectionnez **Ouvrir** dans la barre d’outils au-dessus de la grille. |

#### <a name="products-fasttab"></a>Raccourci Produits

Le raccourci **Produits** vous permet de répertorier chaque produit concerné par la demande de modification. Vous pouvez utiliser les boutons sur la barre d’outils pour ajouter des produits à la grille ou supprimer des produits.

Cette liste est fourni uniquement à titre indicatif. Par conséquent, vous pouvez ajouter autant de produits connexes que vous le jugez pertinent. Si vous créez une demande de modification à partir de la page **Détails du produit** pour un produit existant, ce produit doit être répertorié sur le raccourci **Produits** après avoir enregistré l’enregistrement de la demande.

#### <a name="source-fasttab"></a>Raccourci Source

Le raccourci **Source** vous permet de suivre le point de départ de la demande de modification. C’est utile si, par exemple, vous souhaitez voir si la demande de modification a été créée à partir d’une commande client, qui l’a créée et dans quelle société elle a été créée.

### <a name="evaluate-the-business-impact-of-a-change-request-and-send-notifications"></a>Évaluer l’impact commercial d’une demande de modification et envoyer des notifications

Lorsque vous examinez une demande de modification, vous pouvez rechercher des dépendances. De cette manière, vous pouvez évaluer l’impact de la modification demandée sur les transactions en cours, telles que les commandes client, les ordres de fabrication et le stock disponible. Lorsque vous examinez les demandes de modification, vous pouvez envoyer des notifications aux personnes chargées d’exécuter les différents types de commandes associées.

#### <a name="review-affected-transactions-block-selected-transactions-and-send-notifications"></a>Examiner les transactions affectées, bloquer les transactions sélectionnées et envoyer des notifications

Pour examiner les transactions affectées, bloquer les transactions sélectionnées et envoyer des notifications associées, procédez comme suit.

1. Aller à **Gestion des modifications d’ingénierie \> Commun \> Paramètres des demandes de modifications \> Demandes de changements d’ingénierie**.
1. Ouvrez une demande de modification existante ou sélectionnez **Nouveau** dans le volet Actions pour créer une demande de modification.
1. Dans le volet Actions, sous l’onglet **Demande de modification**, dans le groupe **Impact commercial**, cliquez sur l’un des boutons suivants :

    - **Chercher** – Analyse toutes les transactions ouvertes, puis ouvrez la boîte de dialogue **Impact commercial sur les transactions ouvertes**, qui répertorie toutes les transactions qui seront affectées par la modification.
    - **Afficher la recherche précédente** – Ouvrez la boîte de dialogue **Impact commercial sur les transactions ouvertes**, qui répertorie les résultats de la recherche précédente. (Une nouvelle recherche n’est pas effectuée.)

1. La boîte de dialogue **Impact commercial sur les transactions ouvertes** fournit un ensemble d’onglets, chacun affichant une liste de transactions affectées d’un type spécifique (**Commandes client**, **Commandes fournisseur**, **Ordres de fabrication**, **Inventaire**, etc). Chaque onglet affiche également un nombre indiquant le nombre de transactions affectées de ce type. Sélectionnez un onglet pour afficher la liste appropriée.
1. Pour utiliser une transaction de la liste, sélectionnez-la, puis sélectionnez l’un des boutons suivants dans la barre d’outils :

    - **Afficher la transaction** : ouvrez l’enregistrement de transaction sélectionné.
    - **Bloquer la commande** : ce bouton n’est disponible que dans l’onglet **Commandes client**. Sélectionnez-le pour bloquer la commande client sélectionnée.
    - **Bloquer la ligne** : ce bouton n’est disponible que dans l’onglet **Commandes fournisseur**. Sélectionnez-le pour bloquer la ligne de commande fournisseur sélectionnée.
    - **Notifier le responsable** : ce bouton n’est disponible que dans l’onglet **Commandes client**. Sélectionnez-le pour envoyer une notification de modification à l’utilisateur défini comme le responsable de la commande client sélectionnée. Pour plus d’informations sur qui peut voir les notifications et comment, consultez [Examiner et traiter les notifications de changement pour les transactions](#review-notifications).
    - **Notifier l’auteur de la commande** : ce bouton n’est disponible que dans l’onglet **Commandes fournisseur**. Sélectionnez-le pour envoyer une notification de modification à l’utilisateur défini comme l’auteur de la commande fournisseur sélectionnée. Pour plus d’informations sur qui peut voir les notifications et comment, consultez [Examiner et traiter les notifications de changement pour les transactions](#review-notifications).
    - **Notifier la production** : ce bouton n’est disponible que dans l’onglet **Ordres de fabrication**. Contrairement aux commandes client et aux commandes fournisseur, aucun utilisateur n’est défini comme responsable des ordres de fabrication de bout en bout. À la place, différents superviseurs ou planificateurs s’approprient généralement un site spécifique ou une partie spécifique de la production (par exemple, pour des ressources ou des groupes de ressources spécifiques). Par conséquent, lorsque vous sélectionnez ce bouton, tous les utilisateurs responsables d’une ressource associée à l’ordre de fabrication sélectionné reçoivent une notification de modification. Pour plus d’informations sur qui peut voir les notifications et comment, consultez [Examiner et traiter les notifications de changement pour les transactions](#review-notifications).
    - **Notifier le préparateur** : ce bouton n’est disponible que dans l’onglet **Demande d’achat**. Sélectionnez-le pour envoyer une notification de modification à l’utilisateur défini comme le préparateur de la demande d’achat sélectionnée. Pour plus d’informations sur qui peut voir les notifications et comment, consultez [Examiner et traiter les notifications de changement pour les transactions](#review-notifications).
    - **Notifier le responsable des ventes** : ce bouton n’est disponible que dans l’onglet **Devis**. Sélectionnez-le pour envoyer une notification de modification à l’utilisateur défini comme le responsable du devis sélectionné. Pour plus d’informations sur qui peut voir les notifications et comment, consultez [Examiner et traiter les notifications de changement pour les transactions](#review-notifications).
    - **Mettre au rebut** : ce bouton n’est disponible que dans l’onglet **Inventaire**. Sélectionnez-le pour mettre au rebut l’inventaire sélectionné.
    - **Afficher l’historique** : ouvrez un historique des actions effectuées sur la transaction sélectionnée en utilisant la boîte de dialogue **Impact commercial sur les transactions ouvertes**. (Par exemple, l’historique indique si des notifications ont été envoyées ou si des transactions ont été bloquées.) 
    - **Afficher toutes les transactions** : ouvrez la liste complète de toutes les transactions, et pas seulement les transactions ouvertes.

> [!IMPORTANT]
> Le bouton **Notifier la production** n’est disponible que si la fonction *Notifications d’ingénierie pour la production* est activée pour votre système. Pour savoir comment activer ou désactiver cette fonctionnalité et ses prérequis, consultez [Présentation de la gestion des modifications techniques](product-engineering-overview.md).

#### <a name="review-and-process-change-notifications-for-transactions"></a><a name="review-notifications"></a>Examiner et traiter les notifications de modification pour les transactions

Vous pouvez lire et traiter les notifications de modification que vous recevez des manières suivantes :

- Sauf dans le cas des ordres de fabrication, les notifications de modification pour les transactions dont vous êtes responsable apparaissent dans le centre de notifications. Le bouton **Afficher les messages** (symbole de la cloche) sur le côté droit de la barre de navigation indique quand un message est disponible dans le centre de notifications. Sélectionnez le bouton **Afficher les messages** pour ouvrir le centre de notifications et consulter les messages.
- Pour afficher tous les ordres de fabrication pour lesquels une notification d’ingénierie a été envoyée, accédez à **Ordres de fabrication \> Ordres de fabrication \> Tous les ordres de fabrication**. Puis, dans le volet Actions, sous l’onglet **Ordre de fabrication**, dans le groupe **Demande de modification d’ingénierie**, sélectionnez **Notifications d’ingénierie** pour ouvrir la page **Notifications d’ingénierie**.
- Pour les ordres de fabrication, vous pouvez choisir de consulter uniquement les notifications de modification qui s’appliquent aux ressources de production que vous gérez. Dans l’espace de travail **Gestion de l’atelier de production**, dans le volet Actions, sélectionnez **Configurer mon espace de travail** pour filtrer la page afin qu’elle n’affiche que les informations sur les unités de production, les groupes et/ou les ressources que vous gérez. Dans la section **Résumé**, une vignette nommée **Ordres de fabrication avec produits modifiés** affiche un nombre de notifications correspondant à vos paramètres de filtre. Sélectionnez cette vignette pour ouvrir la page **Notifications d’ingénierie**, qui affiche la liste complète des transactions répondant aux critères de votre filtre.

Lorsque vous consultez les notifications d’ordre de fabrication dans la page **Notifications d’ingénierie**, vous pouvez suivre les liens vers les ordres de modification ou les ordres de fabrication associés en sélectionnant les valeurs de colonne ou en utilisant les commandes associées dans le volet Actions. Une fois que vous avez terminé d’évaluer une modification et une fois que vous avez annulé ou modifié les ordres de fabrication selon vos besoins, vous pouvez marquer une notification comme résolue. Sélectionnez la notification, puis, dans le volet Actions, sélectionnez **Résoudre**. La notification est supprimée des vues de tous les utilisateurs.

> [!IMPORTANT]
> La possibilité d’envoyer des notifications pour les ordres de fabrication nécessite que la fonction *Notifications d’ingénierie pour la production* soit activée pour votre système. Pour savoir comment activer ou désactiver cette fonctionnalité et ses prérequis, consultez [Présentation de la gestion des modifications techniques](product-engineering-overview.md).

### <a name="create-a-change-order-from-a-change-request"></a>Créer un ordre de modification à partir d’une demande de modification

Un ingénieur qui examine une demande de modification technique peut créer un ordre de modification technique directement à partir de la page **Demandes de changement d’ingénierie**. Dans le volet Actions, sous l’onglet **Demande de modification**, dans le groupe **Ordre de modification d’ingénierie**, sélectionnez **Approuver**.

Assurez-vous de sélectionner la bonne société pour le nouvel ordre de modification d’ingénierie. Si l’ordre de modification entraîne la modification du produit d’ingénierie lui-même (nouvelle version, nouveau produit ou nouvelle variante), l’ordre de modification doit être affecté à la société d’ingénierie. Si seule une modification locale est nécessaire (**Impact** est défini sur *Aucune*), l’ordre de modification peut être affecté à une entreprise locale et les modifications s’appliqueront au produit actuel.

## <a name="engineering-change-orders"></a>Ordres de modification d’ingénierie

Les ordres de changements d’ingénierie fournissent un processus structuré pour apporter des changements aux produits d’ingénierie. Vous proposez des modifications en utilisant une copie des données pertinentes pour l’ingénierie. Les vraies données de base ne sont pas affectées. Pour plus d’informations sur les données pertinentes pour l’ingénierie, voir [Versions d’ingénierie et catégories de produits d’ingénierie](engineering-versions-product-category.md).

Vous pouvez créer un ordre de modification technique basé sur une demande de modification technique approuvée. Les ingénieurs peuvent également créer des ordres de modification technique à partir de zéro. Vous pouvez inclure plusieurs produits dans un même ordre de modification technique en suivant l’une de ces étapes :

- Sélectionnez manuellement les produits.
- Utilisez la nomenclature pour inclure les produits inférieurs dans la structure produit (c’est-à-dire les enfants).
- Utilisez une recherche de cas d’emploi pour inclure les produits qui sont plus élevés dans la structure produit (c’est-à-dire les parents).

Une fois la proposition de modification terminée, le processus d’examen et d’approbation sera géré par un workflow. Vous pouvez configurer différents workflows, en fonction de la priorité et de la gravité.

Pour configurer un workflow pour les ordres de modification technique ou les demandes de modification technique, accédez à **Gestion du changement d’ingénierie \> Workflows d’ingénierie**. Sélectionnez **Nouveau**, indiquez si le workflow sera utilisé pour examiner les ordres de modification technique ou les demandes de modification technique, puis configurez le workflow.

Pour plus d’informations sur l’utilisation des workflows, voir [Vue d’ensemble du système des workflows](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

Voici quelques parties prenantes typiques qui pourraient avoir à approuver une demande de modification technique :

- **Propriétaires de produits** – Pour plus d’informations sur les propriétaires de produits, voir [Propriétaires de produits](product-owner.md).
- **Chef d’équipe responsable** – Notez également que le champ **Ingénieur** dans la vue **En-tête** de l’ordre de modification d’ingénierie indique l’ingénieur ayant créé l’ordre de modification d’ingénierie. Si l’ingénieur appartient à une équipe définie dans le système, le champ **Responsable** montre le chef de cette équipe.
- **Sercice Finances** – Le service financier pourrait avoir à examiner les cas où le changement implique des coûts élevés.

Vous pouvez choisir si l’ordre de modification technique doit être traité directement après son approbation, dans le cadre du workflow, ou si le traitement doit être effectué ultérieurement, en tant qu’étape manuelle. Lors du traitement d’un ordre de modification technique, les données techniques du produit réel sont mises à jour.

Pendant que vous examinez une demande de modification, dans le volet Actions, sur l’onglet **Changer de requête**, dans le groupe **Impact sur les entreprises**, sélectionnez **Rechercher** pour évaluer l’impact du changement proposé sur les transactions ouvertes, telles que les commandes client, les ordres de fabrication et les stocks disponibles. Les résultats sont affichés dans la boîte de dialogue **Impact commercial sur les transactions ouvertes**, dans laquelle vous pouvez sélectionner les transactions concernées, puis utiliser les commandes de la barre d’outils pour afficher plus d’informations, avertir l’utilisateur responsable ou bloquer la transaction.

### <a name="engineering-change-orders-in-engineering-or-operational-companies"></a>Ordres de modification d’ingénierie dans des sociétés d’ingénierie ou opérationnelles

Comme décrit dans [Sociétés d’ingénierie et règles de propriété des données](engineering-org-data-ownership-rules.md), les données produit que vous pouvez modifier varient en fonction du type d’entité juridique dans laquelle vous travaillez (une société d’ingénierie par rapport à une société opérationnelle). Les règles de propriété des données sont également appliquées aux demandes de modification technique. Par conséquent, en fonction de l’entité juridique dans laquelle vous créez un ordre de modification technique, différents types de modifications peuvent être effectués. Voici quelques exemples :

- Pour les demandes de modification technique dans une *société d’ingénierie*, vous pouvez apporter des modifications de base aux données d’ingénierie. Par exemple, vous pouvez créer des versions d’un produit, modifier la structure d’un produit via la nomenclature et modifier les valeurs d’attributs d’ingénierie. Pour chaque produit concerné, sélectionnez l’une des valeurs suivantes dans le champ **Impact** :

    - **Aucun** – Mettre à jour la version existante du produit (mise à jour en version).
    - **Nouvelle version** – Créez une version basée sur la version de produit sélectionnée.
    - **Nouveau produit** – Créez un produit complètement nouveau basé sur la version de produit sélectionnée.
    - **Nouvelle variante** – Créez une variante basée sur la version de produit sélectionnée. Sa nomenclature et ses informations de gamme seront copiées.

- Pour les demandes de modification technique dans une *société opérationnelle*, vous pouvez modifier les données logistiques du produit. Par exemple, vous pouvez enrichir la nomenclature existante avec des paramètres d’approvisionnement, ajouter des gammes locales ou des nomenclatures locales, et même enrichir une nomenclature en ajoutant de nouvelles lignes de nomenclature pour les matériaux d’emballage locaux, les fluides de lubrification ou les instructions dans la langue locale. Les enrichissements réalisés par les utilisateurs dans l’entreprise opérationnelle seront préservés lorsque de nouvelles mises à jour seront envoyées par la société d’ingénierie. Pour plus d’informations, consultez [Sociétés d’ingénierie et règles de propriété des données](engineering-org-data-ownership-rules.md).

    Lorsque les ordres de modification technique sont traités dans la société d’ingénierie, les produits sont créés et/ou mis à jour uniquement dans la société d’ingénierie. Par conséquent, si les données de base de produit doivent également être mises à jour, vous devez également transmettre les produits aux sociétés opérationnelles.

- Vous pouvez lancer des produits directement à partir d’ordres de modification technique. Ouvrez l’ordre de modification, puis dans le volet Actions, sur l’onglet **Ordre de modification**, dans le groupe **Versions du produit**, sélectionnez **Lancer la structure du produit**. Le processus fonctionne exactement comme il fonctionne lorsque vous lancez des produits à partir de la page **Produits lancés**. Pour plus d’informations, voir [Lancement de structures de produit](release-product-structure.md).
- Vous pouvez faire sortir automatiquement des produits des ordres de modification technique, en fonction des facteurs suivants :

    - Rééditions aux entreprises où les produits étaient précédemment commercialisés. Sélectionnez **Rechercher** pour analyser toutes les versions précédentes, puis sélectionnez **Vue** pour voir les résultats. La page **Afficher** affiche les versions précédentes du produit et vous pouvez sélectionner les produits que vous souhaitez rééditer. Puis fermez la page **Afficher** et sélectionnez **Processus** pour relancer les produits sélectionnés.
    - Paramètres de validation automatique dans le contrôle de validation de la catégorie de produit d’ingénierie. Vous pouvez faire cette version dans le cadre du workflow. Quand le bloc **recueillir la proposition de sortie** est utilisé, la proposition de lancement sera remplie de propositions de réédition (voir l’élément de liste précédent) et les produits seront mis à la disposition des entreprises si **Lancement automatique** est coché dans le contrôle de validation de la catégorie de produit d’ingénierie. Vous pouvez sélectionner **Afficher** pour afficher les résultats, comme décrit dans l’élément de liste précédent. Les produits seront également commercialisés lorsque le bloc **Proposition de lancement de processus** sera utilisé. Si vous choisissez de collecter uniquement la proposition de version dans le cadre du workflow, vous pouvez démarrer manuellement la version en sélectionnant **Processus**, comme décrit dans l’élément de liste précédent.

## <a name="follow-up-on-an-engineering-change-request-via-an-engineering-change-order"></a>Suivi d’une demande de modification technique via un ordre de modification technique

Dès qu’une demande de modification d’ingénierie est approuvée, vous pouvez la suivre sur un ordre de modification technique. Vous pouvez combiner plusieurs demandes de modification technique en un seul ordre de modification technique. Un seul ordre de modification technique peut même inclure plusieurs produits. (En règle générale, vous utilisez cette approche lorsque la même modification doit être appliquée à plusieurs produits.) Cependant, vous ne pouvez pas créer plusieurs ordres de modification technique à partir d’une seule demande de modification technique.

Pour suivre une demande de modification via un ordre de modification, ouvrez la demande de modification, puis, dans le volet Actions, sur l’onglet **Change l’ordre**, dans le groupe **Ordre de modification technique**, sélectionnez **Copier le lien et les produits**. Vous pouvez ensuite sélectionner un ordre de modification technique existant auquel connecter la demande de modification, ou vous pouvez créer un ordre de modification technique pour cette demande spécifique.

## <a name="engineering-change-order-report"></a>État de l’ordre de modification d’ingénierie

Les rapports d’ordre de modification technique décrivent les modifications apportées dans un ordre de modification technique. Ils sont utiles pendant et après le processus d’examen et d’approbation.

Pour afficher un rapport de demande de modification technique, ouvrez la demande de modification appropriée, puis, dans le volet Actions, sur l’onglet **Ordre de modification**, dans le groupe **Afficher**, sélectionnez **Rapport d’ordre de modification technique**.

## <a name="fields-on-an-engineering-change-order"></a>Champs d’un ordre de modification technique

La plupart des champs des ordres de modification technique sont les mêmes que les champs des produits lancés, des versions d’ingénierie, des documents, des nomenclatures (lignes) et des gammes (opérations). Cependant, les champs du tableau suivant sont uniques pour modifier les ordres.

| Champ | Description |
|---|---|
| Motifs de la modification d’ingénierie | Sélectionnez la raison du changement du produit concerné. |
| Description de la modification | Entrez une description des changements. |
| Outils spéciaux requis | Spécifiez si un outillage spécial est nécessaire pour appliquer la modification. |
| Disposition des matériaux d’ingénierie | Sélectionnez un code d’élimination des matières pour tout déchet produit lorsque la modification est appliquée. |
| Approbation du client obligatoire | Indiquez si l’approbation du client est requise avant que la modification puisse être appliquée. |
| Approbation du client reçue | Spécifiez le statut de l’approbation du client. |
| Environnement, santé et sécurité | Précisez si les règles de santé et de sécurité environnementales sont applicables au changement. Si tel est le cas, vous pouvez sélectionner les règles applicables. |

Vous pouvez utiliser le bouton **Tenir à jour/copier les informations de modification** pour copier les informations de modification entre les produits concernés.

## <a name="use-electronic-signatures-to-approve-and-active-boms-and-routes"></a>Utiliser des signatures électroniques pour approuver et activer les nomenclatures et les itinéraires

Pour utiliser des signatures électroniques pour approuver et/ou activer des modifications de nomenclatures et/ou de gammes, accédez à **Administration de l’organisation \> Installer \> Signature électronique \> Exigences relatives à la signature électronique**. Assurez-vous ensuite que chacun des éléments suivants **Signature requise** est défini sur *Oui* :

- Activer la nomenclature des produits de l’ordre de modification d’ingénierie
- Activer la gamme des produits de l’ordre de modification d’ingénierie
- Approuver la nomenclature des produits de l’ordre de modification d’ingénierie
- Approuver la gamme des produits de l’ordre de modification d’ingénierie
- Approuver la nomenclature des versions d’ingénierie et les versions de nomenclature
- Approuver la gamme des versions d’ingénierie et de gamme

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
