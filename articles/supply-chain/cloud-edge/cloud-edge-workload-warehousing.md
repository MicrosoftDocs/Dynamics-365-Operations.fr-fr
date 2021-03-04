---
title: Charges de travail de gestion de l'entreposage pour les unités de mise à l'échelle du cloud et d'Edge
description: Cette rubrique fournit des informations sur la fonctionnalité qui permet aux unités de mise à l'échelle d'exécuter des processus sélectionnés à partir de votre charge de travail de gestion d'entrepôt.
author: perlynne
manager: tfeyr
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4ac76ad5cd88c35ac312b8e73d942a692f35c8aa
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516782"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Charges de travail de gestion de l'entreposage pour les unités de mise à l'échelle du cloud et d'Edge

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Toutes les fonctionnalités d'entreprise ne sont pas entièrement prises en charge dans la version préliminaire publique lorsque des unités d'échelle de charges de travail sont utilisées. Veillez à n'utiliser que les processus que cette rubrique décrit explicitement comme pris en charge.

## <a name="warehouse-execution-on-scale-units"></a>Exécution d'entrepôt sur des unités de mise à l'échelle

Cette fonctionnalité permet aux unités de mise à l'échelle d'exécuter des processus sélectionnés à partir des capacités de gestion de l'entrepôt. Les unités de mise à l'échelle du cloud exécutent leurs charges de travail dans le cloud en utilisant une capacité de traitement dédiée dans votre zone Microsoft Azure. Pour les unités d'échelle Edge, vous pouvez exécuter certaines charges de travail indépendamment sur site, même lorsque les unités d'échelle sont temporairement déconnectées du cloud.

Dans cette rubrique, les exécutions de gestion d'entrepôt dans un entrepôt défini comme une unité de mise à l'échelle sont appelées *Système d'exécution en entrepôt* (*WES*).

## <a name="prerequisites"></a>Conditions préalables

Vous devez avoir un hub Dynamics 365 Supply Chain Management et une unité d'échelle déployée avec la charge de travail de gestion d'entrepôt. Pour plus d'informations sur l'architecture et le processus de déploiement, voir [Unités à l'échelle du cloud et de Edge pour les charges de travail de fabrication et de gestion d'entrepôt](cloud-edge-landing-page.md).

## <a name="how-the-wes-workload-works-on-scale-units"></a>Fonctionnement de la charge de travail WES sur les unités d'échelle

Pour les processus de la charge de travail de gestion de l'entrepôt, les données sont synchronisées entre le hub et les unités de mise à l'échelle.

Une unité d'échelle ne peut conserver que les données dont elle est propriétaire. Le concept de propriété des données pour les unités d'échelle permet d'éviter les conflits multimaître. Par conséquent, il est important que vous compreniez quels processus sont détenus par le hub et lesquels appartiennent aux unités d'échelle.

Les unités d'échelle possèdent les données suivantes :

- **Données de traitement vague** – Les méthodes de traitement des vagues sélectionnées sont traitées dans le cadre du traitement des vagues par unité d'échelle.
- **Travail de traitement des données** – Les types de traitement des ordres de travail suivants sont pris en charge :

    - Mouvements d'inventaire (mouvement manuel et mouvement par modèle de travail)
    - Commandes fournisseur (travaux de rangement via un ordre d'entrepôt)
    - Commandes client (travaux de prélèvement et de chargement simples)

- **Données de réception de commande d'entrepôt** – Ces données ne sont utilisées que pour les commandes fournisseur qui sont lancées manuellement dans un entrepôt.
- **Données de contenant** – Des contenants peuvent être créés sur le hub et l'unité de mise à l'échelle. Une gestion des conflits dédiée a été fournie. Notez que ces données ne sont pas spécifiques à l'entrepôt.

## <a name="outbound-process-flow"></a>Flux des processus sortants

Le hub possède les données suivantes :

- Tous les documents sources, tels que les commandes client et les ordres de transfert
- Allocation des commandes et traitement des charges sortantes
- Les processus de lancement dans l'entrepôt, de création d'expédition et de création de vague

Les unités d'échelle sont propriétaires du traitement de la vague réelle (tel que la répartition du travail, le travail de réapprovisionnement et la création de la demande de travail) après le lancement de la vague. Par conséquent, les employés d'entrepôt peuvent traiter le travail sortant à l'aide d'une application d'entrepôt connectée à l'unité de mise à l'échelle.

![Flux de traitement de vague](./media/wes_wave_processing_flow.png "Flux de traitement de vague")

## <a name="inbound-process-flow"></a>Flux des processus entrants

Le hub possède les données suivantes :

- Tous les documents sources, tels que les commandes fournisseur et les ordres de retour client
- Traitement de charge entrante

> [!NOTE]
> Le flux de commande fournisseur entrant est conceptuellement différent du flux sortant, où l'unité de mise à l'échelle qui effectue le traitement dépend du fait que la commande a été lancée ou non dans un entrepôt.

Si vous utilisez le processus de *lancement dans l'entrepôt*, les commandes d'entrepôt sont créées et la propriété du flux de réception associé est attribuée à l'unité de mise à l'échelle. Le hub ne pourra pas enregistrer la réception entrante.

Le collaborateur peut exécuter le processus de réception à l'aide d'une application d'entrepôt connectée à l'unité de mise à l'échelle. Les données sont ensuite enregistrées par l'unité de mise à l'échelle et rapportées à la commande magasin entrante. La création et le traitement de la mise en stock ultérieure seront également gérés par l'unité de mise à l'échelle.

Si vous n'utilisez pas le processus de *lancement dans l'entrepôt*, et n'utilisent donc pas les *commandes d'entrepôt*, le hub peut traiter la réception en entrepôt et le traitement du travail indépendamment des unités de mise à l'échelle.

![Flux des processus entrants](./media/wes_Inbound_flow.png "Flux des processus entrants")

## <a name="supported-processes-and-roles"></a>Processus et rôles pris en charge

Tous les processus de gestion d'entrepôt ne sont pas pris en charge dans une charge de travail WES sur une unité d'échelle. Par conséquent, nous vous recommandons d'attribuer des rôles qui correspondent aux fonctionnalités disponibles pour chaque utilisateur.

Pour faciliter ce processus, un exemple de rôle nommé *Gestionnaire d'entrepôt sur la charge de travail* est inclus dans les données de démonstration sur **Administration du système \> Sécurité \> Configuration de la sécurité**. Le but de ce rôle est de permettre aux responsables d'entrepôt d'accéder au WES sur l'unité de mise à l'échelle. Le rôle accorde l'accès aux pages pertinentes dans le contexte d'une charge de travail hébergée sur une unité d'échelle.

Les rôles d'utilisateur sur une unité de mise à l'échelle sont attribués dans le cadre de la synchronisation initiale des données du hub vers l'unité de mise à l'échelle.

Pour modifier les rôles attribués à un utilisateur, accédez à **Administration du système \> Sécurité \> Attribuer des utilisateurs à des rôles** sur l'unité de mise à l'échelle. Les utilisateurs qui agissent en tant que gestionnaires d'entrepôt uniquement sur les unités de mise à l'échelle doivent se voir attribuer uniquement le rôle *Gestionnaire d'entrepôt sur la charge de travail*. Cette approche garantira que ces utilisateurs n'ont accès qu'aux fonctionnalités prises en charge. Supprimez tous les autres rôles attribués à ces utilisateurs.

Les utilisateurs qui agissent en tant que gestionnaires d'entrepôt sur le hub et les unités de mise à l'échelle doivent se voir attribuer uniquement le rôle de *Magasinier* existant. Sachez que ce rôle accorde aux Magasiniers l'accès aux fonctionnalités (telles que le traitement des ordres de transfert) qui apparaissent dans l'interface utilisateur (IU) mais qui ne sont actuellement pas prises en charge sur les unités d'échelle.

## <a name="supported-wes-processes"></a>Processus WES pris en charge

Les processus d'exécution d'entrepôt suivants peuvent être activés pour une charge de travail WES sur une unité de mise à l'échelle :

- Méthodes de vague sélectionnées pour les commandes client et le réapprovisionnement de la demande
- Exécution des ordres de travail à partir des commandes client et du réapprovisionnement de la demande à l'aide de l'application d'entrepôt
- Interrogation du stock disponible à l'aide de l'application d'entrepôt
- Création et exécution des mouvements de stock à l'aide de l'application d'entrepôt
- Enregistrement des commandes fournisseur et travaux de rangement en utilisant l'application d'entrepôt

Les types d'ordre de travail suivants sont actuellement pris en charge pour les charges de travail WES sur les déploiements d'unités de mise à l'échelle :

- Commandes client
- Réapprovisionnement
- Mouvement de stock
- Commandes fournisseur liées aux commandes entrepôt

Aucun autre traitement des documents source n'est actuellement pris en charge sur les unités d'échelle. Par exemple, pour une charge de travail WES sur une unité d'échelle, vous ne pouvez pas effectuer les actions suivantes :

- Lancer un ordre de transfert.
- Traiter les opérations de prélèvement et d'expédition de l'entrepôt sortant.

> [!IMPORTANT]
> Si vous utilisez une charge de travail sur une unité de mise à l'échelle, vous ne pouvez pas exécuter de processus non pris en charge pour l'entrepôt spécifique sur le hub.

La fonctionnalité de gestion d'entrepôt suivante n'est actuellement pas prise en charge sur les unités de mise à l'échelle :

- Traitement entrant et sortant pour les articles qui ont des dimensions de suivi actives (telles que des dimensions de lot ou de numéro de série)
- Traitement des changements de statut des stocks
- Traitement du stock inventaire qui a une valeur de statut de blocage
- Intégration avec la gestion de la qualité
- Intégration à la production
- Traitement des articles en poids variable
- Traitement des sur-livraisons et des sous-livraisons
- Traitement du stock disponible négatif

### <a name="outbound-supported-only-for-sales-orders-and-demand-replenishment"></a>Sortant (pris en charge uniquement pour les commandes client et le réapprovisionnement de la demande)

Le tableau suivant indique quelles fonctionnalités sortantes sont prises en charge et où elles sont prises en charge lorsque les charges de travail de gestion d'entrepôt sont utilisées dans des unités d'échelle de cloud et Edge.

> [!WARNING]
> Étant donné que seul le traitement des commandes client est pris en charge, le traitement de la gestion de l'entrepôt sortant ne peut pas être utilisé pour les ordres de transfert.
>
> Certaines fonctionnalités d'entrepôt ne seront pas disponibles dans les entrepôts qui exécutent les charges de travail de gestion d'entrepôt dans une unité de mise à l'échelle.

| Processus                                                      | Hub | Charge de travail WES sur une unité de mise à l'échelle |
|--------------------------------------------------------------|-----|------------------------------|
| Traitement du document source                                   | Oui | N° |
| Traitement de la gestion du transport et du chargement                | Oui | N° |
| Libérer dans l’entrepôt                                         | Oui | N° |
| Consolidation d'expédition                                       | N°  | N° |
| Cross-docking (travail de prélèvement)                                 | N°  | N° |
| Traitement de vague d'expédition                                     | Non, mais la finalisation du statut de la vague est gérée dans le hub |<p>Oui, mais les capacités suivantes ne sont pas prises en charge :</p><ul><li>Création de travail parallèle</li><li>Création et tri de chargement</li><li>Mise en conteneur</li><li>Impression d’étiquettes de la vague</li></li></ul><p><b>Remarque :</b> l'accès au hub est nécessaire pour finaliser le statut de la vague dans le cadre du traitement de la vague.</p> |
| Traitement du travail en entrepôt (y compris impression de contenant)     | N°  | <p>Oui, mais uniquement pour les fonctionnalités suivantes :</p><ul><li>Préparation des ventes (sans utilisation de dimensions de suivi actives)</li><li>Chargement des ventes (sans utilisation de dimensions de suivi actives)</li></ul> |
| Prélèvement de groupement                                              | N°  | N° |
| Traitement d'emballage                                           | N°  | N° |
| Traitement du tri sortant                                  | N°  | N° |
| Impression de documents relatifs à la charge                           | Oui | N° |
| Connaissement et génération d'APE                            | Oui | N° |
| Confirmation d'expédition et traitement des bons de livraison                | Oui | N° |
| Prélèvement partiel (commandes clients)                                 | N°  | N° |
| Annulation de travail                                            | N°  | N° |
| Changement de lieu de travail (commandes clients)                      | N°  | N° |
| Terminer le travail (commandes clients)                                 | N°  | N° |
| Bloquer et débloquer le travail                                       | N°  | N° |
| Changer d'utilisateur                                                  | N°  | N° |
| Imprimer l'état de travail                                            | N°  | N° |
| Étiquette de vague                                                   | N°  | N° |
| Contrepasser le travail                                                 | N°  | N° |

### <a name="inbound"></a>Entrant(e)

Le tableau suivant indique quelles fonctionnalités entrantes sont prises en charge et où elles sont prises en charge lorsque les charges de travail de gestion d'entrepôt sont utilisées dans des unités d'échelle de cloud et Edge.

| Processus                                                          | Hub | Charge de travail WES sur une unité de mise à l'échelle |
|------------------------------------------------------------------|-----|------------------------------|
| Traitement&nbsp;document&nbsp;source                                       | Oui | N° |
| Traitement de la gestion du transport et du chargement                    | Oui | N° |
| Confirmation d'envoi                                            | Oui | N° |
| Validation de la commande fournisseur vers l'entrepôt (traitement des commandes entrepôt) | Oui | N° |
| Réception et rangement de l'article de commande fournisseur                        | <p>Oui,&nbsp;quand&nbsp;il&nbsp;n'y a pas de commande d'entrepôt</p><p>Non, lorsqu'il y a une commande entrepôt</p> | <p>Oui, lorsqu'il y a une commande entrepôt et lorsqu'une commande fournisseur ne fait pas partie d'un <i>chargement</i>. Cependant, deux éléments de menu de l'appareil mobile doivent être utilisés, l'un pour la réception (<i>Réception d'un article de commande fournisseur</i>) et un autre, avec l'option <b>Utiliser le travail existant</b> activée, pour traiter le rangement.</p><p>Non, lorsqu'il n'y a pas de commande entrepôt.</p> |
| Réception et rangement de la ligne de commande fournisseur                        | <p>Oui, lorsqu'il n'y a pas de commande entrepôt</p><p>Non, lorsqu'il y a une commande entrepôt</p> | N° |
| Réception et rangement d'ordre de retour                               | Oui | N° |
| Réception et rangement de contenant mixte                        | <p>Oui, lorsqu'il n'y a pas de commande entrepôt</p><p>Non, lorsqu'il y a une commande entrepôt</p> | N° |
| Réception des articles du chargement                                              | <p>Oui, lorsqu'il n'y a pas de commande entrepôt</p><p>Non, lorsqu'il y a une commande entrepôt</p> | N° |
| Réception et rangement de contenant                              | <p>Oui, lorsqu'il n'y a pas de commande entrepôt</p><p>Non, lorsqu'il y a une commande entrepôt</p> | N° |
| Réception et rangement des articles de l'ordre de transfert                        | Oui | N° |
| Réception et rangement de la ligne d'ordre de transfert                        | Oui | N° |
| Annulation de travail                                                | <p>Oui, lorsqu'il n'y a pas de commande entrepôt</p><p>Non, lorsqu'il y a une commande entrepôt</p> | <p>Oui, mais l'option <b>Annuler l'enregistrement du reçu lors de l'annulation du travail</b> (sur la page <b>Paramètres de gestion de l'entrepôt</b>) n'est pas prise en charge.</p> |
| Traitement de l'accusé de réception de marchandises d'une commande fournisseur                        | Oui | N° |
| Création de travaux de cross-docking dans le cadre de la réception                 | <p>Oui, lorsqu'il n'y a pas de commande entrepôt</p><p>Non, lorsqu'il y a une commande entrepôt</p> | N° |

### <a name="warehouse-operations-and-exception-handing"></a>Opérations d'entrepôt et traitement des exceptions

Le tableau suivant indique quelles fonctionnalités d'opérations d'entrepôt et de traitement des exceptions sont prises en charge et où elles sont prises en charge lorsque les charges de travail de gestion d'entrepôt sont utilisées dans des unités d'échelle de cloud et Edge.

| Processus                                            | Hub | Charge de travail WES sur une unité de mise à l'échelle |
|----------------------------------------------------|-----|------------------------------|
| Recherche de contenant                              | Oui | Oui                          |
| Recherche d'article                                       | Oui | Oui                          |
| Recherche d'emplacement                                   | Oui | Oui                          |
| Modifier l'entrepôt                                   | Oui | Oui                          |
| Mouvement                                           | N°  | Oui                          |
| Mouvement par modèle                               | N°  | Oui                          |
| Ajustement (entrée/sortie)                                | Oui | N°                           |
| Comptage cyclique et traitement des écarts de comptage | Oui | N°                           |
| Réimpression d’étiquette (impression de contenant)             | Oui | N°                           |
| Création de contenant                                | Oui | N°                           |
| Décomposition du contenant                                | Oui | N°                           |
| Vérification à l'arrivée du chauffeur                                    | Oui | N°                           |
| Vérification au départ du chauffeur                                   | Oui | N°                           |
| Modifier le code de disposition de traitement par lots                      | Oui | N°                           |
| Afficher la liste des travaux en cours                             | Oui | N°                           |
| Consolider les contenants                         | N°  | N°                           |
| Supprimer un conteneur du groupe                        | N°  | N°                           |
| Annuler le travail                                        | N°  | N°                           |
| Traitement du réapprovisionnement min./max.                   | N°  | N°                           |
| Traitement du réapprovisionnement de créneaux                  | N°  | N°                           |

### <a name="production"></a>Production

L'intégration de la gestion des entrepôts pour les scénarios de production n'est actuellement pas prise en charge, comme indiqué dans le tableau suivant.

| Processus | Hub | Charge de travail WES sur une unité de mise à l'échelle |
|---------|-----|------------------------------|
| <p>Tous les processus de gestion d'entrepôt liés à la production. Voici quelques exemples :</p><li>Libérer dans l’entrepôt</li><li>Traitement de vagues de production</li><li>Prélèvement de matières premières</li><li>Rangement des produits finis</li><li>Rangement des coproduits et des sous-produits</li><li>Rangement de kanban</li><li>Prélèvement de kanban</li><li>Démarrer l'ordre de fabrication</li><li>Production au rebut</li><li>Dernière palette de production</li><li>Enregistrer la consommation de matières</li><li>Kanban vide</li></ul> | N° | N° |

## <a name="maintaining-scale-units-for-wes"></a>Gestion des unités d'échelle pour WES

Plusieurs tâches de traitement par lots s'exécutent à la fois sur les unités de hub et de mise à l'échelle.

Sur le déploiement du hub, vous pouvez gérer manuellement les tâches de traitement par lots. Vous pouvez gérer les trois tâches suivantes sur **Gestion d'entrepôt \> Tâches périodiques \> Gestion de la charge de travail back-office** :

- Traiter les événements de mise à jour du statut du travail
- Traiter les événements de transfert du contrôle d’exécution de la vague
- Enregistrer les réceptions de commande source

Sur la charge de travail dans les unités de mise à l'échelle, vous pouvez gérer les deux tâches de traitement par lots suivantes sur **Gestion d'entrepôt \> Tâches périodiques \> Gestion de la charge de travail** :

- Traiter les enregistrements de la table des vagues
- Traiter les événements de transfert du contrôle d’exécution de la vague


[!INCLUDE[footer-include](../../includes/footer-banner.md)]