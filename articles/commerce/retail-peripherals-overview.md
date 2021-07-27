---
title: Périphériques
description: Cette rubrique explique les concepts relatifs aux périphériques de Commerce.
author: rubencdelgado
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTerminalTable, RetailDevice, RetailHardwareProfile
audience: Application User, IT Pro
ms.reviewer: josaw
ms.custom:
- "268444"
- intro-internal
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: df7cb4810b83d74725df3d59b7b08da1e8cf4a53
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345030"
---
# <a name="peripherals"></a>Périphériques

[!include[banner](includes/banner.md)]

Cette rubrique explique les concepts relatifs aux périphériques de magasin. Elle décrit les différentes méthodes de connexion des périphériques au point de vente (PDV) ainsi que les composants en charge de gérer la connexion avec le PDV.

## <a name="concepts"></a>Concepts

### <a name="pos-registers"></a>Caisses enregistreuses de PDV

Navigation : cliquez sur **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **Caisses enregistreuses**. Le registre du point de vente (PDV) est une entité utilisée pour définir les caractéristiques d’une instance spécifique du PDV. Ces caractéristiques comprennent le profil matériel ou la configuration des périphériques utilisés dans le registre, le magasin sur lequel est mappé le registre ainsi que l’expérience visuelle de l’utilisateur qui se connecte à ce registre.

### <a name="devices"></a>Périphériques

Navigation : cliquez sur **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **Périphériques**. Un périphérique est une entité qui représente une instance physique d’un périphérique qui est mappé à une caisse enregistreuse de PDV. Lorsqu’un périphérique est créé, il est mappé sur la caisse enregistreuse d’un PDV. L’entité de périphérique assure le suivi des informations lorsqu’une caisse enregistreuse est activée, le type de client qui est utilisé et le package d’applications qui a été déployé sur un périphérique spécifique. 

Les appareils peuvent être associés aux types d’application suivants : Retail Modern POS, Retail Cloud POS, Retail Modern POS – Windows Phone, Retail Modern POS – Android et Retail Modern POS – iOS.

### <a name="modern-pos"></a>PDV moderne

Modern POS est le programme de PDV pour Microsoft Windows. Il peut être déployé sur les systèmes d’exploitation (OS) Windows 10.

### <a name="cloud-pos"></a>PDV Cloud

Cloud POS est une version basée sur navigateur du programme Modern POS, accessible par un navigateur Web.

### <a name="modern-pos-for-ios"></a>Modern POS pour iOS

Modern POS pour iOS est une version basée sur iOS du programme Modern POS qui peut être déployée sur les périphériques iOS.

### <a name="modern-pos-for-android"></a>Modern POS pour Android

Modern POS pour Android est une version basée sur Android du programme Modern POS qui peut être déployée sur les périphériques Android.

### <a name="pos-peripherals"></a>Périphériques de PDV

Les périphériques de PDV sont des périphériques qui sont explicitement pris en charge pour les fonctions de PDV. Ces périphériques sont généralement divisés en classes spécifiques. Pour plus d’informations sur ces classes, voir la section Classes de périphérique dans cette rubrique.

### <a name="hardware-station"></a>Hardware Station

Navigation : cliquez sur **Commerce et vente au détail** &gt; **Canaux** &gt; **Magasins** &gt; **Tous les magasins**. Sélectionnez un magasin, puis cliquez sur l’organisateur **Stations matérielles**. Le paramètre **Station matérielle** est un paramètre de niveau canal utilisé pour définir des instances où la logique de périphérique doit être déployée. Ce paramètre au niveau du canal sert à déterminer les spécifications de la station matérielle. Il permet également de répertorier les stations matérielles disponibles pour une instance de Modern POS dans un magasin donné. La station matérielle est intégrée dans les programmes Modern POS pour Windows et Android. La station matérielle peut également être déployée indépendamment en tant que programme Microsoft IIS autonome. Dans ce cas, elle est accessible par le réseau.

### <a name="hardware-profile"></a>Profil matériel

Navigation : cliquez sur **Retail et Commerce** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **Profils POS** &gt; **Profils du matériel**. Le profil du matériel est une liste de périphériques configurés pour un registre de PDV ou une station matérielle. Le profil du matériel peut être mappé directement sur un registre de PDV ou une station matérielle.

## <a name="devices-classes"></a>Classes de périphériques
Les périphériques de PDV sont généralement divisés en classes. Cette section décrit et offre une vue d’ensemble des périphériques pris en charge par Modern POS.

### <a name="printer"></a>Imprimante

Les imprimantes comprennent les imprimantes traditionnelles de tickets de PDV et les imprimantes pleine page. Les imprimantes sont prises en charge via les liaisons et l’intégration d’objets pour les périphériques Retail POS (OPOS) et les interfaces de pilotes Microsoft Windows. Il est possible d’utiliser jusqu’à deux imprimantes en même temps. Cette capacité prend en charge les cas où les tickets clients des transactions au comptant sans livraison sont imprimés sur les imprimantes de ticket, alors que les commandes client, qui contiennent plus d’informations, sont imprimées sur une imprimante pleine page. Les imprimantes de tickets peuvent être connectées directement à un ordinateur par USB, à un réseau par Ethernet, ou être connectées par Bluetooth.

### <a name="scanner"></a>Scanneur

Il est possible d’utiliser jusqu’à deux lecteur de codes-barres en même temps. Cette capacité prend en charge les cas où, pour accélérer le passage en caisse, il faut utiliser un lecteur plus mobile pour scanner les articles lourds ou volumineux, alors que le lecteur fixe intégré sert à scanner les articles de taille standard. Les lecteurs peuvent être pris en charge par OPOS, par la plateforme UWP (Universal Windows Platform), ou par les interfaces clavier wedge. Un lecteur peut être connecté à un ordinateur par USB ou par Bluetooth.

### <a name="msr"></a>LBM

Il est possible de configurer un lecteur de bande magnétique (LBM) USB à l’aide des pilotes OPOS. Si vous souhaitez utiliser un LBM autonome pour les transactions de paiement par transfert électronique de fonds (EFT), le LBM doit être géré par un connecteur de paiement. Les LBM autonomes peuvent être utilisés pour l’entrée des points de fidélité des clients, la connexion des employés et l’entrée des cartes-cadeaux, indépendamment du connecteur de paiement.

### <a name="cash-drawer"></a>Caisse enregistreuse

Il est possible de prendre en charge deux caisses enregistreuses par profil matériel. Cette capacité permet que deux équipes actives par caisse enregistreuse soient disponibles simultanément. Dans le cas d’une équipe partagée, ou d’une caisse enregistreuse utilisée par plusieurs périphériques mobiles de PDV simultanément, une seule caisse enregistreuse est autorisée par profil matériel. Les caisses enregistreuses peuvent être connectées directement à un ordinateur par USB, à un réseau par Ethernet, ou être connectées à une imprimante de tickets via une interface RJ12. Dans certains cas, les caisses enregistreuses peuvent également être connectées par Bluetooth.

### <a name="line-display"></a>Affichage de ligne

Les affichages de ligne servent à afficher les produits, les soldes de transactions, ainsi que d’autres informations utiles au client lors d’une transaction. Une ligne d’affichage peut être connectée à l’ordinateur par USB à l’aide des pilotes OPOS.

### <a name="signature-capture"></a>Capture de signature

Les périphériques de capture de signature peuvent être connectés directement à un ordinateur par USB à l’aide des pilotes OPOS. Lorsque la capture de signature est configurée, le client est invité à signer sur le périphérique. Une fois la signature fournie, elle s’affiche au caissier pour qu’il l’accepte.

### <a name="scale"></a>Echelle

Il est possible de connecter des balances à l’ordinateur par USB à l’aide des pilotes OPOS. Lorsqu’un produit marqué comme produit « pesé » est ajouté à une transaction, le PDV relève le poids sur la balance, ajoute le produit à la transaction et utilise la quantité indiquée par la balance.

### <a name="pin-pad"></a>Clavier d’identification personnelle

Les plaquettes PIN (Personal identification number) sont prises en charge via OPOS, mais elles doivent être gérées via un connecteur de paiement.

### <a name="secondary-display"></a>Affichage secondaire

Lorsqu’un affichage secondaire est configuré, l’affichage de Windows numéro 2 est utilisé pour afficher les informations de base. L’objectif de l’affichage secondaire est de prendre en charge une extension logicielle d’éditeur indépendant car, en étant prêt à l’emploi, l’affichage vue secondaire n’est pas configurable et affiche un contenu limité.

### <a name="payment-device"></a>Appareil de paiement

La prise en charge des périphériques de paiement est implémentée par l’intermédiaire du connecteur de paiement. Les périphériques de paiement peuvent remplir une ou plusieurs des fonctions assurées par d’autres classes de périphérique. Par exemple, un périphérique de paiement peut fonctionner comme un lecteur de carte/LBM, une ligne affichage, un dispositif de capture de signature, ou une plaquette PIN. La prise en charge des périphériques de paiement est implémentée indépendamment de la prise en charge de périphérique autonome fournie pour les autres périphériques qui sont inclus dans le profil du matériel.

## <a name="supported-interfaces"></a>Interfaces prises en charge
### <a name="opos"></a>OPOS

Pour permettre d’utiliser la plus large gamme possible de périphériques avec Commerce, la norme OLE pour le secteur des PDV est la principale plateforme de périphériques prise en charge. La norme OLE pour le secteur des PDV a été produite par NRF (National Retail Federation), qui établit les protocoles de transmission standard pour les périphériques. OPOS est une implémentation largement adoptée de la norme OLE pour le secteur des PDV. Il a été développé dans le milieu des années 1990 et a depuis lors été plusieurs fois actualisé. OPOS fournit une architecture de pilote de périphérique qui permet l’intégration facile des matériels de PDV avec les systèmes de PDV fondés sur Windows. Les contrôles OPOS gèrent les communications entre les matériels compatibles et le logiciel de PDV. Un contrôle OPOS est composé de deux parties :

-   **Objet de contrôle** – L’objet de contrôle pour une classe de périphérique (comme une ligne d’affichage) fournit l’interface du programme logiciel. Monroe Consulting Services ([www.monroecs.com](http://www.monroecs.com/)) fournit un ensemble normalisé d’objets de contrôle OPOS qui sont appelés objets de contrôle commun (CCO). Les CCO sont utilisés pour tester le composant PDV de Commerce. Par conséquent, les tests garantissent que, si Commerce prend en charge une classe de périphériques par OPOS, de nombreux types de périphérique peuvent être pris en charge, à condition que le fabricant fournisse un objet de service conçu pour OPOS. Il n’est pas nécessaire de tester explicitement chaque type de périphérique.
-   **Objet de service** – L’objet de service fournit les communications entre l’objet de contrôle (CCO) et le périphérique. Généralement, l’objet de service pour un périphérique est fourni par le fabricant de celui-ci. Toutefois, dans certains cas, vous devez télécharger l’objet de service à partir du site web du fabricant. Par exemple, il peut s’y trouver un objet de service plus récent disponible. Pour trouver l’adresse du site Web du fabricant, consultez la documentation de votre matériel.

[![Objet de contrôle et objet de service.](./media/retail_peripherals_overview01.png)](./media/retail_peripherals_overview01.png) La prise en compte de la norme OLE pour l’implémentation d’OPOS pour les PDV garantit que, si les fabricants de périphérique et les éditeurs de PDV implémentent la norme correctement, les systèmes de PDV et les périphériques pris en charge peuvent fonctionner ensemble, même s’ils n’ont pas été testés ensemble au préalable. 

> [!NOTE]
> La prise en charge d’OPOS ne garantit pas la prise en charge de tous les périphériques dotés de pilotes OPOS. Commerce doit d’abord prendre en charge ce type de périphérique, ou la classe, via OPOS. En outre, les objets de service ne peuvent pas toujours être à jour avec la dernière version des CCO. Vous devez également tenir compte du fait que, de manière générale, la qualité des objets de service est variable.

### <a name="windows"></a>Windows

L’impression de tickets au PDV est optimisée pour OPOS. L’impression via OPOS tend à être beaucoup plus rapide que l’impression via Windows. Par conséquent, il est conseillé d’utiliser OPOS, en particulier dans les environnements où l’on imprime des tickets à 40 colonnes et où les délais de transaction doivent être rapides. Pour la plupart des périphériques, vous utiliserez des contrôles OPOS. Toutefois, certaines imprimantes de tickets OPOS prennent également en charge les pilotes Windows. En utilisant un pilote Windows, vous pouvez accéder aux polices les plus récentes et mettre en réseau une seule imprimante pour plusieurs registres. Toutefois, il y a des inconvénients à utiliser les pilotes Windows. Voici quelques exemples de ces inconvénients :

-   lors de l’utilisation des pilotes Windows, les images sont rendues avant l’impression. Par conséquent, l’impression tend à être plus lente que sur les imprimantes qui utilisent les contrôles OPOS.
-   Les périphériques connectés par l’imprimante (« en guirlande ») peuvent ne pas fonctionner correctement lors de l’utilisation des pilotes Windows. Par exemple, la caisse enregistreuse peut ne pas s’ouvrir, ou l’imprimante de bordereau peut ne pas fonctionner comme prévu.
-   OPOS prend également en charge un ensemble plus étendu de variables spécifiques aux imprimantes de tickets, telles que l’impression de bordereau ou la coupe du papier.
-   Les imprimantes Windows ne sont pas prises en charge par la station matérielle IIS. 

Si les contrôles OPOS sont disponibles pour l’imprimante Windows que vous utilisez, l’imprimante doit encore fonctionner correctement avec Commerce.

### <a name="universal-windows-platform"></a>Universal Windows Platform

UWP, dans le cas des périphériques, est liée à la prise en charge Windows des périphériques plug-and-play. Lorsqu’un périphérique plug-and-play est connecté à une version de SE Windows qui prend en charge ce type de périphérique, aucun pilote n’est nécessaire pour que le périphérique fonctionne comme prévu. Par exemple, si Windows détecte un périphérique de haut-parleur Bluetooth, le SE sait que le périphérique est du type de classe **Haut-parleur**. Par conséquent, il traite ce périphérique comme un haut-parleur. Aucune configuration supplémentaire n’est requise. Dans le cas de périphériques de PDV, il est possible de connecter de nombreux périphériques USB, et Windows les reconnaît comme périphériques HID (Human Interface Device). Toutefois, il peut ne pas pouvoir déterminer les fonctionnalités assurées par le périphérique, parce que celui-ci ne spécifie pas sa classe ou son type. Dans Windows 10, les classes de périphérique pour les lecteurs de code-barres et les LBM ont été ajoutés. Par conséquent, si un périphérique se déclare à Windows 10 comme périphérique d’une de ces classes, Windows détectera les événements du périphérique en temps opportun. Modern POS prend en charge les LBM et les lecteurs UWP. Par conséquent, lorsqu’il est prêt à recevoir l’entrée de l’un de ces périphériques, et qu’un périphérique qui appartient à une de ces classes est connecté, le périphérique peut être utilisé. Par exemple, si un lecteur de codes-barres UWP est branché à un ordinateur Windows 10, et que la connexion de code-barres est configurée pour Modern POS, le lecteur de code-barres devient actif dans l’écran de connexion. Aucune configuration supplémentaire n’est requise. D’autres classes supplémentaires de périphériques UWP de point de service sont en cours d’ajout à Windows. Ces classes incluent des classes pour les caisses enregistreuses et les imprimantes de tickets. La prise en charge de ces nouvelles classes de périphérique dans Modern POS est en attente.

### <a name="keyboard-wedge"></a>Clavier wedge

Les périphériques clavier wedge envoient des données à l’ordinateur comme si ces données étaient saisies au clavier. Par conséquent, par défaut, le champ actif dans le système PDV recevra les données qui sont lues par scanner ou passage de carte. Dans certains cas, ce comportement peut entraîner qu’un type de données erroné soit lu vers un champ. Par exemple, un code-barres peut être lu vers un champ prévu pour la saisie des données de carte de crédit. Dans de nombreux cas, il existe une logique au niveau du PDV qui détermine si les données qui sont lues par scanner ou passage de carte sont un code-barres ou un passage de carte. En conséquence, les données sont traitées correctement. Toutefois, lorsque des périphériques sont configurés comme OPOS au lieu de périphériques clavier Wedge, la manière de consommer les données issues de ces périphériques est mieux contrôlée car « on en sait davantage » sur le périphérique d’où proviennent les données. Par exemple, les données issues d’un lecteur de codes-barres sont automatiquement identifiées comme un code-barres, et l’enregistrement associé dans la base de données est trouvée plus facilement et plus rapidement que par une recherche de chaîne générique, comme dans le cas de périphériques de clavier wedge.

> [!NOTE]
> Lorsque des scanners de clavier « wedge » sont utilisés dans le PDV, ils doivent être programmés pour envoyer un retour chariot, ou événement **Entrée**, après le dernier caractère scanné. Si cette configuration n’est pas effectuée, les scanners de clavier « wedge » ne fonctionneront pas correctement. Consultez la documentation fournie par le fabricant de votre appareil pour savoir comment ajouter l’événement de retour chariot.  

### <a name="native-printer"></a>Imprimante native

Les imprimantes natives (où « périphériques » car le type est défini dans le profil du matériel) peuvent être configurées pour inviter l’utilisateur à sélectionner une imprimante configurée pour l’ordinateur. Lorsqu’une imprimante du type **Device**, si Modern POS rencontre une commande d’impression, l’utilisateur est invité à sélectionner une imprimante dans une liste. Ce comportement diffère du comportement pour les pilotes Windows, car le type d’imprimante **Windows** dans le profil du matériel n’affiche aucune liste d’imprimantes. Au lieu de cela, il nécessite qu’une imprimante nommée soit indiquée dans le champ **Nom du périphérique**.

### <a name="network"></a>Réseau

Les caisses enregistreuses adressables en réseau, les imprimantes de tickets et les terminaux de paiement peuvent être utilisés sur un réseau, soit directement via la station matérielle IPC (Interprocess Communications) qui est intégrée dans le Modern POS de l’application Windows ou via la station matérielle IIS pour les autres clients Modern POS.

## <a name="hardware-station-deployment-options"></a>Options de déploiement de station matérielle

### <a name="dedicated"></a>Dédié(e)

Les clients Modern POS pour Windows et Android comprennent des stations matérielles intégrées ou **dédiées**. Ces clients peuvent communiquer directement avec les périphériques à l’aide d’une logique métier intégrée aux applications. L’application Android ne prend en charge que les périphériques réseau. Pour plus d’informations sur la prise en charge de périphériques pour Android, consultez l’article [Configurer l’application POS Hybrid sur Android et iOS](./dev-itpro/hybridapp.md).

Pour utiliser la station matérielle dédiée, affectez un profil matériel à un registre qui utilise Modern POS pour les applications Windows ou Android. Créez ensuite une station matérielle du type **Dédié** pour le magasin où le registre sera utilisé. Démarrez Modern POS en mode sans tiroir et utilisez l’opération **Gérer les stations matérielles** pour activer les capacités de la station matérielle, la station matérielle dédiée est active par défaut. Ensuite, déconnectez-vous de Modern POS, puis reconnectez-vous et ouvrez une équipe de travail et les périphériques configurés dans le profil matériel sont utilisables. 

### <a name="shared"></a>Partagé(e) 

Également parfois appelée station matérielle IIS, « IIS » impliquant que l’application POS se connecte à la station matérielle via Microsoft Internet Information Services. L’application de PDV se connecte à la station matérielle IIS via les services Web qui s’exécutent sur un ordinateur où les périphériques sont connectés. Si la station matérielle partagée est utilisée, les périphériques associés à une station matérielle peuvent être utilisés par n’importe quelle caisse enregistreuse de PDV située sur le même réseau que la station matérielle IIS. Étant donné que seul Modern POS pour Windows et Android inclut la prise en charge intégrée des périphériques, toutes les autres applications Modern POS doivent utiliser la station matérielle IIS pour communiquer avec les périphériques de PDV configurés dans le profil matériel. Par conséquent, chaque instance de la station matérielle IIS nécessite un ordinateur qui exécute le service Web et l’application qui communique avec les périphériques. 

La station matérielle partagée peut être utilisée pour autoriser plusieurs clients de point de vente à partager les périphériques ou peut être utilisée pour gérer un ensemble validé ou des périphériques pour un seul point de vente. 

Lorsqu’une station matérielle est utilisée pour prendre en charge le partage des périphériques entre plusieurs clients POS, seuls les tiroirs-caisses, les imprimantes de tickets de caisse et les terminaux de paiement doivent être utilisés. Vous ne pouvez pas connecter directement les lecteurs de code-barres, les LBM, les afficheurs de lignes, les balances ou d’autres périphériques. Dans le cas contraire, des conflits apparaîtront quand plusieurs appareils de PDV essaieront de revendiquer ces périphériques simultanément. Voici comment les conflits sont gérés pour les périphériques pris en charge :

-   **Tiroir-caisse** – le tiroir-caisse est ouvert via un événement envoyé au périphérique. Le seul problème qui peut se produire lors de l’appel d’un tiroir-caisse apparaît lorsque le tiroir est déjà ouvert. Dans le cas des stations matérielles partagées, le tiroir-caisse doit être défini comme **Partagé** dans le profil matériel. Ce paramètre empêche le PDV de vérifier si le tiroir-caisse est déjà ouvert lorsqu’il envoie des commandes d’ouverture.
-   **Imprimante de tickets** – Si deux commandes d’impression de ticket sont envoyées à la station matérielle au même moment, une des commandes peut être perdue, selon le périphérique. Certains périphériques ont une mémoire interne ou une mise en commun qui peut éviter ce problème. Si une commande d’impression échoue, le caissier reçoit un message d’erreur et peut réessayer la commande d’impression à partir du PDV.
-   **Terminal de paiement** – Si un caissier essaie de soumettre une transaction à un terminal de paiement qui est déjà utilisé, un message l’informe que le terminal est utilisé et lui demande de réessayer ultérieurement. Généralement, les caissiers peuvent voir qu’un terminal est déjà utilisé et attendre que l’autre transaction soit terminée avant d’essayer à nouveau.

La validation est prévue dans une version à venir, pour le détecter si les périphériques non pris en charge sont paramétrés pour un profil matériel mis en correspondance avec une station matérielle partagée. Si des périphériques non pris en charge sont détectés, l’utilisateur reçoit un message lui indiquant que les périphériques ne sont pas pris en charge pour les stations matérielles partagées. Dans le cas des stations matérielles partagées, l’option **Sélectionner à la soumission** est définie sur **Oui** au niveau du registre. L’utilisateur du PDV est alors invité à sélectionner une station matérielle lorsqu’une soumission est sélectionnée pour une transaction au niveau du PDV. Lorsque la station matérielle est sélectionnée seulement au moment de la soumission, cette sélection est ajoutée directement au workflow du PDV pour les scénarios mobiles. Avantage supplémentaire, l’affichage de ligne au niveau du terminal de paiement n’est pas utilise dans les scénarios de partage. Si le terminal de paiement est utilisé comme affichage de ligne, les autres utilisateurs peuvent être empêchés d’utiliser ce terminal tant que la transaction n’est pas terminée. Dans les scénarios mobiles, il est possible d’ajouter des lignes à une transaction pendant plus longtemps. Par conséquent, l’option **Sélectionner à la soumission** est obligatoire pour garantir la disponibilité optimale du périphérique.

### <a name="network-peripherals"></a>Périphériques réseau

La désignation réseau des périphériques dans le profil matériel permet que les tiroirs-caisses, les imprimantes de tickets et les terminaux de paiement soient connectés via une connexion réseau.

#### <a name="modern-pos-for-windows"></a>Modern POS pour Windows

Vous pouvez spécifier l’adresse IP des périphériques réseau à deux endroits. Si le client Modern POS Windows utilise un seul ensemble de périphériques réseau, vous devez définir les adresse IP de ces périphériques à l’aide de l’option **Configuration IP** dans le volet Actions pour le registre lui-même. Dans le cas de périphériques réseau qui doivent être partagés entre les registres de PDV, un profil matériel ayant des périphériques réseau attribués peut être mis en correspondance directement avec une station matérielle partagée. Pour affecter les adresse IP, sélectionnez la station matérielle dans la page **Magasins**, puis utilisez l’option **Configuration IP** dans la section **Stations matérielles** pour spécifier les périphériques réseau affectés à cette station matérielle. Pour les stations matérielles qui n’ont que des périphériques réseau, vous n’avez pas à déployer la station matérielle elle-même. Dans ce cas, la station matérielle est requise uniquement pour regrouper conceptuellement les périphériques adressables en réseau en fonction de leur emplacement dans le magasin.

#### <a name="cloud-pos-and-modern-pos-for-ios"></a>PDV cloud et Modern POS pour iOS

La logique qui gère les périphériques connectés physiquement ceux qui sont adressables en réseau est contenue dans la station matérielle. Par conséquent, pour tous les clients POS, à l’exception de Modern POS pour Windows et Android, une station matérielle IIS doit être déployée et active pour permettre au PDV de communiquer avec les périphériques, indépendamment du fait que ces périphériques sont connectés physiquement à une station matérielle ou adressés sur le réseau.

## <a name="setup-and-configuration"></a>Paramétrage et configuration
### <a name="hardware-station-installation"></a>Installation de la station matérielle

Pour plus d’informations, voir [Configurer et installer la station matérielle](retail-hardware-station-configuration-installation.md).

### <a name="modern-pos-for-windows-setup-and-configuration"></a>Paramétrage et configuration de Modern POS pour Windows

Pour plus d’informations, voir [Configurer, installer et activer Modern POS (MPOS)](retail-modern-pos-device-activation.md).

### <a name="modern-pos-for-android-and-ios-setup-and-configuration"></a>Paramétrage et configuration de Modern POS pour Windows et Android

Pour plus d’informations, voir [Configurer l’application POS Hybrid sur Android et iOS](./dev-itpro/hybridapp.md).

### <a name="opos-device-setup-and-configuration"></a>Paramétrage et configuration de périphérique OPOS

Pour plus d’informations sur les composants OPOS, voir la section « Interfaces prises en charge » de ce document. De manière générale, les pilotes OPOS sont fournis par le fabricant du périphérique. Lorsqu’un pilote de périphérique OPOS est installé, il ajoute une clé au registre de Windows dans l’un des emplacements suivants :

-   **Système 32 bits :** HKEY\_LOCAL\_MACHINESOFTWAREOLEforRetailServiceOPOS
-   **Système 64 bits :** HKEY\_LOCAL\_MACHINESOFTWAREWOW6432NodeOLEforRetailServiceOPOS

Dans l’emplacement du registre ServiceOPOS, les périphériques configurés sont organisés selon leur classe de périphérique OPOS. Plusieurs pilotes de périphérique sont stockés.

## <a name="supported-scenarios-by-hardware-station-type"></a>Scénarios pris en charge par type de station matérielle
### <a name="client-support--ipc-hardware-station-vs-iis-hardware-station"></a>Prise en charge du client – Station matérielle IPC / Station matérielle IIS

Le tableau suivant indique les topologies et les scénarios de déploiement pris en charge.

| Client      | Station matérielle IPC | Station matérielle IIS |
|-------------|----------------------|----------------------|
| Application Windows | Oui                  | Oui                  |
| PDV Cloud   | Non                   | Oui                  |
| Android     | Oui                  | Oui                  |
| iOS         | Non                   | Oui                  |

### <a name="network-peripherals"></a>Périphériques réseau

Les périphériques réseau peuvent être pris en charge directement par la station matérielle dans l’application Modern POS pour les applications Windows et Android. Pour tous les autres clients, vous devez déployer une station matérielle IIS.

| Client      | Station matérielle IPC | Station matérielle IIS |
|-------------|----------------------|----------------------|
| Application Windows | Oui                  | Oui                  |
| PDV Cloud   | Non                   | Oui                  |
| Android     | Oui                  | Oui                  |
| iOS         | Non                   | Oui                  |

## <a name="supported-device-types-by-hardware-station-type"></a>Types de périphériques pris en charge par type de station matérielle
### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS pour Windows avec une station matérielle IPC (intégrée)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe de périphérique prise en charge</th>
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
<li>UWP (aucun paramétrage nécessaire.)</li>
<li>Clavier wedge (aucun paramétrage nécessaire.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Créateur</td>
<td><ul>
<li>OPOS</li>
<li>Réseau </br><strong>Remarque :</strong> Un seul tiroir-caisse peut être paramétré si <strong>Utiliser les équipes de travail partagées</strong> est configuré sur le tiroir-caisse.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tiroir-caisse 2</td>
<td><ul>
<li>OPOS</li>
<li>Réseau </br><strong>Remarque :</strong> Un seul tiroir-caisse peut être paramétré si <strong>Utiliser les équipes de travail partagées</strong> est configuré sur le tiroir-caisse.</li>
</ul></td>
</tr>
<tr class="even">
<td>Scanneur</td>
<td><ul>
<li>OPOS</li>
<li>UWP (aucun paramétrage nécessaire.)</li>
<li>Clavier wedge (aucun paramétrage nécessaire.)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Scanneur 2</td>
<td><ul>
<li>OPOS</li>
<li>UWP (aucun paramétrage nécessaire.)</li>
<li>Clavier wedge (aucun paramétrage nécessaire.)</li>
</ul></td>
</tr>
<tr class="even">
<td>Echelle</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Clavier d’identification personnelle</td>
<td>OPOS (la prise en charge est disponible via la personnalisation du connecteur de paiement.)</td>
</tr>
<tr class="even">
<td>Capture de signature</td>
<td>OPOS</td>
</tr>
<tr class="odd">
<td>Terminal de paiement</td>
<td><ul>
<li>Prise en charge de périphérique personnalisée</li>
<li>Réseau (pour plus d’informations, voir la documentation du connecteur de paiement.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-that-have-a-committed-shared-iis-hardware-station"></a>Tous les clients Modern POS qui ont une station matérielle IIS « partagée » validée

> [!NOTE]
> Lorsque la station matérielle IIS est « validée », il existe une relation un-à-un entre le client PDV et la station matérielle.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe de périphérique prise en charge</th>
<th>Interfaces prises en charge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Imprimante</td>
<td><ul>
<li>OPOS</li>
<li>Réseau</li>
</ul></td>
</tr>
<tr class="even">
<td>Imprimante 2</td>
<td><ul>
<li>OPOS</li>
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
<li>Réseau </br><strong>Remarque :</strong> Un seul tiroir-caisse par profil matériel peut être paramétré si <strong>Utiliser les équipes de travail partagées</strong> est configuré sur le tiroir-caisse.</li>
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
<td>Clavier d’identification personnelle</td>
<td>OPOS (la prise en charge est disponible via la personnalisation du connecteur de paiement.)</td>
</tr>
<tr class="odd">
<td>Sig. copie</td>
<td>OPOS</td>
</tr>
<tr class="even">
<td>Terminal de paiement</td>
<td><ul>
<li>Prise en charge de périphérique personnalisée</li>
<li>Réseau (pour plus d’informations, voir la documentation du connecteur de paiement.)</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="all-modern-pos-clients-shared-an-iis-hardware-station"></a>Tous les clients Modern POS ont partagé une station matérielle IIS

> [!NOTE]
> Lorsque la station matérielle IIS est « partagée », plusieurs périphériques peuvent utiliser la station matérielle simultanément. Pour ce scénario, vous devez utiliser uniquement les périphériques répertoriés dans le tableau suivant. Si vous tentez de partager des périphériques qui ne sont pas répertoriés, comme des lecteurs de codes-barres et des LBM, des erreurs se produiront lorsque plusieurs appareils essaieront de revendiquer le même périphérique. Une telle configuration sera explicitement impossible à l’avenir.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe de périphérique prise en charge</th>
<th>Interfaces prises en charge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Imprimante</td>
<td><ul>
<li>OPOS</li>
<li>Réseau</li>
</ul></td>
</tr>
<tr class="even">
<td>Imprimante 2</td>
<td><ul>
<li>OPOS</li>
<li>Réseau</li>
</ul></td>
</tr>
<tr class="odd">
<td>Créateur</td>
<td><ul>
<li>OPOS</li>
<li>Réseau </br><strong>Remarque :</strong> Un seul tiroir-caisse par profil matériel peut être paramétré si <strong>Utiliser les équipes de travail partagées</strong> est configuré sur le tiroir-caisse.</li>
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
<td>Terminal de paiement</td>
<td><ul>
<li>Prise en charge de périphérique personnalisée</li>
<li>Réseau (pour plus d’informations, voir la documentation du connecteur de paiement.)</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configuration-for-supported-scenarios"></a>Configuration pour les scénarios pris en charge
Pour plus d’informations sur la création de profils matériels, voir [Définir et tenir à jour des clients de canal, y compris des registres et des stations matérielles](define-maintain-channel-clients-registers-hw-stations.md). 

### <a name="modern-pos-for-windows-with-an-ipc-built-in-hardware-station"></a>Modern POS pour Windows avec une station matérielle IPC (intégrée)

Cette configuration est la configuration la plus courante pour les registres de PDV traditionnels et fixes. Pour ce scénario, les informations de profil matériel sont mises en correspondance directement sur le registre lui-même. Le numéro de terminal TEF doit également être défini dans le registre lui-même. Procédez comme suit pour effectuer cette configuration :

1.  Créez un profil matériel où tous les périphériques obligatoires sont configurés.
2.  Mappez le profil matériel sur le registre de PDV.
3.  Créez une station matérielle du type **Dédié** pour le magasin où la caisse enregistreuse du PDV sera utilisée. La description est facultative. 

    > [!NOTE]
    > Vous n’avez pas besoin de définir aucune autre propriété de la station matérielle. Toutes les autres informations requises, telles que le profil matériel, proviennent du registre lui-même.

4.  Cliquez sur **Commerce et vente au détail** &gt; **IT vente au détail et commerce** &gt; **Programme de distribution**.
5.  Sélectionnez le programme de distribution **1090** pour synchroniser le nouveau profil matériel avec le magasin. Cliquez sur **Exécuter maintenant** pour synchroniser les modifications avec le POS.
6.  Sélectionnez le programme de distribution **1040** pour synchroniser la nouvelle station matérielle avec le magasin. Cliquez sur **Exécuter maintenant** pour synchroniser les modifications avec le POS.
7.  Installez et activez Modern POS pour Windows.
8.  Démarrez Modern POS pour Windows, puis commencez à utiliser les périphérique connectés.

### <a name="modern-pos-for-android-with-an-ipc-built-in-hardware-station"></a>Modern POS pour Android avec une station matérielle IPC (intégrée)

**Nouveau pour la version 10.0.8** - Les imprimantes réseau et les tiroirs-caisses Epson connectés à ces imprimantes parle port DK sont désormais pris en charge pour Modern POS pour Android. Pour plus de détails, consultez l’article [Configurer l’application POS Hybrid sur Android et iOS](./dev-itpro/hybridapp.md).

### <a name="all-modern-pos-clients-that-have-a-committed-shared-iis-hardware-station"></a>Tous les clients Modern POS qui ont une station matérielle IIS « partagée », validée

Cette configuration peut être utilisée pour tous les clients Modern POS qui ont une station matérielle utilisée exclusivement par un registre de PDV. Procédez comme suit pour effectuer cette configuration :

1.  Créez un profil matériel où tous les périphériques obligatoires sont configurés.
2.  Créez une station matérielle du type **Dédié** pour le magasin où la caisse enregistreuse du PDV sera utilisée.
3.  Dans la station matérielle dédiée, définissez les propriétés suivantes :
    -   **Nom d’hôte** – Le nom de l’ordinateur hôte où la station matérielle est exécutée. 
    
        > [!NOTE]
        > Cloud POS peut résoudre **localhost** pour déterminer l’ordinateur sur lequel Cloud POS s’exécute. Toutefois, le certificat requis afin de jumeler Cloud POS avec la station matérielle doit également avoir le nom de l’ordinateur comme valeur de « Localhost ». Pour éviter les problèmes, nous vous recommandons de répertorier une instance de chaque station matérielle dédiée pour le magasin, selon les besoins. Pour chaque station matérielle, le nom d’hôte doit être le nom de l’ordinateur spécifique sur lequel la station matérielle sera déployée.
    
    -   **Port** – Le port à utiliser pour la station matérielle, pour qu’elle communique avec le client Modern POS.
    -   **Le profil matériel** – Si le profil matériel n’est pas indiqué sur la station matérielle elle-même, le profil matériel affecté au registre est utilisé.
    -   **Numéro TEF du PDV**– L’ID du terminal TEF à utiliser lorsque les autorisations TEF sont envoyées. Cet ID est fourni par l’organisme qui traite les cartes de crédit.
    -   **Nom du package** – Le package de station matérielle à utiliser lorsque la station matérielle est déployée.

4.  Cliquez sur **Commerce et vente au détail** &gt; **IT vente au détail et commerce** &gt; **Programme de distribution**.
5.  Sélectionnez le programme de distribution **1090** pour synchroniser le nouveau profil matériel avec le magasin. Cliquez sur **Exécuter maintenant** pour synchroniser les modifications avec le POS.
6.  Sélectionnez le programme de distribution **1040** pour synchroniser la nouvelle station matérielle avec le magasin. Cliquez sur **Exécuter maintenant** pour synchroniser les modifications avec le POS.
7.  Installez la station matérielle. Pour plus d’informations sur l’installation de la station matérielle, voir [Configurer et installer la station matérielle Retail](retail-hardware-station-configuration-installation.md).
8.  Installez et activez Modern POS. Pour plus d’informations sur l’installation de Modern POS, voir [Configurer, installer et activer Modern POS (MPOS)](retail-modern-pos-device-activation.md).
9.  Connectez-vous à Modern POS, puis sélectionnez **Effectuer des opérations sans lien avec le tiroir-caisse**.
10. Lancez l’opération **Gérer les stations matérielles**.
11. Cliquez sur **Gérer**.
12. Dans la page de gestion des stations matérielles, définissez l’option pour activer la station matérielle.
13. Sélectionnez la station matérielle à utiliser, puis cliquez sur **Jumeler**.
14. Une fois la station matérielle jumelée, cliquez sur **Fermer**.
15. Dans la page de sélection de station matérielle, cliquez sur la station matérielle récemment sélectionnée pour la rendre active.

### <a name="all-modern-pos-clients-that-have-a-shared-iis-hardware-station"></a>Tous les clients Modern POS qui ont une station matérielle IIS partagée

Cette configuration peut être utilisée pour tous les clients Modern POS qui partagent des stations matérielles avec d’autres périphériques. Procédez comme suit pour effectuer cette configuration :

1.  Créez un profil matériel où les périphériques obligatoires sont configurés.
2.  Créez une station matérielle du type **Partagé** pour le magasin où la caisse enregistreuse du PDV sera utilisée.
3.  Dans la station matérielle partagée, définissez les propriétés suivantes :
    -   **Nom d’hôte** – Le nom de l’ordinateur hôte où la station matérielle est exécutée.
    -   **Description** – Texte qui permet d’identifier la station matérielle, comme **Retours** ou **Avant du magasin**.
    -   **Port** – Le port à utiliser pour la station matérielle, pour qu’elle communique avec le client Modern POS.
    -   **Profil matériel** – Pour les stations matérielles partagées, chaque station matérielle doit avoir un profil matériel. Les profils matériels peuvent être partagés entre les stations matérielles, mais ils doivent être mis en correspondance avec chacune. En outre, il est recommandé d’utiliser les équipes partagées lorsque plusieurs périphériques utilisent le même station matérielle partagée. Pour configurer une équipe de travail partagée, cliquez sur **Retail et Commerce** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **Profils POS** &gt; **Profils du matériel**. Pour chaque profil matériel partagé, sélectionnez le tiroir-caisse, puis définissez l’option **Tiroir-caisse partagé par l’équipe de travail** sur **Oui**.
    -   **Numéro TEF du PDV**– L’ID du terminal TEF à utiliser lorsque les autorisations TEF sont envoyées. Cet ID est fourni par l’organisme qui traite les cartes de crédit.
    -   **Nom du package** – Le package de station matérielle à utiliser lorsque la station matérielle est déployée.

4.  Répétez les étapes 2 et 3 pour chaque station matérielle supplémentaire requise dans le magasin.
5.  Cliquez sur **Commerce et vente au détail** &gt; **IT vente au détail et commerce** &gt; **Programme de distribution**.
6.  Sélectionnez le programme de distribution **1090** pour synchroniser le nouveau profil matériel avec le magasin. Cliquez sur **Exécuter maintenant** pour synchroniser les modifications avec le POS.
7.  Sélectionnez le programme de distribution **1040** pour synchroniser la nouvelle station matérielle avec le magasin. Cliquez sur **Exécuter maintenant** pour synchroniser les modifications avec le POS.
8.  Installez la station matérielle sur chaque ordinateur hôte que vous avez configuré dans les étapes 2 et 3. Pour plus d’informations sur l’installation de la station matérielle, voir [Configurer et installer la station matérielle Retail](retail-hardware-station-configuration-installation.md).
9.  Installez et activez Modern POS. Pour plus d’informations sur l’installation de Modern POS, voir [Configurer, installer et activer Modern POS (MPOS)](retail-modern-pos-device-activation.md).
10. Connectez-vous à Modern POS, puis sélectionnez **Effectuer des opérations sans lien avec le tiroir-caisse**.
11. Lancez l’opération **Gérer les stations matérielles**.

12. Cliquez sur **Gérer**.
13. Dans la page de gestion des stations matérielles, définissez l’option pour activer la station matérielle.
14. Sélectionnez la station matérielle à utiliser, puis cliquez sur **Jumeler**.
15. Répétez l’étape 14 pour chaque station matérielle utilisée par Modern POS.
16. Une fois que toutes les stations matérielles requises sont jumelées, cliquez sur **Fermer**.
17. Dans la page de sélection de station matérielle, cliquez sur la station matérielle récemment sélectionnée pour la rendre active. 

> [!NOTE]
> Si les périphériques utilisent souvent différentes stations matérielles, nous vous recommandons de configurer Modern POS pour inviter les caissiers à sélectionner une station matérielle lorsqu’ils commencent le processus de soumission. Cliquez sur **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **Caisses enregistreuses**. Sélectionnez le registre, puis définissez l’option **Sélectionner à la soumission** sur **Oui**. Utilisez le programme de distribution **1090** pour synchroniser les modifications avec la base de données des canaux.

## <a name="extensibility"></a>Extensibilité
Pour plus d’informations sur les scénarios d’extensibilité pour la station matérielle, voir [Extensibilité des stations matérielles](dev-itpro/hardware-station-extensibility.md).

## <a name="security"></a>Sécurité
Conformément aux normes de sécurité, les paramètres suivants doivent être utilisés dans un environnement de production : 

### <a name="hardware-station-installer"></a>Programme d’installation de la station matérielle
Le programme d’installation de station matérielle effectue automatiquement ces modification de registre dans le cadre de l’installation via le libre-service.
 
-   Le protocole SSL (Secure Sockets Layer) doit être désactivé.
-   Seul le protocole TLS (Transport Layer Security) de version 1.2 Server (ou la version la plus récente en cours) doit être activé et utilisé. 

### <a name="ssl-and-tls"></a>SSL et TLS
Par défaut, le protocole SSL et toutes les versions de TLS, à l’exception de la version 1.2, sont désactivés. Pour modifier ou activer ces valeurs, procédez comme suit :
    1.  Appuyez sur la touche de logo Windows + R pour ouvrir une fenêtre **Exécuter**.
    2.  Dans le champ **Ouvrir**, tapez **Regedit**, puis cliquez sur **OK**.
    3.  Si une zone de message **Contrôle de compte d’utilisateur** s’affiche, cliquez sur **Oui**.
    4.  Dans la fenêtre **Éditeur du registre**, accédez à **HKEY\_LOCAL\_MACHINESystemCurrentControlSetSecurityProvidersSCHANNELProtocols**. Les clés suivantes ont été automatiquement entrées pour autoriser TLS 1.2 uniquement :
        -   TLS 1.2Server:Enabled=1
        -   TLS 1.2Server:DisabledByDefault=0
        -   TLS 1.2Client:Enabled=1
        -   TLS 1.2Client:DisabledByDefault=0
        -   TLS 1.1Server:Enabled=0
        -   TLS 1.1Client:Enabled=0
        -   TLS 1.0Server:Enabled=0
        -   TLS 1.0Client:Enabled=0
        -   SSL 3.0Server:Enabled=0
        -   SSL 3.0Client:Enabled=0
        -   SSL 2.0Server:Enabled=0
        -   SSL 2.0Client:Enabled=0
-   Aucun port réseau supplémentaire ne doit être ouvert, à moins qu’il ne soit requis pour des motifs spécifiés.
-   Le partage de ressources issues de plusieurs origines doit être désactivé et doit spécifier les origines autorisées qui sont acceptées.
-   Seules les autorités de certification approuvées doivent être utilisées pour obtenir les certificats qui seront utilisés sur les ordinateurs qui gèrent la station matérielle.

> [!NOTE]
> Il est indispensable de consulter les recommandations de sécurité pour IIS et les besoins du secteur des cartes de paiement (PCI).

## <a name="peripheral-simulator"></a>Simulateur périphérique
Pour plus d’informations, voir [Simulateur périphérique pour Commerce](dev-itpro/retail-peripheral-simulator.md).

## <a name="microsoft-tested-peripheral-devices"></a>Périphériques testés par Microsoft
### <a name="ipc-built-in-hardware-station"></a>Station matérielle IPC (intégrée)

Les périphériques suivants ont été testés à l’aide de la station matérielle IPC intégrée dans Modern POS pour Windows.

#### <a name="printer"></a>Imprimante

| Fabricant | Modèle    | Interface | Commentaires                |
|--------------|----------|-----------|-------------------------|
| Epson        | Tm-T88IV | OPOS      |                         |
| Epson        | TM-T88V  | OPOS      |                         |
| Epson        | TM-T88   | Personnalisée    | Connecté via le réseau   |
| Star         | TSP650II | Personnalisée    | Connecté via le réseau   |
| Star         | mPOP     | OPOS      | Connecté via Bluetooth |
| HP           | F7M67AA  | OPOS      | Alimenté par USB             |

> [!NOTE]
> L’imprimante Star TSP 100 n’est pas prise en charge pour la station matérielle intégrée. La station matérielle intégrée utilise un processus 64 bits, qui n’est pas compatible avec les pilotes Star TP 100 existants. 

#### <a name="bar-code-scanner"></a>Lecteur de codes-barres

| Fabricant  | Modèle         | Interface | Commentaires |
|---------------|---------------|-----------|----------|
| Motorola      | DS9208        | OPOS      |          |
| Honeywell     | 1900          | UWP       |          |
| Symbole        | LS2208        | OPOS      |          |
| HP intégré | E1L07AA       | OPOS      |          |
| Datalogic     | Magellan 8400 | OPOS      |          |

#### <a name="pin-pad"></a>Clavier d’identification personnelle

| Fabricant | Modèle  | Interface | Commentaires                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Nécessite la personnalisation du connecteur de paiement |

#### <a name="payment-terminal"></a>Terminal de paiement

| Fabricant | Modèle | Interface | Commentaires                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Personnalisée    | Nécessite la personnalisation du connecteur de paiement                                |
| VeriFone     | MX925 | Personnalisée    | Nécessite la personnalisation du connecteur de paiement ; connecté via le réseau et USB |
| VeriFone     | MX915 | Personnalisée    | Nécessite la personnalisation du connecteur de paiement ; connecté via le réseau et USB |

#### <a name="cash-drawer"></a>Tiroir-caisse

| Fabricant | Modèle     | Interface | Commentaires                |
|--------------|-----------|-----------|-------------------------|
| Star         | mPOP      | OPOS      | Connecté via Bluetooth |
| APG          | Atwood    | Personnalisée    | Connecté via le réseau   |
| Star         | SMD2-1317 | OPOS      |                         |
| HP           | QT457AA   | OPOS      |                         |
| Epson        |           | Personnalisée    | Connecté à l’imprimante réseau Epson par le port DK |

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

### <a name="dedicated-iis-hardware-station"></a>Station matérielle IIS dédiée

Les périphériques suivants ont été testés à l’aide d’une station matérielle IIS dédiée (non partagée), associée à Modern POS pour Windows et Cloud POS.

#### <a name="printer"></a>Imprimante

| Fabricant | Modèle    | Interface | Commentaires                  |
|--------------|----------|-----------|---------------------------|
| Epson        | Tm-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Epson        | TM-T88V  | Personnalisée    | Connecté par le réseau     |
| Star         | TSP650II | Personnalisée    | Connecté via le réseau     |
| HP           | F7M67AA  | OPOS      | Alimenté par USB               |

#### <a name="bar-code-scanner"></a>Lecteur de codes-barres

| Fabricant  | Modèle   | Interface | Commentaires |
|---------------|---------|-----------|----------|
| Motorola      | DS9208  | OPOS      |          |
| Symbole        | LS2208  | OPOS      |          |
| HP intégré | E1L07AA | OPOS      |          |

#### <a name="pin-pad"></a>Clavier d’identification personnelle

| Fabricant | Modèle  | Interface | Commentaires                                        |
|--------------|--------|-----------|-------------------------------------------------|
| VeriFone     | 1000SE | OPOS      | Nécessite la personnalisation du connecteur de paiement |

#### <a name="payment-terminal"></a>Terminal de paiement

| Fabricant | Modèle | Interface | Commentaires                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| Equinox      | L5300 | Personnalisée    | Nécessite la personnalisation du connecteur de paiement                                |
| VeriFone     | MX925 | Personnalisée    | Nécessite la personnalisation du connecteur de paiement ; connecté via le réseau et USB |
| VeriFone     | MX915 | Personnalisée    | Nécessite la personnalisation du connecteur de paiement ; connecté via le réseau et USB |

#### <a name="cash-drawer"></a>Caisse enregistreuse

| Fabricant | Modèle     | Interface | Commentaires              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personnalisée    | Connecté via le réseau |
| Star         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |
| Epson        |           | Personnalisée    | Connecté à l’imprimante réseau Epson par le port DK |

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

### <a name="shared-iis-hardware-station"></a>Station matérielle IIS partagée

Les périphériques suivants ont été testés à l’aide d’une station matérielle IIS partagée, associée à Modern POS pour Windows et Cloud POS. 

> [!NOTE]
> Seuls une imprimante, un terminal de paiement et un tiroir-caisse sont pris en charge.

#### <a name="printer"></a>Imprimante

| Fabricant | Modèle    | Interface | Commentaires                  |
|--------------|----------|-----------|---------------------------|
| Epson        | TM-T88IV | OPOS      |                           |
| Epson        | TM-T88V  | OPOS      |                           |
| Epson        | TM-T88   | Personnalisée    | Connecté via le réseau     |
| Star         | TSP650II | Personnalisée    | Connecté via le réseau     |
| HP           | F7M67AA  | OPOS      | Alimenté par USB               |

#### <a name="payment-terminal"></a>Terminal de paiement

| Fabricant | Modèle | Interface | Commentaires                                                                       |
|--------------|-------|-----------|--------------------------------------------------------------------------------|
| VeriFone     | MX925 | Personnalisée    | Nécessite la personnalisation du connecteur de paiement ; connecté via le réseau et USB |
| VeriFone     | MX915 | Personnalisée    | Nécessite la personnalisation du connecteur de paiement ; connecté via le réseau et USB |

#### <a name="cash-drawer"></a>Caisse enregistreuse

| Fabricant | Modèle     | Interface | Commentaires              |
|--------------|-----------|-----------|-----------------------|
| APG          | Atwood    | Personnalisée    | Connecté via le réseau |
| Star         | SMD2-1317 | OPOS      |                       |
| HP           | QT457AA   | OPOS      |                       |
| Epson        |           | Personnalisée    | Connecté à l’imprimante réseau Epson par le port DK |


## <a name="troubleshooting"></a>Dépannage
### <a name="modern-pos-can-detect-the-hardware-station-in-its-list-for-selection-but-it-cant-complete-the-pairing"></a>Modern POS peut détecter la station matérielle dans sa liste de sélection, mais il ne peut pas effectuer le jumelage

**Solution:** Vérifiez la liste de points de défaillance potentiels suivante :

-   L’ordinateur qui exécute Modern POS approuve le certificat utilisé sur l’ordinateur qui exécute la station matérielle.
    -   Pour vérifier cette configuration, dans un navigateur Web, accédez à l’URL suivante : https://&lt;Nom Ordinateur&gt;:&lt;Numéro Port&gt;/StationMatérielle/ping.
    -   Cette URL envoie un ping pour vérifier que l’ordinateur est accessible, et le navigateur indique si le certificat est approuvé. (Par exemple, dans Internet Explorer, une icône de verrouillage s’affiche dans la barre d’adresse. Lorsque vous cliquez sur cette icône, Internet Explorer vérifie si le certificat est actuellement approuvé. Vous pouvez installer le certificat sur l’ordinateur local en lisant les détails du certificat qui s’affichent.)
-   Sur l’ordinateur qui exécute la station matérielle, le port utilisé par la station matérielle est ouvert dans le pare-feu.
-   La station matérielle a correctement installé les informations de compte marchand via l’outil d’installation des informations du marchand qui s’exécute à la fin du programme d’installation de la station matérielle.

### <a name="modern-pos-cant-detect-the-hardware-station-in-its-list-for-selection"></a>Modern POS ne peut pas détecter la station matérielle dans sa liste de sélection

**Solution:** L’un des facteurs suivants peut être à l’origine de ce problème :

-   La station matérielle n’a pas été correctement paramétrée au siège. Reprenez les étapes qui précèdent dans cette rubrique pour vérifier que le profil de station matérielle et la station matérielle sont correctement entrés.
-   Les tâches de mise à jour de la configuration des canaux n’ont pas été effectuées. Dans ce cas, exécutez la tâche 1070 pour la configuration des canaux.

### <a name="modern-pos-doesnt-reflect-new-cash-drawer-settings"></a>Modern POS ne prend pas en compte les nouveaux paramètres de tiroir-caisse

**Solution :** Fermez le traitement par lots en cours. Les modifications du tiroir-caisse ne seront pas mises à jour dans Modern POS tant que le traitement par lot en cours ne sera pas fermé.

### <a name="modern-pos-is-reporting-an-issue-with-a-peripheral"></a>Modern POS signale un problème avec un périphérique

**Solution :** voici quelques causes de ce problème :

-   Assurez-vous que les autres utilitaires de configuration de pilotes de périphérique sont fermés. Si ces utilitaires sont ouverts, ils peuvent empêcher Modern POS ou la station matérielle de revendiquer le périphérique.
-   Si le périphérique est partagé avec plusieurs périphériques de PDV, assurez-vous qu’il appartient à une des catégories suivantes :
    -   Tiroir-caisse
    -   Imprimante réception
    -   Terminal de paiement

    Si le périphérique n’appartient pas à une de ces catégories, la station matérielle n’est pas conçue pour permettre que le périphérique soit partagé entre plusieurs périphériques de PDV.
-   Parfois, les pilotes de périphérique peuvent empêcher les objets de contrôle commun (CCO) de fonctionner correctement. Si un périphérique a été récemment installé, mais qu’il ne fonctionne pas correctement ou que vous remarquez d’autres problèmes, vous pouvez souvent résoudre ceux-ci en réinstallant les CCO. Pour télécharger les CCO, rendez-vous sur <http://monroecs.com/oposccos_current.htm>.
-   Si vous modifiez fréquemment les périphériques pendant les tests ou la recherche de pannes, vous devrez peut-être réinitialiser IIS au lieu d’attendre que le cache s’actualise. Pour réinitialiser IIS, procédez comme suit :
    1.  Dans le menu **Démarrer**, tapez **CMD**.
    2.  Dans les résultats de la recherche, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.
    3.  Dans la fenêtre **Invite de commandes**, tapez **iisreset /Restart** et appuyez sur Entrée.
    4.  Une fois que IIS a redémarré, redémarrez Modern POS.
-   Alors que vous modifiez fréquemment les périphériques, si également vous démarrez et quittez fréquemment le client POS, le processus dllhost d’une session POS précédente peut interférer avec la session actuelle. Dans ce cas, un appareil peut ne pas être utilisable jusqu’à ce que vous fermiez l’hôte de la bibliothèque de liens dynamiques (DLL) qui gère la session précédente. Procédez comme suit pour fermer l’hôte DLL :
    1.  Dans le menu **Démarrer**, tapez **Gestionnaire des tâches**.
    2.  Dans les résultats de la recherche, cliquez sur **Gestionnaire des tâches**.
    3.  Dans les Gestionnaire des tâches, sous l’onglet **Détails**, cliquez sur l’en-tête de la colonne intitulée **Nom** pour trier le tableau par ordre alphabétique du nom.
    4.  Faites défiler jusqu’à ce que vous trouviez dllhost.exe.
    5.  Sélectionnez chaque hôte DLL, puis cliquez sur **Terminer la tâche**.
    6.  Une fois les hôtes DLL fermés, redémarrez Modern POS.


## <a name="additional-resources"></a>Ressources supplémentaires

[Simulateur périphérique pour Commerce](dev-itpro/retail-peripheral-simulator.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]