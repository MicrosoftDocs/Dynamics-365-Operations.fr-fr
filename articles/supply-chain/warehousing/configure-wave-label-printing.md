---
title: Impression d’étiquettes de la vague
description: Cette rubrique décrit l’impression d’étiquettes de vague et explique comment la configurer.
author: perlynne
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 6360f36b6a3526cdc5680a4059ae1202896986a5
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301769"
---
# <a name="wave-label-printing"></a>Impression d’étiquettes de la vague

[!include [banner](../includes/banner.md)]

L’impression d’étiquettes de vague constitue une alternative à l’impression d’étiquettes en introduisant une nouvelle méthode par d’étape de vague qui vous permet de créer et d’imprimer des étiquettes directement à partir du modèle de vague pendant l’exécution de celle-ci. Par conséquent, les étiquettes seront déjà disponibles avant que les employés n’exécutent l’ordre de travail sur un appareil mobile. Les employés peuvent alors apposer les étiquettes requises pendant le prélèvement plutôt qu’après.

L’impression d’étiquettes de vague utilise le langage de programmation Zebra (ZPL) pour créer des mises en page d’étiquettes. Une mise en page d’étiquette est divisée en trois sections (en-tête, corps et pied de page) pour permettre de créer des étiquettes à structure répétitive. Les modèles d’étiquettes de vague indiquent au système la mise en page d’étiquette à utiliser. Les utilisateurs peuvent spécifier quelle imprimante utiliser. Ils peuvent également imprimer les étiquettes sur plusieurs imprimantes en même temps, selon leurs besoins. La page **Historique des étiquettes de vague** affiche un enregistrement de toutes les étiquettes qui ont été créées à l’aide de cette configuration.

Vous pouvez imprimer et assembler des étiquettes en fonction de leur en-tête de travail, vous pouvez imprimer des étiquettes de séparation par en-tête de travail et vous pouvez imprimer des étiquettes de contenu de conteneur, des étiquettes de casier et d’autres étiquettes similaires.

> [!NOTE]
> Cette fonctionnalité ne remplace pas la fonctionnalité d’impression d’étiquettes existante basée sur l’acheminement des documents.

L’impression d’étiquettes de vague offre les améliorations suivantes :

- Imprimer des étiquettes en fonction du nombre de cartons sur une seule ligne de travail, sans recourir à la conteneurisation. (Un « carton » est une unité désignée sur les lignes des groupes de séquences d’unités.)
- Imprimer plusieurs séquences d’étiquettes différentes (par exemple, des étiquettes de carton et de palette).
- Inclure une énumération d’étiquettes (par exemple, 1/124, 2/124, ... 124/124) et définir la plage d’énumération (par exemple, ligne de travail, ligne de chargement ou expédition).
- Créer et imprimer un identificateur de feuille de chargement sur les étiquettes avant de générer la feuille de chargement.
- Créer un code série de conteneur d’expédition (SSCC) unique pour chaque carton et l’inclure sur chaque étiquette.
- Créer des séquences de numéros conformes GS1 pour les identificateurs de feuille de chargement et les SSCC.
- Réimprimer des étiquettes à partir d’appareils mobiles et du Rich Client.
- Annuler des étiquettes (par exemple, dans les scénarios de prélèvement partiel) et les réimprimer.
- Nettoyage de l’historique des étiquettes de vague.
- Les améliorations apportées aux mises en page de l’acheminement des documents sont partagées entre les mises en page d’acheminement des documents et les mises en page d’étiquettes de vague. (Pour plus d’informations, voir [Mise en page d’acheminement de document pour les étiquettes de contenant](../warehousing/document-routing-layout-for-license-plates.md) .)

Ces améliorations rendent plus efficace l’étiquetage des cartons avant la palettisation. Elles profitent particulièrement aux entreprises qui livrent à de grands distributeurs qui confirment automatiquement la réception des commandes en scannant chaque carton séparément.

> [!NOTE]
> Vous pouvez implémenter les scénarios de configuration décrits dans cette rubrique séparément ou en combinaison, selon les besoins de votre entreprise. Vous pouvez concevoir plusieurs modèles d’étiquettes de vague qui fonctionnent en séquence (comme illustré dans le scénario 3). Par exemple, vous pouvez utiliser le scénario 1 pour imprimer des étiquettes de carton et le scénario 2 pour imprimer des étiquettes de palette (si les palettes en stock varient en taille et en composition).

## <a name="turn-on-the-wave-label-printing-feature"></a>Activer la fonctionnalité d’impression d’étiquette de vague

Avant de pouvoir utiliser la fonctionnalité *Impression d’étiquettes de vague*, celle-ci doit être activée sur votre système. Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonction :** *Impression d’étiquettes de vague*

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a>Scénario 1 : Impression d’étiquettes de vague où une seule étiquette de vague est générée

Ce scénario montre comment une entreprise peut imprimer des étiquettes d’expédition pour un grand distributeur qui confirme automatiquement la réception des commandes en scannant chaque carton séparément.

Ce scénario montre le flux de bout en bout.

### <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Pour suivre ce scénario, vous devez avoir des données de démonstration installées, et vous devez sélectionner l’entité juridique **USMF**.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>S’assurer que la méthode d’étiquette de vague est disponible

Vous devrez peut-être régénérer les méthodes de traitement de la vague pour rendre la méthode d’impression d’étiquettes de vague disponible.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Méthodes de traitement de la vague**.
1. Confirmez que **waveLabelPrinting** est dans la liste. Si elle n’est pas présente, sélectionnez **Régénérer les méthodes** dans le volet Actions pour l’ajouter.

### <a name="configure-a-wave-template"></a>Configurer un modèle de vague

Les modèles de vague vous permettent de lier des instances spécifiques de méthodes de vague à un modèle d’étiquette de vague correspondant.

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.
1. Sélectionnez le modèle de vague, tel que **Expédition par défaut 62**.
1. Dans l’organiseur **Méthodes**, déplacez la méthode **Impression d’étiquettes de vague** vers la colonne **Méthodes sélectionnées**.
1. Dans la colonne **Méthodes sélectionnées**, sélectionnez la méthode **Impression d’étiquettes de vague** et définissez son champ **Code étape de vague** sur *Imprimer l’étiquette*. Pour plus d’informations sur les codes étape de vague, voir [Codes étape de vague](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Créer une mise en page d’étiquette de vague

La mise en page de l’étiquette contrôle quelles informations sont imprimées sur l’étiquette et comment elles sont présentées. Ici, vous entrez le code ZPL qui est envoyé à l’imprimante.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Mises en page d’étiquette de vague**.
1. Créez un enregistrement possédant les paramètres suivants :

    - **ID de mise en page d’étiquette :** *Carton*
    - **Description :** *Carton (SSCC)*

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Paramètres de ligne d’étiquette de vague**.

    La page **Paramètres de ligne d’étiquette de vague** s’affiche. Ici, vous pouvez configurer la partie dynamique de l’étiquette.

1. Ajoutez une ligne ayant les paramètres suivants :

    - **ID de ligne :** *WaveLabel*
    - **Nom de la table de lignes :** *WHSWaveLabel*
    - **Position de début de la ligne :** *0*

        Ce champ définit la position verticale où la ligne commencera sur l’étiquette.

    - **Hauteur de ligne :** *0*

        Ce champ définit la hauteur de chaque ligne (en points), selon la norme ZPL. La hauteur de ligne est positive pour les étiquettes horizontales et négative pour les étiquettes verticales. Comme il n’y a qu’une seule ligne dans cet exemple, vous pouvez définir la valeur sur *0* (zéro).

    - **Lignes par page :** *1*

        Ce champ définit le nombre de lignes pouvant être imprimées sur chaque étiquette.

        > [!NOTE]
        > Cette configuration entraînera l’impression d’une étiquette ZPL distincte pour chaque enregistrement dans la table des étiquettes de vague.

1. Fermez la page.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :

    - **Table :** *Lignes de travail*
    - **Table dérivée :** *Lignes de travail*
    - **Champ :** *Type de travail*
    - **Critères :** *Prélèvement*

    Cette requête garantit que seules les lignes de travail de type Prélèvement seront imprimées sur l’étiquette, et non les lignes de travail de type Placement.

1. Si vous souhaitez pouvoir imprimer l’ID de la feuille de chargement, dans l’onglet **Jointures**, sélectionnez la table **Lignes de travail** et joignez-y la table **Expéditions**.
1. Fermez la boîte de dialogue de l’éditeur de requêtes.
1. L’organisateur **Mise en page du texte de l’imprimante** comporte trois sections dans lesquelles vous pouvez écrire le code de l’imprimante : **Section d’en-tête**, **Section du corps** et **Section pied de page**. Dans la **Section d’en-tête**, dans le champ **En-tête de l’étiquette**, entrez le code de l’en-tête requis. Par exemple, si vous utilisez des imprimantes Zebra, vous pouvez utiliser le code suivant.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. Dans la **Section de corps**, dans le champ **Corps de l’étiquette**, entrez le code ZPL du corps requis. Voici un exemple :

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. Dans la **Section de pied de page**, dans le champ **Pied de page de l’étiquette**, entrez le code ZPL du pied de page requis. Voici un exemple :

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Cette configuration imprimera un exemplaire de chaque étiquette. Si vous avez besoin de davantage d’exemplaires (par exemple, une copie pour chaque côté de la palette), définissez la valeur **n** pour la section **\^PQn** dans le pied de page au nombre d’exemplaires requis. Par exemple, pour imprimer quatre copies de chaque étiquette, spécifiez **\^PQ4**.

Votre étiquette est maintenant prête à être utilisée.

### <a name="create-a-wave-label-type"></a>Créer un type d’étiquette de vague

Les types d’étiquettes de vague sont utilisés pour lier des modèles d’étiquette de vague à une unité sur les lignes de groupe de séquences d’unités.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Types d’étiquette de vague**.
1. Ajoutez un type d’étiquette de vague avec les paramètres suivants :

    - **Type d’étiquette :** *Carton*
    - **Description :** *Carton*

### <a name="set-up-unit-sequence-groups"></a>Définir des groupes de séquences d’unités

Ensuite, configurez le groupe de séquences d’unités pour le type d’étiquette de vague.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Groupes de séquences d’unités**.
1. Sélectionnez le groupe **Ea Box PL**.
1. Pour la ligne **Boîte**, définissez le champ **Type de niveau de vague** sur *Carton*.

### <a name="create-a-wave-label-template"></a>Créer un modèle d’étiquette de vague

Ensuite, créez le modèle d’étiquette de vague pour le type d’étiquette de vague.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Modèles d’étiquette de vague**.
1. Ajoutez un modèle d’étiquette de vague et définissez les valeurs suivantes dans l’en-tête :

    - **Nom du modèle d’étiquette :** *Étiquettes de carton*
    - **Description :** *Étiquettes de carton*
    - **Code étape de vague :** *PrintLabel*
    - **Entrepôt :** *62*

1. Dans l’organisateur **Général**, définissez le champ **Type d’étiquette de vague** sur *Carton*.
1. Dans l’organisateur **Détails du modèle d’étiquette de vague**, ajoutez une nouvelle ligne avec les paramètres suivants :

    - **ID de mise en page d’étiquette :** *Carton*
    - **Nom de l’imprimante :** sélectionnez une imprimante ZPL appropriée.
    - **Exécuter la requête :** *Oui* (Ce paramètre est facultatif, mais il est recommandé pour des performances optimales.)

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Facultatif : si vous configurez une conception d’étiquette spécifique au client, vous devez créer une requête pour trouver le compte du client. Dans l’organisateur **Détails du modèle d’étiquette de vague**, sélectionnez **Modifier la requête**. Ensuite, dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :

    - **Table :** *Expéditions*
    - **Table dérivée :** *Expéditions*
    - **Champ :** *Numéro de compte*
    - **Critères :** saisissez le numéro de compte client concerné.

    Lorsque vous avez terminé, sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.

1. Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue de l’éditeur de requête pour le modèle d’étiquette entier.
1. Dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Tri**, ajoutez une ligne comportant les paramètres suivants :

    - **Table :** *Lignes de travail*
    - **Table dérivée :** *Lignes de travail*
    - **Champ :** *ID de ligne de chargement de référence (Record-ID)*
    - **Ordre de tri :** *Croissant*

1. Sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.
1. Une boîte de message vous invite à confirmer l’opération de réinitialisation du regroupement. Sélectionnez **Oui** pour continuer.
1. Dans le volet Actions, sélectionnez **Regroupement de modèles d’étiquettes de vagues**.
1. Dans la boîte de dialogue **Groupe de modèles d’étiquettes de vague**, sélectionnez la ligne où le champ **Nom du champ de référence** est défini sur *ID de ligne de chargement de référence*, puis cochez la case **ID de build d’étiquette** pour cette ligne.

    > [!NOTE]
    > Cette configuration créera une séquence d’étiquettes (« Carton 1 sur X ») par ligne de chargement tout au long de la vague, quelle que soit la configuration de regroupement du travail. Cette séquence d’étiquettes peut être imprimée sur la mise en page d’étiquette.

### <a name="configure-number-sequence-extensions"></a>Configurer les extensions de séquence numérique

Les extensions de séquence numérique contrôlent la conformité GS1 de séquences de numéros spécifiques. Cette configuration est facultative pour le scénario actuel. Pour plus d’informations et des instructions de configuration, consultez [Configurer les extensions de séquence numérique](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Créer une commande client et la lancer dans l’entrepôt

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Créez une commande client possédant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Entrepôt :** *62*

1. Ajoutez deux lignes de commande client présentant les paramètres suivants :

    - Ligne de commande client 1 :

        - **Numéro d’article :** *A0001*
        - **Quantité :** *9024*
        - **Unité :** *unité* (9024 unités = 376 boîtes = 47 PL)

    - Ligne de commande client 2 :

        - **Numéro d’article :** *A0002*
        - **Quantité :** *9016*
        - **Unité :** *unité* (9016 unités = 322 boîtes = 46 PL)

    > [!NOTE]
    > Les articles et quantités fournis ici ne sont que des exemples. Ils doivent utiliser le groupe de séquences d’unités que vous avez défini précédemment, les conversions d’unités appropriées entre *unité*, *Boîte* et *PL* doivent être définies, et ils doivent être en stock dans l’entrepôt *62*. Pour plus d’informations, voir [Stratégies d’unité de mesure et de stockage](unit-measure-stocking-policies.md).

1. Sélectionnez la ligne de commande client 1. Dans la section **Ligne de commande client**, dans le menu **Stock**, sélectionnez **Réservations**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot**, puis fermez la page.
1. Répétez les étapes 4 et 5 pour la ligne de commande client 2.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

    Les événements suivants surviennent :

    - Le système traite l’expédition créée à l’aide du modèle qui inclut l’étape d’impression d’étiquettes. La mise en page de l’étiquette sera utilisée pour définir le format de l’étiquette et le résultat sera une étiquette imprimée sur l’imprimante sélectionnée dans le modèle d’étiquette.
    - Les étiquettes de vague sont générées et imprimées. Le nombre des étiquettes sera égal au nombre de cartons (dans cet exemple, 376 étiquettes de boîte pour la ligne 1 et 322 étiquettes de boîte pour la ligne 2).
    - Un nouvel identificateur de feuille de chargement est généré pour les expéditions. Si vous avez configuré les extensions de séquence numérique, les ID d’étiquette de vague seront au format numérique **SSCC-18**. 

Vous pouvez afficher et réimprimer des étiquettes de vague à partir des pages suivantes. Dans le volet Actions de chaque page, sous l’onglet **Expéditions**, dans le groupe **Informations associées**, sélectionnez **Étiquettes de vague**.

- Toutes les expéditions \> Détails de l’expédition
- Tous les chargements \> Détails du chargement
- Toutes les vagues
- Étiquettes de vague
- Historique des étiquettes de la vague

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a>Scénario 2 : impression d’étiquettes de vague pour la conteneurisation (sans enregistrements d’étiquettes de vague)

Ce scénario vous permet d’imprimer des étiquettes de vague lorsque vous utilisez la conteneurisation pour répartir automatiquement les articles en cartons et par conséquent, ne pas avoir besoin d’enregistrement d’étiquette de vague. Dans ce cas, l’ID de conteneur se comporte comme un espace réservé pour le SSCC.

Voici les principales différences entre ce scénario et le scénario 1 :

- **Modèles d’étiquettes de vague :** vous ne sélectionnez pas de type d’étiquette de vague sur le modèle d’étiquette de vague et vous n’avez pas besoin d’un regroupement de build d’étiquette. Sinon, vous configurez le modèle d’étiquette de vague et le liez au modèle de vague de la même manière que celle décrite dans le scénario 1. Vous devez laisser le type d’étiquette de vague vide pour empêcher la génération d’étiquettes de vague.
- **Mises en page d’étiquette de vague :** vous allez configurer les paramètres de ligne de la mise en page de l’étiquette de vague pour les lignes de travail au lieu des enregistrements d’étiquette de vague. Vous devez configurer le paramètre de ligne pour la mise en page de l’étiquette à l’aide de la table **WHSWorkLine** au lieu de la table **WHSWaveLabel**. Le paramètre **Lignes par page** contrôle le nombre de lignes que comporte la section de corps. 

Cette configuration convient également aux scénarios métier où plusieurs articles différents sont emballés dans une boîte étiquetée ou dans une palette, et où ce processus d’emballage peut être défini par une création de travail (par exemple, le travail regroupé par expédition).

Ce scénario montre le flux de bout en bout.

### <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Pour suivre ce scénario, vous devez avoir des données de démonstration installées, et vous devez sélectionner l’entité juridique **USMF**.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>S’assurer que la méthode d’étiquette de vague est disponible

Vous devrez peut-être régénérer les méthodes de traitement de la vague pour rendre la méthode d’impression d’étiquettes de vague disponible.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Méthodes de traitement de la vague**.
1. Confirmez que **waveLabelPrinting** est dans la liste. Si elle n’est pas présente, sélectionnez **Régénérer les méthodes** dans le volet Actions pour l’ajouter.

### <a name="set-up-a-wave-template"></a>Paramétrage d’un modèle de vague

Les modèles de vague vous permettent de lier des instances spécifiques de méthodes de vague à un modèle d’étiquette de vague correspondant.

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.
1. Sélectionnez le modèle de vague, tel que **63 Conteneurisation**.
1. Dans l’organiseur **Méthodes**, déplacez la méthode **Impression d’étiquettes de vague** vers la colonne **Méthodes sélectionnées**.
1. Dans la colonne **Méthodes sélectionnées**, sélectionnez la méthode **Impression d’étiquettes de vague** et définissez son champ **Code étape de vague** sur *Imprimer l’étiquette*. Pour plus d’informations sur les codes étape de vague, voir [Codes étape de vague](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Créer une mise en page d’étiquette de vague

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Mises en page d’étiquette de vague**.
1. Créez un enregistrement possédant les paramètres suivants :

    - **ID de mise en page d’étiquette :** *Carton*
    - **Description :** *Carton (SSCC)*

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Paramètres de ligne d’étiquette de vague**.

    La page **Paramètres de ligne d’étiquette de vague** s’affiche. Ici, vous pouvez configurer la partie dynamique de l’étiquette.

1. Ajoutez une ligne ayant les paramètres suivants :

    - **ID de ligne :** *WorkLine*
    - **Nom de la table de lignes :** *WHSWorkLine*
    - **Position de début de la ligne :** *500*

        Ce champ définit la position verticale où la ligne commencera sur l’étiquette.

    - **Hauteur de ligne :** *-50*

        Ce champ définit la hauteur de chaque ligne. La hauteur de ligne est positive pour les étiquettes horizontales et négative pour les étiquettes verticales.

    - **Lignes par page :** *5*

        Ce champ définit le nombre de lignes pouvant être imprimées sur chaque étiquette.

        > [!NOTE]
        > Cette configuration imprimera plusieurs étiquettes ZPL par travail, chaque page pouvant contenir jusqu’à cinq lignes de travail. Par exemple, si une étiquette est imprimée pour un conteneur comportant 12 lignes, trois étiquettes seront imprimées. Si vous souhaitez imprimer une étiquette distincte pour chaque ligne de prélèvement, définissez cette valeur sur *1*.

1. Fermez la page.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :

    - **Table :** *Lignes de travail*
    - **Table dérivée :** *Lignes de travail*
    - **Champ :** *Type de travail*
    - **Critères :** *Prélèvement*

1. Si vous souhaitez pouvoir imprimer l’ID de la feuille de chargement, dans l’onglet **Jointures**, sélectionnez la table **Lignes de travail** et joignez-y la table **Expéditions**.
1. Fermez la boîte de dialogue de l’éditeur de requêtes.
1. L’organisateur **Mise en page du texte de l’imprimante** comporte trois sections dans lesquelles vous pouvez écrire le code de l’imprimante : **Section d’en-tête**, **Section du corps** et **Section pied de page**. Dans la **Section d’en-tête**, dans le champ **En-tête de l’étiquette**, entrez le code de l’en-tête requis. Par exemple, si vous utilisez des imprimantes Zebra, vous pouvez utiliser le code suivant.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. Dans la **Section de corps**, dans le champ **Corps de l’étiquette**, entrez le code ZPL du corps requis. Voici un exemple :

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. Dans la **Section de pied de page**, dans le champ **Pied de page de l’étiquette**, entrez le code ZPL du pied de page requis. Voici un exemple :

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Cette configuration imprimera un exemplaire de chaque étiquette. Si vous avez besoin de davantage d’exemplaires (par exemple, une copie pour chaque côté de la palette), définissez la valeur **n** pour la section **\^PQn** dans le pied de page au nombre d’exemplaires requis. Par exemple, pour imprimer quatre copies de chaque étiquette, spécifiez **\^PQ4**.

Votre étiquette est maintenant prête à être utilisée.

### <a name="create-a-wave-label-template"></a>Créer un modèle d’étiquette de vague

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Modèles d’étiquette de vague**.
1. Ajoutez un modèle d’étiquette de vague et définissez les valeurs suivantes dans l’en-tête :

    - **Nom du modèle d’étiquette :** *Étiquettes de conteneur*
    - **Description :** *Étiquettes de conteneurs*
    - **Code étape de vague :** *PrintLabel*
    - **Entrepôt :** *63*

1. Dans l’organisateur **Détails du modèle d’étiquette de vague**, ajoutez une ligne avec les paramètres suivants :

    - **ID de mise en page d’étiquette :** *Conteneur*
    - **Nom de l’imprimante :** sélectionnez une imprimante ZPL appropriée.
    - **Exécuter la requête :** *Oui* (Ce paramètre est facultatif, mais il est recommandé pour des performances optimales.)

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Facultatif : si vous configurez une conception d’étiquette spécifique au client, vous devez créer une requête pour trouver le compte du client. Dans l’organisateur **Détails du modèle d’étiquette de vague**, sélectionnez **Modifier la requête**. Ensuite, dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :

    - **Table :** *Expéditions*
    - **Table dérivée :** *Expéditions*
    - **Champ :** *Numéro de compte*
    - **Critères :** saisissez le numéro de compte client concerné.

    Lorsque vous avez terminé, sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.

### <a name="configure-number-sequence-extensions"></a>Configurer les extensions de séquence numérique

Les extensions de séquence numérique contrôlent la conformité GS1 de séquences de numéros spécifiques. Cette configuration est facultative pour le scénario actuel. Pour plus d’informations et des instructions de configuration, consultez [Configurer les extensions de séquence numérique](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Créer une commande client et la lancer dans l’entrepôt

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Créez une commande client possédant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Entrepôt :** *63*

1. Ajoutez cinq lignes de commande client :

    - Ligne de commande client 1 :

        - **Numéro d’article :** *A0001*
        - **Quantité :** *10*

    - Ligne de commande client 2 :

        - **Numéro d’article :** *A0002*
        - **Quantité :** *20*

    - Ligne de commande client 3 :

        - **Numéro d’article :** *L0006*
        - **Quantité :** *20*

    - Ligne de commande client 4 :

        - **Numéro d’article :** *L0100*
        - **Quantité :** *40*

    - Ligne de commande client 5 :

        - **Numéro d’article :** *L0101*
        - **Quantité :** *50*

    > [!NOTE]
    > Les articles et quantités fournis ici ne sont que des exemples. Ils doivent être en stock dans l’entrepôt spécifié.

1. Sélectionnez la ligne de commande client 1. Dans la section **Ligne de commande client**, dans le menu **Stock**, sélectionnez **Réservations**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot**, puis fermez la page.
1. Répétez les étapes 4 et 5 pour chaque ligne supplémentaire de la commande client.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

    Les événements suivants surviennent :

    - Le système traite l’expédition créée à l’aide du modèle qui inclut l’étape d’impression d’étiquettes. La mise en page de l’étiquette sera utilisée pour définir le format de l’étiquette et le résultat final sera une étiquette comportant cinq lignes imprimée sur l’imprimante sélectionnée dans le modèle d’étiquette.
    - Un nouvel identificateur de feuille de chargement est généré pour les expéditions. Si vous avez configuré les extensions de séquence numérique, les ID d’étiquette de vague seront au format numérique **SSCC-18**. 

Vous pouvez réimprimer ces étiquettes de vague en accédant à **Gestion des entrepôts \> Recherches et états \> Historique des étiquettes de vague**.

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a>Scénario 3 : Impression d’étiquettes de vague pour des étiquettes à plusieurs niveaux

Ce scénario montre comment utiliser la fonctionnalité d’impression d’étiquettes de vague lorsque les processus d’entreposage nécessitent plusieurs niveaux d’étiquettes d’expédition. Par exemple, il peut falloir imprimer des étiquettes séparées pour les cartons et les palettes, et imprimer une étiquette de séparation pour une expédition entière. Les étiquettes de séparation sont un type distinct d’étiquette qui peut être utilisé comme séparateur entre les rouleaux et les conteneurs ; il peut s’agir d’étiquettes pour l’ID d’expédition et le code-barres, de sorte de pouvoir trier facilement les étiquettes après leur impression.

La principale différence entre la configuration de ce scénario et la configuration du scénario 1, outre le fait que les étiquettes de séparation sont activées, est que plusieurs types d’étiquettes de vague doivent être associés aux modèles d’étiquettes de vague et aux lignes de groupes de séquences d’unités. Pour réaliser cette configuration, vous configurez les éléments suivants pour ce scénario :

- **Méthodes de traitement de vague :** vous marquez la méthode d’étiquette de vague comme « répétable », l’ajoutez deux fois (ou plus) au modèle de vague et définissez différents codes étape de vague.
- **Modèles d’étiquettes de vague :** vous configurez les modèles d’étiquettes de vague et les liez au modèle de vague. Chaque modèle d’étiquette de vague a son propre type d’étiquette de vague.
- **Mises en page des étiquettes de vague :** vous allez créer plusieurs mises en page d’étiquettes de vague. Il y aura une mise en page d’étiquette distincte pour chaque « niveau » d’étiquette, et il y aura également une mise en page d’étiquette de séparation.

Ce scénario montre le flux de bout en bout.

### <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Pour suivre ce scénario, vous devez avoir des données de démonstration installées, et vous devez sélectionner l’entité juridique **USMF**.

### <a name="set-up-a-wave-process-method"></a>Configurer une méthode de traitement de vague

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Méthodes de traitement de la vague**.
1. Confirmez que **waveLabelPrinting** est dans la liste. Si elle n’est pas présente, sélectionnez **Régénérer les méthodes** dans le volet Actions pour l’ajouter.
1. Pour la méthode **waveLabelPrinting**, cochez la case **Rendre la méthode répétable**.

### <a name="set-up-a-wave-template"></a>Paramétrage d’un modèle de vague

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.
2. Sélectionnez le modèle de vague, tel que **Expédition par défaut 62**.
3. Dans l’organiseur **Méthodes**, déplacez la méthode **Impression d’étiquettes de vague** vers la colonne **Méthodes sélectionnées**.
4. Dans la colonne **Méthodes sélectionnées**, attribuez une valeur **Code étape de vague**, telle que *Carton*, à la méthode **Impression d’étiquettes de vague**. Pour plus d’informations sur les codes étape de vague, voir [Codes étape de vague](wave-step-codes.md).
5. Déplacez la méthode **Impression d’étiquettes de vague** vers la colonne **Méthodes sélectionnées** une deuxième fois.
6. Dans la colonne **Méthodes sélectionnées**, attribuez une autre valeur **Code étape de vague**, telle que *Palette*, à la deuxième méthode **Impression d’étiquettes de vague**. Pour plus d’informations sur les codes étape de vague, voir [Codes étape de vague](wave-step-codes.md).

### <a name="create-three-wave-label-layouts"></a>Créer trois mises en page d’étiquette de vague

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Mises en page d’étiquette de vague**.
1. Créez un enregistrement possédant les paramètres suivants :

    - **ID de mise en page d’étiquette :** *Carton*
    - **Description :** *Carton (SSCC)*

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Paramètres de ligne d’étiquette de vague**.

    La page **Paramètres de ligne d’étiquette de vague** s’affiche. Ici, vous pouvez configurer la partie dynamique de l’étiquette.

1. Ajoutez une ligne ayant les paramètres suivants :

    - **ID de ligne :** *WaveLabel*
    - **Nom de la table de lignes :** *WHSWaveLabel*
    - **Position de début de la ligne :** *0*

        Ce champ définit la position verticale où la ligne commencera sur l’étiquette.

    - **Hauteur de ligne :** *0*

        Ce champ définit la hauteur de chaque ligne (en points), selon la norme ZPL. La hauteur de ligne est positive pour les étiquettes horizontales et négative pour les étiquettes verticales. Comme il n’y a qu’une seule ligne dans cet exemple, vous pouvez définir la valeur sur *0* (zéro).

    - **Lignes par page :** *1*

        Ce champ définit le nombre de lignes pouvant être imprimées sur chaque étiquette.

        > [!NOTE]
        > Cette configuration entraînera l’impression d’une étiquette ZPL distincte pour chaque enregistrement dans la table des étiquettes de vague.

1. Fermez la page.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :

    - **Table :** *Lignes de travail*
    - **Table dérivée :** *Lignes de travail*
    - **Champ :** *Type de travail*
    - **Critères :** *Prélèvement*

    Cette requête garantit que seules les lignes de travail de type Prélèvement seront imprimées sur l’étiquette, et non les lignes de travail de type Placement.

1. Si vous souhaitez pouvoir imprimer l’ID de la feuille de chargement, dans l’onglet **Jointures**, sélectionnez la table **Lignes de travail** et joignez-y la table **Expéditions**. 
1. Fermez la boîte de dialogue de l’éditeur de requêtes.
1. L’organisateur **Mise en page du texte de l’imprimante** comporte trois sections dans lesquelles vous pouvez écrire le code de l’imprimante : **Section d’en-tête**, **Section du corps** et **Section pied de page**. Dans la **Section d’en-tête**, dans le champ **En-tête de l’étiquette**, entrez le code de l’en-tête requis. Par exemple, si vous utilisez des imprimantes Zebra, vous pouvez utiliser le code suivant.


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. Dans la **Section de corps**, dans le champ **Corps de l’étiquette**, entrez le code ZPL du corps requis. Voici un exemple :

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. Dans la **Section de pied de page**, dans le champ **Pied de page de l’étiquette**, entrez le code ZPL du pied de page requis. Voici un exemple :

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Cette configuration imprimera un exemplaire de chaque étiquette. Si vous avez besoin de davantage d’exemplaires (par exemple, une copie pour chaque côté de la palette), définissez la valeur **n** pour la section **\^PQn** dans le pied de page au nombre d’exemplaires requis. Par exemple, pour imprimer quatre copies de chaque étiquette, spécifiez **\^PQ4**.

1. La première étiquette est maintenant prête à être utilisée.
1. Créez un deuxième enregistrement de mise en page possédant les paramètres suivants :

    - **ID de mise en page d’étiquette :** *Palette*
    - **Description :** *Palette*

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Paramètres de ligne d’étiquette de vague**.

    La page **Paramètres de ligne d’étiquette de vague** s’affiche. Ici, vous pouvez configurer la partie dynamique de l’étiquette.

1. Ajoutez une ligne ayant les paramètres suivants :

    - **ID de ligne :** *WaveLabel*
    - **Nom de la table de lignes :** *WHSWaveLabel*
    - **Position de début de la ligne :** *0*

        Ce champ définit la position verticale où la ligne commencera sur l’étiquette.

    - **Hauteur de ligne :** *0*

        Ce champ définit la hauteur de chaque ligne (en points), selon la norme ZPL. La hauteur de ligne est positive pour les étiquettes horizontales et négative pour les étiquettes verticales. Comme il n’y a qu’une seule ligne dans cet exemple, vous pouvez définir la valeur sur *0* (zéro).

    - **Lignes par page :** *1*

        Ce champ définit le nombre de lignes pouvant être imprimées sur chaque étiquette.

        > [!NOTE]
        > Cette configuration entraîne l’impression d’une étiquette ZPL distincte pour chaque enregistrement dans la table des étiquettes de vague.

1. Fermez la page.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :

    - **Table :** *Lignes de travail*
    - **Table dérivée :** *Lignes de travail*
    - **Champ :** *Type de travail*
    - **Critères :** *Prélèvement*

    Cette requête garantit que seules les lignes de travail de type Prélèvement seront imprimées sur l’étiquette, et non les lignes de travail de type Placement.

1. Si vous souhaitez pouvoir imprimer l’ID de la feuille de chargement, dans l’onglet **Jointures**, sélectionnez la table **Lignes de travail** et joignez-y la table **Expéditions**.
1. Fermez la boîte de dialogue de l’éditeur de requêtes.
1. L’organisateur **Mise en page du texte de l’imprimante** comporte trois sections dans lesquelles vous pouvez écrire le code de l’imprimante : **Section d’en-tête**, **Section du corps** et **Section pied de page**. Dans la **Section d’en-tête**, dans le champ **En-tête de l’étiquette**, entrez le code de l’en-tête requis. Par exemple, si vous utilisez des imprimantes Zebra, vous pouvez utiliser le code suivant.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. Dans la **Section de corps**, dans le champ **Corps de l’étiquette**, entrez le code ZPL du corps requis. Voici un exemple :

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. Dans la **Section de pied de page**, dans le champ **Pied de page de l’étiquette**, entrez le code ZPL du pied de page requis. Voici un exemple :

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Cette configuration imprimera un exemplaire de chaque étiquette. Si vous avez besoin de davantage d’exemplaires (par exemple, une copie pour chaque côté de la palette), définissez la valeur **n** pour la section **\^PQn** dans le pied de page au nombre d’exemplaires requis. Par exemple, pour imprimer quatre copies de chaque étiquette, spécifiez **\^PQ4**.

1. La deuxième étiquette est maintenant prête à être utilisée.
1. Créez un troisième enregistrement de mise en page possédant les paramètres suivants :

    - **ID de mise en page d’étiquette :** *Séparation*
    - **Description :** *Étiquette de séparation*

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. L’organisateur **Mise en page du texte de l’imprimante** comporte trois sections dans lesquelles vous pouvez écrire le code de l’imprimante : **Section d’en-tête**, **Section du corps** et **Section pied de page**. Dans la **Section d’en-tête**, dans le champ **En-tête de l’étiquette**, entrez le code ZPL de l’en-tête requis. Voici un exemple :

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. Cette fois, aucun corps n’est requis. Par conséquent, entrez simplement le texte requis dans la section **Pied de page**. Voici un exemple :

    ```plaintext
    ^XZ
    ```

    La troisième étiquette est maintenant prête à être utilisée.

    > [!NOTE]
    > Cette troisième étiquette est une étiquette de séparation qui sera utilisée comme séparateur entre les rouleaux d’étiquettes.

### <a name="create-two-wave-label-types"></a>Créer deux types d’étiquette de vague

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Types d’étiquette de vague**.
1. Créez un enregistrement possédant les paramètres suivants :

    - **Type d’étiquette :** *Carton*
    - **Description :** *Carton*

1. Créez un deuxième enregistrement possédant les paramètres suivants :

    - **Type d’étiquette :** *Palette*
    - **Description :** *Palette*

### <a name="set-up-unit-sequence-groups"></a>Définir des groupes de séquences d’unités

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Groupes de séquences d’unités**.
1. Sélectionnez ou créez un groupe **Ea Box PL**.
1. Pour la ligne **Boîte**, définissez le champ **Type de niveau de vague** sur *Carton*.
1. Pour la ligne **PL**, définissez le champ **Type de niveau de vague** sur *Palette*.

### <a name="create-wave-label-templates"></a>Créer des modèles d’étiquette de vague

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Acheminement de document \> Modèles d’étiquette de vague**.
1. Créez un modèle d’étiquette possédant les paramètres suivants :

    - **Nom du modèle d’étiquette :** *Étiquettes de carton*
    - **Description :** *Étiquettes de carton*
    - **Code étape de vague :** *Carton*
    - **Entrepôt :** *62*

1. Dans l’organisateur **Général**, dans le champ **Type d’étiquette de vague**, sélectionnez une valeur, telle que *Carton*.
1. Dans l’organisateur **Détails du modèle d’étiquette de vague**, ajoutez une ligne avec les paramètres suivants :

    - **ID de mise en page d’étiquette :** *Carton*
    - **Nom de l’imprimante :** sélectionnez une imprimante ZPL appropriée.
    - **Exécuter la requête :** *Oui* (Ce paramètre est facultatif, mais il est recommandé pour des performances optimales.)

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Facultatif : si vous configurez une conception d’étiquette spécifique au client, vous devez créer une requête pour trouver le compte du client. Dans l’organisateur **Détails du modèle d’étiquette de vague**, sélectionnez **Modifier la requête**. Ensuite, dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :

    - **Table :** *Expéditions*
    - **Table dérivée :** *Expéditions*
    - **Champ :** *Numéro de compte*
    - **Critères :** saisissez le numéro de compte client concerné.

    Lorsque vous avez terminé, sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.

1. Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue de l’éditeur de requête pour le modèle d’étiquette entier.
1. Dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Tri**, ajoutez une ligne comportant les paramètres suivants :

    - **Table :** *Lignes de travail*
    - **Table dérivée :** *Lignes de travail*
    - **Champ :** *ID de ligne de chargement de référence (Record-ID)*
    - **Ordre de tri :** *Croissant*

1. Ajoutez une deuxième ligne ayant les paramètres suivants :

    - **Table :** *Lignes de travail*
    - **Table dérivée :** *Lignes de travail*
    - **Champ :** *ID expédition*
    - **Ordre de tri :** *Croissant*

1. Sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.
1. Une boîte de message vous invite à confirmer l’opération de réinitialisation du regroupement. Sélectionnez **Oui** pour continuer.
1. Dans le volet Actions, sélectionnez **Regroupement de modèles d’étiquettes de vagues**.
1. Dans la boîte de dialogue **Groupe de modèles d’étiquettes de vague**, pour la ligne où le **Nom du champ de référence** est défini sur *ID d’expédition*, définissez les valeurs suivantes :

    - **Imprimer étiquette de séparation :** cochez cette case.
    - **ID de mise en page d’étiquette :** sélectionnez une étiquette de séparation. (Par exemple, sélectionnez la mise en page d’étiquette *Séparation* que vous avez créée précédemment dans ce scénario.)
    - **Nom de l’imprimante :** sélectionnez l’imprimante pour l’étiquette de séparation. (En général, pour diviser les rouleaux d’étiquettes, vous devez sélectionner la même imprimante que celle sélectionnée dans l’organisateur **Détails du modèle d’étiquette de vague**. Cependant, d’autres scénarios sont possibles.)

1. Pour la rangée où le champ **Nom du champ de référence** est défini sur *ID de ligne de chargement de référence*, cochez la case **ID de build d’étiquette**.

    > [!NOTE]
    > Cette configuration créera une séquence d’étiquettes (« Carton 1 sur X ») par ligne de chargement tout au long de la vague, quelle que soit la configuration de regroupement du travail. Cette séquence d’étiquettes peut être imprimée sur une mise en page d’étiquettes. De plus, les étiquettes des différents envois seront séparées par l’étiquette de séparation sélectionnée.

1. Sélectionnez **OK** pour fermer la boîte de dialogue **Groupe de modèles d’étiquettes de vague**.
1. Créez un deuxième modèle d’étiquette possédant les paramètres suivants :

    - **Nom du modèle d’étiquette :** *Étiquettes de palette*
    - **Description :** *Étiquettes de palette*
    - **Code étape de vague :** *Palette*
    - **Entrepôt :** *62*

1. Dans l’organisateur **Général**, dans le champ **Type d’étiquette de vague**, sélectionnez une valeur, telle que *Palette*.
1. Dans l’organisateur **Détails du modèle d’étiquette de vague**, ajoutez une ligne avec les paramètres suivants :

    - **ID de mise en page d’étiquette :** *Palette*
    - **Nom de l’imprimante :** sélectionnez une imprimante ZPL appropriée.
    - **Exécuter la requête :** *Oui* (Ce paramètre est facultatif, mais il est recommandé pour des performances optimales.)

1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Facultatif : si vous configurez une conception d’étiquette spécifique au client, vous devez créer une requête pour trouver le compte du client. Dans l’organisateur **Détails du modèle d’étiquette de vague**, sélectionnez **Modifier la requête**. Ensuite, dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Plage**, ajoutez une ligne comportant les paramètres suivants :

    - **Table :** *Expéditions*
    - **Table dérivée :** *Expéditions*
    - **Champ :** *Numéro de compte*
    - **Critères :** saisissez le numéro de compte client concerné.

    Lorsque vous avez terminé, sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes. 

1. Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue de l’éditeur de requête pour le modèle d’étiquette entier.
1. Dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Tri**, ajoutez une ligne comportant les paramètres suivants :

    - **Table :** *Lignes de travail*
    - **Table dérivée :** *Lignes de travail*
    - **Champ :** *ID de ligne de chargement de référence (Record-ID)*
    - **Ordre de tri :** *Croissant*

1. Ajoutez une deuxième ligne ayant les paramètres suivants :

    - **Table :** *Lignes de travail*
    - **Table dérivée :** *Lignes de travail*
    - **Champ :** *ID expédition*
    - **Ordre de tri :** *Croissant*

1. Sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.
1. Une boîte de message vous invite à confirmer l’opération de réinitialisation du regroupement. Sélectionnez **Oui** pour continuer.
1. Dans le volet Actions, sélectionnez **Regroupement de modèles d’étiquettes de vagues**.
1. Dans la boîte de dialogue **Groupe de modèles d’étiquettes de vague**, pour la ligne où le **Nom du champ de référence** est défini sur *ID d’expédition*, définissez les valeurs suivantes :

    - **Imprimer étiquette de séparation :** cochez cette case.
    - **ID de mise en page d’étiquette :** sélectionnez une étiquette de séparation. (Par exemple, sélectionnez la mise en page d’étiquette *Séparation* que vous avez créée précédemment dans ce scénario.)
    - **Nom de l’imprimante :** sélectionnez l’imprimante pour l’étiquette de séparation. (En général, pour diviser les rouleaux d’étiquettes, vous devez sélectionner la même imprimante que celle sélectionnée dans l’organisateur **Détails du modèle d’étiquette de vague**. Cependant, d’autres scénarios sont possibles.)

1. Pour la rangée où le champ **Nom du champ de référence** est défini sur *ID de ligne de chargement de référence*, cochez la case **ID de build d’étiquette**.

    > [!NOTE]
    > Cette configuration créera une séquence d’étiquettes (« Carton 1 sur X ») par ligne de chargement tout au long de la vague, quelle que soit la configuration de regroupement du travail. Cette séquence d’étiquettes peut être imprimée sur une mise en page d’étiquettes. De plus, les étiquettes des différents envois seront séparées par l’étiquette de séparation sélectionnée.

### <a name="configure-number-sequence-extensions"></a>Configurer les extensions de séquence numérique

Les extensions de séquence numérique contrôlent la conformité GS1 de séquences de numéros spécifiques. Cette configuration est facultative pour le scénario actuel. Pour plus d’informations et des instructions de configuration, consultez [Configurer les extensions de séquence numérique](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Créer une commande client et la lancer dans l’entrepôt

1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Créez une commande client possédant les paramètres suivants :

    - **Compte client :** *US-001*
    - **Entrepôt :** *62*

1. Ajoutez deux lignes de commande client :

    - Ligne de commande client 1 :

        - **Numéro d’article :** *A0001*
        - **Quantité :** *9024*
        - **Unité :** *unité* (9024 unités = 376 boîtes = 47 PL)

    - Ligne de commande client 2 :

        - **Numéro d’article :** *A0002*
        - **Quantité :** *9016*
        - **Unité :** *unité* (9016 unités = 322 boîtes = 46 PL)

    > [!NOTE]
    > Les articles et quantités fournis ici ne sont que des exemples. Ils doivent utiliser le groupe de séquences d’unités que vous avez défini précédemment, les conversions d’unités appropriées entre *unité*, *Boîte* et *PL* doivent être définies, et ils doivent être en stock dans l’entrepôt *62*. Pour plus d’informations, voir [Stratégies d’unité de mesure et de stockage](unit-measure-stocking-policies.md).

1. Sélectionnez la ligne de commande client 1. Dans la section **Ligne de commande client**, dans le menu **Stock**, sélectionnez **Réservations**.
1. Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot**, puis fermez la page.
1. Répétez les étapes 4 et 5 pour la ligne de commande client 2.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.

    Les événements suivants surviennent : 

    - Le système traite l’expédition créée à l’aide du modèle qui inclut l’étape d’impression d’étiquettes. La mise en page de l’étiquette sera utilisée pour définir le format de l’étiquette et le résultat sera une étiquette imprimée sur l’imprimante sélectionnée dans le modèle d’étiquette.
    - Les étiquettes de vague sont générées et imprimées. Le nombre d’étiquettes sera égal au nombre de cartons (dans cet exemple, 376 étiquettes de boîte pour la ligne 1, 322 étiquettes de boîte pour la ligne 2, 47 étiquettes PL pour la ligne 1, 47 étiquettes PL pour la ligne 2 et deux étiquettes de séparation portant l’ID d’expédition).
    - Un nouvel identificateur de feuille de chargement est généré pour les expéditions. Si vous avez configuré les extensions de séquence numérique, les ID d’étiquette de vague seront au format numérique **SSCC-18**. 

Vous pouvez afficher et réimprimer des étiquettes de vague à partir des pages suivantes :

- Toutes les expéditions \> Détails de l’expédition
- Tous les chargements \> Détails du chargement
- Toutes les vagues
- Étiquettes de vague
- Historique des étiquettes de la vague

Pour la plupart de ces pages, vous pouvez trouver la fonction appropriée en sélectionnant **Étiquettes de vague** dans le groupe **Informations connexes** de l’onglet **Expéditions** du volet Actions.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Réimpression et annulation des étiquettes de vague](reprint-and-void-wave-labels.md)
- [Programmer l’impression d’étiquettes pendant la vague](configure-task-based-wave-label-printing.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
