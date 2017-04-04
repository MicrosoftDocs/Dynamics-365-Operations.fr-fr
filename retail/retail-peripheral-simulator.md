---
title: Retail peripheral simulator
description: "Cette rubrique décrit l&quot;outil périphérique de simulateur indiquées par Microsoft Dynamics 365 pour les opérations - au détail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 266544
ms.assetid: 16f31e70-15fc-441e-9727-e6a31c3a48f5
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 42dc414ff2bb6359b47d89c3bd3c510e4258f816
ms.openlocfilehash: b2229466040351d8c2b9494b30b4c928651820b8
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripheral-simulator"></a>Retail peripheral simulator

Cette rubrique décrit l'outil périphérique de simulateur indiquées par Microsoft Dynamics 365 pour les opérations - au détail.

<a name="overview"></a>Vue d'ensemble
--------

Microsoft Dynamics 365 pour les opérations - Le simulateur périphérique au détail est un outil permettant vous paramétrez, testent, et dépannent les périphérique à utiliser dans des environnements au détail. Vous pouvez utiliser le simulateur périphérique pour rationaliser le test des unités Vente au détail, et pour séparer les problèmes qui sont engendrés les chauffeurs par périphérique incorrect de paramétrage ou de dysfonctionnement. Le simulateur périphérique inclut un programme de bureau qui décrivent les versions virtuelles de périphériques qui Dynamics 365 pour les opérations - support au détail. Une section pour les affiches virtuelles de chaque périphérique l'interaction entre l'unité et le point de vente au détail (POS). Vous pouvez également l'utiliser pour fournir des données valides pour différents scénarios du PDV. Le simulateur périphérique prend en charge l'interaction entre le POS et les périphériques virtuels suivants :

-   ** Imprimante ** – Le simulateur périphérique peut les réceptions d'afficher qui sont configurées pour une imprimante du PDV.
-   ** Ligne affichage ** – Vous pouvez configurer une ligne affichage virtuelle à l'activité d'afficher sur une Ligne physique affichage.
-   ** Lecteur de bande magnétique (MSR) ** – Vous pouvez envoyer des événements simulés de bande magnétique dans le système POS du simulateur périphérique.
-   ** Tiroir-caisse ** – Vous pouvez simuler un tiroir-caisse physique.
-   ** Le tiroir 2 ** – en paramétrant un second tiroir-caisse dans le simulateur périphérique, vous pouvez simuler des scénarios impliquant un TPV unique qui a deux équipes actives.
-   ** Le scanner ** – le scanneur de code-barres virtuel que le simulateur périphérique prend en charge peut publier des événements de l'instruction de code-barres.
-   ** L'échelle ** – une échelle virtuelle permet de simuler l'interaction des articles pesées avec le POS.
-   ** Protection personnelle de (PIN) de numéros d'identification ** – Vous pouvez simuler des opérations de clavier d'identification personnelle. ** Remarque : ** Vous devez mettre en œuvre la prise en charge d'une protection physique PIN dans le Business de paiement.
-   ** La capture de signature ** – Le simulateur périphérique inclut un périphérique virtuel de capture de signature que vous pouvez paramétrer pour demander des signatures requises pour certains offres, tels que les paiements de compte client.

Vous pouvez également utiliser le simulateur périphérique pour simuler des événements de s'arrête en de clavier qui proviennent d'un lecteur de codes-barres et d'un LBM. Les supports de simulateur de périphérique virtuel spécifiquement objet lier et répercuter pour les périphériques de Retail POS (OPOS.)

## <a name="key-scenarios"></a>Scénarios de clé
### <a name="troubleshooting"></a>Dépannage

Vous pouvez utiliser le simulateur périphérique pour résoudre le paramétrage de l'unité. Si vous n'avez pas le simulateur périphérique ou un deuxième unité de la même classe, il peut être difficile de déterminer où les problèmes commencent. Toutefois, lorsque vous avez le simulateur périphérique, vous pouvez paramétrer les périphériques virtuels, puis exécuter le même code les chemins d'accès et la logique métier utilisés pour les périphériques physiques. {{De:From_the_perspective_of}} {{la:From_the_perspective_of}} {{perspective:From_the_perspective_of}} Du simulateur périphérique, la différence principale entre les périphériques virtuels et les périphériques physiques est l'objet de service, ou conducteur du périphérique. Pour les périphériques physiques, l'objet de service est fourni par le fabricant du périphérique. En revanche, pour le simulateur périphérique, les objets de service sont fournis dans le cadre de le simulateur périphérique. Lorsque le simulateur périphérique fonctionne correctement, si un appareil ne fonctionne pas correctement une fois le nom du périphérique dans le profil matériel soit modifié au nom d'un périphérique réel, vous pouvez supposer qu'il y a un problème avec l'objet de service que le fabricant a fourni.

### <a name="training"></a>Formation

Vous pouvez utiliser le simulateur périphérique pour ajouter une couche réaliste à la formation de caisse lorsqu'un paramétrage physique de matières n'est pas disponible. Lorsque le simulateur périphérique est inclus dans les scénarios de formation, le caissier peut plus efficace interagir avec le POS en fournissant des données telles que les analyses de code-barres de produit et des passages de carte de carte cadeau, puis en observant les réceptions sont imprimées pour une transaction spécifique.

### <a name="testing"></a>Test

Vous pouvez utiliser le simulateur périphérique pour tester des code-barres de produit, formats de réception, etc., sans devoir déployer le matériel physique dans un environnement virtuel. Comme le matériel physique n'est nécessaire, et vous ne devez pas déployer un client du PDV dans une station matérielle ou un ordinateur physique, vous pouvez plus rapidement tester les modifications qui sont apportées dans le flux administratifs.

## <a name="set-up-the-peripheral-simulator"></a>Paramétrez le simulateur périphérique
### <a name="set-up-a-hardware-profile"></a>Paramétrez un profil matériel

1.  Pour paramétrer le simulateur périphérique, passez ** au détail et commerce ** &gt; ** au canal paramétré ** &gt; ** la configuration ** &gt; ** des profils de PDV ** &gt; ** des profils matériels **.
2.  Pour créer un profil, cliquez sur ** nouveau **.
3.  Entrez des valeurs dans ** numéro de profil ** et ** description ** des champs.
4.  La table suivante permet de définir les périphériques virtuelles à tester. Voici une explication des colonnes dans la table :
    -   ** Le périphérique ** – Cette colonne donne le nom de l'organisateur que vous développez pour paramétrer le périphérique.
    -   ** Type de périphérique ** – Cette colonne donne la valeur sélectionnée dans le champ qui est appelé avec le nom de l'unité.
    -   ** Nom de l'appareil - ** – Cette colonne donne une valeur exacte que vous entrez pour le nom du périphérique. ** Important : ** Le nom du périphérique qui sont définis ici sont requis, car la station matérielle utilise les noms spécifiques pour corriger les périphériques. Si vous n'utilisez pas les noms spécifiques, le périphérique ne sera pas utilisable.

    | Périphérique            | Type de périphérique | Nom du périphérique              |
    |-------------------|-------------|--------------------------|
    | Imprimante           | OPOS        | MockOPOSPrinter          |
    | Affichage de ligne      | OPOS        | MockOPOSLineDisplay      |
    | LBM               | OPOS        | MockOPOSMSR              |
    | Créateur            | OPOS        | MockOPOSDrawer1          |
    | Drawer2           | OPOS        | MockOPOSDrawers          |
    | Scanneur           | OPOS        | MockOPOSScanner          |
    | Echelle             | OPOS        | MockOPOSScale            |
    | Clavier d'identification personnelle           | OPOS        | MockOPOSPinPad           |
    | Capture de signature | OPOS        | MockOPOSSignatureCapture |

** Remarque : ** Aucun paramétrage spécifique dans le profil matériel n'est requis pour simuler des événements de s'arrête en de clavier du scanneur de code-barres et du LBM.

### <a name="assign-the-hardware-profile-to-a-register"></a>Affectez le profil matériel à un registre

1.  Une fois le profil matériel créé, passez ** au détail et commerce ** &gt; ** au canal paramétré ** &gt; ** la configuration ** &gt; ** des registres **.
2.  Dans ** des registres POS ** répertoriez, cliquez sur le lien du ** numéro de caisse enregistreuse ** le champ pour le registre qui doit utiliser le simulateur périphérique.
3.  Cliquez sur **Modifier**.
4.  Dans ** des profils ** section dans, ** profil matériel ** le champ, sélectionnez le profil matériel créé pour les périphériques virtuels.
5.  Click **Save**.

### <a name="synchronize-changes-to-the-channel-database"></a>Synchronisez les modifications à la base de données des canaux

1.  Allez ** au détail et commerce ** &gt; ** à l'IT au détail ** &gt; ** programme de distribution **.
2.  Sélectionnez ** 1090 ** le programme de distribution.
3.  Cliquez sur ** exécution désormais ** pour synchroniser les modifications au niveau de le POS.

Une fois les données soient synchronisées, le nouveau profil matériel et les modifications de la caisse enregistreuse sont disponibles dans la base de données des canaux.

## <a name="install-the-peripheral-simulator"></a>Installation du simulateur périphérique
1.  Allez ** au détail et commerce ** &gt; ** au canal paramétré ** &gt; ** la configuration ** &gt; ** des profils de PDV ** &gt; ** des profils matériels **.
2.  Cliquez sur ** téléchargement **, puis sur ** PeripheralSimulator **. ** Remarque : ** Vous devez désactiver les dresseurs instantanés avant de charger le simulateur périphérique.
3.  Une fois le téléchargement fait, ouvrez ** les téléchargements ** l'incident, puis double-cliquez dessus ** VirtualPeripherals.msi ** pour démarrer le programme d'installation.
4.  Installation du simulateur périphérique à l'aide de les paramètres par défaut.

Outre le simulateur périphérique, vous devez installer les objets de contrôle commun des services de consultance de Monroe. Sinon, le simulateur périphérique ne fonctionnera pas correctement. Pour télécharger les objets de contrôle commun, cliquez< sur http://monroecs.com/oposccos_current.htm>.

## <a name="using-the-peripheral-simulator"></a>Utilisation du simulateur périphérique
Pour lancer le simulateur, cliquez sur périphériques ** début ** sur votre ordinateur, type ** simulateur périphérique au détail **, puis sélectionnez l'application lorsqu'il apparaît dans les résultats de la recherche. Après avoir mis démarrer le simulateur périphérique, cliquez sur le nom du périphérique pour afficher les périphériques pris en charge. Ces périphériques sont répertoriés comme onglets à gauche de la fenêtre. Pour afficher un périphérique spécifique, cliquez sur l'onglet pour ce périphérique.

### <a name="line-display-capabilities"></a>Ligne capacités d'affichage

La ligne affichage est le premier périphérique répertorié dans le simulateur périphérique. Lorsque la ligne affichage virtuelle est configurée, il des lignes d'afficher des informations telles qu'elles sont analysés dans la transaction POS. Outre les lignes, les affiches d'afficher le total dû lorsqu'une offre est sélectionnée dans le système POS. Elle présente également le solde dû si une offre est entrée mais un solde est toujours due pour la transaction. Lorsque le POS n'est pas utilisé, un message s'affiche pour indiquer que la caisse enregistreuse est clôturée. Vous devez configurer le message dans ** affichage de ligne ** l'organisateur dans le profil matériel.

### <a name="cash-drawer-capabilities"></a>Capacités de caisse

Le tiroir est le deuxième périphérique répertorié dans le simulateur périphérique. Lorsque le profil matériel est configuré pour utiliser les tiroirs-caisse virtuels, le POS affiche le tiroir-caisse pour l'équipe active en réponse à des opérations du tireur telles que des comptages de caisse, et que le caissier puisse que la modification ou déposer des disponibilités pendant les transactions cash-and-carry standard. Les tiroirs-caisse virtuels ont des étiquettes ** tiroir-caisse principal ** et ** tiroir-caisse secondaire **. Ces étiquettes représentent le tiroir-caisse et le tiroir-caisse 2 dans le profil matériel, respectivement. Lorsqu'un tiroir-caisse est clôturé, l'image d'un tiroir-caisse clôturé est affichée, et le bouton dans le tiroir-caisse clôturé est appelé ** tiroir-caisse en cours **. Si vous cliquez sur ce bouton, l'image est remplacée par l'image d'un tiroir-caisse en cours pour indiquer que le tiroir-caisse est désormais en cours. Le bouton dans le tiroir-caisse en cours est appelé ** tiroir-caisse de clôture **. Plusieurs opérations au niveau de le POS peuvent effectuer pour ouvrir le tiroir-caisse. La plupart des opérations ne peuvent pas se poursuivre tandis que le tiroir-caisse. Les exceptions sont certaines procédures de clôture de caisse. Si l'utilisateur POS reçoit un message d'erreur qui indique qu'une opération ne peut pas être effectuée tandis que le tiroir-caisse, l'utilisateur doit clôturer le tiroir-caisse virtuel ou physique pour continuer. Si un tiroir-caisse est marqué comme ** partagé ** dans le profil matériel, le système ne vérifie pas si le tiroir-caisse est terminé avant une opération. L'opération continue normalement, même si le tiroir-caisse. Ce comportement prend en charge les cas où des tiroirs-caisse sont partagés entre des associers de ventes, et dans lequel un associer utilise un tiroir-caisse alors qu'un autre associer effectue des tâches indépendantes dans son propre périphérique du PDV. Les modifications effectués dans le tiroir-caisse ne sont pas indique jusqu'à ce que l'équipe actuelle est clôturée et une équipe est ouverte.

### <a name="msr-capabilities"></a>Capacités de LBM

Le simulateur périphérique prend en charge le robuste des opérations virtuelles de LBM en travaillant en mode OPOS ou mode de s'arrête en de clavier. Le mode OPOS requiert que le LBM soit paramétré dans le profil matériel pour fonctionner comme périphérique OPOS. Mode de s'arrête en de clavier envoie juste des événements de données de s'arrête en de clavier à Microsoft Windows. Outre les différences entre le paramétrage, les modes de s'arrête en OPOS et de clavier diffèrent des manières suivantes :

-   Le client du PDV permet des périphériques OPOS LBM pour les scénarios spécifiques, tels que les scénarios qui permettent les données de bande magnétique pour la fidélité ou l'entrée de carte cadeau.
-   En mode de s'arrête en de clavier, un simulateur périphérique envoie des données de s'arrête en de clavier dans le champ actif lorsque les données sont envoyées. Ce comportement est semblable au comportement qui se produit si les données sont entrées à l'aide d'un clavier. Pour utiliser le LBM comme s'arrête en de clavier, l'utilisateur doit basculer vers le Retail Modern POS (MPOS) pour assurer que les données soient réceptionnées dans le champ approprié. Par conséquent, vous pouvez configurer un retard, afin que l'utilisateur ait le temps pour garantir que les données seront envoyées au champ approprié.

#### <a name="testing-gift-and-payment-card-swipes"></a>Passages de carte de carte de cadeaux et le paiement de test

Le tiroir caisse virtuel que le simulateur périphérique fournit également vous pouvez configurer des données de LBM aux scénarios de test pour le cadeau et la carte de paiement passe la carte. Pour créer une carte, cliquez sur le bouton de plus (**+**), puis sélectionnez le type de carte. Vous spécifiez le numéro de carte ou suivez les données qui doivent être envoyées dans le système POS, avec le mois d'expiration et l'année de la carte que vous définissez. La valeur sélectionnée dans ** type de carte ** le champ est simplement une étiquette qui peut être définie pour une carte. Cette étiquette facilite l'identification des cartes lorsqu'elles ont dépassé la carte via le simulateur périphérique. Vous pouvez sélectionner les cartes qui ont été configurées dans le simulateur périphérique à l'aide de les boutons de flèche vers&lt;la gauche (****) et de flèche vers la droite (&gt;****) au-dessus de l'image de la carte. Vous pouvez modifier et les cartes de suppression à l'aide de le ** modifiez ** et ** Supprimer ** des boutons en regard de le signe plus (**+** se bouton).

### <a name="pin-pad"></a>Clavier d'identification personnelle

Vous pouvez configurer le simulateur de clavier d'identification personnelle pour simuler une clavier d'identification personnelle OPOS. Lorsqu'une transaction de (EFT) de transfert électronique de fonds est effectuée au niveau de le POS et requiert l'entrée PIN, la station matérielle appelle le périphérique PIN pour l'inviter pour l'entrée d'identification personnelle. Pour exécuter, le clavier d'identification personnelle dans le simulateur périphérique exige du support de Business Connector de paiement TEF.

### <a name="printer"></a>Imprimante

Les montre les réceptions d'impression du périphérique virtuel ainsi que leur impression du PDV. Si une opération d'impression produit les réceptions multiples, vous pouvez parcourir les réceptions.

#### <a name="configure-receipt-printing"></a>Configurez l'impression de réception

1.  Allez ** au détail et commerce ** &gt; ** au canal paramétré ** &gt; ** la configuration ** &gt; ** des profils de PDV ** &gt; ** des profils matériels **.
2.  Sélectionnez le profil matériel créé pour les périphériques virtuels.
3.  Sous ** imprimante ** l'organisateur, cliquez sur ** modifiez **.
4.  Dans ** ID profil du ticket de caisse ** le champ, sélectionnez un profil de ticket de caisse.
5.  Click **Save**.

### <a name="scale"></a>Echelle

Lorsqu'un produit d'échelle est ajouté à la transaction POS, et une échelle est configurée, le POS extrait le poids de l'échelle. Pour l'échelle virtuelle et physique, le produit ou le poids doit être spécifié avant que le produit est ajouté à la transaction. Avant d'ajouter le produit d'échelle à la transaction, accédez à l'échelle dans le simulateur périphérique, et d'utiliser le signe plus (**+**) et les boutons de signe moins (** – **) pour ajuster le poids que l'échelle doit déclarer. Vous pouvez également entrer le poids souhaité directement dans ** valeur actuelle ** le champ. Vous pouvez ajuster les unités de poids à l'échelle en utilisant le signe plus (**+**), ** modifiez **, et ** Supprimer ** des boutons. De cette manière, des unités peuvent être spécifiées sur les produits qui sont pesées ou les paramètres régionaux où l'échelle est utilisée.

#### <a name="configure-a-scale-product"></a>Configuration d'un produit d'échelle

1.  Allez ** au détail et ** ** au commerce ** &gt; ** les produits et les catégories ** &gt; ** des produits lancés par catégorie **.
2.  Ouvrez l'enregistrement de produit.
3.  Sélectionnez le produit à peser.
4.  Sous ** au détail ** l'organisateur, définissez ** produit d'échelle ** l'option de ** aucun ** sur Oui ** **.

#### <a name="synchronize-changes-to-the-channel-database"></a>Synchronisez les modifications à la base de données des canaux

1.  Allez ** au détail et commerce ** &gt; ** à l'IT au détail ** &gt; ** programme de distribution **.
2.  Sélectionnez ** 1040 ** le programme de distribution.
3.  Cliquez sur ** exécution désormais ** pour synchroniser les modifications au niveau de le POS.

Une fois les données soient synchronisées, lorsqu'un produit d'échelle est ajouté à la transaction POS, le POS vérifie l'échelle du poids.

### <a name="signature-capture"></a>Capture de signature

Le périphérique virtuel de capture de signature invite l'utilisateur à fournir une signature sur le clavier virtuelle de capture de signature si l'offre utilisée a besoin d'une signature. L'utilisateur peut accepter la signature pour afficher celui-ci dans le système POS. Le caissier peut alors accepter la signature. La signature est alors enregistrée avec l'offre et est synchronisée au flux administratifs utilisés avec d'autres données de transaction.

#### <a name="set-up-a-tender-to-require-a-signature"></a>Paramétrez une offre pour demander une signature

1.  Allez ** au détail et commerce ** &gt; ** les canaux ** &gt; ** les magasins de vente au détail ** &gt; ** tous les magasins de vente au détail **.
2.  Sélectionnez le magasin de vente au détail.
3.  Cliquez sur **Modifier**.
4.  Cliquez sur ** paramétrage **, puis, dans ** paramétrage ** la section, cliquez sur ** modes de paiement **.
5.  Cliquez sur **Modifier**.
6.  Sélectionnez le mode de paiement qui nécessite une signature.
7.  Dans ** général ** section sous, ** capture de signature **, définit ** utilisez un dispositif de capture de signature ** l'option ** Oui **.
8.  Dans ** montant minimal de capture de signature ** le champ, entrez le montant minimal qui doit déclencher la capture de signature.

#### <a name="synchronize-changes-to-the-channel-database"></a>Synchronisez les modifications à la base de données des canaux

1.  Allez ** au détail et commerce ** &gt; ** à l'IT au détail ** &gt; ** programme de distribution **.
2.  Sélectionnez ** 1070 ** le programme de distribution.
3.  Cliquez sur ** exécution désormais ** pour synchroniser les modifications au niveau de le POS.

Une fois les données soient synchronisées, lorsqu'une offre est utilisée qui nécessite une signature, et le montant correspond au seuil de signature, les invites du PDV pour une signature sur le périphérique virtuel de capture de signature.

## <a name="additional-configuration"></a>Configuration supplémentaire
Vous pouvez modifier le fichier de configuration du simulateur périphérique plus appropriée à l'adresse les scénarios testée. Vous pouvez trouver le fichier de configuration à C : Program Files\\(x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Le fichier de configuration définit les unités qui sont disponibles pour tester dans l'échelle, les types de cartes disponibles pour tester, et le code-barres d'acheminement. Par exemple, en modifiant les valeurs de texte dans le fichier de configuration, vous pouvez ajouter un nouvel type ou unité de mesure de carte qui peuvent être sélectionnés au moment de l'exécution. Les nouvelles valeurs apparaissent une fois la candidature est redémarré.

## <a name="troubleshooting"></a>Dépannage
Les activités pour le simulateur périphérique sont enregistrées dans le simulateur périphérique. Vous pouvez trouver le journal à C : Program Files\\(x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Dans simulateur les problèmes périphériques d'états également dans le journal d'événements Windows, auquel vous pouvez accéder ** application et aux services enregistre ** &gt; ** Microsoft DynamicsAX ** &gt; ** **. Si les modifications apportées au profil matériel ou à d'autres zones ne sont pas évidentes lorsque vous utilisez MPOS ou le simulateur périphérique, vérifiez les tâches du planificateur de distribution avoir synchronisé les données à la base de données des canaux. Si des changements sont synchronisées mais ne sont pas toujours évidentes dans le système POS, redémarrez le client du PDV. Les modifications vers les tiroirs-caisse configurés ne sont pas effectives jusqu'à ce qu'une équipe créée. Par conséquent, si vous apportez des modifications à des tiroirs-caisse, assurez-vous que vous fermez toujours l'équipe existante pour tester le nouveau paramétrage du tiroir-caisse. Parfois, si le chauffeur d'un fabricant est installé après les objets de contrôle commun des services de consultance de Monroe, le pilote peut effectuer pour arrêter les objets de contrôle commun de fonctionner correctement. Dans ce cas, vous devez réinstaller les objets de contrôle commun.

<a name="see-also"></a>Voir également :
--------

[Retail peripherals overview](retail-peripherals-overview.md)


