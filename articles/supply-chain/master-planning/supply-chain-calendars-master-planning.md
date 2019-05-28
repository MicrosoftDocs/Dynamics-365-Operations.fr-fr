---
title: Calendriers et planification
description: Cette rubrique offre un aperçu des calendriers de chaîne d'approvisionnement et de la manière dont ils ont un impact sur la planification.
author: t-benebo
manager: AnnBe
ms.date: 05/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: t-benebo
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 266eec2bb870be270b7796b35903a402e014c67c
ms.sourcegitcommit: 1f211ac6bd384fd8a2b5352104baf264d88f39b0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538724"
---
# <a name="calendars-and-master-planning"></a>Calendriers et planification

[!include [banner](../includes/banner.md)]

Cette rubrique offre un aperçu des calendriers de chaîne d'approvisionnement et de la manière dont ils ont un impact sur la planification.  Les différents calendriers utilisés dans le moteur de planification sont présentés, notamment la manière dont ils ont un impact sur les dates d'expédition et de réception dans les ordres prévisionnels. Pour finir, des recommandations concernant l'affectation, l'utilisation et la mise à jour des calendriers sont données.

## <a name="definition-of-a-calendar"></a>Définition d'un calendrier

Vous pouvez définir un calendrier à utiliser dans votre organisation sur la page dans **Administration d'organisation > Paramétrage > Calendriers > Calendriers**. 

Chaque entrée de date dans un calendrier peut avoir un des statuts suivants : **Ouvert** ou **Fermé** ou **Calendrier de base**. Cela est indiqué dans la colonne **Contrôle** de la page **Temps de travail**. Pour chaque date : 
- **Ouvert** - Indique que le travail est effectué le jour sélectionné. Le calendrier est mis à jour en fonction du modèle de temps de travail.
- **Fermé** - Indique que le travail n'est pas effectué le jour sélectionné. 
- **Calendrier de base** - Indique que la date spécifique héritera des temps de travail et des statuts Ouvert/Fermé du calendrier de base. Par conséquent, lorsque le calendrier de base est mis à jour, le calendrier sélectionné héritera de ses durées d'opération. 

Pour toutes les dates non ouvrables, la case à cocher **Clôturé pour prélèvement** est automatiquement affectée. Pour les dates dont le statut est défini sur Ouvert, vous pouvez sélectionner manuellement l'option **Clôturé pour prélèvement**. Cela indique que le travail est effectué en temps et en heure, mais que l'expédition n'est pas encore effectuée. 

## <a name="calendars-that-affect-master-planning"></a>Calendriers ayant un impact sur la planification

### <a name="calendar-for-a-coverage-group"></a>Calendrier pour un groupe de couverture
Un groupe de couverture indique un ensemble de paramètres communs utilisés pour le réapprovisionnement des articles qui appartiennent au groupe de couverture donné. 

Pour ajouter un calendrier à un groupe de couverture, accédez à **Planification > Paramétrage > Couverture > Groupes de couverture**. Recherchez le groupe de couverture auquel vous souhaitez attribuer le calendrier, puis sélectionnez-le sur le champ **Calendrier**.

Le groupe de couverture peut être affecté aux différentes pages : 
    - Sur la page **Détails des produits lancés** d'un article. Pour afficher le groupe de couverture pour un article, **Gestion des informations de produit > Produits > Produits lancés** et sélectionnez l'article pour accéder à la page **Détails des produits lancés**. Vous pouvez afficher le groupe de couverture de l'article sous l'organisateur **Plan**.
    - Sur la page **Couverture de l'article**. Sur la page des détails des produits lancés, cliquez sur **Couverture de l'article** pour accéder à la page de couverture de l'article. Dans l'onglet Vue d'ensemble, vous pouvez voir différents paramètres pour le réapprovisionnement en fonction du site, de l'entrepôt et des dimensions de produit. Le groupe de couverture pour chaque article est hérité du groupe de couverture sur la page **Détails des produits lancés**. Il peut être remplacé via **Utiliser des paramètres spécifiques** ou **Remplacer les paramètres de groupe** sous l'onglet **Général**.
    - Sur la page **Paramètres de planification**. Si un article n'a pas de groupe de couverture défini sur les pages précédentes, la planification tiendra compte du groupe de couverture général défini sur les paramètres de planification. Cela est défini dans **Planification > Paramétrage > Paramètres de planification** dans le champ **Groupe de couverture général**. 

### <a name="calendar-for-a-vendor"></a>Calendrier pour un fournisseur
Pour indiquer les jours ouvrés d'un fournisseur, vous pouvez affecter un calendrier d'achat au fournisseur sur la page **Valeurs par défaut des commandes fournisseur** pour un fournisseur. 

Pour définir un calendrier pour un fournisseur, vous devez créer le calendrier dans **Administration d'organisation > Calendriers > Calendriers**. Lorsque le calendrier est créé, vous devez l'affecter au fournisseur. Accédez à **Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs** et sélectionnez le fournisseur auquel vous souhaitez affecter le calendrier. Puis, sur la page du fournisseur sous l'organisateur **Valeurs par défaut des commandes fournisseur**, affectez le nouveau calendrier d'achat à l'aide du menu déroulant. 

Le calendrier pour un fournisseur indique les jours pendant lesquels ils acceptent la validation de la commande fournisseur et les dates de livraison des commandes à votre entreprise. Par conséquent, les dates de commande pour les commandes fournisseur pour le prestataire avec un calendrier d'achat seront des dates au statut défini comme Ouvert dans le calendrier. Les dates de livraison pour ces commandes seront également en jours ouvrés, et auront ainsi un impact sur le délai de l'article acheté. 

#### <a name="define-the-lead-time-for-a-purchased-item"></a>Définir le délai pour un article acheté

Pour préciser le délai de l'achat (et si seuls des jours ouvrables doivent être pris en compte) d'un article, vous devez accéder à la page des paramètres de commande par défaut pour le produit sous **Gestion des informations des produits > Produits > Produits lancés** et sélectionner **Paramètres de commande par défaut**. 

> [!Note]
> Les **Jours ouvrés** qui s'affichent sous le délai de l'achat correspondent aux jours ouvrés du fournisseur. Par exemple, un calendrier pour livraison uniquement les mardis sous un délai de 10 jours et la case des jours ouvrés sélectionnée indique que la livraison de l'article nécessiterait 10 semaines (10 mardis).
Ainsi, dans la plupart des cas, il n'est pas recommandé de sélectionner des jours ouvrés pour les délais d'exécution de la commande fournisseur.

#### <a name="define-lead-times-from-the-trade-agreements-page"></a>Définir les délais d'exécution depuis la page des accords commerciaux

La planification peut être définie de telle sorte qu'elle inclut tous les accords commerciaux pour les fournisseurs. Les accords commerciaux renvoient à des contrats de pratiques tarifaires ou de remises conclus pour un ou plusieurs clients ou fournisseurs pour la vente ou l'achat d'un seul produit ou de plusieurs produits. Accédez à **Planification > Paramétrage > Paramètres de planification** et sur l'onglet **Ordres prévisionnels**, sélectionnez **Rechercher des accords commerciaux** pour inclure les accords commerciaux lors de la planification. La planification peut sélectionner le fournisseur avec le **Délai minimum** ou le **Prix unitaire minimal**.

### <a name="calendar-for-a-warehouse"></a>Calendrier pour un entrepôt
Vous pouvez attribuer un calendrier à un entrepôt pour indiquer les dates ouvertes pour réceptionner et envoyer les marchandises. Si aucun calendrier n'a été affecté à un entrepôt, on suppose que ce dernier est ouvert tous les jours. 

> [!Note]
> Le fait d'affecter un calendrier à un entrepôt de transit n'a pas d'impact. Les entrepôts de transit sont utilisés en soutien aux ordres de transfert. Les dates de réception ou d'expédition applicables pour les commandes sont définies par les jours ouvrés au sein de l'entrepôt « de départ » et celui « arrivée », et le calendrier du mode de livraison sélectionné.

#### <a name="closed-for-pickup-policy"></a>Stratégie « Fermé pour prélèvement »
Pour indiquer qu'un entrepôt est ouvert pour réception, mais pas pour le prélèvement, vous pouvez utiliser la **Stratégie « Fermé pour prélèvement »** dans le calendrier d'entrepôt. Cela vaut également pour les prélèvements des clients. 

### <a name="transport-calendar"></a>Calendrier de transport 
Pour indiquer les dates disponibles pour l'expédition des ordres de transfert depuis un **Entrepôt de départ**, vous pouvez affecter un **Calendrier de transport**. Vous pouvez paramétrer un calendrier de transport par mode de livraison, ou par mode de livraison et entrepôt de départ. Le calendrier de transport est défini dans **Vente et marketing > Paramétrage > Distribution > Modes de livraison**. Sélectionnez un mode de livraison et cliquez sur le bouton **Calendrier de transport**.

Une ligne peut être créée pour chaque entrepôt et mode de livraison, où le calendrier est ajouté dans la colonne **Calendrier de transport**. Elle spécifie le calendrier de transport utilisé lors de l'envoi des marchandises de l'entrepôt de départ via le mode de livraison indiqué. Pour appliquer un calendrier de transport à toutes les expéditions via un mode de livraison donné, une ligne peut être créée sans spécifier l'entrepôt.  Elle affecte toutes les expéditions à l'aide du mode de livraison donné, indépendamment de l'entrepôt. 

Si aucun calendrier de transport n'est affecté, on suppose qu'il est ouvert tous les jours pour transport.

### <a name="calendar-for-a-customer"></a>Calendrier pour un client
Pour indiquer les dates auxquelles un client peut accepter les livraisons, vous pouvez affecter un calendrier de réception au client. Si aucun calendrier n'est affecté à un client, on suppose que le client peut recevoir des commandes tous les jours. Cela affecte la date de réception aux lignes de commande client. Si vous sélectionnez une date dans les lignes de commande client non définie sur « Ouvert » dans le calendrier client, le système vous indiquera que la date de réception n'est pas valide. 

Notez qu'il est possible de n'inclure qu'un calendrier par client. Si vous devez inclure un calendrier pour chaque adresse différente pour un client, vous pouvez créer un client par adresse, puis affecter son calendrier respectif. 

La date de réception demandée sur les lignes de commande client est affectée par le calendrier client et par la méthode de contrôle de la date de livraison. Découvrez-en davantage sur la manière de calculer la date de livraison la plus proche dans [Promesse de commande.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/delivery-dates-available-promise-calculations).

### <a name="shipping-calendar-for-a-legal-entity"></a>Calendrier d'expédition pour une entité juridique
Pour indiquer les dates auxquelles une entité juridique peut expédier des marchandises, vous pouvez paramétrer un calendrier d'expédition sous **Administration de l'organisation > Organisations > Entités juridiques**. Sélectionnez l'entité juridique et ajoutez le calendrier dans l'onglet **Commerce extérieur et logistique** dans le champ **Calendrier d'expédition**. Le calendrier d'expédition sera considéré comme la source de valeurs par défaut pour tous les calendriers d'entrepôt dans l'entité juridique. 

## <a name="how-calendars-affect-dates-in-planning"></a>Comment les calendriers ont un impact sur les dates dans le cadre de la planification

### <a name="order-date-of-a-planned-purchase-order"></a>Date de commande d'une commande fournisseur prévisionnelle 
La date de commande dans une commande fournisseur prévisionnelle indique la date à laquelle la commande a été passée. Il s'agit d'une date définie sur statut Ouvert dans le calendrier du fournisseur et dans le calendrier du groupe de couverture. Parfois, les fournisseurs ont besoin de quelques jours de marge entre la réception de la commande fournisseur et leur capacité à envoyer les marchandises. Ces dates sont indiquées en jours de marge du fournisseur. Toutefois, si l'article acheté est affecté à un groupe de couverture avec des jours de marge, ces jours de marge remplacent les jours de marge du fournisseur.

### <a name="delivery-date-of-a-planned-purchase-order"></a>Date de livraison d'une commande fournisseur prévisionnelle
La date de réception d'un achat indique la date à laquelle vous allez recevoir les marchandises. Il s'agit d'une date dont le statut est Ouvert dans le calendrier. Le calendrier qui sera pris en compte pour indiquer quels jours les commandes fournisseurs peuvent être reçues est le suivant, dans l'ordre de la priorité la plus élevée à la priorité la plus basse : 
    1. Calendrier du fournisseur
    2. Calendrier pour un groupe de couverture
    3. Calendrier d'entrepôt pour l'entrepôt de réception

Notez que le calendrier de groupe de couverture peut être défini sur différentes pages et reste prioritaire dans l'ordre suivant :
    1. Groupe de couverture de l'article sur la page **Détails des produits lancés**
    2. Groupe de couverture de l'article sur la page **Couverture de l'article**
    3. Groupe de couverture de l'article par défaut dans **Paramètres de planification**

### <a name="shipping-date-of-a-planned-transfer-order"></a>Date d'expédition d'un ordre de transfert prévisionnel
Lors de la création d'un ordre de transfert entre deux entrepôts, la date d'expédition et la date de réception sont incluses en en-tête de l'ordre de transfert, ainsi que l'entrepôt « de départ » et l'entrepôt « d'arrivée ». La différence entre ces deux dates est le temps de transport prévu (en jours) entre les entrepôts.

La date d'expédition d'un ordre de transfert prévisionnel indique la date à laquelle les marchandises sont expédiées depuis l'entrepôt « de départ ». Les calendriers utilisés pour spécifier la date d'expédition disponibles sont répertoriés par ordre de priorité : 
    1. Calendrier de l'entrepôt « de départ »
    2. Le calendrier de groupe de couverture (voir la commande de secours pour ce calendrier ci-dessus) Si un calendrier d'entrepôt est défini, la date d'expédition reste une date ouverte dans le calendrier. Si aucun calendrier d'entrepôt n'est défini, le calendrier de groupe de couverture est nécessaire. 

### <a name="receipt-date-of-a-planned-transfer-order"></a>Date de réception d'un ordre de transfert prévisionnel
La date de réception d'un ordre de transfert indique la date à laquelle les marchandises sont reçues depuis l'entrepôt « d'arrivée ».

Les calendriers utilisés pour spécifier la date de réception sont répertoriés par ordre de priorité : 
    1. Calendrier pour un groupe de couverture 
    2. Calendrier d'entrepôt « d'arrivée » Si un calendrier de couverture est défini, la date de réception reste une date ouverte dans le calendrier. Si aucun calendrier de groupe de couverture n'est défini, le calendrier d'entrepôt est nécessaire. 

En recherchant les dates d'expédition et de réception pour le transfert prévisionnel, les marges établies par l'utilisateur pour l'expédition et la réception sont également prises en compte. 

## <a name="using-calendars-in-master-planning"></a>Utilisation des calendriers dans la planification

### <a name="assignment-of-scm-calendars"></a>Affectation des calendriers SCM
Il est important de définir les calendriers afin d'identifier les jours ouvrés de la société. La meilleure implémentation consiste à définir un calendrier pour chaque élément avec différents jours ouvrés. En d'autres termes, tous les calendriers externes (client, fournisseur) et tous les calendriers internes (entrepôt, groupe de couverture et mode de livraison) associés à la société.

### <a name="recommendation-on-warehouse-calendars"></a>Recommandation relatives aux calendriers d'entrepôt
Il est recommandé d'utiliser un calendrier par entrepôt pour inclure les modifications spécifiques affectant uniquement l'entrepôt. Par exemple, au moins deux entrepôts pourraient avoir les mêmes jours ouvrés, mais une différente stratégie de prélèvement. Dans ce cas, un calendrier pour chacun des entrepôts avec leur stratégie respective de prélèvement est la meilleure solution afin que le système intègre les meilleures dates pour les ordres d'achat prévisionnels, de transfert et de production. Si aucun calendrier d'entrepôt n'est défini, le calendrier d'entité juridique peut être utilisé comme source de valeurs par défaut pour le calendrier d'entrepôt. 

### <a name="recommendation-of-coverage-group-calendars"></a>Recommandation relative aux calendriers de groupe de couverture
Concernant le calendrier de groupe de couverture, il est important de tenir compte de celui qui a un comportement à remplacer concernant les dates de réception dans la planification. Ainsi, il est recommandé de l'utiliser avec précaution. Ainsi, il est utile si un réapprovisionnement doit être effectué certains jours de la semaine. 

### <a name="updating-scm-related-calendars"></a>Mise à jour des calendriers SCM
Même s'il est important que tous les calendriers associés soient attribués à leur place respective (fournisseur, client, entrepôt, mode de livraison ou groupe de couverture), leur mise à jour l'est tout autant dans la mesure où ils reflètent les modifications. Le système définit les dates de production, de transfert, d'achat et de commande client selon l'association des calendriers assignés. Préciser qui est responsable d'attribuer et de mettre à jour les calendriers dans ses zones respectives reste une bonne pratique. En cas de panne ou de tout autre changement inhabituel les jours ouvrés, il est essentiel de mettre à jour les calendriers en conséquence. Toutes les tâches qui dépendent des calendriers, telles que la planification et la programmation de la production, doivent être relancées lors de la mise à jour des calendriers. 
