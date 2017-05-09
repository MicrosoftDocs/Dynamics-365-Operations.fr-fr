---
title: "Simulateur périphérique de vente au détail"
description: "Cette rubrique décrit l&quot;outil de simulation périphérique qui est fourni avec Microsoft Dynamics 365 for Operations - Vente au détail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
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

# <a name="retail-peripheral-simulator"></a>Simulateur périphérique de vente au détail

[!include[banner](includes/banner.md)]


Cette rubrique décrit l'outil de simulation périphérique qui est fourni avec Microsoft Dynamics 365 for Operations - Vente au détail.

<a name="overview"></a>Vue d'ensemble
--------

Le simulateur périphérique Microsoft Dynamics 365 for Operations - Vente au détail est un outil qui vous permet de paramétrer, tester et dépanner les périphériques à utiliser dans des environnements de vente au détail. Vous pouvez utiliser le simulateur périphérique pour rationaliser les tests des périphériques de détail et pour isoler les problèmes causés par une configuration incorrecte ou un dysfonctionnement des pilotes de périphérique. Le simulateur périphérique comprend un programme de bureau qui présente des versions virtuelles de périphériques compatibles avec Dynamics 365 for Operations - Vente au détail. Une section pour chaque périphérique virtuel montre l'interaction entre l'appareil et le point de vente au détail (PDV). Vous pouvez également l'utiliser pour fournir des données valides pour différents scénarios du PDV. Le simulateur périphérique prend en charge l'interaction entre le PDV et les périphériques virtuels suivants :

-   **Imprimante** – Le simulateur périphérique peut afficher les reçus qui sont configurés pour une imprimante du PDV.
-   **Affichage de ligne** – Vous pouvez configurer un affichage de ligne virtuelle pour afficher l'activité sur un affichage de ligne physique.
-   **Lecteur de bande magnétique (MSR)** Vous pouvez envoyer des événements de bande magnétique simulés sur le PDV à partir du simulateur périphérique.
-   **Tiroir-caisse** – Vous pouvez simuler un tiroir-caisse physique.
-   **Tiroir-caisse 2** – En paramétrant un second tiroir-caisse dans le simulateur périphérique, vous pouvez simuler des scénarios impliquant un registre de PDV unique avec deux équipes actives.
-   **Scanneur** – Le scanneur de code-barres virtuel compatible avec le simulateur périphérique peut émettre des événements de numérisation de code-barres.
-   **Balance** – Une balance virtuelle permet de simuler l'interaction des articles pesés avec le PDV.
-   **Pavé PIN (Personal identification number)** – Vous pouvez simuler des opérations de pavé avec identification personnelle. **Remarque :** Vous devez implémenter un support pour un pavé PIN physique via le connecteur de paiement.
-   **Capture de signature** – Le simulateur périphérique inclut un périphérique de capture de signature virtuel que vous pouvez paramétrer pour demander des signatures requises pour certaines offres, tels que les paiements de compte client.

Vous pouvez également utiliser le simulateur périphérique pour simuler des événements clavier Wedge issus d'un scanneur à code-barres et de LBM. Le simulateur périphérique virtuel prend spécifiquement en charge les liaisons et l'intégration d'objets pour les périphériques Retail POS (OPOS).

## <a name="key-scenarios"></a>Principaux scénarios
### <a name="troubleshooting"></a>Dépannage

Vous pouvez utiliser le simulateur périphérique pour résoudre les problèmes liés à la configuration du périphérique. Si vous ne disposez pas du simulateur périphérique ni d'un deuxième périphérique de la même classe, il peut être difficile de déterminer l'origine des problèmes. Toutefois, lorsque vous avez le simulateur périphérique, vous pouvez paramétrer les périphériques virtuels, puis exécuter les chemins d'accès au code et la même logique métier utilisés pour les périphériques physiques. Du point de vue du simulateur périphérique, la différence principale entre les périphériques virtuels et les périphériques physiques est l'objet de service ou le pilote du périphérique. Pour les périphériques physiques, l'objet de service pour un périphérique est fourni par le fabricant de celui-ci. En revanche, pour le simulateur périphérique, les objets de service sont fournis dans le cadre du simulateur périphérique. Lorsque le simulateur périphérique fonctionne correctement, si un périphérique ne fonctionne pas correctement après la modification du nom du périphérique dans le profil matériel par le nom d'un périphérique réel, vous pouvez supposer qu'il y a un problème avec l'objet de service fourni par le fabricant.

### <a name="training"></a>Formation

Vous pouvez utiliser le simulateur périphérique pour ajouter une couche réaliste à la formation en caisse lorsqu'un paramétrage physique n'est pas disponible. Lorsque le simulateur périphérique est inclus dans les scénarios de formation, le caissier peut interagir plus efficacement avec le poste de travail en fournissant des informations telles que les analyses de code à barres de produits et les balises de cartes-cadeaux, et en observant les reçus imprimés pour une transaction spécifique.

### <a name="testing"></a>Test

Vous pouvez utiliser le simulateur périphérique pour tester des code-barres de produit, formats de reçu, etc., sans devoir déployer le matériel physique dans un environnement virtuel. Comme le matériel physique n'est pas nécessaire, et que vous ne devez pas déployer un client du PDV dans une station matérielle ou un ordinateur physique, vous pouvez plus rapidement tester les modifications qui sont apportées en back-office.

## <a name="set-up-the-peripheral-simulator"></a>Paramétrer le simulateur périphérique
### <a name="set-up-a-hardware-profile"></a>Paramétrage d'un profil matériel

1.  Pour configurer le simulateur périphérique, accédez à **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **Profils POS** &gt; **Profils du matériel**.
2.  Pour créer un profil, cliquez sur **Nouveau**.
3.  Entrez des valeurs dans les champs **Numéro de profil** et **Description**.
4.  La table suivante permet de définir les périphériques virtuels à tester. Voici une explication des colonnes du tableau :
    -   **Périphérique** – Cette colonne donne le nom de l'organisateur que vous développez pour paramétrer le périphérique.
    -   **Type de périphérique** – Cette colonne donne la valeur que vous sélectionnez dans le champ qui est libellé avec le nom du périphérique.
    -   **Nom du périphérique** – Cette colonne donne une valeur exacte que vous entrez pour le nom du périphérique. **Important :** Les noms de périphérique qui sont définis ici sont requis, car la station matérielle utilise ces noms spécifiques pour corriger les périphériques. Si vous n'utilisez pas de noms spécifiques, le périphérique ne sera pas utilisable.

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

**Remarque :** Aucun paramétrage spécifique dans le profil matériel n'est requis pour simuler des événements de clavier Wedge à partir du scanneur de code-barres et du LBM.

### <a name="assign-the-hardware-profile-to-a-register"></a>Affectation du profil matériel à un registre

1.  Une fois le profil matériel créé, accédez à **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **Registres**.
2.  Dans **Registres POS**, cliquez sur le lien du champ **Numéro de caisse enregistreuse** pour le registre qui doit utiliser le simulateur périphérique.
3.  Cliquez sur **Modifier**.
4.  Dans la section **Profils**, dans le champ **Profil matériel**, sélectionnez le profil matériel que vous avez créé pour les périphériques virtuels.
5.  Cliquez sur **Enregistrer**.

### <a name="synchronize-changes-to-the-channel-database"></a>Synchroniser les modifications à la base de données des canaux

1.  Accédez à **Commerce et vente au détail** &gt; **Informatique de vente au détail** &gt; **Programme de distribution**.
2.  Sélectionnez le programme de distribution **1090**.
3.  Cliquez sur **Exécuter maintenant** pour synchroniser les modifications avec le PDV.

Une fois que les données sont synchronisées, le nouveau profil matériel et les modifications de la caisse enregistreuse sont disponibles dans la base de données des canaux.

## <a name="install-the-peripheral-simulator"></a>Installer le simulateur périphérique
1.  Accédez à **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **Profils POS** &gt; **Profils matériels**.
2.  Cliquez sur **Télécharger**, puis sur **PeripheralSimulator**. **Remarque :** vous devez désactiver les bloqueurs de fenêtres contextuelles avant de télécharger le simulateur périphérique.
3.  Une fois le téléchargement effectué, ouvrez le dossier **Téléchargements**, puis double-cliquez sur **VirtualPeripherals.msi** pour démarrer le programme d'installation.
4.  Installez le simulateur périphérique à l'aide des paramètres par défaut.

Outre le simulateur périphérique, vous devez installer les objets de contrôle commun de Monroe Consulting Services. Sinon, le simulateur périphérique ne fonctionnera pas correctement. Pour télécharger les objets de contrôle commun, cliquez sur <http://monroecs.com/oposccos_current.htm>.

## <a name="using-the-peripheral-simulator"></a>Utilisation du simulateur périphérique
Pour lancer le simulateur périphérique, cliquez sur **Démarrer** sur votre ordinateur, saisissez **Simulateur périphérique de vente au détail**, puis sélectionnez l'application lorsqu'elle apparaît dans les résultats de la recherche. Après avoir démarrer le simulateur périphérique, cliquez sur le nom du périphérique pour afficher les périphériques pris en charge. Ces périphériques sont répertoriés sous forme d'onglets à gauche de la fenêtre. Pour afficher un périphérique spécifique, cliquez sur l'onglet de ce périphérique.

### <a name="line-display-capabilities"></a>Capacités d'affichage de la ligne

L'affichage de ligne est le premier périphérique répertorié dans le simulateur périphérique. Lorsque l'affichage de la ligne virtuelle est configuré, les éléments de la ligne apparaissent au fur et à mesure de leur numérisation dans la transaction PDV. Outre les articles de la ligne, l'affichage indique le total dû lorsqu'une offre est sélectionnée dans le système PDV. Elle présente également le solde dû si une offre est entrée mais qu'un solde est toujours dû pour la transaction. Lorsque le PDV n'est pas utilisé, un message s'affiche pour indiquer que la caisse enregistreuse est clôturée. Vous devez configurer le message dans l'organisateur **Affichage de ligne** du profil matériel.

### <a name="cash-drawer-capabilities"></a>Capacités du tiroir-caisse

Le tiroir-caisse est le second périphérique répertorié dans le simulateur périphérique. Lorsque le profil matériel est configuré pour utiliser les tiroirs-caisse virtuels, le PDV affiche le tiroir-caisse pour l'équipe active en réponse à des opérations du tiroir, telles que des comptages de caisse, et pour que le caissier puisse effectuer une modification ou déposer de l'argent au cours des opérations de caisse et de transport standard. Les tiroirs-caisse virtuels ont des étiquettes **Tiroir principal** et **Tiroir secondaire**. Ces étiquettes représentent le Tiroir-caisse et le Tiroir-caisse 2 dans le profil matériel, respectivement. Lorsqu'un tiroir-caisse est clôturé, l'image d'un tiroir-caisse clôturé est affichée, et le bouton du tiroir-caisse clôturé est intitulé **Ouvrir tiroir-caisse**. Si vous cliquez sur ce bouton, l'image est remplacée par l'image d'un tiroir-caisse ouvert pour indiquer que le tiroir-caisse est désormais ouvert. Le bouton dans le tiroir-caisse ouvert est intitulé **Fermer tiroir-caisse**. Plusieurs opérations au niveau du PDV peuvent ouvrir le tiroir-caisse. La plupart des opérations ne peuvent pas être effectuées tant que le tiroir-caisse est ouvert. Les exceptions concernent des procédures de fin de journée. Si l'utilisateur du PDV reçoit un message d'erreur qui indique qu'une opération ne peut pas être effectuée tant que le tiroir-caisse est ouvert, l'utilisateur doit fermer le tiroir-caisse virtuel ou physique pour continuer. Si un tiroir-caisse est marqué comme **Partagé** dans le profil matériel, le système ne vérifie pas si le tiroir-caisse est fermé avant une opération. L'opération se poursuit normalement, même si le tiroir-caisse est ouvert. Ce comportement prend en charge les scénarios où les caisses enregistreuses sont partagées entre les associés de vente, et lorsqu'un associé utilise un tiroir-caisse alors qu'un autre associé exécute des tâches indépendantes sur son propre périphérique PDV. Les modifications apportées au tiroir-caisse ne sont pas évidentes tant que le changement d'équipe n'intervient pas (fermeture et ouverture de caisse).

### <a name="msr-capabilities"></a>Capacités LBM

Le simulateur périphérique fournit un support robuste pour les opérations LBM virtuelles en travaillant en mode OPOS ou en mode clavier Wedge. Le mode OPOS requiert que le LBM soit paramétré dans le profil matériel pour fonctionner comme un périphérique OPOS. Le mode clavier Wedge envoie simplement des événements de données de clavier Wedge à Microsoft Windows. Outre les différences de paramétrage, les modes de clavier Wedge et OPOS diffèrent des manières suivantes :

-   Le client PDV permet aux périphériques OPOS LBM pour des scénarios spécifiques, tels que des scénarios qui permettent des données de bande magnétique pour la saisie de données de fidélité ou de carte-cadeau.
-   En mode clavier Wedge, le simulateur périphérique envoie des données du clavier Wedge au champ qui est actif lorsque les données sont envoyées. Ce comportement est semblable au comportement qui se produit si les données sont entrées à l'aide d'un clavier. Pour utiliser le LBM comme clavier Wedge, l'utilisateur doit basculer en mode Retail Modern POS (MPOS) pour vérifier que les données sont réceptionnées dans le champ approprié. Par conséquent, vous pouvez configurer un délai, afin que l'utilisateur ait le temps de vérifier que les données seront envoyées au champ approprié.

#### <a name="testing-gift-and-payment-card-swipes"></a>Test d'insertion des cartes cadeaux et des cartes de paiement

Le LBM virtuel que le simulateur périphérique fournit vous permet également de configurer des données MSR spécifiques pour tester des scénarios pour les balises de cartes cadeaux et de paiement. Pour créer une carte, cliquez sur le bouton plus (**+**), puis sélectionnez le type de carte. Ensuite, spécifiez le numéro de carte ou suivez les données qui doivent être envoyées dans le système PDV, avec le mois et l'année d'expiration de la carte que vous définissez. La valeur sélectionnée dans le champ **Type de carte** est simplement une étiquette qui peut être définie pour une carte. Cette étiquette facilite l'identification des cartes lorsque celles-ci sont insérées dans le simulateur périphérique. Vous pouvez sélectionner les cartes qui ont été configurées dans le simulateur périphérique à l'aide des boutons fléchés à gauche (**&lt;**) et à droite (**&gt;**) au-dessus de l'image de la carte. Vous pouvez modifier et supprimer les cartes à l'aide des boutons **Modifier** et **Supprimer** en regard du bouton de signe plus (**+**).

### <a name="pin-pad"></a>Clavier d'identification personnelle

Vous pouvez configurer le simulateur de clavier d'identification personnelle pour simuler un clavier d'identification personnelle OPOS. Lorsqu'une transaction de transfert électronique de fonds est effectuée au niveau du PDV et requiert la saisie du code PIN, la station matérielle appelle le périphérique PIN pour demander la saisie du code d'identification personnelle. Pour fonctionner, le pavé PIN du simulateur périphérique nécessite la prise en charge du connecteur de paiement TEF.

### <a name="printer"></a>Imprimante

L'imprimante du périphérique virtuel affiche les tickets de caisse au fil de leur impression du PDV. Si une opération d'impression produit plusieurs tickets de caisse, vous pouvez les consulter.

#### <a name="configure-receipt-printing"></a>Configurer l'impression d'un ticket de caisse

1.  Accédez à **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **Profils POS** &gt; **Profils matériels**.
2.  Sélectionnez le profil matériel créé pour les périphériques virtuels.
3.  Sous l'organisateur **Imprimante**, cliquez sur **Modifier**.
4.  Dans le champ **ID profil du ticket de caisse**, sélectionnez un profil de ticket de caisse.
5.  Cliquez sur **Enregistrer**.

### <a name="scale"></a>Echelle

Lorsqu'un produit à l'échelle est ajouté à la transaction PDV, et qu'une balance est configurée, le PDV extrait le poids de la balance. Pour la balance virtuelle et la balance physique, le produit ou le poids doit être spécifié avant que le produit ne soit ajouté à la transaction. Avant d'ajouter le produit à l'échelle à la transaction, accédez à la balance dans le simulateur périphérique, et utilisez les boutons de signe plus (**+**) et les boutons de signe moins (**–**) pour ajuster le poids que la balance doit indiquer. Vous pouvez également entrer le poids souhaité directement dans le champ **Valeur actuelle**. Vous pouvez ajuster les unités de poids à l'échelle en utilisant les boutons signe plus (**+**), **Modifier** et **Supprimer**. De cette façon, les unités peuvent être spécifiées en fonction des produits pesés ou des paramètres régionaux où la balance est utilisée.

#### <a name="configure-a-scale-product"></a>Configurer un produit à l'échelle

1.  Accédez à **Commerce et** **vente au détail** &gt; **Produits et catégories** &gt; **Produits lancés par catégorie**.
2.  Ouvrez l'enregistrement de produit.
3.  Permet de sélectionner le produit à peser.
4.  Dans l'organisateur **Vente au détail**, faites basculer l'option **Mettre le produit à l'échelle** de **Non** à **Oui**.

#### <a name="synchronize-changes-to-the-channel-database"></a>Synchroniser les modifications à la base de données des canaux

1.  Accédez à **Commerce et vente au détail** &gt; **Informatique de vente au détail** &gt; **Programme de distribution**.
2.  Sélectionnez le programme de distribution **1040**.
3.  Cliquez sur **Exécuter maintenant** pour synchroniser les modifications avec le PDV.

Lorsqu'un produit à l'échelle est ajouté à la transaction PDV, et qu'une balance est configurée, le PDV extrait le poids de la balance.

### <a name="signature-capture"></a>Capture de signature

Le périphérique virtuel de capture de signature invite l'utilisateur à fournir une signature sur le clavier de capture de signature virtuelle si l'offre utilisée requiert une signature. L'utilisateur peut accepter que la signature s'affiche dans le système PDV. Le caissier peut alors accepter la signature. La signature est ensuite sauvegardée avec l'offre et est synchronisée au back office avec d'autres données de transaction.

#### <a name="set-up-a-tender-to-require-a-signature"></a>Paramétrer une offre pour demander une signature

1.  Accédez à **Commerce et vente au détail** &gt; **Canaux** &gt; **Magasins de vente au détail** &gt; **Tous les magasins de vente au détail**.
2.  Sélectionnez le magasin de vente au détail.
3.  Cliquez sur **Modifier**.
4.  Cliquez sur **Paramétrer**, puis, dans la section **Paramétrer**, cliquez sur **Modes de paiement**.
5.  Cliquez sur **Modifier**.
6.  Sélectionnez le mode de paiement qui requiert une signature.
7.  Dans la section **Général**, sous **Capture de signature**, définissez l'option **Utiliser l'appareil de capture de signature** sur **Oui**.
8.  Dans le champ **Montant minimal de capture de signature**, entrez le montant minimal qui doit déclencher la capture de signature.

#### <a name="synchronize-changes-to-the-channel-database"></a>Synchroniser les modifications à la base de données des canaux

1.  Accédez à **Commerce et vente au détail** &gt; **Informatique de vente au détail** &gt; **Programme de distribution**.
2.  Sélectionnez le programme de distribution **1070**.
3.  Cliquez sur **Exécuter maintenant** pour synchroniser les modifications avec le PDV.

Une fois que les données sont synchronisées, lorsqu'une offre est utilisée et requiert une signature, et que la quantité correspond au seuil de signature, le PDV demande une signature sur le périphérique de capture de signature virtuelle.

## <a name="additional-configuration"></a>Configuration supplémentaire
Vous pouvez modifier le fichier de configuration du simulateur périphérique pour mieux traiter les scénarios que vous testez. Vous pouvez trouver le fichier de configuration à l'emplacement suivant : C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Le fichier de configuration définit les unités disponibles pour le test sur la balance, les types de cartes disponibles pour les tests et les types de code-barres. Par exemple, en modifiant les valeurs de texte dans le fichier de configuration, vous pouvez ajouter un nouveau type ou une nouvelle unité de mesure de carte qui peut être sélectionné(e) au moment de l'exécution. Les nouvelles valeurs apparaissent une fois que l'application redémarre.

## <a name="troubleshooting"></a>Dépannage
Les activités du simulateur périphérique sont enregistrées dans le simulateur périphérique. Vous pouvez trouver le fichier log à l'emplacement suivant : C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. Le simulateur périphérique indique également les problèmes détectés dans le journal d'événements Windows, auquel vous pouvez accéder dans **Journaux des applications et des services** &gt; **Microsoft** &gt; **DynamicsAX**. Si les modifications apportées au profil matériel ou à d'autres zones ne sont pas évidentes lorsque vous utilisez MPOS ou le simulateur périphérique, vérifiez les tâches du planificateur de distribution ayant permis de synchroniser les données dans la base de données des canaux. Si les changements sont synchronisés mais ne sont pas toujours évidents dans le système PDV, redémarrez le client PDV. Les modifications apportées aux tiroirs-caisses configurés ne sont effectives qu'après la création d'une nouvelle équipe de travail. Par conséquent, si vous apportez des modifications à des tiroirs-caisse, assurez-vous que vous fermez toujours l'équipe existante pour tester le nouveau paramétrage du tiroir-caisse. Parfois, si le pilote d'un fabricant est installé après les objets de contrôle commun de Monroe Consulting Services, le pilote peut perturber le fonctionnement normal des objets de contrôle commun. Dans ce cas, vous devez réinstaller les objets de contrôle commun.

<a name="see-also"></a>Voir également :
--------

[Vue d'ensemble des périphériques de vente au détail](retail-peripherals-overview.md)




