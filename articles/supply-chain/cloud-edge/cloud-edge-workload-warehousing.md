---
title: Charges de travail de gestion de l’entreposage pour les unités d’échelle du cloud et d’Edge
description: Cette rubrique fournit des informations sur la fonctionnalité qui permet aux unités d’échelle d’exécuter des processus sélectionnés à partir de votre charge de travail de gestion d’entrepôt.
author: perlynne
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, InventTransferOrders, SalesTable, SysSecRolesEditUsers, SysWorkloadDuplicateRecord
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 67f78441b0914d18c2a7853bab54c6b8817be3ac
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384482"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Charges de gestion d’entrepôt pour les unités d’échelle Cloud et périphérie

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Toutes les fonctionnalités commerciales de gestion d’entrepôt ne sont pas entièrement prises en charge pour les entrepôts exécutant une charge de travail sur une unité d’échelle. Veillez à n’utiliser que les processus que cette rubrique décrit explicitement comme pris en charge.

## <a name="warehouse-execution-on-scale-units"></a>Exécution d’entrepôt sur des unités d’échelle

Les charges de travail de la gestion des entrepôts permettent aux unités d’échelle du cloud et de la périphérie d’exécuter des processus sélectionnés à partir des fonctionnalités de gestion des entrepôts.

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer à travailler avec la charge de travail de gestion d’entrepôt, votre système doit être préparé comme décrit dans cette section.

### <a name="deploy-a-scale-unit-with-the-warehouse-management-workload"></a>Déployer une unité d’échelle avec la charge de travail de gestion d’entrepôt

Vous devez avoir un hub Dynamics 365 Supply Chain Management et une unité d’échelle déployée avec la charge de travail de gestion d’entrepôt. Pour plus d’informations sur l’architecture et le processus de déploiement, consultez [Unités d’échelle dans une topologie hybride distribuée](cloud-edge-landing-page.md).

### <a name="turn-on-required-features-in-feature-management"></a>Activer les fonctionnalités requises dans la gestion des fonctionnalités

Utilisez l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer les fonctionnalités dans l’ordre suivant : (Les deux fonctionnalités sont répertoriées dans le module *Gestion des entrepôts*.)

- Découpler le travail de rangement des APE
- (Aperçu) Prise en charge de l’unité d’échelle pour les commandes d’entrepôt entrantes et sortantes

## <a name="how-the-warehouse-execution-workload-works-on-scale-units"></a>Fonctionnement de la charge de travail d’exécution de l’entrepôt sur les unités d’échelle

Pour les processus de la charge de travail de gestion de l’entrepôt, les données sont synchronisées entre le hub et les unités d’échelle.

Une unité d’échelle ne peut conserver que les données dont elle est propriétaire. Le concept de propriété des données pour les unités d’échelle permet d’éviter les conflits multimaître. Par conséquent, il est important que vous compreniez quelles données de processus sont détenues par le hub et lesquelles appartiennent aux unités d’échelle.

En fonction des processus métier, le même enregistrement de données peut changer de propriétaire entre le hub et les unités d’échelle. Un exemple de ce scénario est fourni dans la section suivante.

> [!IMPORTANT]
> Certaines données peuvent être créées à la fois sur le hub et sur l’unité d’échelle. Il put s’agir des **Contenants** et des **Numéros de lot**. Une gestion des conflits dédiée est assurée dans le cas d’un scénario où le même enregistrement unique est créé à la fois sur le hub et sur une unité d’échelle au cours du même cycle de synchronisation. Lorsque cela se produit, la synchronisation suivante échouera et vous devrez accéder à **Administration système > Demandes de renseignements > Demandes de renseignements sur les charges de travail > Enregistrements en double**, où vous pouvez afficher et fusionner les données.

## <a name="outbound-process-flow"></a>Flux des processus sortants

Avant de déployer une charge de travail de gestion d’entrepôt sur une unité d’échelle cloud ou périphérique, assurez-vous que la fonctionnalité *Prise en charge de l’unité d’échelle pour la mise en production dans l’entrepôt des commandes sortantes* est activée sur votre hub d’entreprise. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Prise en charge de l’unité d’échelle pour la mise en production dans l’entrepôt des commandes sortantes*

Le processus de propriété des données sortantes dépend de l’utilisation ou non du processus de planification des chargements. Dans tous les cas, le hub est propriétaire des *documents source*, tels que les commandes client et les ordres de transfert, ainsi que du processus de répartition des commandes et des données de transaction de commande associées. Mais lorsque vous utilisez le processus de planification des chargements, les chargements seront créés dans le hub et seront donc initialement détenus par le hub. Dans le cadre du processus *Lancement vers l’entrepôt*, la propriété des données de chargement est transférée au déploiement de l’unité d’échelle dédié, qui deviendra le propriétaire du *traitement de vague d’expédition* consécutif (comme la répartition du travail, le travail de réapprovisionnement et la création de la demande de travail). Par conséquent, les magasiniers ne peuvent traiter le travail de ventes sortantes et d’ordres de transfert qu’à l’aide d’une application mobile Warehouse Management connectée au déploiement qui exécute la charge de travail de l’unité d’échelle spécifique.

Dès que le processus de travail final place le stock au lieu d’expédition final (Baydoor), l’unité d’échelle signale au hub de mettre à jour les transactions de stock sur le document source à *Prélevé*. Jusqu’à ce que ce processus s’exécute et soit de nouveau synchronisé, le stock disponible sur la charge de travail de l’unité d’échelle sera physiquement réservé au niveau de l’entrepôt et vous pourrez immédiatement traiter la confirmation d’expédition sortante sans attendre la fin de cette synchronisation. Le bon de livraison et la facturation ou l’expédition de l’ordre de transfert pour le chargement seront traités dans le hub.

Le schéma suivant montre le flux sortant et indique où se déroulent les processus métier individuels. (Sélectionnez le schéma pour l’agrandir.)

[![Flux des traitements sortants.](media/wes_outbound_warehouse_processes-small.png "Flux des traitements sortants")](media/wes_outbound_warehouse_processes.png)

### <a name="outbound-processing-with-load-planning"></a>Traitement sortant avec planification des chargements

Lorsque vous utilisez le processus de planification des chargements, les chargements et les expéditions sont créés sur le hub et la propriété des données est transférée aux unités d’échelle dans le cadre du processus *Lancement vers l’entrepôt*, comme illustré dans la figure suivante.

![Traitement sortant avec planification des chargements.](./media/wes_outbound_processing_with_load_planning.png "Traitement sortant avec planification des chargements")

### <a name="outbound-processing-without-load-planning"></a>Traitement sortant sans planification des chargements

Lorsque vous n’utilisez pas le processus de planification des chargements, les expéditions sont créées sur les unités d’échelle. Les chargements sont également créés sur les unités d’échelle dans le cadre du processus de vague.

![Traitement sortant sans planification des chargements.](./media/wes_outbound_processing_without_load_planning.png "Traitement sortant sans planification des chargements")

## <a name="inbound-process-flow"></a>Flux des processus entrants

Le hub possède les données suivantes :

- Tous les documents sources, tels que les commandes fournisseur et les ordres de fabrication
- Traitement de charge entrante
- Tous les mises à jour de coût et financières

> [!NOTE]
> Le flux de commandes fournisseur entrant est différent en termes de concept du flux sortant. Vous pouvez gérer le même entrepôt sur l’unité d’échelle ou sur le hub selon que la commande fournisseur a été lancée ou non dans l’entrepôt. Après avoir lancé une commande vers l’entrepôt, vous ne pouvez travailler avec cette commande que lorsque vous êtes connecté à l’unité d’échelle.
>
> Si vous utilisez le processus *Lancement vers l’entrepôt*, les [*commandes d’entrepôt*](cloud-edge-warehouse-order.md) sont créées et la propriété du flux de réception associé est attribuée à l’unité d’échelle. Le hub ne pourra pas enregistrer la réception entrante.

Vous devez vous connecter au hub pour utiliser le processus *Lancement vers l’entrepôt*. Pour le traitement des commandes fournisseur, accédez à l’une des pages suivantes pour l’exécuter ou le planifier :

- **Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur > Entrepôt > Actions > Lancement vers l’entrepôt**
- **Gestion des entrepôts > Lancement vers l’entrepôt > Lancement automatique des commandes fournisseur**

Lors de l’utilisation de **Libération automatique des commandes fournisseur**, vous pouvez sélectionner des lignes de commande fournisseur spécifiques en fonction d’une requête. Un scénario typique serait de configurer un traitement par lots récurrent qui libère toutes les lignes de commande fournisseur confirmées qui devraient arriver le jour suivant.

Le collaborateur peut exécuter le processus de réception à l’aide d’une application mobile Warehouse Management connectée à l’unité d’échelle. Les données sont ensuite enregistrées par l’unité d’échelle et rapportées à la commande magasin entrante. La création et le traitement de la mise en stock ultérieure seront également gérés par l’unité d’échelle.

Si vous n’utilisez pas le processus de *Lancement vers l’entrepôt*, et n’utilisez donc pas les *commandes d’entrepôt*, le hub peut traiter la réception en entrepôt et le traitement du travail indépendamment des unités d’échelle.

![Flux des processus entrants.](./media/wes-inbound-ga.png "Flux des processus entrants")

Lorsqu’un collaborateur effectue un enregistrement entrant à l’aide d’un processus de réception de l’application mobile Warehouse Management par rapport à l’unité d’échelle, une réception est enregistrée par rapport à l’ordre d’entrepôt associé, qui est stocké sur l’unité d’échelle. La charge de travail de l’unité d’échelle indique alors au hub de mettre à jour les transactions de ligne de commande fournisseur associées sur *Enregistré*. Dès que cela est terminé, vous serez en mesure d’accuser réception du produit concerné par la commande d’achat sur le hub.

Le schéma suivant montre le flux entrant et indique où se déroulent les processus métier individuels. (Sélectionnez le schéma pour l’agrandir.)

[![Flux des traitements entrants](media/wes_inbound_warehouse_processes-small.png "Flux des traitements entrants")](media/wes_inbound_warehouse_processes.png)

## <a name="production-control"></a>Contrôle de la production

La charge de travail de gestion d’entrepôt prend en charge les trois flux suivants pour la production dans l’application Warehouse Management :

- Déclarer comme terminé et ranger
- Démarrer l’ordre de fabrication
- Enregistrer la consommation de matières

### <a name="report-as-finished-and-put-away"></a>Déclarer comme terminé et ranger

Les collaborateurs peuvent utiliser le flux **Déclarer comme terminé et ranger** dans l’application Warehouse Management pour signaler une production ou un lot de production comme terminé. Ils peuvent également déclarer les coproduits et les sous-produits d’un lot de production comme terminés. Lorsqu’une tâche est signalée comme terminée, le système génère généralement les travaux de rangement d’entrepôt sur l’unité d’échelle. Si vous n’avez pas besoin de travaux de rangement, vous pouvez configurer vos stratégies de travail pour les omettre.

### <a name="start-production-order"></a>Démarrer l’ordre de fabrication

Les collaborateurs peuvent utiliser le flux **Démarrer l’ordre de fabrication** dans l’application Warehouse Management pour enregistrer le démarrage d’une production ou d’un lot de production.

### <a name="register-material-consumption"></a>Enregistrer la consommation de matières

Les collaborateurs peuvent utiliser le flux **Enregistrer la consommation des matières** dans l’application Warehouse Management pour signaler la consommation des matières pour une production ou un lot de production. Un journal des prélèvements est ensuite créé pour le matériel déclaré sur la production ou le lot de production sur l’unité d’échelle. Les lignes de journal effectuent une réservation physique sur le stock consommé. Lorsque les données sont synchronisées entre l’unité d’échelle et le hub, un journal de prélèvement est généré et publié sur l’instance du hub.

## <a name="supported-processes-and-roles"></a>Processus et rôles pris en charge

Tous les processus de gestion d’entrepôt ne sont pas pris en charge dans une charge de travail d’exécution de l’entrepôt sur une unité d’échelle. Par conséquent, nous vous recommandons d’attribuer des rôles qui correspondent aux fonctionnalités disponibles pour chaque utilisateur.

Pour faciliter ce processus, un exemple de rôle nommé *Gestionnaire d’entrepôt sur la charge de travail* est inclus dans les données de démonstration sur **Administration du système \> Sécurité \> Configuration de la sécurité**. Le but de ce rôle est de permettre aux responsables d’entrepôt d’accéder à la charge de travail d’exécution de l’entrepôt sur l’unité d’échelle. Le rôle accorde l’accès aux pages pertinentes dans le contexte d’une charge de travail hébergée sur une unité d’échelle.

Les rôles d’utilisateur sur une unité d’échelle sont attribués dans le cadre de la synchronisation initiale des données du hub vers l’unité d’échelle.

Pour modifier les rôles attribués à un utilisateur, accédez à **Administration du système \> Sécurité \> Attribuer des utilisateurs à des rôles**. Les utilisateurs qui agissent en tant que gestionnaires d’entrepôt uniquement sur les unités d’échelle doivent se voir attribuer uniquement le rôle *Gestionnaire d’entrepôt sur la charge de travail*. Cette approche garantira que ces utilisateurs n’ont accès qu’aux fonctionnalités prises en charge. Supprimez tous les autres rôles attribués à ces utilisateurs.

Les utilisateurs qui agissent en tant que gestionnaires d’entrepôt sur le hub et les unités d’échelle doivent se voir attribuer uniquement le rôle de *Magasinier* existant. Sachez que ce rôle accorde aux Magasiniers l’accès aux fonctionnalités (telles que le traitement de la réception des ordres de transfert) qui apparaissent dans l’interface utilisateur (IU) mais qui ne sont actuellement pas prises en charge sur les unités d’échelle.

### <a name="supported-warehouse-execution-processes"></a>Processus d’exécution d’entrepôt pris en charge

Les processus d’exécution d’entrepôt suivants peuvent être activés pour une charge de travail d’exécution d’entrepôt sur une unité d’échelle :

- Méthodes de vague sélectionnées pour les commandes client et les ordres de transfert (validation, création de chargement, répartition, réapprovisionnement de la demande, mise en conteneur, création de travail et impression d’étiquettes de vague)

- Traitement des tâches d’entrepôt des ordres de transfert et de commande avec l’application d’entreposage (y compris la tâche de réapprovisionnement)
- Interrogation du stock disponible à l’aide de l’application d’entrepôt
- Création et exécution des mouvements de stock à l’aide de l’application d’entrepôt
- Création et traitement d’un travail de comptage cyclique à l’aide de l’application d’entrepôt
- Ajustements du stock à l’aide de l’application d’entrepôt
- Enregistrement des commandes fournisseur et travaux de rangement en utilisant l’application d’entrepôt

Les types de travail suivants peuvent être créés sur une unité d’échelle et peuvent donc être traités dans le cadre d’une charge de travail de gestion d’entrepôt :

- **Mouvements d’inventaire** : mouvement manuel et mouvement par modèle de travail.
- **Inventaire tournant** : comprend un processus d’approbation/rejet des écarts dans le cadre des opérations de comptage.
- **Commandes fournisseur** : tâches de rangement via une commande entrepôt lorsque les commandes fournisseur ne sont pas associées à des chargements.
- **Commandes client** : tâches de prélèvement et de chargement simples.
- **Réception du transfert** : via le traitement de réception du contenant.
- **Problème de transfert** : tâches de prélèvement et de chargement simples.
- **Réapprovisionnement** : hors matières premières pour la production.
- **Produits finis rangés** : après le processus de déclaration de fin de production.
- **Rangement des co-produits et sous-produits** : après le processus de déclaration de fin de production.
<!-- - **Packed container picking** - After manual packing station processing. -->

Aucun autre type de traitement des documents source ou des tâches d’entrepôt n’est actuellement pris en charge sur les unités d’échelle. Par exemple, lorsque vous exécutez une charge de travail d’exécution d’entrepôt sur une unité d’échelle, vous ne pouvez pas utiliser le processus de réception d’un retour vente pour traiter les ordres de retour. Au lieu de cela, ce traitement doit être effectué par l’instance du hub.

> [!NOTE]
> Les éléments de menu et les boutons de l’appareil mobile pour les fonctionnalités non prises en charge ne sont pas affichés dans l’_application mobile Warehouse Management_ lorsqu’elle est connecté à un déploiement d’unité d’échelle.
>
> Quelques étapes supplémentaires sont nécessaires pour configurer l’application mobile Warehouse Management afin qu’elle fonctionne avec une unité d’échelle cloud ou périphérique. Pour plus d’informations, voir [Configurer l’application mobile Warehouse Management pour les unités d’échelle périphériques et cloud](cloud-edge-workload-setup-warehouse-app.md).
>
> Lorsque vous exécutez une charge de travail sur une unité d’échelle, vous ne pouvez pas exécuter de processus non pris en charge pour l’entrepôt spécifique sur le hub. Les tables indiquées ultérieurement dans cette rubrique documentent les fonctionnalités prises en charge.
>
> Les types de travaux d’entrepôt sélectionnés peuvent être créés à la fois sur le hub et sur les unités d’échelle, mais ne peuvent être gérés que par le hub ou l’unité d’échelle propriétaire (le déploiement qui a créé les données).
>
> Même lorsqu’un processus spécifique est pris en charge par l’unité d’échelle, sachez que toutes les données nécessaires peuvent ne pas être synchronisées depuis le hub vers l’unité d’échelle, ou depuis l’unité d’échelle vers le hub, ce qui risque d’entraîner un traitement système inattendu. Voici des exemples de ce scénario :
>
> - Si vous utilisez une requête de directive d’emplacement qui joint un enregistrement de table de données qui n’existe qu’au niveau du déploiement du hub.
> - Si vous utilisez les fonctionnalités d’état d’emplacement et/ou de charge volumétrique d’emplacement. Ces données ne seront pas synchronisées entre les déploiements et ne fonctionneront donc que lors de la mise à jour de l’inventaire des emplacements disponible sur l’un des déploiements.

La fonctionnalité de gestion d’entrepôt suivante n’est actuellement pas prise en charge pour les charges de travail de l’unité d’échelle :

- Traitement entrant des lignes de commande fournisseur affectées à un chargement.
- Traitement entrant des commandes fournisseur pour un projet.
- Gestion des coûts au débarquement, utilisation des trajets et suivi des marchandises en transit.
- Traitement entrant et sortant pour les articles qui ont des dimensions de suivi actives **Propriétaire** et/ou **Numéro de série**.
- Traitement du stock inventaire qui a une valeur de statut de blocage.
- Modification d’un statut d’inventaire pendant tout processus de mouvement de travail.
- Réservations flexibles de dimension au niveau de l’entrepôt validées par la commande.
- Utilisation de la fonctionnalité *Statut de l’emplacement de l’entrepôt* (les données ne sont pas synchronisées entre les déploiements).
- Utilisation de la fonctionnalité *Positionnement des contenants d’emplacement*.
- Utilisation des fonctionnalités *Filtres de produit* et *Groupes de filtres de produit*, y compris le paramètre **Nombre de jours pour mélanger les lots**.
- Intégration avec la gestion de la qualité.
- Traitement avec articles en poids variable.
- Traitement avec articles activés uniquement pour la gestion du transport (TMS).
- Traitement avec stock disponible négatif.
- Partage de données entre sociétés pour les produits. <!-- Planned -->
- Traitement du travail d’entrepôt avec des notes d’expédition (par exemple, des notes d’emballage à la station d’emballage).
- Images des données principales du produit (par exemple, sur l’application mobile Warehouse Management).
- Traitement du travail en entrepôt avec manutention des matières/Warehouse Automation.

> [!WARNING]
> Certaines fonctionnalités d’entrepôt ne seront pas disponibles pour les entrepôts exécutant les charges de travail de gestion d’entrepôt sur une unité d’échelle et ne sont pas non plus prises en charge sur le hub ou sur la charge de travail de l’unité d’échelle.
>
> D’autres fonctionnalités peuvent être traitées sur les deux, mais nécessiteront une utilisation prudente dans certains scénarios, par exemple lorsque l’inventaire disponible est mis à jour pour le même entrepôt sur le hub et l’unité d’échelle en raison du processus de mise à jour des données asynchrone.
>
> Les fonctionnalités spécifiques (telles que *bloquer le travail*), qui sont prises en charge à la fois sur les unités d’échelle et le hub ne seront prises en charge que pour le propriétaire des données.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>Sortant (pris en charge uniquement pour les commandes client et les ordres de transfert)

Le tableau suivant indique quelles fonctionnalités sortantes sont prises en charge et où elles sont prises en charge lorsque les charges de travail de gestion d’entrepôt sont utilisées dans des unités d’échelle de cloud et Edge.

| Processus                                                      | Hub | Charge de travail de l’exécution d’entrepôt sur une unité d’échelle |
|--------------------------------------------------------------|-----|------------------------------|
| Traitement du document source                                   | Oui | Non |
| Traitement de la gestion du transport et du chargement                | Oui, mais uniquement les processus de planification des chargements. Le traitement de la gestion des transports n’est pas pris en charge  | Non |
| Lancement vers l’entrepôt                                         | Oui | Non |
| Cross-docking planifié                                        | Non  | Non |
| Regroupement d’expéditions                                       | Oui, lors de l’utilisation de la planification des chargements | Oui |
| Traitement de vague d’expédition                                     | Non  |Oui, sauf **Création et tri de chargement** |
| Gérer les expéditions pour la vague                                  | Non  | Oui|
| Traitement du travail en entrepôt (y compris impression de contenant)        | Non  | Oui, mais uniquement pour les fonctionnalités prises en charge mentionnées précédemment |
| Prélèvement de groupement                                              | N°  | Oui|
| Traitement manuel de la station d’emballage  | N°  | N° |
| Traitement du tri sortant                                  | N°  | N° |
| Impression de documents relatifs à la charge                           | Oui | Oui|
| Connaissement et génération d’APE                            | Non  | Oui|
| Confirmation d’envoi                                             | N°  | Oui|
| Confirmation d’expédition avec « Confirmer et transférer »            | N°  | Oui|
| Traitement des bons de livraison et des factures                        | Oui | N° |
| Prélèvement partiel (commandes client et ordres de transfert)                    | Non  | Oui, sans supprimer les réservations pour les documents source|
| Prélèvement excessif (commandes client et ordres de transfert)                     | N°  | Oui|
| Consolider les contenants                                   | N°  | Oui|
| Changement de lieu de travail (commandes clients et ordres de transfert)         | Non  | Oui|
| Travaux complets (commandes client et ordres de transfert)                    | Non  | Oui|
| Imprimer l’état de travail                                            | Oui | Oui|
| Étiquette de vague                                                   | Non  | Oui|
| Fractionnement du travail                                                   | Non  | Oui|
| Traitement du travail - Dirigé par « Chargement de transport »            | N°  | N° |
| Réduire la quantité prélevée                                       | N°  | Oui|
| Contrepasser le travail                                                 | N°  | Oui|
| Inverse la confirmation d’expédition                                | N°  | Oui|
| Demande d’annulation des lignes de commande d’entrepôt                      | Oui | Non, mais la demande sera approuvée ou rejetée |
| <p>Lancer les ordres de transfert pour réception</p><p>Ce processus se produira automatiquement dans le cadre du processus d’expédition de l’ordre de transfert. Cependant, il peut être utilisé manuellement pour activer la réception des contenants à une unité d’échelle si les lignes de commande entrantes de l’entrepôt ont été annulées ou dans le cadre d’un nouveau processus de déploiement de charge de travail.</p> | Oui | N°|
<!--| Traitement de la station d’emballage manuel, y compris les travaux de type « Prélèvement du conteneur compressé »  | N°  | Oui, mais sans manifeste d’expédition TMS ni envoi de bordereau d’emballage de vente et sans notes d’emballage et images de produits |-->

### <a name="inbound"></a>Entrant(e)

Le tableau suivant indique quelles fonctionnalités entrantes sont prises en charge et où elles sont prises en charge lorsque les charges de travail de gestion d’entrepôt sont utilisées dans des unités d’échelle de cloud et Edge.

| Processus                                                          | Hub | Charge de travail de l’exécution d’entrepôt sur une unité d’échelle<BR>*(Les articles accompagnés de la mention « Oui » s’appliquent uniquement aux commandes d’entrepôt)* |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Traitement&nbsp;document&nbsp;source                             | Oui | Non |
| Traitement de la gestion du transport et du chargement                    | Oui | Non |
| Marchandises au débarquement et en transit                       | Oui | Non |
| Confirmation d’envoi entrant                                    | Oui | Non |
| Lancement de la commande fournisseur vers l’entrepôt (traitement des commandes entrepôt) | Oui | N° |
| Demande d’annulation des lignes de commande d’entrepôt                            | Oui | Non, mais la demande sera approuvée ou rejetée |
| Traitement des documents source de réception de marchandises d’une commande fournisseur                        | Oui | N° |
| Réception et rangement de l’article de commande fournisseur                       | <p>Oui,&nbsp;quand&nbsp;il&nbsp;n’y a pas de commande d’entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | <p>Oui, lorsqu’un bon de commande ne fait pas partie d’une <i>charge</i></p> |
| Réception et rangement de la ligne de commande fournisseur                       | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | <p>Oui, lorsqu’un bon de commande ne fait pas partie d’une <i>charge</i></p></p> |
| Réception et rangement d’ordre de retour                              | Oui | Non |
| Réception et rangement de contenant mixte                       | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Oui |
| Réception des articles du chargement                                              | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | N° |
| Réception et rangement du contenant de commande fournisseur              | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | N° |
| Réception et rangement du contenant de commande de transfert             | N° | Oui |
| Réception et rangement des articles de l’ordre de transfert                       | Oui | N° |
| Réception et rangement de la ligne d’ordre de transfert                       | Oui | N° |
| Réception de bon de commande avec sous-livraison                      | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Oui, mais uniquement en effectuant une demande d’annulation depuis le hub |
| Réception de bon de commande avec livraison excédentaire                       | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Oui  |
| Réception avec création de travaux de *Cross docking*                 | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Non |
| Réception avec création de travaux de type *Ordre de qualité*                  | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Non |
| Réception avec création de travaux de type *Échantillonnage d’articles de qualité*          | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Non |
| Réception avec création de travaux de type *Qualité dans le contrôle qualité*       | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Non |
| Réception avec création d’ordre de qualité                            | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Non |
| Traitement du travail - Dirigé par *Rangement de groupement*                 | Oui | N° |
| Traitement du travail avec *Prélèvement partiel*                               | Oui | N° |
| Annuler le travail (entrant)                                            | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | <p>Oui, mais uniquement lorsque l’option <b>Annuler l’enregistrement du reçu lors de l’annulation du travail</b> (sur la page <b>Paramètres de gestion des entrepôts</b>) est désactivée</p> |
| Chargement de contenant                                           | Oui | Oui |

### <a name="warehouse-operations-and-exception-handing"></a>Opérations d’entrepôt et traitement des exceptions

Le tableau suivant indique quelles fonctionnalités d’opérations d’entrepôt et de traitement des exceptions sont prises en charge et où elles sont prises en charge lorsque les charges de travail de gestion d’entrepôt sont utilisées dans des unités d’échelle de cloud et Edge.

| Processus                                            | Hub | Charge de travail de l’exécution d’entrepôt sur une unité d’échelle |
|----------------------------------------------------|-----|------------------------------|
| Recherche de contenant                              | Oui | Oui                          |
| Recherche d’article                                       | Oui | Oui                          |
| Recherche d’emplacement                                   | Oui | Oui                          |
| Modifier l’entrepôt                                   | Oui | Oui                          |
| Mouvement                                           | Oui | Oui                          |
| Mouvement par modèle                               | Oui | Oui                          |
| Transfert d’entrepôt                                 | Oui | Non                           |
| Créer un ordre de transfert depuis l’application d’entreposage           | Oui | Non                           |
| Ajustement (entrée/sortie)                                | Oui | Oui, mais pas pour le scénario d’ajustement si la réservation de stock doit être supprimée à l’aide du paramètre **Supprimer les réservations** sur les types d’ajustement de stock</p>                           |
| Modification du statut du stock                            | Oui | Non                           |
| Comptage cyclique et traitement des écarts de comptage | Oui | Oui                           |
| Réimpression d’étiquette (impression de contenant)             | Oui | Oui                          |
| Création de contenant                                | Oui | Non                           |
| Décomposition du contenant                                | Oui | Non                           |
| Conditionner dans des contenants imbriqués                      | Oui | Non                           |
| Vérification à l’arrivée du chauffeur                                    | Oui | Non                           |
| Vérification au départ du chauffeur                                   | Oui | Non                           |
| Modifier le code de disposition de traitement par lots                      | Oui | Oui                          |
| Afficher la liste des travaux en cours                             | Oui | Oui                          |
| Traitement de réapprovisionnement du seuil de zone et min/max| Oui <p>Il est recommandé de ne pas inclure les mêmes emplacements dans le cadre des requêtes</p>| Oui                          |
| Traitement du réapprovisionnement de créneaux                  | Oui  | Oui<p>Notez que la configuration doit être effectuée sur l’unité d’échelle</p>                           |
| Bloquer et débloquer le travail                             | Oui | Oui                          |
| Changer d’utilisateur                                        | Oui | Oui                          |
| Modifier le pool de travail sur le travail                           | Oui | Oui                          |
| Annuler le travail                                        | Oui | Oui                          |

### <a name="production"></a>Production

Le tableau suivant résume les scénarios de production de gestion des entrepôts qui sont actuellement pris en charge sur les charges de travail d’unité d’échelle.

| Processus | Hub | Charge de travail de l’exécution d’entrepôt sur une unité d’échelle |
|---------|-----|----------------------------------------------|
| Traitement des documents sources des ordres de fabrication    | Oui | N° |
| Lancement vers l’entrepôt                           | Oui | N° |
| Démarrer l’ordre de fabrication                         | Oui | Oui|
| Créer des commandes d’entrepôt                        | Oui | N° |
| Demande d’annulation des lignes de commande d’entrepôt        | Oui | Non, mais la demande sera approuvée ou rejetée |
| Rangement des produits finis et déclarés terminés | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Oui|
| Rangement des coproduits et des sous-produits             | <p>Oui, lorsqu’il n’y a pas de commande entrepôt</p><p>Non, lorsqu’il y a une commande entrepôt</p> | Oui|
| Enregistrer la consommation de matières                  | Oui | Oui|
| Traitement de vagues de production                     | Oui | N° |
| Prélèvement de matières premières                           | Oui | N° |
| Rangement de kanban                                | Oui | N° |
| Prélèvement de kanban                                 | Oui | N° |
| Kanban vide                                   | Oui | N° |
| Production au rebut                               | Oui | N° |
| Dernière palette de production                         | Oui | N° |
| Réapprovisionnement en matières premières                     | N°  | N° |

## <a name="maintaining-scale-units-for-warehouse-execution"></a>Tenue à jour des unités d’échelle pour l’exécution d’entrepôt

Plusieurs tâches de traitement par lots s’exécutent à la fois sur les unités de hub et d’échelle.

Sur le déploiement du hub, vous pouvez gérer manuellement les tâches de traitement par lots suivantes :

- Gérer les tâches de traitement par lots suivantes sur **Gestion des entrepôts \> Tâches périodiques \> Gestion de la charge de travail back-office** :

    - Unité d’échelle du processeur de messages du hub
    - Enregistrer les réceptions de commande source
    - Terminer les commandes d’entrepôt
    - Générer les commandes d’entrepôt sortantes manquantes

- Gérer les tâches de traitement par lots suivantes sur **Gestion des entrepôts \> Tâches périodiques \> Gestion de la charge de travail** :

    - Point de transbordement de l’entrepôt du processeur de messages d’unité d’échelle
    - Traiter les réceptions de lignes de commande d’entrepôt pour la validation des réceptions entrepôt

Dans le cadre des déploiements des unités d’échelle, vous pouvez gérer les tâches de traitement par lots suivantes sur **Gestion des entrepôts \> Tâches périodiques \> Gestion de la charge de travail** :

- Traiter les enregistrements de la table des vagues
- Point de transbordement de l’entrepôt du processeur de messages d’unité d’échelle
- Traiter les réceptions de lignes de commande d’entrepôt pour la validation des réceptions entrepôt

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
