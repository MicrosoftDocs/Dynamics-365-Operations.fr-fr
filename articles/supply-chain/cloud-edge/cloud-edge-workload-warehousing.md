---
title: Charges de travail de gestion de l’entreposage pour les unités de mise à l’échelle du cloud et d’Edge
description: Cette rubrique fournit des informations sur la fonctionnalité qui permet aux unités de mise à l’échelle d’exécuter des processus sélectionnés à partir de votre charge de travail de gestion d’entrepôt.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers, SysWorkloadDuplicateRecord
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 725b6dea98805baaf3f4d60b3922543067a205bc7196a05f33af21a6cd680a37
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740693"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Charges de gestion d’entrepôt pour les unités d’échelle Cloud et périphérie

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Toutes les fonctionnalités commerciales de gestion d’entrepôt ne sont pas entièrement prises en charge pour les entrepôts exécutant une charge de travail sur une unité d’échelle. Veillez à n’utiliser que les processus que cette rubrique décrit explicitement comme pris en charge.

## <a name="warehouse-execution-on-scale-units"></a>Exécution d’entrepôt sur des unités de mise à l’échelle

Cette fonctionnalité permet aux unités de mise à l’échelle d’exécuter des processus sélectionnés à partir des capacités de gestion de l’entrepôt.

Dans cette rubrique, les exécutions de gestion d’entrepôt dans un entrepôt défini comme une unité de mise à l’échelle sont appelées *Système d’exécution en entrepôt* (*WES*).

## <a name="prerequisites"></a>Conditions préalables

Vous devez avoir un hub Dynamics 365 Supply Chain Management et une unité d’échelle déployée avec la charge de travail de gestion d’entrepôt. Pour plus d’informations sur l’architecture et le processus de déploiement, consultez [Utiliser des unités d’échelle pour augmenter la résilience des charges de travail de gestion de la chaîne d’approvisionnement](cloud-edge-landing-page.md).

## <a name="how-the-wes-workload-works-on-scale-units"></a>Fonctionnement de la charge de travail WES sur les unités d’échelle

Pour les processus de la charge de travail de gestion de l’entrepôt, les données sont synchronisées entre le hub et les unités de mise à l’échelle.

Une unité d’échelle ne peut conserver que les données dont elle est propriétaire. Le concept de propriété des données pour les unités d’échelle permet d’éviter les conflits multimaître. Par conséquent, il est important que vous compreniez quels processus sont détenus par le hub et lesquels appartiennent aux unités d’échelle.

Les unités d’échelle possèdent les données suivantes :

- **Données de traitement de vague d’expédition** – Les méthodes de traitement des vagues sélectionnées sont traitées dans le cadre du traitement des vagues par unité d’échelle.
- **Données de traitement de travail** - Le travail d’entrepôt créé sur une unité d’échelle appartiendra à cette unité d’échelle spécifique. Les types de traitement d’ordres de travail suivants sont pris en charge :

  - **Mouvements d’inventaire** (mouvement manuel et mouvement par modèle de travail)
  - **Inventaire tournant** et processus d’approbation / rejet dans le cadre des opérations de comptage
  - **Commandes fournisseur** (tâches de rangement via une commande entrepôt lorsque les commandes fournisseur ne sont pas associées à des charges)
  - **Commandes client** (tâches de prélèvement et de chargement simples)
  - **Ordres de transfert** (uniquement sortants avec tâches de prélèvement et de chargement simples)

- **Données de réception de commande d’entrepôt** – Ces données ne sont utilisées que pour les commandes fournisseur qui ont été lancées manuellement dans un entrepôt.
- **Données de contenant** – Des contenants peuvent être créés à la fois sur le hub et sur les unités de mise à l’échelle. Une gestion des conflits dédiée est fournie. 

    > [!IMPORTANT]
    > Les données de contenants ne sont pas spécifiques à l’entrepôt. Si le même numéro de contenant est créé à la fois sur le concentrateur et sur une balance au cours du même cycle de synchronisation, la synchronisation suivante échouera. Si cela se produit, accédez à **Administration système > Demandes de renseignements > Demandes de charge de travail > Enregistrements en double**, où vous pouvez afficher et fusionner les données.

## <a name="outbound-process-flow"></a>Flux des processus sortants

Le hub possède les données suivantes :

- Tous les documents sources, tels que les commandes client et les ordres de transfert
- Allocation des commandes et traitement des charges sortantes
- Les processus de lancement dans l’entrepôt, de création d’expédition, création de vagues et processus de finalisation de vagues

Les unités d’échelle sont propriétaires du traitement de la vague réelle (tel que la répartition du travail, le travail de réapprovisionnement et la création de la demande de travail) après le lancement de la vague. Par conséquent, les employés d’entrepôt peuvent traiter le travail sortant à l’aide d’une application mobile Gestion des entrepôts connectée à l’unité de mise à l’échelle.

![Flux de traitement de vague.](./media/wes-wave-processing-ga.png "Flux de traitement de vague")

### <a name="process-work-and-ship"></a>Traiter le travail et expédier

Dès que le processus de travail final place le stock au lieu d’expédition final (Baydoor), l’unité d’échelle signale au hub de mettre à jour les transactions de stock sur le document source à *Prélevé*. Jusqu’à ce que ce processus s’exécute et soit de nouveau synchronisé, le stock disponible sur la charge de travail de l’unité d’échelle sera physiquement réservé au niveau de l’entrepôt.

Dès que le hub a mis à jour les transactions à *Prélevé*, il peut traiter la confirmation d’expédition sortante et le bon de livraison associé ou transférer l’ordre de transfert pour le chargement.

![Flux des traitements sortants.](./media/WES-outbound-processing-19.png "Flux des traitements sortants")

## <a name="inbound-process-flow"></a>Flux des processus entrants

Le hub possède les données suivantes :

- Tous les documents sources, tels que les commandes fournisseur et les ordres de retour client
- Traitement de charge entrante
- Tous les mises à jour de coût et financières

> [!NOTE]
> Le flux de commandes fournisseur entrant est différent en termes de concept du flux sortant. Vous pouvez gérer le même entrepôt sur l’unité d’échelle ou sur le hub selon que la commande fournisseur a été lancée ou non dans l’entrepôt. Une fois que vous avez validé une commande à l’entrepôt, vous ne pouvez travailler avec cette commande que lorsque vous êtes connecté à l’unité d’échelle.
>
> Si vous utilisez le processus *Lancement dans l’entrepôt*, les [*commandes d’entrepôt*](cloud-edge-warehouse-order.md) sont créées et la propriété du flux de réception associé est attribuée à l’unité de mise à l’échelle. Le hub ne pourra pas enregistrer la réception entrante.

Vous devez vous connecter au hub pour utiliser le processus *Libération dans l’entrepôt*. Accédez à l’une des pages suivantes pour l’exécuter ou le planifier :

- **Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur > Entrepôt > Actions > Libération dans l’entrepôt**
- **Gestion des entrepôts > Lancement dans l’entrepôt > Lancement automatique des commandes fournisseur**

Lors de l’utilisation de **Libération automatique des commandes fournisseur**, vous pouvez sélectionner des lignes de commande fournisseur spécifiques en fonction d’une requête. Un scénario typique serait de configurer un traitement par lots récurrent qui libère toutes les lignes de commande fournisseur confirmées qui devraient arriver le jour suivant.

Le collaborateur peut exécuter le processus de réception à l’aide d’une application mobile Gestion des entrepôts connectée à l’unité de mise à l’échelle. Les données sont ensuite enregistrées par l’unité de mise à l’échelle et rapportées à la commande magasin entrante. La création et le traitement de la mise en stock ultérieure seront également gérés par l’unité de mise à l’échelle.

Si vous n’utilisez pas le processus de *lancement dans l’entrepôt*, et n’utilisent donc pas les *commandes d’entrepôt*, le hub peut traiter la réception en entrepôt et le traitement du travail indépendamment des unités de mise à l’échelle.

![Flux des processus entrants.](./media/wes-inbound-ga.png "Flux des processus entrants")

Lors de l’enregistrement entrant via le processus de réception de la commande d’entrepôt d’unité d’échelle au niveau de l’application d’entrepôt, la charge de travail de l’unité d’échelle signalera au hub de mettre à jour les transactions de ligne de commande d’achat associées à *Enregistré*. Dès que cela est terminé, vous serez en mesure d’accuser réception du produit concerné par la commande d’achat sur le hub.

![Flux des traitements entrants.](./media/WES-inbound-processing-19.png "Flux des traitements entrants")

## <a name="supported-processes-and-roles"></a>Processus et rôles pris en charge

Tous les processus de gestion d’entrepôt ne sont pas pris en charge dans une charge de travail WES sur une unité d’échelle. Par conséquent, nous vous recommandons d’attribuer des rôles qui correspondent aux fonctionnalités disponibles pour chaque utilisateur.

Pour faciliter ce processus, un exemple de rôle nommé *Gestionnaire d’entrepôt sur la charge de travail* est inclus dans les données de démonstration sur **Administration du système \> Sécurité \> Configuration de la sécurité**. Le but de ce rôle est de permettre aux responsables d’entrepôt d’accéder au WES sur l’unité de mise à l’échelle. Le rôle accorde l’accès aux pages pertinentes dans le contexte d’une charge de travail hébergée sur une unité d’échelle.

Les rôles d’utilisateur sur une unité de mise à l’échelle sont attribués dans le cadre de la synchronisation initiale des données du hub vers l’unité de mise à l’échelle.

Pour modifier les rôles attribués à un utilisateur, accédez à **Administration du système \> Sécurité \> Attribuer des utilisateurs à des rôles**. Les utilisateurs qui agissent en tant que gestionnaires d’entrepôt uniquement sur les unités de mise à l’échelle doivent se voir attribuer uniquement le rôle *Gestionnaire d’entrepôt sur la charge de travail*. Cette approche garantira que ces utilisateurs n’ont accès qu’aux fonctionnalités prises en charge. Supprimez tous les autres rôles attribués à ces utilisateurs.

Les utilisateurs qui agissent en tant que gestionnaires d’entrepôt sur le hub et les unités de mise à l’échelle doivent se voir attribuer uniquement le rôle de *Magasinier* existant. Sachez que ce rôle accorde aux Magasiniers l’accès aux fonctionnalités (telles que le traitement de la réception des ordres de transfert) qui apparaissent dans l’interface utilisateur (IU) mais qui ne sont actuellement pas prises en charge sur les unités d’échelle.

## <a name="supported-wes-processes"></a>Processus WES pris en charge

Les processus d’exécution d’entrepôt suivants peuvent être activés pour une charge de travail WES sur une unité de mise à l’échelle :

- Méthodes de vague sélectionnées pour les commandes client et les ordres de transfert (affectation, réapprovisionnement de la demande, mise en conteneur, création de travail et impression d’étiquettes de vague)

- Traitement des tâches d’entrepôt des ordres de transfert et de commande avec l’application d’entreposage (y compris la tâche de réapprovisionnement)
- Interrogation du stock disponible à l’aide de l’application d’entrepôt
- Création et exécution des mouvements de stock à l’aide de l’application d’entrepôt
- Création et traitement d’un travail de comptage cyclique à l’aide de l’application d’entrepôt
- Ajustements du stock à l’aide de l’application d’entrepôt
- Enregistrement des commandes fournisseur et travaux de rangement en utilisant l’application d’entrepôt

Les types d’ordre de travail suivants sont actuellement pris en charge pour les charges de travail WES sur les déploiements d’unités de mise à l’échelle :

- Commandes client
- Sortie de transfert
- Réapprovisionnement (hors matières premières pour la production)
- Mouvement de stock
- Inventaire tournant
- Commandes fournisseur (liées aux commandes entrepôt)

Aucun autre traitement des documents source ou des tâches d’entrepôt n’est actuellement pris en charge sur les unités d’échelle. Par exemple, pour une charge de travail WES sur une unité d’échelle, vous ne pouvez pas accuser réception d’un ordre de transfert (réception de transfert), car cela est traité par l’instance du hub.

> [!NOTE]
> Les éléments de menu et les boutons de l’appareil mobile pour les fonctionnalités non prises en charge ne sont pas affichés dans l’_application mobile Gestion des entrepôts_ lorsqu’elle est connecté à un déploiement d’unité d’échelle.

> [!WARNING]
> Lorsque vous exécutez une charge de travail sur une unité de mise à l’échelle, vous ne pouvez pas exécuter de processus non pris en charge pour l’entrepôt spécifique sur le hub. Les tables indiquées ultérieurement dans cette rubrique documentent les fonctionnalités prises en charge.
>
> Les types de travaux d’entrepôt sélectionnés peuvent être créés à la fois sur le hub et sur les unités d’échelle, mais ne peuvent être gérés que par le hub ou l’unité d’échelle propriétaire (le déploiement qui a créé les données).
>
> Même lorsqu’un processus spécifique est pris en charge par l’unité d’échelle, sachez que toutes les données nécessaires peuvent ne pas être synchronisées depuis le hub vers l’unité d’échelle, ou depuis l’unité d’échelle vers le hub, ce qui risque d’entraîner un traitement système inattendu. Exemples :
> 
> - Si vous utilisez une requête de directive d’emplacement qui joint un enregistrement de table de données qui n’existe qu’au niveau du déploiement du hub.
> - Si vous utilisez les fonctionnalités d’état d’emplacement et/ou de charge volumétrique d’emplacement. Ces données ne seront pas synchronisées entre les déploiements et ne fonctionneront donc que lors de la mise à jour de l’inventaire des emplacements disponible sur l’un des déploiements.

La fonctionnalité de gestion d’entrepôt suivante n’est actuellement pas prise en charge pour les charges de travail de l’unité d’échelle :

- Traitement entrant des lignes de commande fournisseur affectées à un chargement
- Traitement entrant des commandes fournisseur pour un projet
- Traitement entrant et sortant pour les articles qui ont des dimensions de suivi actives **Propriétaire** et/ou **Numéro de série**
- Traitement du stock inventaire qui a une valeur de statut de blocage
- Modification d’un statut d’inventaire pendant tout processus de mouvement de travail
- Réservations flexibles de dimension au niveau de l’entrepôt validées par la commande
- Utilisation de la fonctionnalité *Statut de l’emplacement de l’entrepôt* (les données ne sont pas synchronisées entre les déploiements)
- Utilisation de la fonctionnalité *Positionnement des contenants d’emplacement*
- Utilisation des fonctionnalités *Filtres de produit* et *Groupes de filtres de produit*, y compris le paramètre **Nombre de jours pour mélanger les lots**
- Intégration avec la gestion de la qualité
- Traitement avec articles en poids variable
- Traitement avec articles activés uniquement pour la gestion du transport (TMS)
- Traitement avec stock disponible négatif
- Traitement du travail en entrepôt avec des types de travaux personnalisés
- Traitement du travail en entrepôt avec notes d’expédition
- Traitement du travail en entrepôt avec manutention des matières/Warehouse Automation
- Utilisation de l’image des données principales du produit (par exemple, sur l’application mobile Gestion des entrepôts)

> [!WARNING]
> Certaines fonctionnalités d’entrepôt ne seront pas disponibles pour les entrepôts exécutant les charges de travail de gestion d’entrepôt sur une unité d’échelle et ne sont pas non plus prises en charge sur le hub ou sur la charge de travail de l’unité d’échelle.
> 
> D’autres fonctionnalités peuvent être traitées sur les deux, mais nécessiteront une utilisation prudente dans certains scénarios, par exemple lorsque l’inventaire disponible est mis à jour pour le même entrepôt sur le hub et l’unité d’échelle en raison du processus de mise à jour des données asynchrone.
> 
> Les fonctionnalités spécifiques (telles que *bloquer le travail*) qui sont prises en charge à la fois sur les unités d’échelle et le hub ne seront pris en charge que pour le propriétaire des données.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>Sortant (pris en charge uniquement pour les commandes client et les ordres de transfert)

Le tableau suivant indique quelles fonctionnalités sortantes sont prises en charge et où elles sont prises en charge lorsque les charges de travail de gestion d’entrepôt sont utilisées dans des unités d’échelle de cloud et Edge.

| Processus                                                      | Hub | Charge de travail WES sur une unité de mise à l’échelle |
|--------------------------------------------------------------|-----|------------------------------|
| Traitement du document source                                   | Oui | N° |
| Traitement de la gestion du transport et du chargement                | Oui | N° |
| Libérer dans l’entrepôt                                         | Oui | N° |
| Cross-docking planifié                                        | N°  | N° |
| Consolidation d’expédition                                       | Oui | N° |
| Traitement de vague d’expédition                                     | Oui, mais uniquement l’initialisation et la finalisation du statut de la vague sont gérées dans le hub. Cela signifie que le transfert sortant et le traitement des commandes client ne peuvent être gérés que par l’unité d’échelle.|<p>Non, l’initialisation et la finalisation sont gérées par le hub et la fonctionnalité **Création et tri de chargement** n’est pas prise en charge<p><b>Remarque :</b> l’accès au hub est nécessaire pour finaliser le statut de la vague dans le cadre du traitement de la vague.</p> |
| Gérer les expéditions pour la vague                                  | Oui | N° |
| Traitement du travail en entrepôt (y compris impression de contenant)        | N°  | <p>Oui, mais uniquement pour les fonctionnalités prises en charge mentionnées ci-dessus. |
| Prélèvement de groupement                                              | N°  | Oui|
| Traitement d’emballage manuel, y compris le traitement des travaux de type « Prélèvement du conteneur compressé » | N° <P>Un certain traitement peut être effectué après un processus de prélèvement initial géré par une unité d’échelle, mais n’est pas recommandé en raison des opérations bloquées suivantes.</p>  | N° |
| Supprimer un conteneur du groupe                                  | N°  | N° |
| Traitement du tri sortant                                  | N°  | N° |
| Impression de documents relatifs à la charge                           | Oui | N° |
| Connaissement et génération d’APE                            | Oui | N° |
| Confirmation d’envoi                                             | Oui | N° |
| Confirmation d’expédition avec « Confirmer et transférer »            | N°  | N° |
| Traitement des bons de livraison et des factures                        | Oui | N° |
| Prélèvement partiel (commandes client et ordres de transfert)                    | N°  | N° |
| Prélèvement excessif (commandes client et ordres de transfert)                     | N°  | N° |
| Changement de lieu de travail (commandes clients et ordres de transfert)         | N°  | Oui|
| Travaux complets (commandes client et ordres de transfert)                    | N°  | Oui|
| Imprimer l’état de travail                                            | Oui | N° |
| Étiquette de vague                                                   | N°  | Oui|
| Fractionnement du travail                                                   | N°  | Oui|
| Traitement du travail - Dirigé par « Chargement de transport »            | N°  | N° |
| Réduire la quantité prélevée                                       | N°  | N° |
| Contrepasser le travail                                                 | N°  | N° |
| Inverse la confirmation d’expédition                                | Oui | N° |

### <a name="inbound"></a>Entrant(e)

Le tableau suivant indique quelles fonctionnalités entrantes sont prises en charge et où elles sont prises en charge lorsque les charges de travail de gestion d’entrepôt sont utilisées dans des unités d’échelle de cloud et Edge.

| Processus                                                          | Hub | Charge de travail WES sur une unité de mise à l’échelle<BR>*(Les articles accompagnés de la mention « Oui » s’appliquent uniquement aux commandes d’entrepôt)*</p> |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Traitement&nbsp;document&nbsp;source                             | Oui | N° |
| Traitement de la gestion du transport et du chargement                    | Oui | N° |
| Confirmation d’envoi entrant                                    | Oui | N° |
| Validation de la commande fournisseur vers l’entrepôt (traitement des commandes entrepôt) | Oui | N° |
| Annulation des lignes de commande d’entrepôt<p>Notez que cela n’est pris en charge que lorsqu’aucun enregistrement n’a eu lieu sur la ligne</p> | Oui | N° |
| Réception et rangement de l’article de commande fournisseur                       | <p>Oui,&nbsp;quand&nbsp;il&nbsp;n’y a pas de commande d’entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | <p>Oui, lorsqu’un bon de commande ne fait pas partie d’une <i>charge</i></p> |
| Réception et rangement de la ligne de commande fournisseur                       | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | <p>Oui, lorsqu’un bon de commande ne fait pas partie d’une <i>charge</i></p></p> |
| Réception et rangement d’ordre de retour                              | Oui | N° |
| Réception et rangement de contenant mixte                       | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | N° |
| Réception des articles du chargement                                              | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | N° |
| Réception et rangement de contenant                             | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | N° |
| Réception et rangement des articles de l’ordre de transfert                       | Oui | N° |
| Réception et rangement de la ligne d’ordre de transfert                       | Oui | N° |
| Annuler le travail (entrant)                                            | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | <p>Oui, mais uniquement lorsque l’option <b>Annuler l’enregistrement du reçu lors de l’annulation du travail</b> (sur la page <b>Paramètres de gestion de l’entrepôt</b>) est désactivée</p> |
| Traitement de l’accusé de réception de marchandises d’une commande fournisseur                        | Oui | N° |
| Réception de bon de commande avec sous-livraison                      | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Oui, mais uniquement en effectuant une demande d’annulation depuis le hub |
| Réception de bon de commande avec livraison excédentaire                       | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Oui  |
| Réception avec création de travaux de *Cross docking*                 | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Non |
| Réception avec création de travaux de type *Ordre de qualité*                  | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Non |
| Réception avec création de travaux de type *Échantillonnage d’articles de qualité*          | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Non |
| Réception avec création de travaux de type *Qualité dans le contrôle qualité*       | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Non |
| Réception avec création d’ordre de qualité                            | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Non |
| Traitement du travail - Dirigé par *Rangement de groupement*                 | Oui | Non |
| Traitement du travail avec *Prélèvement partiel*                               | Oui | N° |
| Chargement de contenant                                           | Oui | Oui |

### <a name="warehouse-operations-and-exception-handing"></a>Opérations d’entrepôt et traitement des exceptions

Le tableau suivant indique quelles fonctionnalités d’opérations d’entrepôt et de traitement des exceptions sont prises en charge et où elles sont prises en charge lorsque les charges de travail de gestion d’entrepôt sont utilisées dans des unités d’échelle de cloud et Edge.

| Processus                                            | Hub | Charge de travail WES sur une unité de mise à l’échelle |
|----------------------------------------------------|-----|------------------------------|
| Recherche de contenant                              | Oui | Oui                          |
| Recherche d’article                                       | Oui | Oui                          |
| Recherche d’emplacement                                   | Oui | Oui                          |
| Modifier l’entrepôt                                   | Oui | Oui                          |
| Mouvement                                           | Oui | Oui                          |
| Mouvement par modèle                               | Oui | Oui                          |
| Transfert d’entrepôt                                 | Oui | Non                           |
| Créer un ordre de transfert depuis l’application d’entreposage           | Oui | N°                           |
| Ajustement (entrée/sortie)                                | Oui | Oui, mais pas pour le scénario d’ajustement si la réservation de stock doit être supprimée à l’aide du paramètre **Supprimer les réservations** sur les types d’ajustement de stock.</p>                           |
| Modification du statut du stock                            | Oui | N°                           |
| Comptage cyclique et traitement des écarts de comptage | Oui | Oui                           |
| Réimpression d’étiquette (impression de contenant)             | Oui | Oui                          |
| Création de contenant                                | Oui | Non                           |
| Décomposition du contenant                                | Oui | Non                           |
| Conditionner dans des contenants imbriqués                                | Oui | Non                           |
| Vérification à l’arrivée du chauffeur                                    | Oui | Non                           |
| Vérification au départ du chauffeur                                   | Oui | Non                           |
| Modifier le code de disposition de traitement par lots                      | Oui | Oui                          |
| Afficher la liste des travaux en cours                             | Oui | Oui                          |
| Consolider les contenants                         | Oui | Non                           |
| Traitement de réapprovisionnement du seuil de zone et min/max| Oui <p>Il est recommandé de ne pas inclure les mêmes emplacements dans le cadre des requêtes</p>| Oui                          |
| Traitement du réapprovisionnement de créneaux                  | Oui  | Oui<p>Notez que la configuration doit être effectuée sur l’unité d’échelle</p>                           |
| Bloquer et débloquer le travail                             | Oui | Oui                          |
| Changer d’utilisateur                                        | Oui | Oui                          |
| Modifier le pool de travail sur le travail                           | Oui | Oui                          |
| Annuler le travail                                        | Oui | Oui                          |

### <a name="production"></a>Production

Le tableau suivant résume les scénarios de production de gestion des entrepôts qui sont actuellement pris en charge (ou non) sur les charges de travail d’unité d’échelle.

| Processus | Hub | Charge de travail WES sur une unité de mise à l’échelle |
|---------|-----|------------------------------|
| Rangement des produits finis et déclarés terminés | Oui | Oui |
| Rangement des coproduits et des sous-produits | Oui | Oui |
| <p>Tous les autres processus de gestion d’entrepôt liés à la production, notamment :</p><li>Libérer dans l’entrepôt</li><li>Traitement de vagues de production</li><li>Prélèvement de matières premières</li><li>Rangement de kanban</li><li>Prélèvement de kanban</li><li>Démarrer l’ordre de fabrication</li><li>Production au rebut</li><li>Dernière palette de production</li><li>Enregistrer la consommation de matières</li><li>Kanban vide</li></ul> | Oui | N° |
| Réapprovisionnement en matières premières | N° | N° |

## <a name="maintaining-scale-units-for-wes"></a>Gestion des unités d’échelle pour WES

Plusieurs tâches de traitement par lots s’exécutent à la fois sur les unités de hub et de mise à l’échelle.

Sur le déploiement du hub, vous pouvez gérer manuellement les tâches de traitement par lots. Vous pouvez gérer les tâches de traitement par lots suivantes sur **Gestion d’entrepôt \> Tâches périodiques \> Gestion de la charge de travail back-office** :

- Unité d’échelle du processeur de messages du hub
- Enregistrer les réceptions de commande source
- Terminer les commandes d’entrepôt

Sur la charge de travail dans les unités de mise à l’échelle, vous pouvez gérer les tâches de traitement par lots suivantes sur **Gestion d’entrepôt \> Tâches périodiques \> Gestion de la charge de travail** :

- Traiter les enregistrements de la table des vagues
- Point de transbordement de l’entrepôt du processeur de messages d’unité d’échelle
- Traiter les demandes de mise à jour de la quantité pour les lignes de commande d’entrepôt

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
