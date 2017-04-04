---
title: "Vue d&quot;ensemble des ventes au détail des périphériques"
description: "Cette rubrique explique les concepts associés à vendre des périphériques au détail. Elle décrit les différentes méthodes que les périphériques peuvent être connectés au point de vente (POS) et aux composants responsables de gérer la connexion avec le POS."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 268444
ms.assetid: 2ea93e43-8019-49a0-a7f8-325565ebc52d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 79a43c35691f16d773b88faad63c4ab79cb93f1f
ms.openlocfilehash: c6fb3922ba2c4b15f1043d0bcbac40ff2da9a469
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripherals-overview"></a>Vue d'ensemble des ventes au détail des périphériques

Cette rubrique explique les concepts associés à vendre des périphériques au détail. Elle décrit les différentes méthodes que les périphériques peuvent être connectés au point de vente (POS) et aux composants responsables de gérer la connexion avec le POS.

<a name="concepts"></a>Concepts
--------

### <a name="pos-registers"></a>Caisses enregistreuses de PDV

Chemin d'accès : Cliquez sur ** au détail et commerce ** &gt; ** canal paramétré ** &gt; ** la configuration ** &gt; ** registres **. Registre de (POS) du point de vente est une entité utilisée pour définir les caractéristiques d'une instance spécifique du PDV. Ces informations comprennent le profil matériel ou paramètrentes pour les périphériques au détail qui seront utilisés dans le Registre, le magasin que la caisse enregistreuse est mis en correspondance, et l'expérience visuelle de l'utilisateur qui signe dans à ce registre.

### <a name="devices"></a>Périphériques

Chemin d'accès : Cliquez sur ** au détail et commerce ** &gt; ** canal paramétré ** &gt; ** la configuration ** &gt; ** périphériques **. Un périphérique est une entité qui représente une instance physique d’un périphérique qui est mappé à une caisse enregistreuse de PDV. Lorsqu'un périphérique est créé, il a mis en correspondance avec un TPV. L’entité de périphérique assure le suivi des informations lorsqu’une caisse enregistreuse est activée, le type de client qui est utilisé et le package d’applications qui a été déployé sur un périphérique spécifique. Les unités peuvent être mis en correspondance avec les types d'application suivants : Retail Modern POS, PDV au détail de cloud, Retail Modern POS – Windows Phone, Retail Modern POS – Android, puis Retail Modern POS – uniquement.

### <a name="retail-modern-pos"></a>Retail Modern POS

Le Modern POS est le programme de PDV pour Microsoft Windows. Il peut être déployé sous Windows 10 systèmes d'exploitation (systèmes d'exploitation).

### <a name="cloud-pos"></a>Cloud POS

Le PDV de cloud est une version navigateur- basée du programme de Modern POS accessible dans un navigateur Web.

### <a name="modern-pos-for-ios"></a>Modern POS pour l'IOS

Le Modern POS pour l'(est une version IOS- basée du programme de Modern POS qui peut être déployé sur les périphériques d'uniquement.

### <a name="modern-pos-for-android"></a>Modern POS pour Android

Le Modern POS pour Android est une version Android-basée du programme de Modern POS qui peut être déployé sur les périphériques androïdes.

### <a name="pos-peripherals"></a>Périphériques de PDV

Les périphériques POS sont des périphériques qui sont explicitement pris en charge pour les fonctions du PDV. Ces périphériques sont généralement divisés en classes spécifiques. Pour plus d'informations sur ces classes, voir la section « classes de périphérique » dans cette rubrique.

### <a name="hardware-station"></a>Station matérielle

Chemin d'accès : Cliquez sur ** au détail et commerce ** &gt; ** canaux ** &gt; ** magasins de vente au détail ** &gt; ** tous les magasins de vente au détail **. Sélectionnez un magasin, puis cliquez sur l'organisateur **Stations matérielles**. ** Station matérielle ** le paramètre est un paramètre niveau du canal utilisé pour définir des instances où la logique périphérique au détail est déployée. Ce paramètre au niveau de le canal utilisé pour déterminer les spécifications de la station de matières. Il permet également de répertorier les stations matérielles disponibles pour une instance de Modern POS dans un magasin donné. La station matérielle est intégrée dans le programme de Modern POS pour Windows. La station matérielle peut également être déployé indépendamment comme un programme autonome de (IIS) de services Microsoft Internet Microsoft. Dans ce cas, elle peut accéder via un réseau.

### <a name="hardware-profile"></a>Profil matériel

Chemin d'accès : Cliquez sur ** au détail et commerce ** &gt; ** canal paramétré ** &gt; ** la configuration ** &gt; ** le POS profils ** &gt; ** des profils matériels **. Le profil matériel est une liste des périphériques configurés pour un TPV ou une station matérielle. Le profil matériel peut être mis en correspondance directement à un TPV ou une autre station de matières.

## <a name="devices-classes"></a>Classes de périphériques
Les périphériques POS sont généralement divisés en classes. Cette section décrit et offre une vue d'ensemble des périphériques que le Modern POS prend en charge.

### <a name="printer"></a>Imprimante

Les imprimantes incluent les imprimantes traditionnelles de réception du PDV et les imprimantes sur une page. Imprimante sont prises en charge via l'objet liant et intégrant des interfaces du de Retail POS (enregistreuse et) de Microsoft Windows pilote. Arrondi à deux imprimantes peuvent être utilisées en même temps. Cette capacité prend en charge les cas où les réceptions cash-and-carry de client sont imprimées dans les imprimantes de réception, alors que les commandes client, comportant plus d'informations, sont imprimées sur une imprimante sur une page. Des imprimantes de réception peuvent être liées directement à un ordinateur via l'USB, être liées à un réseau via l'Ethernet, ou connecter via Bluetooth.

### <a name="scanner"></a>Scanneur

Arrondi à deux scanneurs de codes-barres peuvent être utilisés simultanément. Cette capacité prend en charge les cas où un lecteur de plus portable est requis afin d'analyser des gros ou lourds articles, alors qu'un scanneur intégré fixe est utilisé pour la plupart des articles de taille d'un standard, pour accélérer les temps d'extraction. Les scanneurs peuvent être pris en charge par OPOS plateforme (UWP), Windows universel, ou interfaces du s'arrête en de clavier. L'USB ou le Bluetooth permet de connecter un scanneur à un ordinateur.

### <a name="msr"></a>LBM

Un lecteur de bande magnétique (MSR) destinée USB peut être paramétré à l'aide de les conducteurs OPOS. Si vous souhaitez utiliser un LBM autonome pour les transactions de paiement de (EFT) de transfert électronique de fonds, le LBM doit être effectué par un Business de paiement. Les MSRs autonomes peuvent être utilisés pour l'entrée de fidélité du client, l'employé {{signe-:sign-in}}, {{dans:sign-in}} et l'entrée de carte cadeau, indépendamment du Business de paiement.

### <a name="cash-drawer"></a>Caisse enregistreuse

Deux tiroirs-caisse peuvent être pris en charge par profil matériel. Cette capacité permet à deux équipes actives par caisse enregistreuse soient disponibles simultanément. Dans le cas d'une équipe partagée, ou d'un tiroir-caisse utilisé par des périphériques mobiles plusieurs POS en même temps, seul le ainsi un tiroir-caisse par profil matériel. Des tiroirs-caisse peuvent être liés directement à un ordinateur via l'USB, être liés à un réseau, ou être liés à une imprimante de réception via une interface RJ12. Dans certains cas, des tiroirs-caisse peuvent également être connectés via Bluetooth.

### <a name="line-display"></a>Affichage de ligne

La ligne affiche sont utilisées aux produits Afficher, aux soldes des transactions, ainsi que d'autres informations utiles au client lors d'une transaction. Une ligne affichage peut être associée à l'ordinateur via l'USB à l'aide de les conducteurs OPOS.

### <a name="signature-capture"></a>Capture de signature

Les périphériques de capture de signature peuvent être liés directement à un ordinateur via l'USB à l'aide de les conducteurs OPOS. Lorsque la capture de signature est configurée, le client est invité à signer sur le périphérique. Une fois la signature soit livrée, elle s'est affichée au caissier pour l'acceptation.

### <a name="scale"></a>Echelle

Les échelles peuvent être liées à l'ordinateur via USP à l'aide de les conducteurs OPOS. Lorsqu'un produit qui est marqué comme produit « pesé » est ajouté à une transaction, le POS relève le poids de l'échelle, ajoute le produit à la transaction, et utilise la quantité que l'échelle est livrée.

### <a name="pin-pad"></a>Clavier d'identification personnelle

Les plaquettes personnelles de (PIN) de numéros d'identification sont prises en charge via OPOS, mais elles doivent être gérées via un Business de paiement.

### <a name="secondary-display"></a>Affichage secondaire

Lorsqu'une vue secondaire est configuré, l'affichage de Windows du numéro 2 est utilisé pour les informations de base d'affiche. L'objectif de la vue secondaire est de permettre l'extension de (ISV) d'éditeur de logiciels indépendant, car prédéfini, la vue secondaire ne figure pas configurable et par affiches limité.

### <a name="payment-device"></a>Appareil de paiement

Support de périphérique de paiement est implémenté par le Business de paiement. Les périphériques de paiement peuvent remplir une ou plusieurs des fonctions que d'autres classes de périphérique fournissent. Par exemple, un périphérique de paiement peut fonctionner comme un lecteur de LBM/card, une ligne affichage, un dispositif de capture de signature, ou une clavier d'identification personnelle. L'aide de périphériques de paiement est implémenté indépendamment du support autonome de périphérique qui est indiqué pour d'autres périphériques qui sont inclus dans le profil matériel.

## <a name="supported-interfaces"></a>Interfaces prises en charge
### <a name="opos"></a>OPOS

Pour assurer que la plus grande plage des périphériques peut être utilisée avec Microsoft Dynamics 365 pour les opérations - au détail, l'OLE pour la norme du secteur du PDV est la principale plateforme périphérique du périphérique pris en charge dans Microsoft Dynamics 365 pour les opérations - au détail. L'OLE pour la norme du PDV a été produit par la fédération au détail nationale (NRF), qui établit les protocoles de transmission standard pour les périphérique au détail. OPOS est une implémentation vaste adoptée de l'OLE pour la norme du PDV. C'est le en mi-1990 est développé et a été mis à jour plusieurs fois depuis l'. OPOS fournit une architecture de pilote du périphérique qui permet l'intégration facile de matières du PDV à des systèmes POS basés sur Windows. Communication poignée de commande OPOS entre le matériel compatible et le logiciel du PDV. Un contrôle OPOS est composé de deux parties :

-   ** Objet de contrôle ** – L'objet de contrôle pour une classe de périphérique (comme ligne affiche) permet l'interface du logiciel. Services de consultance de Monroe (www.monroecs.com [] (http://www.monroecs.com/)) fournit un ensemble normalisé d'objets de contrôle OPOS qui sont appelés objets (CCOs) de contrôle commun. Le CCOs sont utilisés pour tester le composant du PDV de Microsoft Dynamics 365 pour les opérations - au détail. Par conséquent, les applications de tests garantissent que, si Microsoft Dynamics 365 pour les opérations - au détail prend en charge une classe de périphérique via OPOS, de nombreux types de périphérique peut être pris en charge, à condition que le fabricant livrés par un objet de service qui est établi pour OPOS. Vous ne devez pas explicitement tester chaque type de périphérique.
-   ** Objet de service ** – L'objet de service propose les communications entre l'objet de contrôle (CCO) et le périphérique. Généralement, l'objet de service pour un périphérique est fourni par le fabricant du périphérique. Toutefois, dans certains cas, vous devez télécharger l'objet de service du site Web du fabricant. Par exemple, un objet de service plus récent peut être disponible. Pour trouver l'adresse du site Web du fabricant, voir la documentation de matériel.

[objet de service et le même objet de contrôle![] (. /media/retail_peripherals_overview01.png)](. L'aide de /media/retail_peripherals_overview01.png) de l'implémentation OPOS d'OLE pour les applications d'assistance de PDV garantissent que, si les fabricants de périphérique et aux éditeurs de PDV implémentation la norme correctement, les systèmes POS et les périphériques pris en charge peut fonctionner ensemble, même s'ils n'ont pas été précédemment testés ensemble. ** Remarque : ** Support OPOS ne garantit pas le support technique de tous les périphériques qui ont des pilotes) OPOS. Microsoft Dynamics 365 pour les opérations - premier support de obligatoire au détail qui type de périphérique, ou classe, via OPOS. En outre, les objets de service ne peuvent pas toujours être à jour avec la dernière version de CCOs. Vous devez également tenir compte du fait que, généralement la qualité des objets de service varie.

### <a name="windows"></a>Windows

L'impression de réception au niveau de le POS est optimisée pour OPOS. OPOS tend à être beaucoup plus rapide que l'impression dans Windows. Par conséquent, il est conseillé d'utiliser OPOS, en particulier dans les environnements au détail où 40 réceptions de colonne sont imprimées et les durées de transaction doit être rapide. Pour la plupart des périphériques, vous allez utiliser des contrôles OPOS. Toutefois, les imprimantes de réception d'un certain OPOS prennent également en charge les chauffeurs Windows. En utilisant un chauffeur de Windows, vous pouvez parcourir les plus défuntes polices et impression du réseau un pour les plusieurs caisses. Toutefois, il existe des inconvénients à utiliser les conducteurs de Windows. Voici quelques exemples de ces inconvénients :

-   Lorsque les conducteurs de Windows sont utilisés, des images sont affichées avant d'imprimer se produise. Par conséquent, imprimer tend à être plus lent qu'il est sur les imprimantes qui utilisent des contrôles OPOS.
-   Les périphériques qui sont connectés via l'imprimante (« connecté en série ") peuvent ne pas fonctionner correctement lorsque les conducteurs de Windows sont utilisés. Par exemple, le tiroir-caisse ne peut pas ouvrir, ou l'imprimante de bordereau ne peut pas exprimer comme prévu.
-   OPOS prend également en charge un ensemble de variables plus développé qui sont spécifiques à vendre des imprimantes au détail de réception, telles que l'impression de papier de ou coupé de bordereau.

Si les contrôles OPOS sont disponibles pour l'imprimante Windows que vous utilisez, l'imprimante doit encore fonctionner correctement avec Microsoft Dynamics 365 pour les opérations - au détail.

### <a name="universal-windows-platform"></a>Plateforme Windows universelle

UWP, dans le cas de périphériques au détail, est lié au support technique de Windows des périphériques prêts à l'emploi. Lorsqu'un périphérique prêt à l'emploi est lié à une version du SE Windows qui prend en charge ce type de périphérique, aucun chauffeur n'est indispensable pour que l'unité soit utilisé comme prévu. Par exemple, si Windows détecte un périphérique de haut-parleur de Bluetooth, l'SE sait que l'unité a ** haut-parleur ** commandent le type. Par conséquent, et lui gère ce périphérique comme haut-parleur. Aucun paramétrage supplémentaire n'est nécessaire. En cas de périphériques de PDV, nombre de périphériques d'USB peuvent être branchés, et Windows les identifiera comme périphériques (HIDs) de l'interface humaines. Toutefois, il ne peut pas pouvoir déterminer les capacités dont le périphérique fournit, car le périphérique ne spécifie pas la classe, ou type, de l'unité. Dans Windows 10, les classes de périphérique pour les scanneurs de code-barres et les MSRs ont été ajoutés. Par conséquent, si un périphérique se déclare à Windows 10 comme périphérique d'une de ces classes, Windows détectera à l'oreille des événements du périphérique aux temps appropriés. Le Modern POS prend en charge UWP MSRs et scanneurs. Par conséquent, lorsque cela est prêt pour la saisie d'un de ces périphériques, et un périphérique qui appartient à une de ces classes est connecté, le périphérique peut être utilisé. Par exemple, si un lecteur de codes-barres d'UWP est branché à un ordinateur Windows 10, et code-barres {{signe-:sign-in}} {{dans:sign-in}} est configuré pour le Modern POS, le scanneur de code-barres devient actif dans {{signe-:sign-in}} {{dans:sign-in}} l'écran. Aucun paramétrage supplémentaire n'est nécessaire. Les classes supplémentaires de point de service que les périphériques d'UWP sont ajoutés à Windows. Ces classes incluent des classes et des tiroirs-caisse et les imprimantes de réception. L'aide de ces classes de périphérique dans le Modern POS est en attente.

### <a name="keyboard-wedge"></a>Cale de clavier

Les périphériques de s'arrête en de clavier envoient des données sur l'ordinateur comme si ces données ont été entrées sur le clavier. Par conséquent, par défaut, le champ actif dans le système POS recevra les données qui sont scannées ou passées la carte. Dans certains cas, ce comportement peut entraîner le type convient pas de données à analyser dans le champ fausse. Par exemple, un code-barres peut être analysé dans un champ attendu pour la saisie de données de carte de crédit. Dans de nombreux cas, il existe de logique au niveau de le POS qui détermine si les données qui sont scannées ou passées la carte est un code-barres ou un passage de cartes. Par conséquent, les données sont traitées normalement. Toutefois, lorsque des périphériques sont paramétrés comme OPOS au lieu des périphériques de s'arrête en de clavier, il y a plus de contrôle du mode d'utilisation des données de ces unités peuvent être consommées, car plus « est appelé » sur le périphérique à partir duquel les données provenant. Par exemple, les données d'un lecteur de codes-barres sont automatiquement identifiées comme codes-barres, et l'enregistrement associé dans la base de données est indiqué plus facilement et plus rapidement que si une recherche de chaîne de caractères génériques étaient utilisées, comme dans le cas de périphériques de s'arrête en de clavier.

### <a name="native-printer"></a>Imprimante maternelle

Tandis que le type est appelé dans le profil matériel) des imprimantes natifs (ou « périphérique » peuvent être configurées pour inviter l'utilisateur à sélectionner une imprimante configurée pour l'ordinateur. Lorsqu'une imprimante ** périphérique ** du type est configurée, si le Modern POS rencontre une commande print, l'utilisateur est invité à sélectionner une imprimante dans une liste. Ce comportement est différent du comportement pour les conducteurs de Windows, car ** Windows ** le type de l'imprimante dans le profil matériel ne fait pas affiche la liste des imprimantes. Au lieu de cela, elle nécessite qu'une imprimante nommée soit livrée dans ** nom du périphérique ** le champ.

### <a name="windows"></a>Windows

** Windows ** le type de périphérique est utilisé pour les imprimantes uniquement. Lorsqu'une imprimante Windows est configurée dans le profil matériel, le nom de l'imprimante spécifique doit être livré. Lorsque les rencontres de Modern POS que des événements, si une imprimante Windows est configurée, l'événement est passé à l'imprimante spécifiée Windows. L'utilisateur ne sera pas invité à sélectionner une imprimante.

### <a name="network"></a>Réseau

des tiroirs-caisse Réseau- adressables, les imprimantes de réception, et les terminaux de paiement peuvent être utilisés sur un réseau, l'une ou l'autre directement via la station matérielle les communications d'interprocessus (CPI) qui est intégrée dans le Modern POS de l'application Windows ou via la station matérielle IIS pour d'autres clients de Modern POS.

## <a name="hardware-station-deployment-options"></a>Options de déploiement de station matérielle
### <a name="ipc-built-in"></a>CPI (intégré)

La station matérielle les communications d'interprocessus (CPI) est intégrée dans le Modern POS de l'application Windows. Pour utiliser la station matérielle CPI, affectez un profil matériel à un registre qui utilise le Modern POS de l'application Windows. Créez ensuite une station matérielle de ** dédié ** saisissent pour le magasin dans lequel la caisse enregistreuse est utilisé. Lorsque vous commencez le Modern POS, la station matérielle CPI est active, et les périphériques de PDV configurés sont prêts à utiliser. Si vous temporairement n'avez pas besoin de matériel local pour quelque raison, utilisez ** de gérer les stations matérielles ** l'opération permet de désactiver les fonctionnalités de station matérielle. Le Modern POS peut également utiliser la station matérielle CPI pour communiquer directement avec des périphériques de réseau.

### <a name="iis"></a>IIS

Vous pouvez utiliser l'IIS ou la version autonome de la station de matière de deux manières. Le descripteur IIS «  » implique que l'application POS se connecte à la station matérielle via Microsoft Internet Information Services de Microsoft. L'application POS se connecte à la station de matériel IIS via les services Web exécutées sur un ordinateur sur lequel les périphériques sont connectés. Si IIS est utilisé, les périphériques au détail qui sont associés à une station de matériel peuvent être utilisés par tout TPV basé sur le même réseau que la station matérielle IIS. Étant donné que le Modern POS pour Windows inclut la prise en charge intégré des périphériques au détail, toutes les autres applications de Modern POS doivent utiliser la station matérielle IIS pour communiquer avec les périphériques de PDV configurés dans le profil matériel. Par conséquent, chaque instance de la station de matériel IIS nécessite un ordinateur qui exécute le service Web et de l'application qui communique avec les périphériques. La station matérielle IIS est requise pour toutes les applications de Modern POS non Windows.

#### <a name="dedicated"></a>Dédié

Le Modern POS utilise les stations de matière de ** dédié ** type pour les détecter que des périphériques sont directement liés à l'ordinateur sur lequel la candidature est utilisée. Toutefois, ** dédié ** le type peut également être utilisé pour les stations de matériel IIS. Dans un scénario traditionnel et fixe POS utilisant le POS de cloud comme application du PDV, ** dédié ** le type de station matérielle est utilisé pour les stations matérielles IIS qui sont déployées sur le même ordinateur qui est PDV actuel de cloud. Dans une perspective au détail de périphériques, la station matérielle dédiée IIS a un meilleur support technique périphérique au détail des scénarios traditionnels et fixes du PDV. Les stations matérielles dédiées prennent en charge tous les périphériques pris en charge dans le profil matériel.

#### <a name="shared"></a>Partagées

Les stations de matériel sont partagées sont prévues pour être utilisées par les périphériques plusieurs du PDV via le cours du jour. Les stations de matériel sont partagées sont optimisées pour prendre en charge uniquement des tiroirs-caisse, les imprimantes de réception, et des terminaux de paiement. Vous ne pouvez pas directement lier les scanneurs autonomes de code-barres, MSRs, ligne affiche, échelles, ou d'autres périphériques. Sinon, les conflits se produisent lorsque test multiple de périphériques POS afin de réclamer les périphériques simultanément. Voici la manière dont les conflits sont gérés pour les périphériques pris en charge :

-   ** Le tiroir ** – le tiroir-caisse est ouvert via un événement envoyé au périphérique. Code unique problème qui peut survenir lorsque le tiroir-caisse est appelé se produit si le tiroir-caisse est déjà en cours. Dans le cas de les stations de matériel sont partagées, le tiroir-caisse doit être défini comme ** partagé ** dans le profil matériel. Ce paramètre empêché le POS de vérifier si le tiroir-caisse est déjà en cours lorsqu'il soumet des commandes en cours.
-   ** Imprimante de réception ** – Si deux commandes d'impression de réception sont envoyées à la station de matériel en même temps, une de commande peut être perdue, selon le périphérique. Certains périphériques ont la mémoire interne ou en commun pouvant éviter ce problème. Si une commande print échoue, il reçoit un message d'erreur et peut tentative la commande print du PDV.
-   ** Le terminal de paiement ** – Si les tests d'un caissier pour offrir une transaction dans un terminal de paiement qui est déjà utilisé, un message vous informe le caissier que le terminal est utilisé et demande au caissier de tester à nouveau ultérieurement. Généralement, les caissiers peuvent voir qu'un terminal est déjà utilisé et attendra tant que l'autre transaction soit terminée avant qu'ils essayient d'offrir de nouveau.

Le contrôle est planifié pour une version future, pour le détecter si les périphériques non prise en charge sont paramétrés pour un profil matériel qui est mis en correspondance avec une station de matériel partagée. Si des périphériques non prise en charge sont détectés, l'utilisateur reçoit un message qui indique que les périphériques ne sont pas pris en charge pour les stations matérielles partagées. Dans le cas de les stations de matériel sont partagées, ** sélectionnez lors de la soumission ** l'option est définie ** Oui ** au niveau de la caisse enregistreuse. L'utilisateur POS est alors invité à sélectionner une station matérielle lorsqu'une offre est activée pour une transaction dans le système POS. Lorsque la station matérielle est activée qu'au moment de l'offre, la sélection de station matérielle est ajoutée directement au workflow du PDV pour les scénarios portable. Comme avantages en nature, la ligne afficher sur le terminal de paiement n'est pas utilisée pour les scénarios partagés. Si le terminal de paiement est utilisé comme affichage de ligne, les autres utilisateurs peuvent être bloqués d'utiliser ce terminal tant que la transaction soit terminée. Dans les scénarios mobiles, des lignes peuvent être ajoutées à une transaction à long terme. Par conséquent, ** sélectionnez lors de la soumission ** l'option est obligatoire pour garantir la disponibilité optimale de l'unité.

### <a name="network-peripherals"></a>Périphériques de réseaux

Désignation du réseau des périphériques de le profil matériel active des tiroirs-caisse, les imprimantes de réception, et des terminaux de paiement à connecter via une connexion réseau.

#### <a name="modern-pos-for-windows"></a>Modern POS pour Windows

Vous pouvez spécifier l'adresse IP pour les périphériques réseau dans deux emplacements. Si le client Windows de Modern POS utilise un ensemble simple des périphériques de réseau, vous devez définir les adresse IP pour les périphériques à l'aide ** configuration d'IP ** de l'option dans le volet Actions pour le registre. En cas de périphériques de réseau qui seront partagés entre les registres POS, un profil matériel qui a des périphériques de réseau qui lui peut être mis en correspondance directement pour une station de matériel partagée. Pour répartir les adresse IP, sélectionnez la station matérielle sur ** les magasins de vente au détail ** la page, puis utilisez ** configuration d'IP ** l'option dans ** des stations matérielles ** la section de spécifier les périphériques de réseaux affectés à cette station matérielle. Pour les stations matérielles qui ont uniquement des périphériques de réseau, vous ne devez pas déployer la station matérielle elle-même. Dans ce cas, la station matérielle est requise afin de regrouper uniquement conceptuellement les périphériques réseau- adressables en fonction de leur emplacement dans le magasin de vente au détail.

#### <a name="cloud-pos-modern-pos-for-ios-and-modern-pos-for-android"></a>PDV de cloud, Modern POS pour l'(, et Modern POS pour Android

La logique qui mène les périphériques physiquement associés et réseau- adressables figurant dans la station matérielle. Par conséquent, pour tous les clients du PDV à l'exception de le Modern POS pour Windows, une station matérielle IIS doit être déployé et active pour permettre au niveau de le POS pour communiquer avec les périphériques, que les périphériques sont physiquement liés à la station matérielle ou adressés sur le réseau.

## <a name="setup-and-configuration"></a>Paramétrage et configuration
### <a name="hardware-station-installation"></a>Installation de station matérielle

Pour plus d'informations, voir [configuration de station matérielle et installation au détail] (retail-hardware-station-configuration-installation.md).

### <a name="modern-pos-for-windows-setup-and-configuration"></a>Modern POS pour le paramétrage et la configuration Windows

Pour plus d'informations, voir [configuration de Retail Modern POS et installation] (retail-modern-pos-device-activation.md).

### <a name="opos-device-setup-and-configuration"></a>Paramétrage et configuration de périphérique OPOS

Pour plus d'informations sur les composants OPOS, voir la section « des interfaces prises en charge » de ce document. Généralement, les chauffeurs OPOS sont fournis par le fabricant du périphérique. Lorsqu'un pilote du périphérique OPOS est installé, il ajoute une clé au registre de Windows depuis les emplacements suivants :

-   ** système de 32 bits : ** HKEY\_\_LOCAL MACHINESOFTWAREOLEforRetailServiceOPOS
-   ** système 64 bits : ** HKEY\_\_LOCAL MACHINESOFTWAREWOW6432NodeOLEforRetailServiceOPOS

Dans l'emplacement du registre des ServiceOPOS, les périphériques configurés sont organisés selon la classe de périphérique OPOS. Des chauffeurs multiples de périphérique sont stockés.

## <a name="supported-scenarios-by-hardware-station-type"></a>Scénarios pris en charge par le type de station matérielle
### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Supports du client – station matérielle CPI Réel/Budget la station matérielle IIS

Le tableau suivant indique les topologies et les scénarios de déploiement pris en charge.

| Client      | Station matérielle CPI | Station matérielle IIS |
|-------------|----------------------|----------------------|
| Application de Windows | Oui                  | Oui                  |
| Cloud POS   | N°                   | Oui                  |
| Android     | N°                   | Oui                  |
| IOS         | N°                   | Oui                  |

### <a name="network-peripherals"></a>Périphériques de réseaux

Les périphériques de réseau peuvent être pris en charge directement via la station matérielle qui est intégrée dans le Modern POS de l'application Windows. Pour tous les autres clients, vous devez déployer une station matérielle IIS.

| Client      | Station matérielle CPI | Station matérielle IIS |
|-------------|----------------------|----------------------|
| Application de Windows | Oui                  | Oui                  |
| Cloud POS   | N°                   | Oui                  |
| Android     | N°                   | Oui                  |
| IOS         | N°                   | Oui                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Types pris en charge de périphérique par le type de station matérielle
### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS pour Windows avec une station matérielle (intégrée CPI)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de prise en charge de périphérique</th>
<th>Interfaces prises en charge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Imprimante</td>
<td><ul>
<li>OPOS</li>
<li>Pilote Windows</li>
<li>Périphérique</li>
<li>Réseau</li>
</ul></td>
</tr>
<tr class="even">
<td>Imprimante 2</td>
<td><ul>
<li>OPOS</li>
<li>Pilote Windows</li>
<li>Périphérique</li>
<li>Réseau</li>
</ul></td>
</tr>
<tr class="odd">
<td>Affichage de ligne</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Affichage double</td>
<td>Pilote Windows</td>
</tr>
<tr class="odd">
<td>LBM</td>
<td><ul>
<li>OPOS</li>
<li>UWP (aucun paramétrage n'est nécessaire.)</li>
<li>Cale de clavier (aucun paramétrage n'est nécessaire.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Créateur</td>
<td><ul>
<li>OPOS</li>
<li>Le réseau <strong>Remarque :</strong> uniquement un tiroir-caisse peut être paramétré si <strong>Équipe partagés utilisation</strong> est configuré dans le tiroir-caisse.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tiroir-caisse 2</td>
<td><ul>
<li>OPOS</li>
<li>Le réseau <strong>Remarque :</strong> uniquement un tiroir-caisse peut être paramétré si <strong>Équipe partagés utilisation</strong> est configuré dans le tiroir-caisse.</li>
</ul></td>
</tr>
<tr class="even">
<td>Scanneur</td>
<td><ul>
<li>OPOS</li>
<li>UWP (aucun paramétrage n'est nécessaire.)</li>
<li>Cale de clavier (aucun paramétrage n'est nécessaire.)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Scanneur 2</td>
<td><ul>
<li>OPOS</li>
<li>UWP (aucun paramétrage n'est nécessaire.)</li>
<li>Cale de clavier (aucun paramétrage n'est nécessaire.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Echelle</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Clavier d'identification personnelle</td>
<td>OPOS (le support est disponible via la personnalisation du Business de paiement.)</td>
</tr>
<tr class="even">
<td>Capture de signature</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Terminal de paiement </td>
<td><ul>
<li>Support personnalisé de périphérique</li>
<li>Réseau (Pour plus d'informations, voir la documentation de Business Connector de paiement.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Tous les clients de Modern POS qui ont une station matérielle dédiée IIS

** Remarque : ** Lorsque la station matérielle IIS est dédiée « , » il existe une relation de entre le client du PDV et la station matérielle.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de prise en charge de périphérique</th>
<th>Interfaces prises en charge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Imprimante</td>
<td><ul>
<li>OPOS</li>
<li>Le pilote Windows <strong>Remarque :</strong> Pour les imprimantes Windows sur un réseau, l'utilisateur de la station de matière doit disposer d'une autorisation d'accès à l'imprimante.</li>
<li>Réseau</li>
</ul></td>
</tr>
<tr class="even">
<td>Imprimante 2</td>
<td><ul>
<li>OPOS</li>
<li>Pilote Windows</li>
<li>Réseau</li>
</ul></td>
</tr>
<tr class="odd">
<td>Affichage de ligne</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>LBM</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Créateur</td>
<td><ul>
<li>OPOS</li>
<li>Le réseau <strong>Remarque :</strong> uniquement un tiroir-caisse par profil matériel peut être paramétré si <strong>Équipe partagés utilisation</strong> est configuré dans le tiroir-caisse.</li>
</ul></td>
</tr>
<tr class="even">
<td>Tiroir-caisse 2</td>
<td><ul>
<li>OPOS</li>
<li>Réseau</li>
</ul></td>
</tr>
<tr class="odd">
<td>Scanneur</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Scanneur 2</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Echelle</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Clavier d'identification personnelle</td>
<td>OPOS (le support est disponible via la personnalisation du Business de paiement.)</td>
</tr>
<tr class="odd">
<td>Sig. copie</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Terminal de paiement </td>
<td><ul>
<li>Support personnalisé de périphérique</li>
<li>Réseau (Pour plus d'informations, voir la documentation de Business Connector de paiement.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Tous les clients de Modern POS qui ont une station matérielle partagée IIS

** Remarque : ** Lorsque la station matérielle IIS « est partagée, » les périphériques plusieurs peuvent utiliser la station matérielle simultanément. Pour ce scénario, vous devez utiliser uniquement les périphériques répertoriés dans le tableau suivant. Si vous tentez de partager les périphériques qui ne sont pas répertoriés, comme des scanneurs de codes-barres et les MSRs, des erreurs se produisent lorsque test multiple de périphériques de réclamer le même périphérique. À venir, une configuration sera explicitement impossible.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de prise en charge de périphérique</th>
<th>Interfaces prises en charge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Imprimante</td>
<td><ul>
<li>OPOS</li>
<li>Le pilote Windows <strong>Remarque :</strong> Pour les imprimantes Windows sur un réseau, l'utilisateur de la station de matière doit disposer d'une autorisation d'accès à l'imprimante.</li>
<li>Réseau</li>
</ul></td>
</tr>
<tr class="even">
<td>Imprimante 2</td>
<td><ul>
<li>OPOS</li>
<li>Pilote Windows</li>
<li>Réseau</li>
</ul></td>
</tr>
<tr class="odd">
<td>Créateur</td>
<td><ul>
<li>OPOS</li>
<li>Le réseau <strong>Remarque :</strong> uniquement un tiroir-caisse par profil matériel peut être paramétré si <strong>Équipe partagés utilisation</strong> est configuré dans le tiroir-caisse.</li>
</ul></td>
</tr>
<tr class="even">
<td>Tiroir-caisse 2</td>
<td><ul>
<li>OPOS</li>
<li>Réseau</li>
</ul></td>
</tr>
<tr class="odd">
<td>Terminal de paiement </td>
<td><ul>
<li>Support personnalisé de périphérique</li>
<li>Réseau (Pour plus d'informations, voir la documentation de Business Connector de paiement.)</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Configuration des scénarios pris en charge
Pour plus d'informations sur la création de profils matériels, voir [définir et de tenir à jour les clients de canal, notamment les registres et les stations matérielles] (define-maintain-channel-clients-registers-hw-stations.md). ** Remarque : ** Pour Microsoft Dynamics 365 pour la version 1611 d'opérations, le profil de station matérielle n'est plus utilisé. Les attributs que vous avez préalablement paramétrée dans le profil de station matérielle sont désormais une partie de la station de matériel elle-même.

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS pour Windows avec une station matérielle (intégrée CPI)

Cette configuration est la configuration les plus courantes pour les registres POS traditionnels et fixes. Pour ce scénario, les informations de profil matériel en correspondance directement au registre lui-même. Le numéro de terminal TEF doit également être défini sur la caisse enregistreuse lui-même. Pour paramétrer cette configuration, procédez comme suit.

1.  Créez un profil matériel où tous les périphériques obligatoires sont configurés.
2.  Mappez le profil matériel du TPV.
3.  Créez une station matérielle de ** dédié ** saisissent for Retail où le Registre POS est utilisé. Description est facultative. ** Remarque : ** Vous ne devez définir aucune autres propriétés de la station matérielle. Toutes les autres informations requises, telles que le profil matériel, proviennent du registre lui-même.
4.  Cliquez sur ** au détail et commerce ** &gt; ** IT au détail ** &gt; ** programme de distribution **.
5.  Sélectionnez ** 1090 ** le programme de distribution à la synchronisation le nouveau profil matériel au magasin. Cliquez sur ** exécution désormais ** à la synchronisation devient le POS.
6.  Sélectionnez ** 1040 ** le programme de distribution à la synchronisation la nouvelle station matérielle au magasin. Cliquez sur ** exécution désormais ** à la synchronisation devient le POS.
7.  Permet d'installer et d'activer le Modern POS pour Windows.
8.  Démarrez le Modern POS pour Windows, puis de commencer à utiliser les périphérique connectés.

### <a name="all-modern-pos-clients-that-have-a-dedicated-iis-hardware-station"></a>Tous les clients de Modern POS qui ont une station matérielle dédiée IIS

Cette configuration peut être utilisée pour tous les clients de Modern POS qui ont une station matérielle utilisée uniquement à un TPV. Pour paramétrer cette configuration, procédez comme suit.

1.  Créez un profil matériel où tous les périphériques obligatoires sont configurés.
2.  Créez une station matérielle de ** dédié ** saisissent for Retail où le Registre POS est utilisé.
3.  Dans la station matérielle dédiée, définissez les propriétés suivantes :
    -   ** Nom de l'hôte ** – Nom de l'ordinateur principale où la station matérielle lots. ** Remarque : ** Le POS de cloud peut le résoudre ** hôte local " ** de déterminer l'ordinateur local dans lequel le POS de cloud exécute. Toutefois, le certificat requis afin d'accoupler le POS de cloud avec la station matérielle doit également être « Localhost » comme nom de l'ordinateur. Pour éviter les problèmes, nous recommandons que vous répertoriez une instance de chaque station matérielle dédiée pour le magasin, au besoin. Pour chaque station matérielle, le nom d'hôte doit être le nom de l'ordinateur spécifique pour lequel la station matérielle est déployée.
    -   ** Port ** – Le port à utiliser pour la station matérielle communique avec le client de Modern POS.
    -   ** Le profil matériel ** – Si le profil matériel n'est pas indiqué sur la station matérielle elle-même, le profil matériel affecté au registre est utilisé.
    -   ** Numéro POS TEF ** – ID terminal TEF à utiliser lorsque des autorisations TEF sont envoyées. Cet ID est fourni par le processeur de carte de crédit.
    -   ** Nom du module ** – Le module de station matérielle à utiliser lorsque la station matérielle est déployé.

4.  Cliquez sur ** au détail et commerce ** &gt; ** IT au détail ** &gt; ** programme de distribution **.
5.  Sélectionnez ** 1090 ** le programme de distribution à la synchronisation le nouveau profil matériel au magasin. Cliquez sur ** exécution désormais ** à la synchronisation devient le POS.
6.  Sélectionnez ** 1040 ** le programme de distribution à la synchronisation la nouvelle station matérielle au magasin. Cliquez sur ** exécution désormais ** à la synchronisation devient le POS.
7.  Installez la station matérielle. Pour plus d'informations sur l'installation de la base de la station matérielle, voir [configuration de station matérielle et installation au détail] (retail-hardware-station-configuration-installation.md).
8.  Permet d'installer et d'activer le Modern POS. Pour plus d'informations sur l'installation de la base de le Modern POS, voir [configuration de Retail Modern POS et installation] (retail-modern-pos-device-activation.md).
9.  Connexion au Modern POS, puis sélectionnez ** exécutez les opérations non tiroir-caisse **.
10. Démarrez ** gérer les stations de matériel ** l'opération.
11. Cliquez sur ** gérez **.
12. Dans la page de gestion de station matérielle, définissez l'option pour activer la station matérielle.
13. Sélectionnez la station matérielle à utiliser, puis cliquez sur ** une paire **.
14. Une fois la station matérielle soit accouplée, cliquez sur ** clôture **.
15. Dans la page de sélection de station matérielle, cliquez sur la station matérielle récemment sélectionnée pour lui rendre active.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Tous les clients de Modern POS qui ont une station matérielle partagée IIS

Cette configuration peut être utilisée pour tous les clients de Modern POS qui partagent les stations de matières avec d'autres périphériques. Pour paramétrer cette configuration, procédez comme suit.

1.  Créez un profil matériel où les périphériques obligatoires sont configurés.
2.  Créez une station matérielle de ** partagé ** saisissent for Retail où le Registre POS est utilisé.
3.  Dans la station matérielle partagée, définissez les propriétés suivantes :
    -   ** Nom de l'hôte ** – Nom de l'ordinateur principale où la station matérielle lots.
    -   ** La description ** – Texte qui permet d'identifier la station matérielle, comme ** des retours ** ou ** avant de magasin **.
    -   ** Port ** – Le port à utiliser pour la station matérielle communique avec le client de Modern POS.
    -   ** Le profil matériel ** – Pour les stations matérielles partagées, chaque station matérielle doit avoir un profil matériel. Des profils matériels peuvent être partagés entre les stations matérielles, mais ils doivent être mis en correspondance avec chaque station matérielle. En outre, il est recommandé d'utiliser les équipes partagées lorsque les périphériques plusieurs utilisent le même station matérielle partagée. Pour paramétrer une équipe partagée, cliquez sur ** au détail et commerce ** &gt; ** canal paramétré ** &gt; ** la configuration ** &gt; ** le POS profils ** &gt; ** des profils matériels **. Pour chaque profil matériel partagé, sélectionnez le tiroir-caisse, puis définissez ** tiroir-caisse partagé d'équipe ** l'option ** Oui **.
    -   ** Numéro POS TEF ** – ID terminal TEF à utiliser lorsque des autorisations TEF sont envoyées. Cet ID est fourni par le processeur de carte de crédit.
    -   ** Nom du module ** – Le module de station matérielle à utiliser lorsque la station matérielle est déployé.

4.  Répétez les étapes 2 et 3 pour chaque station matérielle supplémentaire requise dans le magasin.
5.  Cliquez sur ** au détail et commerce ** &gt; ** IT au détail ** &gt; ** programme de distribution **.
6.  Sélectionnez ** 1090 ** le programme de distribution à la synchronisation le nouveau profil matériel au magasin. Cliquez sur ** exécution désormais ** à la synchronisation devient le POS.
7.  Sélectionnez ** 1040 ** le programme de distribution à la synchronisation la nouvelle station matérielle au magasin. Cliquez sur ** exécution désormais ** à la synchronisation devient le POS.
8.  Installez la station matérielle sur chaque ordinateur principal que vous paramétrez dans les étapes 2 et 3. Pour plus d'informations sur l'installation de la base de la station matérielle, voir [configuration de station matérielle et installation au détail] (retail-hardware-station-configuration-installation.md).
9.  Permet d'installer et d'activer le Modern POS. Pour plus d'informations sur l'installation de la base de le Modern POS, voir [configuration de Retail Modern POS et installation] (retail-modern-pos-device-activation.md).
10. Connexion au Modern POS, puis sélectionnez ** exécutez les opérations non tiroir-caisse **.
11. Démarrez ** gérer les stations de matériel ** l'opération.

12. Cliquez sur ** gérez **.
13. Dans la page de gestion de station matérielle, définissez l'option pour activer la station matérielle.
14. Sélectionnez la station matérielle à utiliser, puis cliquez sur ** une paire **.
15. Répétez l'étape 14 pour chaque station matérielle que le Modern POS utilise.
16. Une fois toutes les stations matérielles requises soient accouplées, cliquez sur ** clôture **.
17. Dans la page de sélection de station matérielle, cliquez sur la station matérielle récemment sélectionnée pour lui rendre active. ** Remarque : ** Si les périphériques utilisent souvent différentes stations matérielles, nous recommandons que vous configurez le Modern POS qui avertissent les caissiers à sélectionner une station matérielle lorsqu'ils commencent le processus de devis. Cliquez sur ** au détail et commerce ** &gt; ** canal paramétré ** &gt; ** la configuration ** &gt; ** registres **. Sélectionnez le Registre, puis définissez ** sélectionnez lors de l'offre ** l'option ** Oui **. Utilisez ** 1090 ** le programme de distribution aux modifications de synchronisation à la base de données des canaux.

## <a name="extensibility"></a>Extensibilité
Pour plus d'informations sur les scénarios d'extensibilité pour la station matérielle, voir [Extensibilité de station matérielle] (DEV -itpro - itpro/hardware-station-extensibility.md).

## <a name="security"></a>Sécurité
En fonction de les standard de sécurité, les paramètres suivants doivent être utilisés dans un environnement de production : ** Remarque : ** Le programme d'installation de station matérielle effectue automatiquement si ces le registre modifie partie de l'installation via le self-service.

-   Le protocole SSL (SSL) doit être désactivé.
-   Seule la version 1,2 Server (TLS) de sécurité de couche transport (ou la version la plus élevée en cours) doit être activée et utilisée. ** Remarque : ** Par défaut, le protocole SSL et toute la version de TLS à l'exception TLS 1,2 sont désactivés. Pour modifier ou activer ces valeurs, procédez comme suit :
    1.  Appuyez sur le logo key+R Windows pour ouvrir a ** exécution ** fenêtre.
    2.  Dans ** en cours ** le champ, tapez ** Regedit **, puis cliquez sur ** effectué correctement **.
    3.  Si a ** contrôle de compte d'utilisateur ** zone de message s'affiche, cliquez sur Oui ** **.
    4.  Dans ** éditeur de registre ** la fenêtre, accédez à ** HKEY\_\_LOCAL MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols **. Les clés suivantes ont été automatiquement entrées pour permettre qu'TLS 1,2 que :
        -   TLS 1.2Server : Enabled=1
        -   TLS 1.2Server : DisabledByDefault=0
        -   TLS 1.2Client : Enabled=1
        -   TLS 1.2Client : DisabledByDefault=0
        -   TLS 1.1Server : Enabled=0
        -   TLS 1.1Client : Enabled=0
        -   TLS 1.0Server : Enabled=0
        -   TLS 1.0Client : Enabled=0
        -   Protocole SSL 3.0Server : Enabled=0
        -   Protocole SSL 3.0Client : Enabled=0
        -   Protocole SSL 2.0Server : Enabled=0
        -   Protocole SSL 2.0Client : Enabled=0
-   Aucun port de réseaux supplémentaire ne doit être en cours, à moins qu'ils sont requis pour échéant, des motifs spécifiés.
-   partager de ressource de Croix- origine doit être désactivée et doit spécifier les origines autorisées qui sont acceptés.
-   Seuls les autorités de certificat de confiance doivent être utilisées pour obtenir des certificats qui seront utilisés sur les ordinateurs qui gèrent la station matérielle.

** Remarque : ** Il est primordial que vous avez examiné les recommandations de sécurité pour les services IIS et les besoins de (PCI) de secteur de carte de paiement.

## <a name="peripheral-simulator"></a>Simulateur périphérique
Pour plus d'informations, voir [simulateur périphérique au détail] (retail-peripheral-simulator.md).

## <a name="microsofttested-peripheral-devices"></a>Périphériques de périphérique de Microsofttested
### <a name="ipc-built-in-hardware-station"></a>Station de matériel (intégrée CPI)

Les périphériques suivants ont été testés à l'aide de la station de CPI qui est intégrée dans le Modern POS pour Windows.

#### <a name="printer"></a>Imprimante

| Fabricant | Modèle    | Interface | Commentaires                |
|--------------|----------|-----------|-------------------------|
| Epson        | Tm-T88IV | OPOS      |                         |
| Epson        | TM-T88V  | OPOS      |                         |
| Étoile         | TSP650II | OPOS      |                         |
| Étoile         | TSP650II | Personnalisée    | Connecté via le réseau   |
| Étoile         | mPOP     | OPOS      | Connecté via Bluetooth |
| HP           | F7M67AA  | OPOS      | USB activé             |

#### <a name="bar-code-scanner"></a>Scanneur de code-barres

| Fabricant  | Modèle         | Interface | Commentaires |
|---------------|---------------|-----------|----------|
| Motorola      | DS9208        | OPOS      |          |
| Honeywell     | 1900          | UWP       |          |
| Symbole        | LS2208        | OPOS      |          |
| HP intégré | E1L07AA       | OPOS      |          |
| Datalogic     | Magellan 8400 | OPOS      |          |

#### <a name="pin-pad"></a>Clavier d'identification personnelle

| Fabricant | Modèle  | Interface | Commentaires                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Nécessite la personnalisation du Business de paiement |

#### <a name="payment-terminal"></a>Terminal de paiement 

| Fabricant | Modèle | Interface | Commentaires                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Équinoxe      | L5300 | Personnalisée    | Nécessite la personnalisation du Business de paiement                                |
| VeriFone     | MX925 | Personnalisée    | Nécessite la personnalisation du Business de paiement ; connecté via le réseau et de l'USB |
| VeriFone     | MX915 | Personnalisée    | Nécessite la personnalisation du Business de paiement ; connecté via le réseau et de l'USB |

#### <a name="cash-drawer"></a>Caisse enregistreuse

| Fabricant | Modèle     | Interface | Commentaires                |
|--------------|-----------|-----------|-------------------------|
| Étoile         | mPOP      | OPOS      | Connecté via Bluetooth |
| APG          | Atwood    | Personnalisée    | Connecté via le réseau   |
| Étoile         | SMD2-1317 | OPOS      |                         |
| HP           | QT457AA   | OPOS      |                         |

#### <a name="line-display"></a>Affichage de ligne

| Fabricant  | Modèle   | Interface | Commentaires |
|---------------|---------|-----------|----------|
| HP intégré | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Capture de signature

| Fabricant | Modèle  | Interface | Commentaires |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Echelle

| Fabricant | Modèle         | Interface | Commentaires |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>LBM

| Fabricant | Modèle       | Interface | Commentaires |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="dedicated-iis-hardware-station"></a>Station matérielle dédiée IIS

Les périphériques suivants ont été testés à l'aide () d'une station matérielle non partagée dédiée IIS avec le Modern POS pour le POS Windows et de cloud.

#### <a name="printer"></a>Imprimante

| Fabricant | Modèle    | Interface | Commentaires                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Étoile         | TSP650II | OPOS      |                           |
| Étoile         | TSP650II | Personnalisée    | Connecté via le réseau     |
| Étoile         | TSP100   | OPOS      | Nécessite les conducteurs de TSP650II |
| HP           | F7M67AA  | OPOS      | USB activé               |

#### <a name="bar-code-scanner"></a>Scanneur de code-barres

| Fabricant  | Modèle   | Interface | Commentaires |
|---------------|---------|-----------|----------|
| Motorola      | DS9208  | OPOS      |          |
| Symbole        | LS2208  | OPOS      |          |
| HP intégré | E1L07AA | OPOS      |          |

#### <a name="pin-pad"></a>Clavier d'identification personnelle

| Fabricant | Modèle  | Interface | Commentaires                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Nécessite la personnalisation du Business de paiement |

#### <a name="payment-terminal"></a>Terminal de paiement 

| Fabricant | Modèle | Interface | Commentaires                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Équinoxe      | L5300 | Personnalisée    | Nécessite la personnalisation du Business de paiement                                |
| VeriFone     | MX925 | Personnalisée    | Nécessite la personnalisation du Business de paiement ; connecté via le réseau et de l'USB |
| VeriFone     | MX915 | Personnalisée    | Nécessite la personnalisation du Business de paiement ; connecté via le réseau et de l'USB |

#### <a name="cash-drawer"></a>Caisse enregistreuse

| Fabricant | Modèle     | Interface | Commentaires              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personnalisée    | Connecté via le réseau |
| Étoile         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

#### <a name="line-display"></a>Affichage de ligne

| Fabricant  | Modèle   | Interface | Commentaires |
|---------------|---------|-----------|----------|
| HP intégré | G6U79AA | OPOS      |          |
| Epson         | M58DC   | OPOS      |          |

#### <a name="signature-capture"></a>Capture de signature

| Fabricant | Modèle  | Interface | Commentaires |
|--------------|--------|-----------|----------|
| Scriptel     | ST1550 | OPOS      |          |

#### <a name="scale"></a>Echelle

| Fabricant | Modèle         | Interface | Commentaires |
|--------------|---------------|-----------|----------|
| Datalogic    | Magellan 8400 | OPOS      |          |

#### <a name="msr"></a>LBM

| Fabricant | Modèle       | Interface | Commentaires |
|--------------|-------------|-----------|----------|
| Magtek       | 21073075    | UWP       |          |
| Magtek       | 21073062    | OPOS      |          |
| HP           | IDRA-334133 | OPOS      |          |

### <a name="shared-iis-hardware-station"></a>Station matérielle partagée IIS

Les périphériques suivants ont été testés à l'aide d'une station matérielle partagée IIS avec le Modern POS pour le POS Windows et de cloud. ** Remarque : ** Seule une imprimante, un terminal de paiement, et un tiroir-caisse sont pris en charge.

#### <a name="printer"></a>Imprimante

| Fabricant | Modèle    | Interface | Commentaires                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Étoile         | TSP650II | OPOS      |                           |
| Étoile         | TSP650II | Personnalisée    | Connecté via le réseau     |
| Étoile         | TSP100   | OPOS      | Nécessite les conducteurs de TSP650II |
| HP           | F7M67AA  | OPOS      | USB activé               |

#### <a name="payment-terminal"></a>Terminal de paiement 

| Fabricant | Modèle | Interface | Commentaires                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| VeriFone     | MX925 | Personnalisée    | Nécessite la personnalisation du Business de paiement ; connecté via le réseau et de l'USB |
| VeriFone     | MX915 | Personnalisée    | Nécessite la personnalisation du Business de paiement ; connecté via le réseau et de l'USB |

#### <a name="cash-drawer"></a>Caisse enregistreuse

| Fabricant | Modèle     | Interface | Commentaires              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personnalisée    | Connecté via le réseau |
| Étoile         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |

## <a name="troubleshooting"></a>Dépannage
### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>Le Modern POS peut détecter la station matérielle de la liste de sélection, mais il ne peut pas effectuer s'accoupler

** Solution : ** Vérifiez la liste suivante de panne potentiel points :

-   L'ordinateur qui est Modern POS actuel fait approuver le certificat utilisé sur l'ordinateur qui exécute la station matérielle.
    -   Pour vérifier ce paramétrage, dans un navigateur Web, accédez à l'adresse suivante : nom&lt;de https://Computer&gt;:&lt;Numéro d'accès&gt;/HardwareStation/cinglement.
    -   Celle-ci utilise ping pour vérifier que l'ordinateur est accessible, et le navigateur indique si le certificat sont approuvées. (Par exemple, dans Internet Explorer, une icône de verrouillage s'affiche dans la barre d'adresse. Lorsque vous cliquez sur cette icône, Internet Explorer vérifie si le certificat est actuellement fait confiance. Vous pouvez installer le certificat de l'ordinateur local en affichant les détails du certificat qui s'affiche.)
-   Sur l'ordinateur qui exécute la station matérielle, le port utilisé par la station matérielle est ouvert dans le Pare-feu.
-   La station matérielle est correctement installé les informations de compte du marchand via l'outil de les informations du marchand d'installer qui exécute à la fin de le programme d'installation de station matérielle.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>Le Modern POS ne peut pas détecter la station matérielle de la liste de sélection

** Solution : ** Vous pouvez procéder à des facteurs suivants peut entraîner ce problème :

-   La station matérielle n'a pas été correctement paramétrée dans Retail Headquarters. Les étapes plus haut dans cette rubrique pour vérifier que le profil de station matérielle et la station matérielle sont correctement entrés.
-   Les tâches qui n'ont pas été exécutées de mettre la configuration à jour de canal. Dans ce cas, exécutez la tâche 1070 pour la configuration des canaux.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>Le Modern POS ne reflète pas de nouveaux paramètres du tireur

** Solution : ** Fermez le lot actuel. Les modifications vers le tiroir-caisse ne sont pas mises à jour au Modern POS tant que le lot actuel soit fermé.

### <a name="modern-pos-is-reporting-an-issue-with-a-retail-peripheral"></a>Le Modern POS inclut un problème avec un périphérique de vente au détail

** Solution : ** Voici quelques causes des ce problème :

-   Assurez-vous que d'autres utilitaires de configuration de pilote du périphérique sont clôturés. Si ces utilitaires sont en cours, ils peuvent empêcher le Modern POS ou la station matérielle de réclamer le périphérique.
-   Si le périphérique au détail est partagé avec les périphériques plusieurs POS, assurez-vous qu'il appartient à une des catégories suivantes :
    -   Caisse enregistreuse
    -   Imprimante réception
    -   Terminal de paiement 

    Si le périphérique n'appartient pas à une de ces catégories, la station matérielle n'est pas conçue pour activer le périphérique à partager entre les périphériques plusieurs du PDV.
-   Parfois, les conducteurs de périphérique peuvent effectuer pour arrêter les objets (CCOs) de contrôle commun de fonctionner correctement. Si un périphérique a été récemment installé, mais il ne fonctionne pas correctement ou vous remarquez d'autres éléments, vous pouvez souvent résoudre le problème en réinstallant le CCOs. Pour télécharger le CCOs, contactez http://monroecs.com/oposccos_current.htm>.
-   Si vous apportez des modifications périphériques sont au cours de le test ou le dépannage, vous devrez peut-être réinitialiser IIS au lieu d'attendre le cache d'actualiser. Pour réinitialiser IIS, procédez comme suit :
    1.  ** Début ** du menu, type ** CMD **.
    2.  Dans les résultats de la recherche, cliquez avec le bouton droit ** invite de commandes **, puis cliquez sur ** exécuté comme administrateur **.
    3.  Dans ** invite de commandes ** la fenêtre, le type ** iisreset /Restart ** puis appuyez sur la touche Entrée.
    4.  Une fois qu'IIS est redémarré, redémarrez le Modern POS.
-   Alors que vous apportez les modifications sont les périphériques périphériques, si vous utilisez fréquemment également et quittez le client du PDV, le processus de dllhost d'une session précédente POS peut gêner la session actuelle. Dans ce cas, un appareil ne peut pas être utilisable jusqu'à ce que la fermeture de le serveur de (DLL) de la bibliothèque de dynamique- lien qui gère la session précédente. Pour fermer le serveur de DLL, procédez comme suit :
    1.  ** Début ** du menu, tapez ** responsable de tâche **.
    2.  Dans les résultats de la recherche, cliquez sur ** responsable de tâche **.
    3.  Dans Gestionnaire de tâche, sous ** les détails ** l'onglet, cliquez sur l'en-tête de colonne qui est marquée ** nom ** à la table par ordre alphabétique des noms.
    4.  Faites défiler l'écran jusqu'à ce que vous en trouviez dllhost.exe.
    5.  Sélectionnez chaque serveur de DLL, puis cliquez sur ** tâche de fin **.
    6.  Une fois les serveurs de DLL ont été terminées, redémarrez le Modern POS.


<a name="see-also"></a>Voir également :
--------

[Simulateur périphérique au détail] (retail-peripheral-simulator.md)


