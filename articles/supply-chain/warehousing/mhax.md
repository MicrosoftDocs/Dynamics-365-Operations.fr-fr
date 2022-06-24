---
title: Interface de l’équipement de manutention du matériel (MHAX)
description: Cet article décrit comment configurer l’Interface de l’équipement de manutention du matériel (MHAX) afin que vous puissiez vous connecter à des systèmes de manutention physique (MH) externes.
author: Mirzaab
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMHEParameters, WMHESubscription, WMHEQueueManagerWorkspace, WMHEInboundQueue, WMHEOutboundQueue
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c4b0d991d320d5a679d0ed60880c56a6cb849e2d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907085"
---
# <a name="material-handling-equipment-interface-mhax"></a>Interface de l’équipement de manutention du matériel (MHAX)

[!include [banner](../../includes/banner.md)]

Vous pouvez utiliser *l’interface d’équipement de manutention de matériel* (MHAX) pour connecter des systèmes de manutention physique (MH) externes à un entrepôt géré par la gestion avancée des entrepôts (WMS) dans Microsoft Dynamics 365 Supply Chain Management. L’interface entre les systèmes WMS et MH se compose de deux files d’attente : une pour les événements sortants (WMS vers MH) et une pour les événements entrants (MH vers WMS). Le système WMS génère des événements sortants basés sur des lignes de travail créées lors de divers processus de création et d’exécution de travaux. Le système MH interroge ensuite régulièrement le système WMS à la recherche de nouveaux événements et traite les réponses. Une fois que le système MH a fini de traiter les événements conformément aux instructions de travail, il envoie des événements entrants, tels que l’achèvement de la ligne de travail et le prélèvement court.

L’illustration suivante montre les différents éléments et l’ordre dans lequel les processus se produisent lorsque vous utilisez l’intégration MHAX.

![Composants et interactions MHAX.](media/mhax-components.png "Composants et interactions MHAX")

Voici une explication des interactions présentées dans l’illustration précédente :

1. Lors de la création ou de l’exécution du travail, des événements sortants sont créés dans la file d’attente sortante.
2. L’équipement MH se connecte au service d’équipement MH, interroge les nouveaux événements qui le concernent et traite ces événements.
3. Lorsque l’équipement MH est prêt à faire un rapport, il se reconnecte au service et soumet les événements entrants. Ces événements sont immédiatement traités par le processeur de file d’attente.
4. En fonction des données d’événements entrants, le processeur de file d’attente peut exécuter le travail existant, le modifier ou en créer un nouveau.

## <a name="turn-on-the-mhax-feature"></a>Activer la fonctionnalité MHAX

Avant de pouvoir utiliser la fonction MHAX, vous devez activer à la fois sa fonction et sa clé de configuration.

1. Accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.
2. Dans l’espace de travail **[Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)**, activez la fonctionnalité nommée *Interface d’équipement de manutention du matériel*.
3. Mettez votre système en mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
4. Accédez à **Administration système \> Paramétrage \> Configuration des licences**.
5. Développer **Échanger \> Gestion des entrepôts et du transport**, puis cochez la case **Interface d’équipement de manutention du matériel**.
6. Désactiver le mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

## <a name="set-mhax-parameters"></a>Définition des paramètres MHAX

Vous devez définir quelques paramètres généraux sur la page **Paramètres d’interface de l’équipement de manutention du matériel** pour configurer la fonctionnalité.

1. Aller à **Interface d’équipement de manutention du matériel \> Configurer \> Paramètres d’interface de l’équipement de manutention du matériel**.
2. Dans l’onglet **Général**, définissez les champs suivantes :

    - **Identifiant utilisateur** – Sélectionnez un collaborateur. Ce collaborateur sera utilisé pour exécuter toutes les opérations de travail (prélèvements et mises) qui sont traitées via la file d’attente entrante.
    - **Activer l’ID de message entrant** – Lorsque cette option est définie sur *Oui*, si un ID de message entrant en double est reçu, le message sera rejeté et un message d’erreur indiquera que le message existe déjà. Lorsque cette option est définie sur *Non*, les ID de messages entrants en double seront autorisés.

3. Sur l’onglet **Séquences de numéros**, sélectionnez les séquences de numéros à l’échelle du système à utiliser pour générer des ID uniques pour les éléments de file d’attente entrante, les éléments de file d’attente sortante et les paires de lignes de travail.

## <a name="outbound-events"></a>Événements sortants

À des moments spécifiques lors de la création ou de l’exécution du travail, le système détermine s’il doit générer des événements sortants à envoyer au système MH. Si un abonnement est configuré pour un point spécifique pendant le traitement de l’entrepôt, le système génère l’événement en fonction de la configuration de l’abonnement.

### <a name="structure-of-outbound-events"></a>Structure des événements sortants

Chaque événement sortant est identifié de manière unique par un ID de file d’attente sortante. Le type de transaction sortante détermine le type de l’événement. L’entrepôt et l’ID de l’abonnement qui a généré l’événement sont également enregistrés sur l’événement.

Pour transporter des données vers le système MH, l’événement sortant contient 10 champs pour les données (**données01** à **données10**). Ces champs de données ont un mappage un à un (1:1) avec les champs de base de données existants. Plus précisément, ils sont extraits des champs de la ligne de travail et des tables d’en-tête de travail. Les champs peuvent être librement sélectionnés. Vous les configurez lorsque vous créez l’abonnement.

Outre les 10 champs de données qui ont un mappage 1:1 avec les champs de base de données existants, l’événement peut contenir un champ de données supplémentaire appelé *charge utile*. Le contenu de ce champ est généré par un code X++ personnalisé appelé *générateur de charge utile*. Tout générateur de charge utile qui doit être utilisé est configuré dans l’abonnement.

Pour garantir que le système MH ne reçoit chaque ID de file d’attente sortante qu’une seule fois, un champ de statut est utilisé pour spécifier si un événement est prêt à être envoyé au système externe ou s’il a déjà été envoyé.

### <a name="outbound-queue-subscriptions"></a>Abonnements aux files d’attente sortantes

Avant de générer des événements, un abonnement doit être configuré pour indiquer à la fonction MHAX si et comment générer des événements. Les événements générés sont marqués par l’identificateur d’abonnement. Par conséquent, plusieurs systèmes MH peuvent se connecter au même système WMS mais garder leurs événements séparés. Lorsque le service MHAX est interrogé pour de nouveaux événements, un abonnement est l’une des options disponibles pour récupérer les événements.

Pour créer un abonnement, accédez à **Interface d’équipement de manutention de matériel \> Configurer \> Abonnements**. Pour chaque abonnement, les paramètres suivants sont disponibles :

- **ID d’abonnement** – Un nom unique qui identifie l’abonnement.
- **Description** – Description libre de l’abonnement.
- **Entrepôt** – Les entrepôts spécifiques par lesquels les événements doivent être filtrés.
- **Type de transaction sortante** – Type d’événements que l’abonnement doit contenir.
- **Générateur de charge utile** – Une extension de code facultative qui peut entrer des informations supplémentaires dans le champ **Charge utile** de l’événement sortant.

Une requête peut être associée à chaque abonnement. Cette requête filtre les lignes de travail et les en-têtes pour limiter davantage le travail qui utilisera l’abonnement pour générer des événements. Pour ajouter une requête à un abonnement, cochez la case **Exécuter la requête** pour l’abonnement concerné sur la page **Abonnements**, puis sélectionnez **Modifier la requête** dans le volet Actions. L’éditeur de requête standard de Supply Chain Management apparaît.

De plus, l’abonnement comprend une *carte d’abonnement* qui mappe les champs de l’en-tête de travail ou de la ligne de travail à tout ou partie des 10 champs de données libres de l’événement sortant, selon les besoins. Pour renvoyer des informations au service MHAX, vous incluez généralement l’ID d’enregistrement de ligne de travail ou *l’ID de paire de lignes de travail*. (L’ID de paire de lignes de travail est une nouvelle propriété qui permet au système d’utiliser une seule commande de retour pour traiter les lignes de prélèvement et de placement.) Les champs restants dépendent du cas d’utilisation. Quelques exemples sont fournis plus loin dans cet article.

Pour configurer une carte d’abonnement, sélectionnez l’abonnement correspondant sur la page **Abonnements**, puis **Carte d’abonnement** dans le volet Actions. Dans la boîte de dialogue **Carte d’abonnement** qui apparaît, vous pouvez affecter une table et un champ pour chaque champ de données disponible selon vos besoins.

### <a name="outbound-event-types"></a>Types d’événements sortants

Cette section décrit les différents types d’événements disponibles. (Les types d’événements sont également appelés *types de transaction*.) Il explique également quand chaque type d’événement est créé dans le système WMS.

#### <a name="work-creation-events"></a>Événements de création de travail

Les événements de création de travail sont créés une fois que le travail est généré par l’application. Ce comportement s’applique à la plupart des types de processus de création de travaux, notamment à la création de travaux de prélèvement et de réapprovisionnement. En général, si le travail est créé dans un état *Ouvert*, qui indique que le travail est prêt à être exécuté par un collaborateur, un événement de création de travail sera généré. En outre, des événements de création de travail seront générés pour le travail de mouvement de base (pas le mouvement par travail de modèle), même si ce travail n’est pas créé en tant que travail ouvert.

Une exception notable à ce comportement est le travail de comptage de cycles, qui n’est actuellement pas pris en charge. Les inventaires de stock dans le système MH sont hors du champ d’application de MHAX, et les résultats des comptages doivent être importés dans un journal d’inventaire.

Une fois le travail créé, le service MHAX traite les lignes de travail générées et attribue un ID de paire de lignes de travail à toutes les lignes de travail générées pour chaque en-tête de travail. L’objectif est de regrouper toutes les lignes de travail de prélèvement avec les rangements successifs sous un ID de paire de lignes de travail. (Les groupes correspondent à des paires de prélèvement/rangement dans des modèles de travail.) De cette manière, un seul ID peut être utilisé pour signaler l’achèvement du travail pour toutes les lignes de prélèvement et de placement associées. Le processus de regroupement commence par la première ligne, puis se poursuit avec le même ID jusqu’à ce qu’il rencontre une paire successive de lignes de travail rangement/prélèvement. L’ID en cours d’exécution est attribué à la ligne de rangement de cette paire. Un nouvel ID qu’il a ensuite utilisé pour la ligne de sélection de la paire. Ce processus se poursuit jusqu’à ce qu’il ait traité toutes les lignes appartenant à l’en-tête de travail.

En tant que particularité des événements de création de travail, si l’option **Vague bloquée** est définie sur *Oui* sur l’en-tête de travail, les événements générés auront un statut de *Bloqué* au lieu du statut habituel de *Prêt* qui est utilisé pour les envoyer au système MH. L’indicateur **Vague bloquée** sur l’en-tête de travail indique que l’en-tête de travail n’est pas encore prêt à être exécuté, peut-être en raison d’un travail de réapprovisionnement inachevé. Quand l’indicateur **Vague bloquée** est effacé, les événements qui ont déjà été générés sont débloqués et peuvent être récupérés par le système MH dans la file d’attente.

#### <a name="work-initiation-events"></a>Événements de lancement de travail

Les événements de lancement du travail sont déclenchés lorsque le statut du travail passe de *Ouvert* à *En cours* pendant la mise à jour du travail.

#### <a name="work-completion-events"></a>Événements d’achèvement de travail

Les événements d’achèvement du travail sont déclenchés lorsque le statut du travail passe de *En cours* à *Clôturé* pendant la mise à jour du travail.

#### <a name="work-cancellation-events"></a>Événements d’annulation de travail

Les événements d’annulation du travail sont déclenchés lorsque le statut du travail passe de tous les statuts sauf *d’Annulé* à *Annulé* pendant la mise à jour du travail. En outre, tous les autres événements liés à l’en-tête de travail sont supprimés de la file d’attente pour tous les abonnements. De cette manière, les systèmes externes sont empêchés de traiter des événements qui ne sont pas nécessaires.

#### <a name="pickput-completion-events"></a>Événements d’achèvement Prélèvement/Rangement

Les événements d’achèvement Prélèvement/Rangement sont déclenchés lorsque le statut Prélèvement/Rangement passe de *En cours* à *Clôturé* pendant la mise à jour de la ligne du travail.

### <a name="monitor-the-outbound-queue"></a>Surveiller la file d’attente sortante

Pour consulter votre file d’attente sortante, accédez à **Interface d’équipement de manutention de matériel \> Commun \> File d’attente sortante**. La page **File d’attente sortante** répertorie chaque élément de file d’attente sortant et son statut. Sélectionnez un élément de file d’attente pour afficher ses détails. Ces détails incluent le type de transaction de l’article, l’abonnement qu’il a utilisé et les valeurs de chaque champ de données (**données01** à **données10**) et la charge utile.

### <a name="clean-up-the-outbound-queue"></a>Nettoyez la file d’attente sortante

Finalement, votre file d’attente sortante commencera à se remplir d’éléments de file d’attente qui ont déjà été envoyés. Pour supprimer ces éléments, accédez à **Interface d’équipement de manutention de matériel \> Tâches périodiques \> Nettoyer \> Nettoyage de la file d’attente sortante**.

## <a name="inbound-events"></a>Événements entrants

Cette section décrit les différents types d’événements entrants que le système MH peut rapporter au système WMS. Il explique également que les données doivent être fournies par le système MH et ce que fait chaque événement entrant dans le système WMS.

### <a name="structure-of-inbound-events"></a>Structure des événements entrants

Lorsqu’un événement entrant est soumis, le système externe doit fournir le type de transaction entrante avec jusqu’à 10 paramètres (**données01** à **données10**). Une validation facultative peut garantir que le service MHAX n’a pas reçu le même événement entrant plus d’une fois. Pour activer cette validation, chaque événement entrant doit avoir un ID de message unique. Si un ID de message en double est reçu et si l’option **Activer l’ID de message entrant** est définie sur *Oui* sur la page **Paramètres d’interface de l’équipement de manutention du matériel**, le message sera rejeté. Un message d’erreur indiquera que le message existe déjà.

En plus des champs de données entrantes, le système attribue un ID de file d’attente entrante unique à l’événement.

### <a name="inbound-event-types"></a>Types d’événements entrants

Cette section décrit les types d’événements entrants (types de transaction) pris en charge et les données qui doivent être fournies pour que les événements soient traités.

#### <a name="work-confirm-events"></a>Événements de confirmation de travail

Les événements de confirmation de travail nécessitent que les champs de données entrantes incluent les informations suivantes :

- **données01**– L’ID de paire de lignes de travail.
- **données02** – L’ID d’enregistrement de ligne de travail (`RecId` évaluer).

    > [!NOTE]
    > *Soit* le champ **données01** *soit* le champs **données02** doit être présent.

- **données03** – L’ID de contenant à choisir.
- **données04** – ID de contenant cible de la tête de travail.

Si l’ID de paire de lignes de travail est fourni, toutes les lignes de travail de prélèvement, de placement ou personnalisées qui sont marquées par l’ID de paire de lignes de travail et dont le statut est *Ouvert* ou *En cours*, sont exécutés séquentiellement. Si un ID d’enregistrement de ligne de travail (`RecId` value) est fournie, la ligne de travail doit être une ligne de travail de prélèvement, de mise en vente ou personnalisée dont le statut est *Ouvert* ou *En cours*.

Choisir des lignes de prélèvement à partir d’emplacements contrôlés par le contenant nécessite que **données03** spécifie le contenant à partir de laquelle vous devez choisir, que les lignes soient marquées par l’ID d’enregistrement de ligne de travail ou l’ID de paire de lignes de travail. Le champ **données04** doit spécifier le contenant cible de la tête de travail pour le prélèvement.

Les lignes de rangement n’acceptent pas plus d’informations. Ils sont exécutés uniquement en fonction de l’emplacement de la ligne de travail actuelle et du contenant cible du travail. Si le rangement doit être effectuée à un emplacement différent, modifiez l’emplacement de la ligne de travail comme décrit dans la section [Ignorer les événements](#override-events) plus loin dans cet article.

Les lignes de travail personnalisées ne nécessitent ni ne prennent en charge aucune information supplémentaire dans l’événement entrant.

#### <a name="short-pick-events"></a>Événements de prélèvement courts

Les événements de prélèvement courts nécessitent que les champs de données entrantes incluent les informations suivantes :

- **données02** – L’ID d’enregistrement de travail (`RecId` évaluer).
- **données03** – L’ID de contenant à choisir.
- **données04** – Quantité à prélever.
- **données05** – Code d’exception de prélèvement courte.
- **données06** – ID de contenant cible de la tête de travail.

> [!NOTE]
> Le champ **données01** n’est pas utilisé pour les événements de sélection courte.

Cet événement ressemble à l’événement de confirmation de travail, mais il s’applique uniquement aux lignes de prélèvement.

#### <a name="override-events"></a><a id="override-events"></a>Événements de remplacement

Les événements de remplacement nécessitent que les champs de données entrantes incluent les informations suivantes :

- **données01** – L’ID d’enregistrement de travail (`RecId` évaluer).
- **données02** - Le nouvel identifiant d’emplacement.

La ligne de travail doit avoir un statut soit *Ouvert* soit *En cours* et le nouvel emplacement doit exister.

#### <a name="license-plate-receipt-events"></a>Événements de réception de contenant

Les événements de contenant nécessitent que les champs de données entrantes incluent les informations suivantes :

- **données01** – L’ID de contenant entrant à recevoir.

Le système effectue une opération de réception de contenant, en fonction du contenant transmise comme valeur du champ **données01**.

### <a name="monitor-the-inbound-queue"></a>Surveiller la file d’attente entrante

Pour consulter votre file d’attente entrante, accédez à **Interface d’équipement de manutention de matériel \> Commun \> File d’attente entrante**. La page **File d’attente entrante** répertorie chaque élément de file d’attente entrant et son statut. Sélectionnez un élément de file d’attente pour afficher ses détails. Ces détails incluent le type de transaction de l’article, l’ID de message et les valeurs de chaque champ de données (**données01** à **données10**).

Si une erreur ou un autre type d’élément de journal s’est produit lors du traitement des événements entrants, vous pouvez inspecter le journal en sélectionnant **Journal des erreurs** dans le volet Actions.

### <a name="inbound-event-processing"></a>Traitement d’événement entrante

Les événements entrants sont d’abord écrits dans la base de données, puis exécutés immédiatement (de manière synchrone). Si une erreur se produit pendant le traitement, l’événement est toujours écrit dans la file d’attente, mais le statut est défini sur *Erroné*. Le service MHAX renvoie un message d’erreur au système MH et stocke le journal des erreurs dans l’enregistrement des événements entrants pour une enquête ultérieure.

Événements dont le statut est *Erroné* peut être retraité plus tard si la condition d’erreur est corrigée. Pour les traiter à nouveau, exécutez l’une des étapes ci-dessous :

- Accédez à **Interface d’équipement de manutention de matériel \> Commun \> File d’attente entrante**. Sélectionnez la file d’attente entrante appropriée, puis sélectionnez **Retraiter** dans le volet Actions.
- Accédez à **Interface d’équipement de manutention de matériel \> Commun \> Retraiter la file d’attente entrante erronée**. Une boîte de dialogue de traitement par lots standard apparaît. Là, vous pouvez configurer un filtre d’enregistrement et planifier ou exécuter un traitement par lots pour retraiter la file d’attente.

Toutes les opérations de travail (prélèvements et rangements) sont exécutées en utilisant le collaborateur sélectionné dans le champ **Identifiant utilisateur** sur la page **Paramètres d’interface de l’équipement de manutention de matériel**.

### <a name="clean-up-the-inbound-queue"></a>Nettoyez la file d’attente entrante

Finalement, votre file d’attente entrante commencera à se remplir d’éléments de file d’attente qui ont déjà été traités. Pour supprimer ces éléments, accédez à **Interface d’équipement de manutention de matériel \> Tâches périodiques \> Nettoyer \> Nettoyage de la file d’attente entrante**.

## <a name="get-a-quick-overview-by-using-the-queue-manager"></a>Obtenez un aperçu rapide en utilisant le gestionnaire de files d’attente

Pour obtenir un aperçu rapide de toutes les activités liées à vos files d’attente entrantes et sortantes, accédez à **Interface d’équipement de manutention de matériel \> Espaces de travail \> Gestionnaire de file d’attente**. La page **Gestionnaire de file d’attente** fournit un ensemble d’onglets et de vignettes que vous pouvez utiliser pour surveiller et explorer vos files d’attente. Il fournit également des liens utiles vers la plupart des autres pages mentionnées dans cet article.

## <a name="connect-to-the-mhax-service"></a>Connecter au service MHAX

MHAX est implémenté en tant que service personnalisé. Par conséquent, il est accessible via des appels SOAP et REST. Voici les adresses des points de terminaison SOAP et REST :

- **SOAP :** `https://base_environment_URL/soap/services/WMHEServices`
- **REST :** `https://base_environment_URL/api/services/WMHEServices/WMHEService`

## <a name="retrieve-messages-from-the-outbound-queue"></a>Récupérer les messages de la file d’attente sortante

Pour récupérer les messages de la file d’attente sortante, utilisez l’une des méthodes suivantes :

- Utilisation `readOutboundSubscriptionQueue` pour récupérer les événements en fonction de l’ID d’abonnement.
- Utilisation `readOutboundWarehouseQueue` pour récupérer les événements en fonction du type d’événement et de l’ID de l’entrepôt sur plusieurs abonnements.
