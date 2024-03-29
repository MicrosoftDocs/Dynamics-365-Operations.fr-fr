---
title: Connecter des périphériques au point de vente (POS)
description: Cet article décrit comment connecter des périphériques à votre Retail POS.
author: BrianShook
ms.date: 03/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTerminalTable, RetailDevice
audience: Application User
ms.reviewer: josaw
ms.custom: 92383
ms.assetid: 83f31ea6-f0a2-4501-9d4d-a37b6eec2599
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: ffee75e1713c7c9d31b1d023cd055c2f1a3fc43d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897106"
---
# <a name="connect-peripherals-to-the-point-of-sale-pos"></a>Connecter des périphériques au point de vente (POS)

[!include [banner](includes/banner.md)]

Cet article décrit comment connecter des périphériques à votre Retail POS.

> [!NOTE]
> Pour obtenir des instructions d’installation spécifiques, voir [Configurer et installer la station matérielle Retail](retail-hardware-station-configuration-installation.md) et [Configurer, installer et activer Modern POS (MPOS)](retail-modern-pos-device-activation.md).

## <a name="key-components"></a>Composants principaux

Plusieurs composants sont utilisés pour définir les relations entre un magasin, les caisses enregistreuses ou canaux de point de vente (PDV) au sein du magasin et les périphériques que ces caisses enregistreuses ou canaux utilisent pour traiter les transactions. Cette section décrit chaque composant et explique comment il doit être utilisé dans un déploiement de magasin.

### <a name="pos-registers"></a>Caisses enregistreuses de PDV

Navigation : cliquez sur **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **Caisses enregistreuses**.

La caisse enregistreuse du PDV est une entité utilisée pour définir les caractéristiques d’une instance spécifique du PDV. Ces caractéristiques sont notamment le profil matériel ou la configuration des périphériques qui seront utilisés au niveau de la caisse enregistreuse, le magasin auquel la caisse enregistreuse se rapporte et l’expérience visuelle de l’utilisateur qui se connecte à cette caisse enregistreuse.

### <a name="devices"></a>Périphériques

Navigation : cliquez sur **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **Périphériques**.

Un périphérique est une entité qui représente une instance physique d’un périphérique qui est mappé à une caisse enregistreuse de PDV. Lorsqu’un périphérique est créé, il est mappé à une caisse enregistreuse de PDV. L’entité de périphérique assure le suivi des informations lorsqu’une caisse enregistreuse est activée, le type de client qui est utilisé et le package d’applications qui a été déployé sur un périphérique spécifique. Les périphériques peuvent être de deux types : **Retail modern POS** (MPOS) ou **Retail Cloud POS** (Cloud POS).

#### <a name="mpos"></a>MPOS

MPOS est une application de client de PDV qui est installée sur le système d’exploitation basé sur PC Windows 8.1 ou une version ultérieure. Si le type d’application **Retail modern POS** est mappé à un périphérique, le package de téléchargement peut être spécifié pour un périphérique particulier. Le package de téléchargement peut être personnalisé pour inclure différentes versions du package d’installation. La possibilité de déployer différents packages fournit de la flexibilité au cas où différentes caisses enregistreuses de PDV nécessitent différentes intégrations. MPOS est déployé avec une station matérielle intégrée.

#### <a name="cloud-pos"></a>Cloud POS

Cloud POS est un PDV basé sur un navigateur. Du fait qu’il s’exécute dans le navigateur, Cloud POS ne nécessite pas le système d’exploitation basé sur PC Windows 8.1 ou une version ultérieure. Si le type d’application **Retail Cloud POS** est mappé à un périphérique spécifique dans Siège, ce périphérique peut être utilisé via le navigateur sans avoir besoin de télécharger ou d’installer un package. Cloud POS nécessite une station matérielle pour utiliser le matériel au-delà de l’analyse de code-barres basée sur Wedge clavier.

### <a name="hardware-profile"></a>Profil matériel

Navigation : accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils du matériel**.

Un profil de matériel identifie le matériel qui est connecté à une caisse enregistreuse de PDV via une station matérielle intégrée ou partagée. Le profil de matériel est également utilisé pour spécifier les paramètres de processeur de paiement qui doivent être utilisés pendant la communication avec le kit de développement de logiciel (SDK) de paiement. Le Kit de développement logiciel de paiement est déployé dans le cadre de la station matérielle.

### <a name="hardware-station"></a>Station matérielle

Navigation : Accédez à **Retail et Commerce \> Chaînes \> Magasins \> Tous les magasins**, sélectionnez un magasin, puis sélectionnez le raccourci **Stations matérielles**.

Une station matérielle est une instance de logique métier pilotant les périphériques du PDV. Une station matérielle est installée automatiquement avec MPOS. Sinon, la station matérielle peut être installée comme composant autonome, on y accède par MPOS ou Cloud POS via un service web. La station matérielle doit être définie au niveau du canal.

## <a name="scenarios"></a>Scénarios

### <a name="mpos-with-connected-peripheral-devices"></a>MPOS avec des périphériques connectés

[![Point de vente fixe traditionnel.](./media/traditional-300x279.png)](./media/traditional.png)

Pour connecter MPOS aux périphériques de PDV dans un scénario de PDV fixe traditionnel, accédez d’abord à la caisse enregistreuse elle-même et affectez-lui un profil de matériel. Vous pouvez trouver les caisses enregistreuses de PDV dans **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **Caisses enregistreuses**. 

Une fois que vous avez affecté le profil de matériel, la synchronisation modifie la base de données de canal à l’aide du programme de distribution **Caisses enregistreuses**. Vous trouverez les programmes de distribution à l’adresse **Commerce et vente au détail** &gt; **Informatique Commerce et vente au détail** &gt; **Programme de distribution**. 

Ensuite, configurez une station matérielle dédiée sur le canal. Accédez à **Commerce et vente au détail \> Canaux \> Magasins de vente au détail \> Tous les magasins de vente au détail** et sélectionnez un magasin. 

Puis, dans le raccourci **Stations matérielles**, sélectionnez **Ajouter** pour ajouter une station matérielle. Sélectionnez **Dédié** comme type de station matérielle, puis entrez une description. Le champ **Profil matériel** peut être laissé vide, car le profil matériel utilisé dans ce scénario provient du registre de PDV lui-même. Puis synchronisez les modifications entre les canaux à l’aide du programme de distribution **Configuration de canal**. Vous trouverez les programmes de distribution à l’adresse **Retail et Commerce \> Retail et Commerce IT \> Programme de distribution**. 

Enfin, dans MPOS, utilisez l’opération **Sélectionner la station matérielle** pour sélectionner la station matérielle qui correspond à la valeur que vous avez saisie précédemment pour la description, et définissez la station matérielle sur **Actif**. 

> [!NOTE]
> - Certaines modifications apportées au profil de matériel, telles que les tiroirs-caisses, nécessitent que la nouvelle équipe ait commencé une fois que les modifications aient été synchronisées sur le canal.
> - PDV Cloud doit utiliser la station matérielle autonome pour communiquer avec les périphériques.

### <a name="mpos-or-cloud-pos-with-a-stand-alone-hardware-station"></a>MPOS ou Cloud POS avec une station matérielle autonome

[![Périphériques partagés.](./media/shared-300x254.png)](./media/shared.png)

Dans ce scénario, une station matérielle autonome est partagée entre les clients MPOS et Cloud POS. Ce scénario nécessite de créer un profil de station matérielle partagée et de spécifier le package de téléchargement, le port et le profil de matériel qu’utilise la station matérielle. Vous définissez une nouvelle station matérielle en sélectionnant le raccourci **Postes matériels** dans le canal spécifique (**Retail et Commerce \> Canaux \> Magasins \> Tous les magasins**) et en ajoutant une nouvelle station matérielle de type **partagée**. 

Ensuite, fournissez une description qui aidera le caissier à identifier la station matérielle. Dans le champ **Nom d’hôte**, saisissez l’URL de la machine hôte au format suivant : `https://<MachineName:Port>/HardwareStation`. (Remplacez **&lt;MachineName:Port&gt;** par le nom réel de la station matérielle et le port qui est spécifié dans le profil de station matérielle.) Pour une station matérielle autonome, vous devez également spécifier l’ID du terminal de transfert électronique de fonds (TEF). Cette valeur identifie le terminal TEF connecté à la station matérielle lorsque le connecteur de paiement communique avec le fournisseur de paiement. 

Ensuite, à partir de la machine qui hébergera la station matérielle, accédez au canal dans Headquarters et sélectionnez la station matérielle. Sélectionnez ensuite **Télécharger** pour télécharger le programme d’installation de la station matérielle et installez la station matérielle. Pour plus d’informations sur l’installation de la station matérielle, voir [Configurer et installer la station matérielle Retail](retail-hardware-station-configuration-installation.md). 

Ensuite, dans MPOS ou Cloud POS, utilisez l’opération **Sélectionner une station matérielle** pour sélectionner la station matérielle qui a été précédemment installée. Sélectionnez **Jumeler** pour établir une relation sécurisée entre le PDV et la station matérielle. Cette étape doit être effectuée une fois pour chaque combinaison de POS et de station matérielle. 

Une fois que la station matérielle est jumelée, la même opération est utilisée pour rendre la station matérielle active alors qu’elle est utilisée. Dans ce scénario, le profil de matériel doit être assigné au profil de station matérielle partagée plutôt qu’à la caisse enregistreuse elle-même. Si aucun profil matériel n’est directement attribué à une station matérielle pour une quelconque raison, le profil matériel attribué à la caisse enregistreuse sera utilisé.

## <a name="client-maintenance"></a>Maintenance client

### <a name="registers"></a>Caisses enregistreuses

Les caisses enregistreuses du PDV sont gérées principalement via les caisses enregistreuses elles-mêmes, ainsi que via les profils qui leur sont affectés. Les attributs qui sont spécifiques à chaque caisse enregistreuse sont gérés au niveau de la caisse enregistreuse. Ces attributs incluent le magasin dans lequel la caisse enregistreuse est utilisée, le numéro de la caisse enregistreuse, la description et l’ID de terminal TEF qui est spécifique à la caisse enregistreuse elle-même.

### <a name="pos-profiles"></a>Profils POS

Vous pouvez trouver les profils de PDV dans **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **Profils PDV**. Il est utile de gérer de nombreux aspects d’une caisse enregistreuse par le biais des profils, dans la mesure où les profils peuvent être partagées entre plusieurs caisses enregistreuses. Les profils peuvent être mappés à une caisse enregistreuse individuelle ou, si un profil est en vigueur dans l’ensemble d’un magasin, au magasin. Les sections suivantes décrivent les profils POS et comment ils sont utilisés.

#### <a name="offline-profile"></a>Profil hors connexion

Le profil hors connexion est défini au niveau du magasin. Il est utilisé pour spécifier les paramètres de téléchargement des transactions qui sont exécutées sur une caisse enregistreuse du PDV pendant que cette caisse enregistreuse n’est pas connectée à la base de données du canal.

#### <a name="functionality-profile"></a>Profil de la fonctionnalité

Le profil de fonctionnalité est défini au niveau du magasin. Il est utilisé pour spécifier des paramètres à l’échelle du magasin concernant les fonctions qui peuvent être effectuées au niveau du PDV. Les fonctionnalités suivantes sont gérées via le profil de fonctionnalité. Ces fonctionnalités sont organisées par l’organisateur.

- Organisateur **Général** :

    - Organisation internationale de normalisation (ISO).
    - Créez un client en mode hors connexion.
    - Profil du ticket de caisse par e-mail.
    - Authentification de connexion du personnel central.

- Organisateur **Fonctions** :

    - Gestion de connexion et de connexion étendue.
    - Aspects financiers et liés à la devise du PDV, telles que la capacité de saisir des prix et si les décimales sont requises pour la devise secondaire.
    - Activation de l’enregistrement de l’heure via le PDV.
    - Comment les produits et les paiements s’affichent dans le PDV et sur les reçus.
    - Gestion de clôture
    - Paramètres de rétention de transaction de base de données de canal.
    - Comment les clients sont recherchés et créés dans le PDV.
    - Comment les remises sont calculées.

- Organisateur **Montant** :

    - Prix maximum et minimum autorisés.
    - Application et calcul de remises.

- Organisateur **Codes info** :

    - Tous les aspects de la manière dont les codes info sont gérés dans le PDV. Pour plus d’informations, voir [Codes info et groupes de codes info](info-codes-retail.md).

- Organisateur **Numérotation des tickets de caisse** :

    - Spécifiez les masques de la numérotation des tickets de caisse, qui peuvent inclure des segments pour le numéro du magasin, le numéro du terminal, des constantes et si les ventes, les retours, les commandes client et les devis sont imprimés dans des souches distinctes, ou si ils suivent tous la même souche.

#### <a name="receipt-profiles"></a>Profils du ticket de caisse

Les profils de tickets de caisse sont affectés aux imprimantes via le profil de matériel. Ils sont utilisés pour spécifier les types de tickets de caisse qui sont imprimés sur une imprimante spécifique. Les profils incluent des paramètres pour les formats de tickets de caisse et les paramètres qui déterminent si le ticket de caisse est toujours imprimé, ou si le caissier est invité à décider si le ticket de caisse doit être imprimée. Différentes imprimantes peuvent également utiliser des profils de tickets de caisse différents. Par exemple, l’imprimante 1 est une imprimante à tickets de caisse thermiques standard et a donc des formats de ticket de caisse plus petits. Toutefois, l’imprimante 2 est une imprimante de tickets de caisse de taille normale utilisée pour imprimer uniquement les reçus de commande client, qui requièrent plus d’espace. Pour plus d’informations, voir [Configurer un profil du ticket de caisse](configure-emailed-receipt-formats.md#configure-a-receipt-profile).

#### <a name="hardware-profiles"></a>Profils du matériel

Les profils de matériel sont décrits comme des composant de paramétrage du client plus haut dans cet article. Les profils matériels sont attribués directement au registre de PDV ou à une station matérielle partagée, et sont utilisés pour spécifier les types de périphériques utilisés par un registre de PDV ou une station matérielle spécifique. Les profils de matériel sont également utilisés pour spécifier les paramètres TEF utilisés pour communiquer avec le Kit de développement logiciel de paiement.

#### <a name="visual-profiles"></a>Profils visuels

Les profils visuels sont utilisés pour préciser le thème pour un registre spécifique et sont attribués au niveau du registre. Les profils incluent des paramètres pour le type d’application qui est utilisé (MPOS ou Cloud POS), la couleur d’accentuation et le thème, le jeu de polices, l’arrière-plan de la page de connexion et l’arrière-plan du PDV. Pour plus d’informations, voir [Créer des profils visuels de point de vente (PDV)](tasks/create-pos-visual-profile-2016-02.md). 

### <a name="custom-fields"></a>Champs personnalisés

Vous pouvez créer des champs personnalisés pour ajouter des champs qui ne sont pas fournis prêts à l’emploi au PDV. Pour plus d’informations sur l’utilisation de champs personnalisés, consultez la [publication de blog Utilisation de champs personnalisés](https://blogs.msdn.microsoft.com/axsupport/2012/08/06/ax-for-retail-2012-working-with-custom-fields/).

### <a name="language-text"></a>Texte linguistique

Vous pouvez remplacer les chaînes par défaut dans le PDV à l’aide d’entrées de texte en langue étrangère. Pour remplacer une chaîne dans le PDV, ajoutez une nouvelle ligne de texte en langue étrangère. Puis spécifiez un ID, la chaîne par défaut qui doit être substituée et le texte qui doit apparaître dans le PDV au lieu de la chaîne par défaut.

### <a name="channel-reports-configuration"></a>Configuration des états sur les canaux

Vous paramétrez les états disponibles au niveau du canal sur la page **Configuration des états sur les canaux**. Vous pouvez créer de nouveaux états en fournissant la définition XML de l’état et en affectant l’état à un groupe d’autorisations spécifiques dans le PDV.

### <a name="devices"></a>Périphériques

Les périphériques sont expliqués plus haut dans cet article. Ils sont utilisés pour gérer l’activation d’une caisse enregistreuse de PDV spécifique. Les périphériques sont également utilisés pour spécifier l’application qui est utilisée pour une caisse enregistreuse spécifique et le package d’installation qui doit être utilisé pour installer le client MPOS. Voici les états d’activation de périphérique :

- **En attente** – le périphérique est prêt à être activé.
- **Activé** – le périphérique a été activé.
- **Désactivé** – le périphérique a été désactivé dans Siège ou par l’intermédiaire du PDV.
- **Désactivé** – le périphérique a été désactivé.

Les informations supplémentaires relatives à l’activation comprennent le travailleur qui a modifié l’état d’activation du périphérique, un horodatage de l’activation, et si la configuration du périphérique a été validée.

### <a name="client-data-synchronization"></a>Synchronisation des données client

Toutes les modifications apportées à un client de PDV, à l’exception des modifications apportées à l’état d’activation du périphérique, doivent être synchronisées sur la base de données du canal pour être prises en compte. Pour synchroniser les modifications apportées à la base de données de canal, accédez à **Commerce et vente au détail** &gt; **Informatique Commerce et vente au détail** &gt; **Programme de distribution** et exécutez le programme de distribution requis. Pour les modifications du client, vous devez exécuter les programmes de distribution **Caisses enregistreuses** et **Configuration des canaux**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration et installation d’une Retail Hardware Station](retail-hardware-station-configuration-installation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
