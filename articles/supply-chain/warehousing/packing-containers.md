---
title: Emballage de conteneurs à expédier
description: Cet article décrit le processus d’emballage qui vous permet de valider les articles en stock et de les emballer dans des conteneurs.
author: perlynne
ms.date: 7/13/2022
ms.topic: business-process
ms.search.form: WHSLocationType, WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup, WHSPack, WHSContainerTable,
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 118b1c79d23cd1b5044ede9aa9c469409cd22166
ms.sourcegitcommit: 9e6a9d644a34158390c6e209e80053ccbdb7d974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708781"
---
# <a name="pack-containers-for-shipment"></a>Emballage de conteneurs à expédier

[!include [banner](../../includes/banner.md)]

Le processus d'emballage de conteneurs vous permet de valider les articles en stock et de les emballer dans des conteneurs. Au cours de ce processus, les magasiniers sélectionnent généralement les articles en stock dans les zones de stockage en masse et les déplacent vers une zone d’emballage. Là, plusieurs magasiniers vérifient les quantités et les types d’articles et les affectent aux tailles de conteneur appropriées. Lorsqu’un conteneur est entièrement emballé, il est fermé et déplacé vers la zone de quai de sortie, où il est préparé pour l'expédition.

Les conteneurs représentent des structures physiques dans lesquelles les articles sont emballés et vous pouvez suivre les informations sur les conteneurs dans le système. Ces informations peuvent être utiles lors de la planification du transport, en particulier si vous calculez les frais d’expédition en fonction des conteneurs. Avant d’expédier, vous pouvez afficher le nombre de conteneurs utilisés dans un envoi, les types de conteneurs utilisés et les dimensions physiques de chaque conteneur (telles que le volume total et le poids).

Plusieurs fonctionnalités d’entrepôt sortant associées peuvent être utilisées avec des conteneurs. Pour plus d’informations, voir l’article suivant :

- [Conteneurisation vague](wave-containerization.md)
- [Tri sortant](outbound-sorting.md)
- [Expédition de petits colis](small-parcel-shipping.md)
- [Confirmer et transférer](confirm-and-transfer.md)
- [Définir différentes dimensions pour l’emballage et le stockage](packing-vs-storage-dimensions.md)
- [Travaux d’emballage pour l’emballage des conteneurs sortants et le traitement des expéditions](packing-work.md)
- [Conteneurs de conditionnement avec l’application mobile Warehouse Management](warehouse-app-packing-containers.md)
- [Exemple de scénario – Conteneurs de conditionnement avec l’application mobile Warehouse Management](warehouse-app-pack-containers-scenario.md)
- [Imprimer les étiquettes de conteneurs](print-container-labels.md)

## <a name="set-up-your-warehouse-to-use-manual-packing-operations"></a>Configurez votre entrepôt pour utiliser les opérations d’emballage manuelles

Il existe deux manières de base d’organiser vos opérations sortantes :

- **Création et traitement des vagues** – Les travailleurs sélectionnent les articles en fonction du travail d’entrepôt sortant. Ils placent ensuite les articles directement dans un lieu d’expédition sortant, où ils sont prêts pour une expédition immédiate. Pour plus d’informations sur la configuration et l’utilisation de ce processus, voir [Création et traitement des vagues](wave-processing.md).
- **Emballage manuel dans les stations d’emballage** – Ce processus comporte une opération supplémentaire entre les opérations de prélèvement et d’expédition. Au lieu de mettre l’inventaire dans un *emplacement d’expédition de porte de baie*, les ouvriers le mettent dans un *emplacement d’emballage*. Ils gèrent ensuite le processus d’emballage à la station d’emballage en utilisant la page **Emballer** dans le client Web. Pour activer ce processus, vous devez configurer votre système comme décrit dans cette section.

### <a name="set-up-warehouse-locations-for-packing"></a>Définir des emplacements d'entrepôt pour l'emballage

Vous devez disposer d’au moins un emplacement d’emballage où les travailleurs mettront les articles en stock afin qu’ils puissent être emballés dans des conteneurs. Pour plus d'informations sur la façon de créer des emplacements d’entrepôt, voir [Configurer des emplacements dans un entrepôt compatible WMS](tasks\configure-locations-wms-enabled-warehouse.md). Les sous-sections suivantes décrivent comment créer et configurer des emplacements d'emballage.

#### <a name="set-up-location-types-for-packing"></a>Définir les types d'emplacement pour emballage

Vous devez définir un *Type d'emplacement* pour les emplacements d'emballage. Les types d’emplacements peuvent être utilisés comme options de filtrage pour contrôler les différents processus de gestion des entrepôts. Le nom de chaque type d’emplacement décrit généralement quelque chose sur la façon dont ce type d’emplacement doit être utilisé. Le type d’emplacement que vous configurez ici doit être associé à chaque emplacement utilisé pour les opérations d’emballage.

Suivez ces étapes pour configurer un type d'emplacement.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Types d’emplacements**.
1. Dans le volet Action, sélectionnez **Nouveau** pour ajouter un type d'emplacement à la grille.
1. Définissez les champs suivants pour le nouveau type d'emplacement :

    - **Type d'emplacement** – Entrez un nom pour le type d'emplacement. Chaque nom doit être unique et doit décrire quelque chose sur la façon dont le type d’emplacement est destiné à être utilisé.
    - **Description** – Entrez une brève description du type d'emplacement.

#### <a name="inform-the-system-about-the-packing-location-type"></a>Informer le système du type d’emplacement d’emballage

Après avoir créé un type d’emplacement, vous devez configurer votre système pour qu’il le reconnaisse comme le type d’emplacement à utiliser pour les opérations d’emballage.

Suivez ces étapes pour définir le type d’emplacement utilisé pour les opérations d’emballage.

1. Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**
2. Sur l'onglet **Général**, sur le raccourci **Types d’emplacement**, définissez le champ **Type d'emplacement d’emballage** au type d’emplacement que vous utiliserez pour identifier les stations d’emballage.

> [!NOTE]
> Si vous effectuez une mise à niveau à partir d’une version de Microsoft Dynamics AX, le statut *Dans l’emballage* a été supprimé des expéditions et des chargements, car il ne fonctionnait pas de manière cohérente et provoquait des données redondantes. Par conséquent, les pages de liste **En expéditions** et **Charges dans l’emballage** sont obsolètes. Les conteneurs qui doivent être emballés sont suivis au niveau de l’emplacement.
>
> Dans les versions précédentes, vous définissiez l’emplacement d'emballage en utilisant le champ **ID profil pour l'emplacement d’emballage** sur l'onglet **Emballage** de la page **Paramètres de gestion d’entrepôt** pour spécifier un *profil d’emplacement*. Dans la version actuelle, vous utilisez le champ **Type d'emplacement d’emballage** sur l'onglet **Général** de la page **Paramètres de gestion d’entrepôt** pour spécifier un *Type d'emplacement*, comme décrit dans cet article. Le nouveau champ est mieux aligné sur le processus d’identification des emplacements de mises en lots et des emplacements d’expédition finaux.
>
> Bien que vous puissiez continuer à utiliser l’ancien champ **ID profil pour l'emplacement d’emballage**, nous vous recommandons de commencer à utiliser le nouveau champ **Type d'emplacement d’emballage** à la place, car l’ancien champ finira par être obsolète.
>
> Si vous effacez le réglage de l’ancien chanp **ID profil pour l'emplacement d’emballage** et puis enregistrez la page, le champ sera définitivement effacé. Pour les installations où le champ **ID profil pour l'emplacement d’emballage** n’a jamais été utilisé, il sera toujours désactivé. Après avoir effacé le réglage du champ **ID profil pour l'emplacement d’emballage**, utilisez les paramètres décrits dans cet article pour configurer et identifier votre emplacement d’emballage.

#### <a name="set-up-location-profiles-for-packing-locations"></a>Définir des profils d'emplacements pour emplacements d'emballage

Chaque *profil d’emplacement* établit les informations et les règles qui s’appliquent aux emplacements associés. Étant donné que vous avez besoin d’au moins un emplacement à utiliser pour les opérations d’emballage, vous devez créer un profil d’emplacement pour celui-ci en plus d’un type d’emplacement. Chaque profil peut être utilisé par n’importe quel nombre d’emplacements. Les emplacements utilisés pour l’emballage doivent être configurés pour suivre les plaques d’immatriculation.

Suivez ces étapes pour configurer un profil d’emplacement pour un emplacement d’emballage.

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d’emplacement**.
1. Sélectionnez un profil existant du volet de liste ou sélectionnez **Nouveau** dans le volet Action pour en créer un nouveau.
1. Dans l’en-tête du nouveau profil ou du profil sélectionné, définissez les champs suivants :

    - **ID profil d'emplacement** – Entrez un ID unique pour le profil.
    - **Nom** – Entrez un nom descriptif pour le profil.

1. Dans l’organisateur **Général**, définissez les champs suivants :

    - **Format de l’emplacement** – Sélectionnez le format d’emplacement à utiliser pour l’emplacement actuel. Les formats d’emplacements constituent un système de dénomination pour créer des noms uniques et cohérents pour les différentes positions d'emplacement de corbeille utilisées dans un entrepôt. Si vous ne disposez pas déjà du format dont vous avez besoin, vous pouvez le créer en accédant à **Gestion d’entrepôt \> Configuration \> Entrepôt \> Formats d’emplacement**. Pour plus d’informations, consultez [Configurer les emplacements dans un entrepôt compatible WMS](tasks/configure-locations-wms-enabled-warehouse.md).
    - **Type d'emplacement** – Sélectionnez le type d’emplacement défini comme type d’emplacement d’emballage sur la page **Paramètres de gestion d’entrepôt**, comme décrit précédemment dans cet article.
    - **Utiliser le suivi des plaques d’immatriculation** – Pour les emplacements d’emballage, définissez cette option sur *Oui*. Le système doit être en mesure de suivre les identifiants des plaques d’immatriculation aux emplacements d’emballage, afin de pouvoir contrôler le processus d’emballage.
    - **Autoriser l’inventaire négatif** – Pour les emplacements d’emballage, définissez cette option sur *Non*.
    - **Autoriser les articles mixtes** – Pour les emplacements d’emballage, définissez cette option sur *Oui*. Ce paramètre est nécessaire car de nombreux numéros d’articles différents sont généralement apportés aux emplacements d’emballage en même temps.
    - **Autoriser les statuts d'inventaire mixtes** – Pour les emplacements d’emballage, définissez cette option sur *Oui*. Ce paramètre est nécessaire car les articles qui ont des statuts d'inventaire différents sont généralement apportés aux emplacements d’emballage en même temps.
    - **Autoriser les lots d'inventaire mixtes** – Pour les emplacements d’emballage, définissez cette option sur *Oui*. Cette option est automatiquement définie sur *Oui* chaque fois que l’option **Autoriser les articles mixtes** est définie sur *Oui*.

#### <a name="set-up-packing-locations"></a>Paramétrage des emplacements d'emballage

Vous devez disposer d'au moins un *emplacement* où les travailleurs mettront les articles d'inventaire qui doivent être emballés dans des conteneurs.

Suivez ces étapes pour ajouter un emplacement d'emballage.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Emplacements**.
1. Dans le volet Action, sélectionnez **Nouveau** pour ajouter un emplacement.
1. Définissez les champs suivants pour le nouvel emplacement :

    - **Entrepôt** – Spécifiez l'entrepôt où l'emplacement d'emballage doit exister.
    - **Emplacement** – Entrez un nom pour le nouvel emplacement.
    - **Identifiant du profil d’emplacement** – Assurez-vous de spécifier l’ID que vous avez créé dans la section précédente.

## <a name="set-up-the-packing-process"></a>Configurer le processus d’emballage

Cette section décrit comment configurer les paramètres qui activent le processus d’emballage et permettent aux travailleurs d’emballer l’inventaire dans des conteneurs.

### <a name="set-up-container-packing-policies"></a><a name="packing-policy"></a>Définir des stratégies d’emballage de conteneurs

Chaque *politique d’emballage des conteneurs* définit comment un conteneur doit être traité. Chaque fois que vous créez un nouveau conteneur, vous sélectionnerez également une politique d’emballage de conteneur à lui appliquer.

Procédez comme suit pour définir une stratégie d’emballage de conteneur.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Conteneurs \> Stratégies d’emballage de conteneurs**.
1. Sélectionnez une politique existante du volet de liste ou sélectionnez **Nouveau** dans le volet Action pour en créer un nouveau.
1. Dans l’en-tête de la nouvelle stratégie ou de la stratégie sélectionnée, définissez les champs suivants :

    - **Politique d’emballage des conteneurs** – Saisissez un nom unique pour la politique.
    - **Description** – Entrez un nom descriptif pour la politique.

1. Dans l’onglet **Vue d’ensemble**, définissez les champs suivants : Ces champs vous permettent de spécifier quelles actions doivent être entreprises lorsque le conteneur est fermé, s’il faut opérer avec ou sans création de travail, et quand le conteneur doit être libéré de la station d’emballage.

    - **Entrepôt** – Sélectionnez l’entrepôt où la politique d'emballage s'applique.
    - **Emplacement par défaut pour l’expédition finale** – Spécifiez l’emplacement préféré du conteneur après sa fermeture. Ce champ est disponible seulement lorsque le champ **Politque de libération de conteneur** est défini sur *Rendre disponible à l'emplacement d'expédition final*.
    - **Emplacement par défaut pour le tri** – Ce champ est utilisé avec la capacité [tri sortant](outbound-sorting.md).
    - **Unité de poids** – Sélectionnez l’unité de mesure par défaut à utiliser lorsqu’un conteneur est fermé et manifesté. En règle générale, cette unité de mesure sera l’unité de mesure utilisée par une balance au poste d’emballage. Ce champ s’applique aux politiques avec ou sans création de travail.
    - **Politique de fermeture des conteneurs** – Sélectionnez l’une des options suivantes pour définir ce qui doit se produire lorsque le conteneur est fermé :

        - *Libération automatique* – Le conteneur sera considéré comme libéré de la station d’emballage et l’action spécifiée dans le champ **Politique de libération des conteneurs** sera déclenchée.
        - *Libération retardée* – Le conteneur ne sera pas immédiatement libéré de la station d’emballage. Un magasinier doit le libérer manuellement plus tard.
        - *Optionnel* – Pendant qu’un travailleur ferme le conteneur, il pourra choisir si le conteneur doit être libéré.

        Si la station d’emballage gère principalement des conteneurs individuels qui sont expédiés directement aux clients, l’approche la plus naturelle consiste à libérer les conteneurs immédiatement. Si la station d’emballage gère des envois composés de plusieurs conteneurs ou même de palettes, il est probablement préférable de retarder la libération jusqu’à ce que l’ensemble de l’envoi ou de la palette ait été emballé et soit prêt à être récupéré.

    - **Politique de libération de conteneurs** – Sélectionnez l’une des options suivantes pour définir ce qui doit se produire lorsque le conteneur est libéré de l'emplacement d'emballage :

        - *Rendre disponible à l'emplacement d’expédition final* – Mettre à jour le conteneur vers l'emplacement d’expédition final. Si vous sélectionnez cette option, utililsez le champ **Emplacement par défaut pour l’expédition finale** pour spécifier un emplacement préféré du conteneur après sa fermeture.
        - *Créer un travail pour déplacer le conteneur de la station d’emballage* – Créer un travail pour déplacer le conteneur de la station d’emballage à la zone de mise en lots ou directement à la porte de baie. Utilisez le champ **Modèle de travail** pour spécifier le modèle de travail qui doit être appliqué lors de la création du travail pour le conteneur.
        - *Affecter le conteneur à la position de tri sortant* – Cette option est utilisée avec la capacité de [tri sortant](outbound-sorting.md).

        Dans la plupart des cas, nous vous recommandons de créer un travail pour déplacer les conteneurs, car cette approche représente mieux les processus manuels réels dans l’entrepôt. Cependant, pour des scénarios simples ou des situations où la station d’emballage est située directement dans la zone de la porte de la baie, il peut être préférable que le conteneur soit immédiatement disponible à l'emplacement d’expédition final.

    - **Modèle de travail** – Sélectionnez le modèle de travail qui doit être appliqué lors de la création du travail pour le conteneur. Ce champ n’est disponible que lorsque le champ **Politique de libération des conteneurs** est défini sur *Créer un travail pour déplacer le conteneur de la station d’emballage* et lié à un type d’ordre de travail nommé *Préparation de conteneurs emballés*. Pour plus d'informations, voir [Modèles de travail et directives d'emplacement](control-warehouse-location-directives.md).

    Dans les étapes restantes, vous configurerez les paramètres liés à *manifester*. Le manifeste est le processus qui consiste à spécifier le poids d’un conteneur, d’un groupe de conteneurs ou d’une expédition, ainsi que l’ID de suivi reçu d’un fournisseur de transport. Dynamics 365 Supply Chain Management ne s’intègre pas aux systèmes des fournisseurs de transport externes. Au lieu de cela, les employés d’entrepôt doivent imprimer les étiquettes reçues du fournisseur de transport, puis numériser un numéro de suivi lorsqu’ils terminent la procédure de manifeste.

    Étant donné que les exigences en matière de manifestes varient d’un client à l’autre, et même d’une expédition à l’autre, les politiques d’emballage permettent une grande flexibilité dans le flux de travail. Vous pouvez configurer des manifestes pour les conteneurs, les groupes de conteneurs et les expéditions dans n’importe quelle combinaison.

    Si vous utilisez une procédure de manifeste à plusieurs niveaux, les agents doivent manifester tous les conteneurs avant de manifester le groupe de conteneurs associé, et ils doivent manifester tous les groupes de conteneurs avant de manifester l’expédition associée.

1. Dans le raccourci **Manifeste de conteneur**, définissez les champs suivants :

    - **Manifeste automatique à la fermeture du conteneur** – Réglez cette option sur *Oui* pour appliquer les informations du manifeste dans le cadre du processus de fermeture du conteneur. Si vous n’utilisez pas l’intégration du transport, les informations doivent être enregistrées manuellement.
    - **Exigences du manifeste pour le conteneur** – Sélectionnez l’une des options suivantes :

        - *Aucun* – Aucun processus de manifeste ne sera utilisé.
        - *Manuel* – Le manifeste sera requis par le flux de travail d’emballage. Le système n’autorisera pas la fermeture ou la libération d’un conteneur tant que le manifeste n’est pas terminé.
        - *Gestion des transports* – Le manifeste sera effectué via les moteurs de tarification de la gestion du transport (TMS). Étant donné que cette option nécessite un développement personnalisé pour implémenter un moteur spécifique pour le fournisseur de transport, elle ne fonctionnera pas immédiatement dans la version actuelle.

    - **Imprimer le contenu du conteneur** – Réglez cette option sur *Oui* pour imprimer automatiquement le rapport sur le contenu du conteneur lorsqu’un conteneur est enregistré comme fermé. Le rapport peut également être imprimé sur demande.

1. Sur le raccourci **Manifeste du groupe de conteneurs**, dans le champ **Exigences relatives au manifeste pour le groupe de conteneurs**, sélectionnez l’une des options suivantes :

    - *Aucun* – Le manifeste du groupe de conteneurs ne sera pas inclus en tant qu’exigence dans le flux de travail d’emballage.
    - *Manuel* – Le manifeste du groupe de conteneurs sera inclus en tant qu’exigence dans le flux de travail d’emballage. Tous les conteneurs qui sont inclus dans le groupe doivent être clôturés avant que le groupe puisse faire l'objet d'un manifeste. Sélectionnez cette option si vous devez remplir un manifeste pour chaque groupe de conteneurs conditionné à la station de conditionnement. Vous sélectionnerez généralement cette option si les conteneurs sont emballés sur une palette et que toute la palette est affichée.

    > [!NOTE]
    > La version actuelle ne prend pas en charge les rapports de manifeste pour les groupes de conteneurs et il n’y a pas de prise en charge du moteur TMS pour les groupes de conteneurs.

1. Dans le raccourci **Manifeste d'expédition**, définissez les champs suivants :

    - **Exigences de manifeste pour l'expédition** – Sélectionnez l’une des options suivantes :

        - *Aucun* – Le manifeste d'expédition ne sera pas inclus en tant qu’exigence dans le flux de travail d’emballage.
        - *Manuel* – Le manifeste d'expédition sera inclus en tant qu’exigence dans le flux de travail d’emballage. Aucun conteneur d’une expédition ne peut être libéré tant que le manifeste n’est pas terminé.
        - *Gestion des transports* – Le manifeste sera effectué via les moteurs de tarification de TMS. Étant donné que cette option nécessite un développement personnalisé pour implémenter un moteur spécifique pour le fournisseur de transport, elle ne fonctionnera pas immédiatement dans la version actuelle.

        Le manifeste d’expédition doit être activé si vous devez remplir un manifeste pour l’ensemble de l’envoi qui est emballé à la station d’emballage. Il est généralement utilisé lorsqu’un manifeste consolidé est requis même si l’envoi se compose de plusieurs conteneurs ou groupes de conteneurs.

    - **Imprimer le bon de livraison** – Réglez cette option sur *Oui* pour imprimer automatiquement le bon de livraison dans le cadre du manifeste d’expédition. Le bon de livraison peut également être imprimé sur demande.

### <a name="set-up-container-types"></a>Paramétrer les types de conteneur

Au cours du processus d’emballage manuel, les conteneurs doivent être créés avant que les articles puissent y être emballés. Chaque conteneur doit être basé sur un *type de conteneur*, qui définit le volume physique maximal et la capacité pondérale d’un conteneur.

Suivez ces étapes pour créer un type de conteneur.

1. Accédez à **Gestion des entrepôts \> Configuration \> Conteneurs \> Types de conteneurs**.
1. Dans le volet Action, sélectionnez **Nouveau** pour ajouter un type de conteneur.
1. Définissez les champs suivants pour le nouveau type de conteneur :

    - **Code du type de conteneur** – Entrez un ID unique pour le type de conteneur.
    - **Description** - Entrez une description du type de nouveau conteneur.
    - **Tarage poids** – Entrez le poids réel ou estimé du conteneur.
    - **Poids net maximal** – Entrez le poids maximal que le conteneur peut renfermer.

1. Dans la section **Dimensions du conteneur**, dans les champs **Longueur**, **Largeur**, **Hauteur**, et **Volume**, entrez les dimensions physiques du conteneur lui-même.
1. Dans la section **Maximums**, dans les champs **Longueur**, **Largeur**, **Hauteur**, et **Volume**, entrez les dimensions physiques maximales que le conteneur peut recevoir.
1. Vous pouvez définir des attributs supplémentaires pour les types de conteneurs associés à d’autres opérations utilisant des conteneurs. Pour plus d'informations, voir [Conteneurisation](wave-containerization.md).

> [!NOTE]
> Pour le processus d’emballage manuel, le système utilise uniquement la valeur du champ **Poids net maximal** et la valeur du champ **Volume** dans la section **Maximums**.

### <a name="set-up-packing-profiles"></a>Paramétrer les profils de conditionnement

*Profils d’emballage* sont nécessaires pour le processus d’emballage. Ils peuvent être sélectionnés ou définis par défaut lorsque vous démarrez une opération d’emballage sur la page **Emballer**.

Procédez comme suit pour configurer un profil d’emballage.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Emballage \> Profils d’emballage**.
1. Sélectionnez un profil existant du volet de liste ou sélectionnez **Nouveau** dans le volet Action pour en créer un nouveau.
1. Dans l’en-tête du nouveau profil ou du profil sélectionné, définissez les champs suivants :

    - **ID profil d'emballage** – Entrez un ID court pour le profil.
    - **Description** - Entrez une description du profil d'emballage.
    - **Politique d’emballage des conteneurs** – Sélectionnez la politique d’emballage qui s’applique au profil. Pour plus d’informations, voir la section [Paramétrer des poliques d'emballage de conteneurs](#packing-policy) de cet article.
    - **Mode ID conteneur** – Sélectionnez si un ID conteneur doit être généré automatiquement lors de la création d'un conteneur ou s'il doit être créé manuellement.
    - **Type de conteneur** – Sélectionnez le type de conteneur qui est utilisé par défaut lorsqu’un nouveau conteneur est créé.
    - **Créer automatiquement un conteneur à la fermeture du conteneur** – Sélectionnez cette case pour créer automatiquement un nouveau conteneur si le conteneur précédent est fermé et qu’il reste une ou plusieurs lignes dans l’envoi en cours.

### <a name="set-up-warehouse-workers"></a>Paramétrer les magasiniers

Tout utilisateur ou travailleur qui emballe des conteneurs en utilisant la page **Emballer** du client Web ou le code d’activité *Emballage* dans l’application mobile Warehouse Management doit avoir un compte utilisateur associé à un enregistrement de *travailleur/personne* auquel les droits d’accès de sécurité requis sont attribués. (Pour plus d'informations sur la configuration des utilisateurs, voir [Créer de nouveaux utilisateurs](../../fin-ops-core/dev-itpro/sysadmin/tasks/create-new-users.md).)

Suivez ces étapes pour configurer un enregistrement de *travailleur/personne* pour le processus d’emballage.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Employé**.
1. Dans le volet Action, sélectionnez **Nouveau** pour ajouter un travailleur utilisateur.
1. Définissez le champ **Travailleur** à l’enregistrement de travailleur existant qui est défini dans le module **Ressources humaines** pour l’utilisateur qui terminera le processus d’emballage.
1. Dans l’organisateur **Profil**, définissez les champs suivants :

    - **Stratégie d’emballage de conteneur** – Sélectionnez une stratégie d’emballage de conteneur qui définit la manière dont les conteneurs doivent être traités à la station d’emballage. La stratégie d’emballage de conteneur que vous sélectionnez sera présélectionnée pour le collaborateur lorsqu’il ouvrira la station d’emballage. Pour plus d’informations, consultez le billet de blog suivant : [Fonctionnalités d’emballage améliorées](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611).
    - **ID de profil d’emballage** – Sélectionnez un ID de profil d’emballage qui définit la stratégie d’emballage et les paramètres de conteneur qui devraient être utilisés. Si l’ID de profil d’emballage sélectionné est associé à une stratégie d’emballage de conteneur, vous ne pourrez pas modifier le paramètre du champ **Stratégie d’emballage de conteneur** sur cette page.

1. Sur le raccourci **Station d’emballage par défaut**, sélectionnez le site, l’entrepôt et l’emplacement par défaut qui s’appliquent au collaborateur.
1. Si le travailleur utilise l’application mobile Warehouse Management pour gérer et enregistrer son travail d’emballage de conteneurs, sur le raccourci **Utilisateurs**, configurez un ou plusieurs comptes que le travailleur peut utiliser pour se connecter à l’application. Pour plus d’informations, voir [Comptes d’utilisateur d’appareil mobile](mobile-device-work-users.md).

## <a name="example-scenario"></a><a name="scenario"></a>Exemple de scénario

Cette section fournit un exemple de scénario qui montre comment créer une commande et emballer les articles.

### <a name="make-sample-data-available"></a>Rendre les exemple de données disponibles

Pour utiliser ce scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard sont installées. En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.

Vous pouvez également utiliser ce scénario comme orientation pour utiliser la fonctionnalité dans un système de production. Cependant, dans ce cas, vous devez remplacer les valeurs de chaque paramètre décrit ici par les vôtres.

### <a name="sign-in-as-a-user-that-can-do-packing-work"></a>Connectez-vous en tant qu’utilisateur pouvant effectuer des travaux d’emballage

Connectez-vous à Supply Chain Management à l’aide d’un compte d’utilisateur disposant des autorisations requises pour emballer des conteneurs. L’utilisateur *Julia Funderburk* est inclus dans les données de démonstration et dispose des autorisations requises. Cet utilisateur a l’ID utilisateur *Administrateur*.

### <a name="create-a-sales-order-and-complete-the-work"></a>Créer une commande client et terminer le travail

Suivez ces étapes pour créer une commande client et terminer le travail de déplacement des articles commandés vers la station d’emballage.

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande client**, dans le champ **Compte client**, sélectionnez *US-005*.
1. Sélectionnez **OK** pour fermer la boîte de dialogue.
1. La nouvelle commande client est ouverte et comprend une seule ligne vide sur le raccourci **Lignes de commande client**. Définissez les valeurs suivantes pour la nouvelle ligne de commande :

    - **Numéro d’article :** *A0001*
    - **Quantité :** *2*
    - **Site :** *6*
    - **Entrepôt :** *62*

1. Alors que la ligne de commande est toujours sélectionnée, sélectionnez **Inventaire \> Réservation** dans la barre d'outils du raccourci **Lignes de commande de ventes**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la quantité totale de la ligne sélectionnée dans l’entrepôt.
1. Fermez la page **Réservation** pour revenir à la commande client.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

    Un message affiche les identifiants d’expédition et de vague pour la commande.

1. Alors que la ligne de commande est toujours sélectionnée, sélectionnez **Entrepôt** \> **Détails de travail** dans la barre d'outils du raccourci **Lignes de commande de ventes**. Si vous utilisez le traitement par lots pour exécuter vos vagues, vous devrez peut-être attendre un peu de temps pour que le travail soit créé.
1. Sur la page **Travail**, dans le volet Action, sur l'onglet **Travail**, sélectionnez **Terminer le travail**.
1. Sur la page **Achèvement du travail**, définissez le champ **ID utilisateur** sur *62*.
1. Sur le volet Action, sélectionnez **Valider le travail**.
1. Lorsque vous recevez un message indiquant que votre travail est valide, sélectionnez **Travail complet** pour terminer le processus de sélection des articles d’inventaire et de les mettre dans l'emplacement *Emballer*.
1. Prenez note de la valeur **ID d’expédition** indiquée pour le travail dans la grille supérieure.

### <a name="pack-the-ordered-items-into-a-container"></a>Emballez les articles commandés dans un conteneur

Les articles en stock ont maintenant été amenés dans la zone d’emballage et sont prêts à être emballés dans des conteneurs. Suivez ces étapes pour créer un nouveau conteneur dans le système et l'emballer.

1. Accédez à **Gestion d’entrepôt \> Emballage et conteneurisation \> Emballer**.
1. Dans la boîte de dialogue **Sélectionner une station de conditionnement**, définissez les valeurs suivantes :

    - **Site :** *6*
    - **Entrepôt :** *62*
    - **Emplacement :** *Emballer*
    - **ID profil d'emballage:** *WH62*

1. Cliquez sur **OK**.
1. Dans la page **Emballer**, dans le champ **Plaque d'immatriculation ou expédition**, entrez l'ID d'expédition que vous avez noté précédemment. Vous devriez maintenant voir les articles déballés restants sur le raccourci **Lignes ouvertes**.
1. Dans le volet Action, sélectionnez **Nouveau conteneur** pour créer un conteneur dans le système.
1. Dans la boîte de dialogue **ID du nouveau conteneur**, définissez le champ **Type de conteneur** sur *SmallBox*.
1. Sélectionnez sur **OK** pour créer le conteneur.
1. Sélectionnez **OK** pour revenir à la page **Emballer**. Le raccourci **Conteneurs ouverts** affiche maintenant la valeur **Identifiant du conteneur** du conteneur que vous avez créé.
1. Pour ce scénario, vous emballerez un seul des articles commandés pour le moment. Par conséquent, dans le raccourci **Emballage de l’article**, définissez les valeurs suivantes :

    - **Quantité :** *1.00*
    - **Identificateur :** *A0001*

    Immédiatement après avoir sélectionné la valeur **Identifiant**, la page met à jour les raccourcis **Lignes ouvertes** et **Toutes les lignes** pour indiquer qu’un article a été emballé. Vous devriez maintenant avoir emballé l’un des deux articles *A0001*.

1. Dans le volet Actions, sélectionnez **Fermer le conteneur**.
1. Dans la boîte de dialogue **Fermer le conteneur**, sélectionnez **Obtenir le poids système** pour remplir la valeur par défaut **Poids brut**.
1. Sélectionnez **OK** pour fermer le conteneur.

> [!TIP]
> Il existe différentes manières d’afficher les conteneurs en fonction du contexte. Par exemple, lorsque vous emballez une expédition, il est souvent utile d’afficher soit les conteneurs qui font partie de l’expédition, soit tous les conteneurs qui se trouvent physiquement à une station d’emballage. La page **Station d’emballage** contient des boutons que vous pouvez utiliser pour afficher tous les conteneurs ouverts et fermés à une station d’emballage. Ces vues ne sont pas limitées à un envoi spécifique. Ils peuvent être très utiles dans les situations où un travailleur emballe un conteneur et un autre travailleur manifeste et libère le conteneur.
>
> Une vue consolidée de tous les conteneurs est également disponible. Cette vue est utile principalement pour les utilisateurs qui travaillent en dehors du contexte d’une seule station d’emballage. Pour le voir, accédez à **Gestion d’entrepôt \> Emballage et conteneurisation \> Conteneurs**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
