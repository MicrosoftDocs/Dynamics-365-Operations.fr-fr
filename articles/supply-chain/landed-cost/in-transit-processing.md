---
title: Traitement de marchandises en transit
description: Cette rubrique décrit l’utilisation des commandes de marchandises en transit. Lorsqu’une commande ou un voyage est configuré pour utiliser le traitement des marchandises en transit, les marchandises peuvent être facturées avant d’avoir été reçues dans l’entrepôt pour consommation.
author: Weijiesa
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DeliveryTerms, InventLocation, InventPosting, ITMGoodsInTransitOrder, ITMTableListPage, ITMTable, ITMContainersListPage, ITMContainers, ITMFolioTableListPage, ITMFolioTable, ITMGoodsInTransitOrderEditLines, SysOperationTemplateForm, WHSRFMenuItem, WHSLocDirTable, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8df07c7c94cf64b0e4cf1def794270e176241b5f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694653"
---
# <a name="goods-in-transit-processing"></a>Traitement de marchandises en transit

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit l’utilisation des commandes de marchandises en transit. Ce type de commande n’est utilisé que par le module **Prix au débarquement**. Lorsqu’une commande ou un voyage est configuré pour utiliser le traitement des marchandises en transit, vous n’avez pas besoin d’attendre que les marchandises soient reçues en entrepôt pour les facturer. Au lieu de cela, les marchandises sont facturées lorsqu’elles quittent l’entrepôt ou le port d’origine du vendeur, et les coûts financiers sont comptabilisés au début du voyage. Cette fonctionnalité vous permet de prendre correctement possession du stock, car les marchandises deviennent souvent la propriété de votre organisation lorsqu’elles quittent le port d’expédition.

Lorsque des commandes de marchandises en transit sont utilisées, les articles mis à jour financièrement sont reçus dans un entrepôt intermédiaire appelé entrepôt de marchandises en transit. Les marchandises restent ensuite dans cet entrepôt jusqu’à ce qu’elles puissent être reçues à l’entrepôt de destination finale (c’est-à-dire l’entrepôt défini sur la ligne d’achat). Elles ne peuvent pas être supprimées manuellement.

Tant que les articles sont en transit, ils ne sont pas disponibles dans le stock et ne peuvent pas être prélevés du stock pour une livraison. Cependant, vous pouvez afficher le stock de marchandises en transit. Vous pouvez également utiliser les marchandises dans la planification. Dans ce cas, utilisez la date de livraison confirmée sur la ligne de commande fournisseur comme date prévue à laquelle le stock sera disponible à la consommation.

Les sections suivantes décrivent la configuration requise pour traiter le stock et les voyages à l’aide du concept et de la fonctionnalité des marchandises en transit.

## <a name="terms-of-delivery"></a>Conditions de livraison

Lorsque vous activez le module **Prix au débarquement**, l’entité de *conditions de livraison* standard est améliorée pour prendre en charge la fonction de marchandises en transit.

Quand l’option **Gestion des marchandises en transit** est définie sur *Oui* pour les conditions de livraison applicables, les marchandises sont placées dans l’entrepôt de marchandises en transit. Cette action est déclenchée uniquement si la réception de stock n’est pas traitée avant le traitement d’une facture. Lorsque les conditions de livraison d’une commande sont définies pour utiliser des marchandises en transit, les utilisateurs ne peuvent plus enregistrer un accusé de réception de marchandise pour la commande fournisseur. S’ils essaient, une erreur se produit. Le message d’erreur indique qu’ils doivent utiliser la fonctionnalité de marchandises en transit pour continuer.

Pour utiliser les informations sur les conditions de livraison des marchandises en transit, accédez à **Approvisionnement \> Configurer \> Distribution \> Conditions de livraison**. Le tableau suivant décrit les champs que le module **Prix au débarquement** ajoute à la page **Conditions de livraison** pour prendre en charge la fonctionnalité de marchandises en transit. Les deux champs sont sur le raccourci **Général**. Pour plus d’informations sur les autres champs de cette page, consultez [Conditions de livraison (formulaire)](/dynamicsax-2012//terms-of-delivery-form).

| Champ | Description |
|---|---|
| Port d’expédition obligatoire | Définissez cette option sur *Oui* si un port d’expédition est obligatoire lorsque les conditions de livraison s’appliquent. |
| Gestion des marchandises en transit | Définissez cette option sur *Oui* d’utiliser la gestion des marchandises en transit lorsque les conditions de livraison s’appliquent. |

## <a name="warehouses-for-goods-in-transit-and-under-delivery"></a>Entrepôts pour marchandises en transit et en sous-livraison

Lorsque vous activez le module **Prix au débarquement**, l’entité *entrepôts* standard est améliorée pour permettre la facturation des commandes fournisseur pendant que les marchandises se trouvent dans un entrepôt de marchandises en transit.

Le coût au débarquement ajoute deux nouveaux types d’entrepôts : *les marchandises en transit* et *sous livraison*. Les entrepôts des deux types peuvent être sélectionnés comme entrepôts par défaut. Le traitement réussi des commandes de marchandises en transit nécessite que l’entrepôt de marchandises en transit et l’entrepôt de sous-livraison soient configurés sur la page **Entrepôts**. Ensuite, pour chaque entrepôt par défaut qui sera utilisé avec le coût au débarquement et les marchandises en transit, l’entrepôt de marchandises en transit et l’entrepôt en sous-livraison doivent être sélectionnés pour les entrepôts disponibles de chaque type.

Le type d’entrepôt *marchandises en transit* sera associé à votre entrepôt de marchandises en transit, et cet entrepôt sera utilisé pour traiter les marchandises des commandes de marchandises en transit avant leur réception à l’entrepôt de destination finale. En général, un entrepôt de marchandises en transit suffit pour chaque site si Site et Entrepôt sont les seules dimensions de stock utilisées pour la gestion des stocks. Si la dimension de stock Emplacement est également utilisée, un entrepôt de marchandises en transit doit être configuré pour chaque combinaison d’un site et d’un entrepôt, afin que l’emplacement par défaut puisse également être spécifié.

Pour utiliser les paramètres de marchandises en transit pour vos entrepôts, accédez à **Gestion des stocks \> Configurer \> Décomposition du stock \> Entrepôts**. Le tableau suivant décrit les champs que le module **Prix au débarquement** ajoute à la page **Entrepôts** pour prendre en charge la fonctionnalité de marchandises en transit. Les deux champs s’affichent sur le raccourci **Général**. Pour plus d’informations sur les autres champs de la page, voir [Entrepôts (formulaire)](/dynamicsax-2012//warehouses-form).

| Champ | Description |
|---|---|
| Entrepôt des marchandises en transit | Identifiez l’entrepôt de marchandises en transit lié à l’entrepôt principal. |
| Entrepôt des livraisons incomplètes | Identifiez l’entrepôt de sous livraison lié à l’entrepôt principal. |

## <a name="posting-rules-for-landed-cost"></a>Règles de comptabilisation pour le coût au débarquement

Le coût au débarquement ajoute deux nouvelles règles de validation que vous pouvez configurer. Ces règles de comptabilisation sont utilisées pour enregistrer financièrement les montants des factures de commande fournisseur direct afin d’identifier la propriété des marchandises lorsqu’elles quittent le point d’origine. Ce processus remplace le concept de *marchandises reçues non facturées*, car les marchandises sont facturées avant leur réception. <!-- KFM: Add a link to the related scenario when available. -->

Pour travailler avec des profils de validation, accédez à **Gestion des stocks \> Configurer \> Validation \> Validation**. Sur l’onglet **Commande fournisseur**, les nouvelles règles de comptabilisation suivantes sont disponibles :

- **Coût au débarquement, marchandises en transit** – Spécifiez les règles d’enregistrement pour la gestion des marchandises en transit.
- **Coût au débarquement, régularisation des frais de coûts** – Spécifiez les règles de comptabilisation pour la constitution des comptes de facturation.

## <a name="goods-in-transit-orders"></a>Ordres des marchandises en transit

Vous pouvez consulter et gérer les commandes de marchandises en transit directement dans le module **Prix au débarquement**. Vous pouvez traiter les commandes de marchandises en transit directement à partir de la page **Marchandises en transit**. Vous pouvez également accéder au voyage associé aux commandes de marchandises en transit et traiter l’intégralité du voyage, du conteneur d’expédition ou du folio. Lorsque vous facturez un voyage et créez des commandes de marchandises en transit, une commande de marchandises en transit est créée pour chaque combinaison de dimensions de stock et de stock associée à la ligne de commande fournisseur.

Pour gérer les marchandises en transit, le coût au débarquement utilise une procédure en deux étapes :

1. Un article est reçu lorsqu’une facture de stock est traitée et affectée d’un statut de *En transit*.
1. La commande de marchandises en transit est traitée sur la page **Marchandises en transit**, puis reçu dans l’entrepôt spécifié sur la commande fournisseur. À ce stade, le statut devient *Reçu*.

Pour gérer les commandes de marchandises en transit, accédez à **Prix au débarquement \> Tâches périodiques \> Marchandises en transit**.

## <a name="receiving-stock-from-the-goods-in-transit-warehouse"></a>Réception du stock de l’entrepôt de marchandises en transit

Vous pouvez recevoir des marchandises d’une commande de marchandises en transit de plusieurs manières, selon la configuration de votre système.

### <a name="in-transit-receiving"></a>Réception en transit

Vous pouvez effectuer la réception en transit à partir de l’une des pages suivantes :

- Sur la page **Marchandises en transit**, sélectionnez la ligne, puis, dans le volet Actions, sélectionnez **Recevoir**.
- Sur la page **Tous les voyages**, sélectionnez ou ouvrez un voyage. Ensuite, dans le volet Actions, sur l’onglet **Gérer**, dans le groupe **Marchandises en transit**, sélectionnez **Recevoir les marchandises en transit**.
- Sur la page **Tous les conteneurs d’expédition**, sélectionnez ou ouvrez un conteneur d’expédition. Ensuite, dans le volet Actions, sur l’onglet **Gérer**, dans le groupe **Marchandises en transit**, sélectionnez **Recevoir les marchandises en transit**.
- Sur la page **Tous les folios**, sélectionnez ou ouvrez un folio. Ensuite, dans le volet Actions, sur l’onglet **Gérer**, dans le groupe **Marchandises en transit**, sélectionnez **Recevoir les marchandises en transit**.

> [!NOTE]
> La réception en transit est généralement utilisée dans les situations où les emplacements et le suivi des lots/séries ne sont pas utilisés.

### <a name="arrival-journal"></a>Journal des arrivées

Vous pouvez également recevoir des marchandises en créant un journal des arrivées. Vous pouvez créer un journal des arrivées directement à partir de la page de voyage. Les meilleures pratiques établies par votre organisation déterminent si le journal des arrivées est utilisé pour recevoir des marchandises.

1. Ouvrez le voyage, le conteneur ou le folio.
1. Dans le volet Actions, sous l’onglet **Gestion**, dans le groupe **Fonctions**, sélectionnez **Créer un journal des arrivées**.
1. Dans la boîte de dialogue **Créer un journal des arrivées**, définissez les valeurs suivantes :

    - **Initialiser la quantité** – Réglez cette option sur *Oui* pour définir la quantité à partir de la quantité en transit. Si cette option est définie sur *Non*, aucune quantité par défaut n’est définie à partir des lignes de marchandises en transit.
    - **Créer à partir de marchandises en transit** – Réglez cette option sur *Oui* pour prendre des quantités des lignes en transit sélectionnées pour le voyage, le conteneur ou le folio sélectionné.
    - **Créer à partir des lignes de commande** – Réglez cette option sur *Oui* pour définir la quantité par défaut dans le journal des arrivées à partir des lignes de commande fournisseur. La quantité par défaut dans le journal des arrivées peut être définie de cette manière uniquement si la quantité sur la ligne de commande correspond à la quantité sur la commande de marchandises en transit.

1. Traitez le journal des arrivées comme décrit dans [Enregistrer les réceptions d’articles avec un journal des arrivées d’articles](/dynamicsax-2012/appuser-itpro/register-item-receipts-with-an-item-arrival-journal).

> [!NOTE]
> Le journal des arrivées est généralement utilisé dans les situations où les emplacements et le suivi des lots/séries sont utilisés, mais la gestion des entrepôts n’est pas utilisée.
>
> Les emplacements de réception par défaut ne doivent pas être spécifiés sur les lignes de commande si un emplacement d’entrée en stock est spécifié dans le journal des arrivées.

## <a name="warehouse-management"></a>Gestion des entrepôts

Lorsque vous activez le module **Prix au débarquement**, plusieurs pages dans le module **Gestion d’entrepôt** sont modifiés afin que le traitement des commandes (en particulier, le traitement des marchandises en transit) puisse être effectué via le module **Prix au débarquement**. Cette section décrit les champs et les processus qui sont ajoutés dans le module **Gestion d’entrepôt**.

### <a name="mobile-device-menu-items"></a>Options de menu d’appareil mobile

Les marchandises peuvent être reçues à l’aide d’un appareil mobile, à condition que le menu de l’appareil mobile et le module **Gestion d’entrepôt** ont été mis en place pour recevoir des marchandises sur une commande de marchandises en transit. Cette section décrit la configuration associée à la réception des marchandises en transit.

Pour configurer des appareils mobiles pour le traitement des marchandises en transit, accédez à **Gestion d’entrepôt \> Configurer \> Appareil mobile \> Éléments du menu de l’appareil mobile**.

Le coût au débarquement ajoute les processus de création de travail suivants aux éléments de menu de l’appareil mobile pour prendre en charge le traitement des marchandises en transit :

- Réception de marchandises en transit
- Marchandises en transit réception et mise en stock des articles

Les paramètres de configuration de ces processus ressemblent aux paramètres des [processus de réception et de création des travaux de mise en stock des commandes fournisseur](/dynamicsax-2012/appuser-itpro/configure-mobile-devices-for-warehouse-work). Cependant, le processus *réception et mise en stock des articles de marchandises en transit* ajoute également le champ suivant.

- **Activer le conteneur d’expédition terminé** – Si cette option est définie sur *Oui*, lorsque le travail de mise en stock est terminé, l’application mobile Gestion des entrepôts fournira une option supplémentaire nommée **Conteneur d’expédition complet**. Lorsque cette option est sélectionnée, le collaborateur sera invité à confirmer que le conteneur est complet. À ce stade, tous les reçus courts seront traités comme une sous-transaction.

### <a name="location-directives"></a>Instructions d’emplacement

Le coût au débarquement ajoute un nouveau type d’ordre de travail nommé *Marchandises en transit* à la page **Directives de localisation**. Ce type d’ordre de travail doit être configuré de la même manière que les [types d’ordres de travail de commande fournisseur](/dynamicsax-2012/appuser-itpro/create-a-work-template).

### <a name="work-templates"></a>Modèles de travail

Cette section décrit les fonctionnalités que le module **Prix au débarquement** ajoute aux modèles de travail.

#### <a name="goods-in-transit-work-order-type"></a>Type d’ordre de travail Marchandises en transit

Le coût au débarquement ajoute un nouveau type d’ordre de travail nommé *Marchandises en transit* à la page **Modèles de travail**. Ce type d’ordre de travail doit être configuré de la même manière que les [Modèles de travail de commande fournisseur](/dynamicsax-2012/appuser-itpro/create-a-work-template).

#### <a name="work-header-breaks"></a>Décompositions de l’en-tête de travail

Modèles de travail qui ont un type d’ordre de travail de *Marchandises en transit* peut être configuré pour fractionner les en-têtes de travail. Dans la page **Modèles de travail**, suivez l’une des étapes suivantes :

- Sur l’onglet **Général** pour le modèle, définissez les maximums d’en-tête de travail. Ces maximums fonctionnent de la même manière que pour les modèles de travail de commande fournisseur. (Pour plus d’informations, voir les [modèles de travail de commande fournisseur](/dynamicsax-2012/appuser-itpro/create-a-work-template).)
- Utilisez le bouton **Pauses d’en-tête de travail** pour définir quand le système doit créer des en-têtes de travail, selon les champs utilisés pour le tri. Par exemple, pour créer un en-tête de travail pour chaque ID conteneur, sélectionnez **Modifier la requête** dans le volet Actions, puis ajoutez le champ **ID conteneur** à l’onglet **Tri** de l’éditeur de requêtes. Les champs ajoutés à l’onglet **Tri** sont disponibles pour la sélection comme *champs de regroupement*. Pour configurer vos champs de regroupement, sélectionnez **Pauses d’en-tête de travail** dans le volet Actions, puis, pour chaque champ que vous souhaitez utiliser comme champ de regroupement, cochez la case dans la colonne **Regrouper selon ce champ**.

Le prix au débarquement [crée une transaction en surplus](over-under-transactions.md) si la quantité enregistrée dépasse la quantité d’origine de la commande. Lorsqu’un en-tête de travail est terminé, le système met à jour le statut des transactions de stock pour la quantité de commande principale. Cependant, il met d’abord à jour la quantité liée à la transaction en surplus après l’achat complet du principal.

Si vous annulez un en-tête de travail pour une transaction en surplus qui a déjà été enregistrée, l’opération de dépassement est d’abord réduite de la quantité annulée. Une fois la transaction en surplus réduite à une quantité de 0 (zéro), l’enregistrement est supprimé et toute quantité supplémentaire n’est pas enregistrée par rapport à la quantité de commande principale.
