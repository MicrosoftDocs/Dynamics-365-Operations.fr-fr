---
title: Concevoir une nouvelle solution de gestion des états électroniques pour imprimer des étiquettes ZPL
description: Cet article explique comment concevoir une solution de gestion des états électroniques (ER) pour imprimer des étiquettes ZPL.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: f861fe63c6d7d00d0a9f84d33c0d1b1b23735b61
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845713"
---
# <a name="design-a-new-er-solution-to-print-zpl-labels"></a>Concevoir une nouvelle solution de gestion des états électroniques pour imprimer des étiquettes ZPL

[!include [banner](../includes/banner.md)]


Cet article explique comment un utilisateur avec le rôle d’administrateur système, de développeur d’états électroniques ou de consultant technique de gestion des états électroniques peut configurer les paramètres de la structure de [gestion des états électroniques (ER)](general-electronic-reporting.md), concevoir les [configurations](general-electronic-reporting.md#Configuration) de gestion des états électroniques requises d’une nouvelle solution de gestion des états électroniques pour accéder aux données du système de gestion des entrepôts et générer des étiquettes d’emplacement d’entrepôt personnalisées au format ZPL II. Ces étapes peuvent être effectuées dans la société **USRT**.

## <a name="business-scenario"></a>Scénario d’entreprise

Vous représentez une entreprise qui a implémenté le système de gestion des entrepôts dans Microsoft Dynamics 365 Finance. Chaque emplacement d’entrepôt doit être étiqueté avec une étiquette autocollante qui comprend un code à barres. Les employés de l’entrepôt utiliseront des lecteurs de codes-barres portables pour scanner les codes-barres.

Tous les emplacements des entrepôts ont été étiquetés dans le cadre des activités de pré-démarrage. Cependant, vous devez également être en mesure d’imprimer des étiquettes d’emplacement d’entrepôt à la demande si les étiquettes existantes sont endommagées ou si les étagères de l’entrepôt sont reconfigurées. En utilisant la fonctionnalité de gestion des états électroniques (ER) récemment publiée, vous pouvez configurer une nouvelle solution ER qui permet à un superviseur d’entrepôt d’imprimer des étiquettes directement sur une imprimante d’étiquettes thermiques.

## <a name="configure-the-er-framework"></a>Configurer la structure de gestion des états électroniques

Procédez comme suit dans [Configurer la structure des états électroniques](er-quick-start2-customize-report.md#ConfigureFramework) pour configurer l’ensemble minimum de paramètres d’état électronique. Vous devez terminer cette configuration avant de commencer à utiliser la structure des états électroniques pour concevoir une nouvelle solution de gestion des états électroniques.

## <a name="design-a-domain-specific-data-model"></a>Concevoir un modèle de données spécifique à un domaine

Créez une configuration de la gestion des états électroniques contenant un composant de [modèle de données](er-overview-components.md#data-model-component) pour le domaine de gestion des entrepôts. Ce modèle de données sera ultérieurement utilisé comme source de données lorsque vous concevez un format ER pour générer des étiquettes d’emplacement d’entrepôt.

### <a name="import-a-data-model-configuration"></a>Importer une configuration de modèle de données

Suivez ces étapes pour importer le modèle de données requis à partir d’un fichier XML fourni par Microsoft. Vous pouvez également créer votre propre modèle de données comme décrit dans la section suivante.

1. Téléchargez le fichier [Warehouse model.version.1.xml](https://download.microsoft.com/download/9/f/1/9f136e9b-bf5f-403a-b089-a2b2ed1da2ba/Warehouse-model.version.1.xml) et enregistrez-le sur votre ordinateur local.
2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
3. Dans l’espace de travail **Génération des états électronique**, sélectionnez **Configurations des états**.
4. Sur la page **Configurations**, dans le volet Action, sélectionnez **Échanger** \> **Charger depuis le fichier XML**.
5. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **Warehouse model.version.1.xml**.
6. Sélectionnez **OK** pour importer la configuration.

![Configuration du modèle de données ER importé sur la page Configurations.](./media/er-design-zpl-labels-imported-model.png)

### <a name="create-a-data-model-configuration"></a>Créer une configuration de modèle de données

Au lieu d’importer le fichier de modèle de données fourni par Microsoft, vous pouvez créer un modèle de données à partir de rien. Pour un exemple qui montre comment effectuer cette tâche, voir [Créer une configuration de modèle de données](er-quick-start1-new-solution.md#DesignDataModel).

### <a name="review-the-data-model"></a>Examiner le modèle de données

Vous pouvez afficher une version modifiable du modèle de données configuré sur la page **Concepteur de modèle de données**.

![Structure du modèle de données ER sur la page Concepteur de modèle de données.](./media/er-design-zpl-labels-model.png)

## <a name="design-a-model-mapping-for-the-configured-data-model"></a>Concevoir une mise en correspondance de modèles pour le modèle de données configuré

En tant qu’utilisateur avec le rôle de développeur d’états électroniques, vous devez créer une configuration de la gestion des états électroniques contenant un composant [mise en correspondance des modèles](er-overview-components.md#model-mapping-component) pour le modèle de données Entrepôt. Ce composant implémente le modèle de données configuré pour Dynamics 365 Finance et est spécifique à cette application. Vous devez configurer le composant de mise en correspondance des modèles pour spécifier les objets d’application qui doivent être utilisés pour remplir le modèle de données configuré avec les données d’application au moment de l’exécution. Pour effectuer cette tâche, vous devez comprendre la mise en œuvre de la structure de données du domaine d’activités de gestion des entrepôts dans Finance.

### <a name="import-a-model-mapping-configuration"></a>Importer une configuration de mise en correspondance de modèles

Suivez ces étapes pour importer la mise en correspondance de modèle requise à partir d’un fichier XML fourni par Microsoft. Vous pouvez également créer votre propre mise en correspondance de modèle comme décrit dans la section suivante.

1. Téléchargez le fichier [Warehouse model mapping.version.1.1.xml](https://download.microsoft.com/download/1/c/c/1cc94d28-3d90-4ffd-a118-77d6c322904f/Warehouse-model-mapping.version.1.1.xml) et enregistrez-le sur votre ordinateur local.
2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
3. Dans l’espace de travail **Génération des états électronique**, sélectionnez **Configurations des états**.
4. Sur la page **Configurations**, dans le volet Action, sélectionnez **Échanger** \> **Charger depuis le fichier XML**.
5. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **Warehouse model mapping.version.1.1.xml**.
6. Sélectionnez **OK** pour importer la configuration.

![Configuration de la mise en correspondance de modèle ER importé sur la page Configurations.](./media/er-design-zpl-labels-imported-mapping.png)

### <a name="create-a-model-mapping-configuration"></a>Créer une configuration de mise en correspondance de modèle

Au lieu d’importer le fichier de mise en correspondance de modèle fourni par Microsoft, vous pouvez créer une mise en correspondance de modèle à partir de rien. Pour un exemple qui montre comment effectuer cette tâche, voir [Créer une configuration de mise en correspondance de modèle](er-quick-start1-new-solution.md#CreateModelMapping).

### <a name="review-the-model-mapping"></a>Examiner la mise en correspondance des modèles

Vous pouvez afficher une version modifiable de la mise en correspondance de modèle configurée sur la page **Concepteur de mise en correspondance de modèle**.

![Structure de mise en correspondance de modèle ER sur la page Concepteur de mise en correspondance de modèle.](./media/er-design-zpl-labels-mapping.png)

## <a name="design-a-format"></a>Concevoir un format

En tant qu’utilisateur avec un rôle de Consultant fonctionnel de gestion des états électroniques, vous devez créer une configuration ER contenant un composant de [format](er-overview-components.md#format-component). Pour configurer ce composant, vous utiliserez le code ZPL II pour spécifier la disposition de votre étiquette d’emplacement d’entrepôt.

### <a name="import-a-format-configuration"></a>Importer une configuration du format

Suivez ces étapes pour importer le format requis à partir d’un fichier XML fourni par Microsoft. Vous pouvez également créer votre propre format comme décrit dans la section suivante.

1. Téléchargez le fichier [Warehouse location labels.version.1.1.xml](https://download.microsoft.com/download/5/7/5/5758b551-69a5-45bd-a2b2-21c3db73a6fc/Warehouse-location-labels.version.1.1.xml) et enregistrez-le sur votre ordinateur local.
2. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
3. Dans l’espace de travail **Génération des états électronique**, sélectionnez **Configurations des états**.
4. Sur la page **Configurations**, dans le volet Action, sélectionnez **Échanger** \> **Charger depuis le fichier XML**.
5. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **Warehouse location labels.version.1.1.xml**.
6. Sélectionnez **OK** pour importer la configuration.

![Configuration du format ER importé sur la page Configurations.](./media/er-design-zpl-labels-imported-format.png)

### <a name="create-a-format-configuration"></a>Créer une configuration de format

Au lieu d’importer le fichier de format fourni par Microsoft, vous pouvez créer un format à partir de rien. Pour un exemple qui montre comment effectuer cette tâche, voir [Créer une configuration de format](er-quick-start1-new-solution.md#FormatCreate).

### <a name="review-the-format"></a>Examiner le format

Vous pouvez afficher une version modifiable du format configuré sur la page **Concepteur de format**.

![Structure du format ER sur la page Concepteur de format.](./media/er-design-zpl-labels-format.png)

La source de données `model.Location.Label` de ce format est configurée pour générer des étiquettes contenant les informations suivantes :

- Le titre de l’entrepôt sous forme de texte
- Le titre de l’entrepôt sous forme de code-barres
- Le titre de l’emplacement
- Chiffres de contrôle

Sur la page **Concepteur de formules** pour la source de données, la formule ER qui est utilisée pour générer des étiquettes inclut une fonction `CONCATENATE` qui combine les informations dans la mise en page souhaitée.

![Formules pour la source de données sur la page Concepteur de format.](./media/er-design-zpl-labels-review-formula.png)

> [!TIP]
> La mise en page de l’étiquette est conçue de sorte que le titre de l’emplacement et les chiffres de contrôle soient alignés au centre de l’étiquette. Cependant, ZPL II ne prend pas en charge l’alignement central pour les codes à barres. Par conséquent, la formule de la source de données `model.Location.Warehouse.Alignment` est utilisée pour aligner le code-barres au centre de l’étiquette. Cette formule calcule le décalage à gauche du code-barres, en fonction du nombre de caractères du titre de l’entrepôt.

## <a name="prepare-your-environment-for-previewing-generated-labels"></a>Préparer votre environnement pour prévisualiser les étiquettes générées

L’exemple suivant utilise une application d’émulation d’imprimante pour les étiquettes ZPL afin d’afficher un aperçu des étiquettes générées à l’écran. Procédez comme suit pour activer cette option.

1. Ajoutez la destination de gestion des états électroniques [Imprimante](er-destination-type-print.md) pour le format de gestion des états électroniques **Étiquette d’emplacement d’entrepôt** et configurez-la pour envoyer les étiquettes générées de Finance à l’[Agent d’acheminement de document (DRA)](install-document-routing-agent.md).
2. Installez et configurez le DRA pour acheminer les étiquettes générées depuis Finance vers une imprimante locale accessible depuis le poste de travail actuel.
3. Ajoutez une imprimante locale pour le poste de travail actuel et configurez-la pour transmettre les étiquettes générées du DRA à une application d’émulation d’imprimante.
4. Installez une application d’émulateur d’imprimante en tant qu’extension du navigateur Web Chrome et configurez-la pour transmettre les étiquettes générées d’une imprimante locale à un service Web qui restituera les étiquettes générées et les renverra à l’émulateur d’imprimante pour un aperçu.

<table>
<tbody>
<tr align="center">
<td>
<p>Finance</p>
<p>Rapport de gestion des états électroniques</p>
<p>Destination d’imprimante</p>
</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from Finance to the DRA."></td>
<td>Agent d’acheminement de document</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from the DRA to a local printer."></td>
<td>Imprimante locale</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from a local printer to a printer emulator."></td>
<td>Émulateur d’imprimante</td>
<td><img src="./media/er-design-zpl-labels-flow2.png" alt="Data flow direction: from a printer emulator to a rendering web service and then back to the printer emulator."></td>
<td>Rendu du service Web</td>
</td>
</tr>
</tbody>
</table>

### <a name="install-and-configure-a-printer-emulator-application"></a>Installer et configurer une application d’émulation d’imprimante

Ajoutez une application d’émulation d’imprimante pour le moteur de rendu ZPL à votre navigateur Web Chrome. Cet exemple utilise l’émulateur d’[imprimante ZPL](https://chrome.google.com/webstore/detail/zpl-printer/phoidlklenidapnijkabnfdgmadlcmjo) basé sur le [service Web ZPL](http://labelary.com/service.html). L’application d’émulation d’imprimante transmettra les étiquettes générées au format ZPL d’une imprimante locale au service Web, puis renverra les étiquettes sous forme de fichiers PDF ou PNG pour prévisualisation.

1. Dans la boutique en ligne Chrome, recherchez et sélectionnez l’application d’émulateur d’imprimante que vous souhaitez utiliser. Sélectionnez ensuite **Ajouter à Chrome** pour l’ajouter à votre navigateur Web Chrome.

    ![Ajout de l’application d’émulation d’imprimante au navigateur Web Chrome à partir de la boutique en ligne Chrome.](./media/er-design-zpl-labels-add-app.png)

2. Sélectionnez **Lancer l’application** pour exécuter l’application d’émulation d’imprimante à partir du navigateur Web Chrome.

    ![Exécution de l’application d’émulation d’imprimante à partir du navigateur Web Chrome.](./media/er-design-zpl-labels-run-app.png)

3. Configurer l’application d’exécution :

    1. Désactivez l’application.
    2. Dans les paramètres de l’imprimante, définissez l’hôte sur **127.0.0.1**.
    3. Définissez le port sur **9100**.

        ![Configuration de l’application d’émulation d’imprimante.](./media/er-design-zpl-labels-configure-app.png)

    4. Réactivez l’application. Vous devriez recevoir un message indiquant que l’imprimante a été démarrée sur l’hôte et le port spécifiés.

        ![L’application d’émulation d’imprimante s’est réactivée.](./media/er-design-zpl-labels-turn-on-app.png)

> [!NOTE]
> Étant donné que l’application d’émulation d’imprimante utilisée dans cet exemple s’appuie sur un service Web pour restituer les étiquettes, assurez-vous que vos paramètres de sécurité vous permettent de communiquer avec le service. Sinon, l’application ne recevra pas les étiquettes rendues et aucun aperçu de ces étiquettes ne sera disponible.

### <a name="add-and-configure-a-local-printer"></a>Ajouter et configurer une imprimante locale

[Ajoutez une nouvelle imprimante locale](https://support.microsoft.com/windows/install-a-printer-in-windows-10-cc0724cf-793e-3542-d1ff-727e4978638b) que l’appareil actuel peut utiliser pour transmettre les étiquettes générées du DRA à une application d’émulation d’imprimante.

1. Sous Windows, sélectionnez **Démarrer** \> **Paramètres** \> **Appareils** \> **Imprimantes \& scanners**.
2. Sélectionnez **Paramètres des imprimantes \& scanners**.
3. Pour **Ajouter une imprimante ou un scanner**, sélectionnez **Ajouter un appareil**.
4. Pour **L’imprimante que je veux n’est pas répertoriée**, sélectionnez **Ajouter manuellement**.
5. Dans le chemin **Trouver une imprimante par d’autres options**, sélectionnez **Ajouter une imprimante locale ou une imprimante réseau avec des paramètres manuels**.
6. Dans le champ **Choisir un port d’imprimante**, sélectionnez **Créer un port**, puis procédez comme suit :

    1. Dans le champ **Type de port**, sélectionnez **Port TCP/IP standard**.
    2. Dans le champ **Nom d’hôte ou adresse IP**, entrez **127.0.0.1**.
    3. Dans le champ **Nom de port**, entrez **ZPL**.
    4. Attendez que l’opération **Détection du port TCP/IP** est terminée.
    5. Dans le champ **Type d’appareil**, sélectionnez **Personnaliser**, puis sélectionnez **Paramètres**.
    6. Assurez-vous que les paramètres de port suivants sont spécifiés :

        - **Nom du port :** ZPL
        - **Nom ou adresse IP de l’imprimante :** 127.0.0.1
        - **Protocole :** Brut
        - **Numéro de port :** 9100

7. Dans le champ **Installer le pilote d’imprimante**, sélectionnez **Générique/Texte uniquement**.
8. Dans le champ **Nom de l’imprimante**, entrez **ZebraPrinter**.

![Ajout d’une imprimante locale pour l’appareil actuel.](./media/er-design-zpl-labels-configure-printer.png)

### <a name="install-and-configure-the-dra"></a>Installer et configurer DRA

Préparez le DRA pour transmettre les étiquettes générées de Finance à l’imprimante locale configurée.

1. [Installer l’application DRA](install-document-routing-agent.md#install-the-document-routing-agent)
2. [Configuration du DRA](install-document-routing-agent.md#configure-the-document-routing-agent).
3. [Enregistrez l’imprimante locale](install-document-routing-agent.md#register-network-printers) dans le DRA.
4. [Activez l’imprimante locale](install-document-routing-agent.md#administer-network-printers) dans votre environnement Finance.

![Préparation du DRA pour imprimer les étiquettes générées.](./media/er-design-zpl-labels-configure-dra.png)

### <a name="configure-the-er-destination"></a>Configurer la destination ER

Préparez la destination ER pour transmettre les étiquettes générées de Finance au DRA.

1. Allez dans **Administration d’organisation** \> **Génération d’états électroniques** \> **Destination des états électroniques**.
2. Sur la page **Destination d’états électroniques**, dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Référence**, sélectionnez **Étiquettes d’emplacement d’entrepôt**.
4. Dans le raccourci **Destination du fichier**, sélectionnez **Nouveau**.
5. Dans le champ **Nom**, entrez **Étiquettes**.
6. Dans le champ **Nom du composant de fichier**, entrez ou sélectionnez **Rapport**.
7. Sélectionnez **Paramètres**.
8. Dans la boîte de dialogue **Paramètres de destination** qui apparaît, sur l’onglet **Imprimante**, définissez l’option **Activée** sur **Oui**.
9. Dans le champ **Nom de l’imprimante**, sélectionnez **ZebraPrinter**.
10. Dans le champ **Type d’acheminement de document**, sélectionnez **ZPL**.
11. Cliquez sur **OK**.

![Configuration de la destination ER pour le format d’étiquettes d’emplacement d’entrepôt sur la page de destination des états électroniques.](./media/er-design-zpl-labels-configure-destination.png)

## <a name="review-warehouse-locations"></a>Passer en revue les emplacements des entrepôts

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Entrepôt** \> **Emplacements**.
2. Sur la page **Emplacements** page, filtrez pour afficher uniquement les emplacements qui ont une valeur dans le champ **Chiffres de contrôle**.

![Examen des emplacements d’entrepôt sur la page Emplacements.](./media/er-design-zpl-labels-review-locations.png)

## <a name="print-warehouse-location-labels"></a>Imprimer des étiquettes d’emplacement d’entrepôt

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle d’entrepôt** et sélectionnez **Étiquettes d’emplacement d’entrepôt**.
3. Dans le volet Actions, sélectionnez **Exécuter**.
4. Dans la boîte de dialogue **Paramètres du rapport de gestion des états électroniques**, sur l’onglet **Enregistrements à inclure**, sélectionnez **Filtre**.
5. Sur l’onglet **Plage**, recherchez la ligne où le champ **Table** est défini sur **Emplacements** et le champ **Champ** est défini sur **Emplacement**. Dans le champ **Critère**, entrez **LPEnabled**.
6. Cliquez sur **OK**.
7. Cliquez sur **OK**. Une étiquette est générée et affichée sur la page d’aperçu dans l’application de l’émulateur d’imprimante.

![Révision d’une étiquette générée sur la page d’aperçu de l’application de l’émulateur d’imprimante Zpl.](./media/er-design-zpl-labels-preview-label.png)

## <a name="modify-the-layout-of-a-label"></a>Modifier la mise en page d’une étiquette

Vous pouvez modifier la disposition actuelle de vos étiquettes d’emplacement d’entrepôt. L’exemple suivant montre comment modifier la mise en page afin que les étiquettes générées incluent un ID de profil d’emplacement.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Paramétrez l’option **Utiliser des destinations pour le statut de brouillon** [paramètr d’utilisateur ER](electronic-reporting-destinations.md#applicability) sur **Oui**.
3. Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle d’entrepôt** et sélectionnez **Étiquettes d’emplacement d’entrepôt**.
4. Sélectionnez **Concepteur**.
5. Sur la page **Concepteur de format**, sous l’onglet **Mise en correspondance**, sélectionnez la source de données de `model.Location.Label`.
6. Dans la boîte de dialogue **Propriétés de la source de données**, sélectionnez **Modifier** \> **Modifier la formule**.
7. Sur la page **Concepteur de formule**, dans le champ **Formule**, passez en revue la formule ER qui est utilisée pour générer des étiquettes.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^XZ")
    ```

8. Mettez à jour la formule pour ajouter un ID de profil d’emplacement aux étiquettes générées.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^CF0,40,40^FO0,240^FB800,1,0,C,0^FD",@.ProfileID,"\&^FS",CrLf,
    "^XZ")
    ```

9. Cliquez sur **Enregistrer**.
10. Cliquez sur **OK**.
11. Dans le volet Actions, sélectionnez **Exécuter**.
12. Dans la boîte de dialogue **Paramètres du rapport de gestion des états électroniques**, sur l’onglet **Enregistrements à inclure**, sélectionnez **Filtre**.
13. Sur l’onglet **Plage**, recherchez la ligne où le champ **Table** est défini sur **Emplacements** et le champ **Champ** est défini sur **Emplacement**. Dans le champ **Critères**, entrez **Bay**.
14. Cliquez sur **OK**.
15. Cliquez sur **OK**. Une étiquette est générée et affichée sur la page d’aperçu dans l’application de l’émulateur d’imprimante.

![Examen d’une étiquette générée qui inclut un ID de profil d’emplacement sur la page d’aperçu de l’application de l’émulateur d’imprimante Zpl.](./media/er-design-zpl-labels-preview-label2.png)

## <a name="encoding"></a>Codage

> [!NOTE]
> Vous devez synchroniser le paramètre d’encodage du composant **Common\\File** du format ER modifiable et le réglage approprié de l’étiquette conçue. La valeur du champ **[Encodage](er-suppress-bom-characters.md)** du composant **Common\\File** ne doit pas contredire une commande ZPL utilisée pour contrôler l’encodage de l’étiquette (par exemple, la commande `^CI`). ER ne valide pas que ces paramètres sont synchronisés.

## <a name="additional-resources"></a>Ressources supplémentaires

[Destination d’imprimante](er-destination-type-print.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
