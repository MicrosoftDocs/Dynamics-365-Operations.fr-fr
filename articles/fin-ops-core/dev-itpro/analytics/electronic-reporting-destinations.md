---
title: Destinations pour la gestion des états électroniques
description: Cet article fournit des informations sur la gestion des destinations pour la gestion des états électroniques, les types de destinations prises en charge et les considérations de sécurité.
author: kfend
ms.date: 08/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.form: DocuType, ERSolutionTable
ms.openlocfilehash: b1bf6289e80769dfe8858f307cbb9b217b42dbb4
ms.sourcegitcommit: f2edc193003564c5bee1747f9c2b800feee342bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/29/2022
ms.locfileid: "9360977"
---
# <a name="electronic-reporting-er-destinations"></a>Destinations pour la gestion des états électroniques

[!include [banner](../includes/banner.md)]

Vous pouvez configurer une destination pour chaque configuration de génération d’états électroniques (ER) et son composant de sortie (un dossier ou un fichier). Les utilisateurs qui disposent des droits d’accès appropriés peuvent également modifier les paramètres de destination au moment de l’exécution. Cet article explique la gestion des destinations des états électroniques, les types de destinations pris en charge et des considérations sur la sécurité.

Les configurations de format des ER contiennent généralement au moins un composant de sortie : un fichier. En règle générale, les configurations contiennent plusieurs composants de sortie de fichiers de différents types (par exemple, XML, TXT, XLSX, DOCX ou PDF) qui sont regroupés dans un dossier unique ou dans plusieurs dossiers. La gestion des destinations des états électroniques vous permet de préconfigurer ce qui se produit lors de l’exécution de chaque composant. Par défaut, lorsqu’une configuration est exécutée, une boîte de dialogue s’affiche pour vous permettre d’enregistrer ou d’ouvrir le fichier. Le même comportement se produit également lorsque vous importez une configuration ER et que vous ne lui configurez pas de destinations spécifiques. Après la création d’une destination pour un composant de sortie principal, cette destination remplace le comportement par défaut et le dossier ou le fichier est envoyé en fonction des paramètres de la destination.

## <a name="availability-and-general-prerequisites"></a>Disponibilité et conditions préalables générales

La fonctionnalité des destinations d’ER n’est pas disponible dans Microsoft Dynamics AX 7.0 (février 2016). Par conséquent, vous devez installer Microsoft Dynamics 365 for Operations version 1611 (novembre 2016) ou ultérieure pour utiliser les types de destination suivants :

- [Courrier électronique](er-destination-type-email.md)
- [Archiver](er-destination-type-archive.md)
- [Fichier](er-destination-type-file.md)
- [Ecran](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)

Vous pouvez également installer l’un des éléments requis suivants. Toutefois, notez que ces solutions de remplacement offrent une expérience de destination ER plus limitée.

- Application Microsoft Dynamics AX version 7.0.1 (mai 2016)
- [Correctif de l’application de gestion des destinations de rapports électroniques](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

Il y a aussi un type de destination [Impression](er-destination-type-print.md). Pour l’utiliser, vous devez installer Microsoft Dynamics 365 Finance version 10.0.9 (avril 2020).

## <a name="overview"></a>Présentation

Vous pouvez paramétrer des destinations uniquement pour les configurations d’ER qui ont été [importées](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) dans l’instance Finance actuelle, et pour les formats qui sont disponibles sur la page **Configurations de la gestion des états électroniques**. La fonctionnalité pour la gestion de destination des ER est disponible ici : **Administration d’organisation** \> **Gestion des états électroniques** \> **Destination de la gestion des états électroniques**.

### <a name="default-behavior"></a>Comportement par défaut

Le comportement par défaut d’une configuration au format ER dépend du type d’exécution que vous spécifiez au démarrage d’un format ER.

Dans la boîte de dialogue **État de déclaration d’échanges de biens**, dans le raccourci **Exécuter en arrière-plan**, si vous définissez l’option **Traitement par lots** sur **Non**, un format ER est exécuté immédiatement en mode interactif. Une fois cette exécution terminée, un document sortant généré est mis à disposition pour téléchargement.

Si vous définissez l’option **Traitement par lots** sur **Oui**, un format ER est exécuté en mode [Traitement par lots](../sysadmin/batch-processing-overview.md). Le traitement par lots approprié est créé, en fonction des paramètres que vous spécifiez dans l’onglet **Exécuter à l’arrière-plan** de la boîte de dialogue **Paramètres ER**.

> [!NOTE]
> La description de travail vous informe de l’exécution d’une mise en correspondance des formats de gestion des états électroniques. Il contient également le nom du composant de gestion des états électroniques exécuté.

[![Exécution d’un format ER.](./media/ER_Destinations-RunInBatchMode.png)](./media/ER_Destinations-RunInBatchMode.png)

Vous pouvez trouver des informations sur cette tâche à plusieurs endroits :

- Accédez à **Commun** \> **Demandes** \> **Traitements par lots** \> **Mes traitements par lots** pour vérifier l’état de la tâche planifiée.
- Accédez à **Administration de l’organisation** \> **Rapports électroniques** \> **Tâches d’états électroniques** pour vérifier l’état du travail planifié et les résultats d’exécution du travail terminé. Une fois l’exécution de la tâche terminée, sélectionnez **Afficher les fichiers** dans la page **Tâches d’états électroniques** pour obtenir un document sortant généré.

    > [!NOTE]
    > Ce document est stocké en tant que pièce jointe de l’enregistrement de tâche actuel et est contrôlé par la structure [Gestion des documents](../../fin-ops/organization-administration/configure-document-management.md). Le [Type de document](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) qui est utilisé pour stocker les artefacts ER de ce type est configuré dans les [Paramètres ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

- Dans la page **Tâches d’états électroniques**, sélectionnez **Afficher les fichiers** pour afficher la liste des erreurs et avertissements générés lors de l’exécution des tâches.

    [![Révision de la liste des tâches ER.](./media/ER_Destinations-ReviewERJobs.png)](./media/ER_Destinations-ReviewERJobs.png)

### <a name="user-configured-behavior"></a>Comportement configuré par l’utilisateur

Sur la page **Destination de la gestion des états électroniques**, vous pouvez remplacer le comportement par défaut d’une configuration. Les configurations importées ne sont pas affichées sur cette page jusqu’à ce que vous sélectionniez **Nouveau** puis, dans le champ **Référence**, une configuration pour créer des paramètres de destination.

[![Sélection d’une configuration dans le champ Référence.](./media/ER_Destinations-SelectFormat.png)](./media/ER_Destinations-SelectFormat.png)

Après avoir créé une référence, vous pouvez créer une destination de fichier pour chaque composant de sortie de **Dossier** ou de **Fichier** du format ER référencé.

[![Création d’une destination de fichier.](./media/ER_Destinations-ConfigureElementDestination.png)](./media/ER_Destinations-ConfigureElementDestination.png)

Ensuite, dans la boîte de dialogue **Paramètres de destination**, vous pouvez activer et désactiver des destinations individuelles pour la destination de fichier. Le bouton **Paramètres** est utilisé pour contrôler l’ensemble des destinations pour une destination de fichier sélectionnée. Dans la boîte de dialogue **Paramètres de destination**, vous pouvez contrôler séparément chaque destination en définissant l’option **Activé** pour celle-ci.

Dans certaines versions de Finance **avant la version 10.0.9**, vous pouvez créer **une destination de fichier** pour chaque composant de sortie du même format, tel qu’un dossier ou un fichier sélectionné dans le champ **Nom du fichier**. Cependant, dans les **versions 10.0.9 et ultérieures**, vous pouvez créer **plusieurs destinations de fichiers** pour chaque composant de sortie du même format.

Par exemple, vous pouvez utiliser cette fonctionnalité pour configurer des destinations de fichier pour un composant de fichier utilisé pour générer un document sortant au format Excel. Une destination ([Archiver](er-destination-type-archive.md)) peut être configurée pour stocker le fichier Excel d’origine dans l’archive des tâches ER et une autre destination ([Email](er-destination-type-email.md)) peut être configurée pour [convertir](#OutputConversionToPDF) le fichier Excel au format PDF et envoyer le fichier PDF par e-mail.

[![Configuration de plusieurs destinations pour un seul élément de format.](./media/ER_Destinations-SampleDestinations.png)](./media/ER_Destinations-SampleDestinations.png)

Lorsque vous exécutez un format de gestion des états électroniques, toutes les destinations qui ont été configurées pour les composants du format sont toujours exécutées. De plus, dans Finance **version 10.0.17 et ultérieure**, la fonctionnalité des destinations de gestion des états électroniques a été améliorée et vous permet désormais de configurer différents ensembles de destinations pour un seul format de gestion des états électroniques. Cette configuration marque chaque ensemble comme configuré pour une action utilisateur particulière. L’API de gestion des états électroniques a été [étendue](er-apis-app10-0-17.md) afin qu’une action puisse être exécutée par l’utilisateur en exécutant un format de gestion des états électroniques. Le code d’action fourni est transmis aux destinations pour la gestion des états électroniques. Vous pouvez exécuter différentes destinations d’un format de gestion des états électroniques, en fonction du code d’action fourni. Pour plus d’informations, consultez [Configurer les destinations de gestion des états électroniques dépendant de l’action](er-action-dependent-destinations.md).

## <a name="destination-types"></a>Types de destinations

Les destinations suivantes sont actuellement prises en charge pour les formats ER. Vous pouvez désactiver ou activer tous les types en même temps. De cette façon, vous pouvez soit ne rien faire soit envoyer le composant à toutes les destinations configurées.

- [Courrier électronique](er-destination-type-email.md)
- [Archiver](er-destination-type-archive.md)
- [Fichier](er-destination-type-file.md)
- [Ecran](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)
- [Imprimer](er-destination-type-print.md)

## <a name="applicability"></a>Conditions d’application

Vous pouvez paramétrer des destinations uniquement pour les configurations d’états électroniques qui ont été importées et pour les formats qui sont disponibles sur la page **Configurations des états électroniques**.

> [!NOTE]
> Les destinations configurées sont spécifiques à l’entreprise. Si vous prévoyez d’utiliser un format ER dans différentes sociétés de l’instance Finance actuelle, vous devez configurer des destinations pour ce format ER pour chacune de ces sociétés.

Lorsque vous configurez des destinations de fichiers pour un format sélectionné, vous les configurez pour l’ensemble du format.

[![Lien Configuration.](./media/ER_Destinations-ConfigurationLink.png)](./media/ER_Destinations-ConfigurationLink.png)

En même temps, vous pouvez avoir plusieurs versions du format importé dans l’instance Finance actuelle. Vous pouvez les afficher si vous sélectionnez le lien **Configuration** proposé lorsque vous sélectionnez le champ **Référence**.

[![Versions de configuration.](./media/ER_Destinations-ConfigurationVersions.png)](./media/ER_Destinations-ConfigurationVersions.png)

Par défaut, les destinations configurées sont appliquées uniquement lorsque vous exécutez une version au format ER dont l’état est soit **Terminé**, soit **Partagé**. Cependant, vous devez parfois utiliser des destinations configurées lorsque la version préliminaire d’un format ER est exécutée. Par exemple, vous modifiez une version provisoire de votre format et vous souhaitez utiliser des destinations configurées pour tester la manière dont la sortie générée sera livrée. Suivez ces étapes pour appliquer des destinations pour un format ER lorsque la version préliminaire est exécutée.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Paramétrez l’option **Utiliser des destinations pour le statut de brouillon** sur **Oui**.

[![Option Utiliser des destinations pour le statut de brouillon.](./media/ER_Destinations-UserSetting1.png)](./media/ER_Destinations-UserSetting1.png)

Pour utiliser la version de brouillon d’un format ER, vous devez marquer le format ER en conséquence.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Définissez l’option **Exécuter la configuration** sur **Oui**.

[![Option Exécuter la configuration.](./media/ER_Destinations-UserSetting2.png)](./media/ER_Destinations-UserSetting2.png)

Une fois cette configuration terminée, l’option **Exécuter le brouillon** devient disponible pour les formats ER que vous modifiez. Définissez cette option sur **Oui** pour commencer à utiliser la version de brouillon du format lorsque le format est exécuté.

[![Option Exécuter le brouillon.](./media/ER_Destinations-FormatSetting.png)](./media/ER_Destinations-FormatSetting.png)

## <a name="destination-failure-handling"></a><a name="DestinationFailure"></a>Gestion des échecs de destination

Habituellement, un format ER est exécuté dans le cadre d’un processus métier spécifique. Cependant, la livraison d’un document sortant généré lors de l’exécution d’un format ER doit parfois être considérée comme faisant partie de ce processus métier. Dans ce cas, si la livraison d’un document sortant généré vers une destination configurée échoue, l’exécution du processus métier doit être annulée. Pour configurer la destination ER appropriée, sélectionnez l’option **Arrêter le traitement en cas d’échec**.

Par exemple, vous configurez le traitement des paiements fournisseur afin que le format ER **Transfert de crédit ISO20022** soit exécuté pour générer le fichier de paiement et les documents supplémentaires (par exemple, la lettre explicative et l’état de contrôle). Si un paiement doit être considéré comme ayant été traité avec succès uniquement si la lettre explicative est envoyée avec succès par e-mail, vous devez cocher la case **Arrêter le traitement en cas d’échec** pour le composant **CoveringLetter** dans la destination de fichier appropriée, comme indiqué dans l’illustration suivante. Dans ce cas, le statut du paiement sélectionné pour le traitement passe de **Aucun** à **Expédié** uniquement lorsque la lettre explicative générée est acceptée pour livraison par un fournisseur de messagerie configuré dans l’instance Finance.

[![Configuration de la gestion des processus pour l’échec de destination du fichier.](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)

Si vous décochez la case **Arrêter le traitement en cas d’échec** pour le composant **CoveringLetter** dans la destination, un paiement sera considéré comme ayant été traité avec succès même si la lettre explicative n’est pas livrée avec succès par e-mail,. Le statut du paiement sera modifié de **Aucun** à **Expédié** même si la lettre explicative ne peut pas être envoyée car, par exemple, l’adresse e-mail du destinataire ou de l’expéditeur est manquante ou incorrecte.

## <a name="output-conversion-to-pdf"></a><a name="OutputConversionToPDF"></a>Conversion de sortie en PDF

Vous pouvez utiliser l’option de conversion PDF pour convertir la sortie au format Microsoft Office (Excel ou Word) au format PDF.

### <a name="make-pdf-conversion-available"></a>Rendre la conversion PDF disponible

Pour rendre l’option de conversion PDF disponible dans l’instance Finance actuelle, ouvrez l’espace de travail **Gestion des fonctionnalités** et activez la fonctionnalité **Convertir les documents sortants de rapports électroniques à partir de formats Microsoft Office au format PDF**.

[![Activation de la fonctionnalité de conversion PDF des documents sortants dans Gestion des fonctionnalités.](./media/ER_Destinations-EnablePdfConversionFeature.png)](./media/ER_Destinations-EnablePdfConversionFeature.png)

### <a name="applicability"></a>Conditions d’application

Dans les versions de Finance **antérieures à la version 10.0.18**, l’option de conversion PDF ne peut être activée que pour les composants **Excel\\File** utilisés pour générer une sortie au format Office (Excel ou Word). Lorsque cette option est activée, la sortie générée au format Office est automatiquement convertie au format PDF. Cependant, dans **la version 10.0.18 et les versions ultérieures**, vous pouvez également activer cette option pour les composants du type **Common\\File**.

> [!NOTE]
> Soyez attentif au message d’avertissement que vous recevez lorsque vous activez l’option de conversion PDF pour un composant ER du type **Common\\File**. Ce message vous informe qu’il n’y a aucun moyen de garantir, au moment de la conception, que le composant de fichier sélectionné exposera le contenu au format PDF ou le contenu convertible en PDF au moment de l’exécution. Par conséquent, vous ne devez activer l’option que si vous êtes sûr que le composant de fichier sélectionné a été configuré pour exposer le contenu au format PDF ou le contenu convertible en PDF au moment de l’exécution.
> 
> Si vous activez l’option de conversion PDF pour un composant de format, si ce composant expose le contenu dans un format autre que PDF, et si le contenu exposé ne peut pas être converti au format PDF, une exception se produira lors de l’exécution. Le message que vous recevez vous informe que le contenu généré ne peut pas être converti au format PDF.

### <a name="limitations"></a>Limitations

Depuis la **version 10.0.9** de Finance, l’option de conversion PDF n’est disponible que pour les déploiements cloud. À partir de la version **10.0.27** de Finance, l’option de conversion PDF est disponible pour tout déploiement sur site ayant une [connectivité Internet](../user-interface/client-disconnected.md) activée.

Le document PDF produit est limité à une longueur maximum de 300 pages.

Depuis la **version 10.0.9** de Finance, seule l’orientation de la page au format paysage est prise en charge dans le document PDF généré depuis une sortie Excel. À compter de la **version 10.0.10** de Finance, vous pouvez [spécifier l’orientation de la page](#SelectPdfPageOrientation) dans le document PDF généré à partir d’une sortie Excel pendant que vous configurez une destination pour les états électroniques (ER).

Seules les polices système courantes du système d’exploitation Windows sont utilisées pour la conversion d’une sortie qui ne contient aucune police intégrée.

### <a name="resources"></a>Ressources

Avant Finance version 10.0.29, la conversion PDF ne pouvait être effectuée qu’en dehors de l’instance Finance actuelle. Un fichier généré a été envoyé par Finance au service de conversion, et ce service a ensuite renvoyé le document converti. Cependant, dans la version **10.0.29 et versions ultérieures**, en plus de la fonctionnalité **Convertir les documents sortants de rapports électroniques Microsoft Office au format PDF**, vous pouvez activer la fonctionnalité **Utiliser les ressources de l’application pour effectuer la conversion des documents CBD du format Word au format PDF**. Cette fonctionnalité vous permet de convertir localement des documents Word générés au format PDF en utilisant les ressources du serveur d’applications dans l’instance Finance actuelle. 

Voici les avantages de la conversion PDF locale lorsque la fonctionnalité **Utiliser les ressources de l’application pour effectuer la conversion des documents CBD du format Word au format PDF** est activée :

- Le document PDF produit n’est pas [limité](#limitations) à un nombre de pages maximal.
- Le document Word qui est converti peut contenir un [grand nombre de contrôles de contenu](https://fix.lcs.dynamics.com/Issue/Details?bugId=647877&dbType=3).
- La connectivité Internet n’est pas requise dans les déploiements sur site.

### <a name="use-the-pdf-conversion-option"></a>Utilisez l’option de conversion PDF

Pour activer la conversion PDF pour une destination de fichier, cochez la case **Convertir en PDF**.

[![Activation de la conversion PDF pour une destination de fichier.](./media/ER_Destinations-TurnOnPDFConversion.png)](./media/ER_Destinations-TurnOnPDFConversion.png)

### <a name=""></a><a name="SelectPdfPageOrientation">Sélectionner une orientation de page pour la conversion PDF</a>

Si vous générez une configuration des états électroniques au format Excel et si vous souhaitez la convertir au format PDF, vous pouvez explicitement spécifier l’orientation de page du document PDF. Lorsque vous cochez la case **Convertir en PDF** pour activer la conversion PDF pour une destination de fichier qui produit un fichier de sortie au format Excel, le champ **Orientation de la page** devient disponible sur le raccourci **Paramètres de conversion PDF**. Dans le champ **Orientation de la page**, sélectionnez l’orientation préférée.

[![Sélection d’une orientation de page pour la conversion PDF.](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)

Pour avoir la possibilité de sélectionner l’orientation de la page PDF, installez Finance version 10.0.10 ou ultérieure. Dans les versions de Finance **antérieures à la version 10.0.23**, cette option propose les options d’orientation de page suivantes :

- Portrait
- Paysage

L’orientation de page sélectionnée est appliquée à toutes les pages d’un document sortant généré au format Excel, puis converti au format PDF.

Cependant, dans les **versions 10.0.23 et ultérieures**, la liste des options d’orientation de page a été étendue comme suit :

- Portrait
- Paysage
- Spécifique à la feuille de calcul

Lorsque vous sélectionnez l’option **Spécifique à la feuille de calcul**, chaque feuille de calcul d’un classeur Excel généré est convertie au format PDF en utilisant l’orientation de page qui a été configurée pour cette feuille de calcul dans le modèle Excel utilisé. Ainsi, vous pouvez avoir un document PDF final contenant des pages portrait et paysage. 

Si une configuration des états électroniques au format Word est convertie au format PDF, l’orientation de page du document PDF provient toujours du document Word.

## <a name="output-unfolding"></a>Déploiement de la sortie

Lorsque vous configurez une destination pour le composant **Dossier** de votre format d’états électroniques, vous pouvez spécifier comment la sortie de ce composant est transmise à la destination configurée.

### <a name="make-output-unfolding-available"></a>Rendre le déploiement de la sortie disponible

Pour rendre l’option de déploiement de la sortie disponible dans l’instance actuelle de Finance, ouvrez l’espace de travail **Gestion des fonctionnalités** et activez la fonctionnalité **Autoriser la configuration des destinations d’états électroniques pour envoyer le contenu des dossiers en tant que fichiers distincts**.

### <a name="applicability"></a>Conditions d’application

L’option de déploiement de la sortie ne peut être configurée que pour les composants de format de type **Dossier**. Lorsque vous commencez à configurer un composant **Dossier**, le raccourci **Général** devient disponible dans la page **Destination des états électroniques**. 

### <a name="use-the-output-unfolding-option"></a>Utiliser l’option de déploiement de la sortie

Dans le raccourci **Général**, dans le champ **Envoyer le dossier en tant que**, sélectionnez l’une des valeurs suivantes :

- **Archive ZIP** : transmettez un fichier généré en tant que fichier zip.
- **Fichiers distincts** : transmettez chaque fichier d’un fichier zip généré en tant que fichier individuel.

    > [!NOTE]
    > Lorsque vous sélectionnez **Fichiers distincts**, la sortie générée est collectée en mémoire dans un état compressé. Par conséquent, la [limite de taille de fichier](er-compress-outbound-files.md) maximale est appliquée pour la sortie compressée lorsque la taille réelle du fichier peut dépasser cette limite. Nous vous recommandons de sélectionner cette valeur lorsque vous prévoyez que la taille de la sortie générée est relativement importante.

[![Configuration d’une destination pour un composant de format Dossier.](./media/er_destinations-set-unfolding-option.png)](./media/er_destinations-set-unfolding-option.png)

### <a name="limitations"></a>Limitations

Si vous définissez le champ **Envoyer le dossier en tant que** sur **Fichiers distincts** pour un composant **Dossier** contenant d’autres composants **Dossier** imbriqués, le paramètre n’est pas appliqué de manière récursive aux composants **Dossier** imbriqués.

## <a name="change-page-layout-properties-of-a-template"></a><a name="change-page-layout-properties-of-a-template"></a> Modifier les propriétés de mise en page d’un modèle

Vous pouvez configurer une destination d’états électroniques pour un composant au format d’état électronique conçu pour utiliser un modèle dans un format Microsoft Office (Excel ou Word) pour la génération d’états. Si vous n’êtes pas le propriétaire de ce format et que vous devez modifier les propriétés de mise en page du modèle de format, dans les versions de Finance antérieures à la version 10.0.29, vous devez créer un format dérivé et modifier les propriétés du modèle. Ensuite, vous devez conserver la configuration du format dérivé. Cependant, dans la version 10.0.29 et les versions ultérieures, vous pouvez modifier les propriétés de mise en page du modèle lors de l’exécution pour éviter de créer et de gérer la configuration du format dérivé. Pour ce faire, configurez les propriétés souhaitées dans le cadre des paramètres de la destination des états électroniques configurée. Lorsque vous exécutez un format d’état électronique et exécutez une destination d’états électroniques configurée pour utiliser certaines propriétés de mise en page, les valeurs des propriétés de mise en page de la destination exécutée sont appliquées au modèle que vous utilisez, remplaçant les propriétés du modèle d’origine. Vous pouvez configurer différentes destinations pour le même composant de format en configurant différentes propriétés de mise en page pour le modèle utilisé.

Les propriétés suivantes peuvent être configurées dans une destination d’états électroniques pour un composant de format conçu pour utiliser un modèle dans un format Excel ou Word :

- Orientation de la page
    - Portrait
    - Paysage
- Format du papier
    - A3
    - A4
    - A5
    - B4
    - B5
    - Exécutif US
    - Legal US
    - Lettre US
    - Statement US
    - Tabloïd
- Marges de la page
    - Haut
        - En-tête
    - Bas
        - Pied de page
    - Gauche
    - Droite

> [!NOTE]
> L’orientation de la page du modèle ainsi configuré doit être alignée sur l’[orientation de la page pour la conversion PDF](#select-a-page-orientation-for-pdf-conversion) si la conversion PDF est configurée.

Vous devez sélectionner l’unité de longueur pour définir les marges de la page :

- Pouces
- Centimètres
- Millimètres

![Configurez les propriétés de mise en page sur la page de destination des états électroniques.](./media/er_destinations-set-page-layout-properties.png)

> [!TIP]
> Lorsqu’une valeur de marge est désignée en centimètres et spécifiée avec plusieurs décimales, elle est arrondie au moment de l’exécution à la valeur la plus proche avec 1 décimale.
>
> Lorsqu’une valeur de marge est désignée en millimètres et spécifiée avec plusieurs décimales, elle est arrondie au moment de l’exécution d’Excel à la valeur la plus proche sans décimale.
>
> Lorsqu’une valeur de marge est désignée en millimètres et spécifiée avec plusieurs décimales, elle est arrondie au moment de l’exécution de Word à la valeur la plus proche avec une décimale.

## <a name="security-considerations"></a>Considérations de sécurité

Deux types de privilèges et de droits sont utilisés pour les destinations d’états électroniques. Un type contrôle la possibilité globale d’un utilisateur de mettre à jour les destinations qui sont configurées pour une entité juridique (autrement dit, il contrôle l’accès à la page **Destinations des états électroniques**). L’autre type contrôle la capacité de l’utilisateur d’une application à substituer, au moment de l’exécution, les paramètres de destination qu’un développeur d’états électroniques ou un consultant fonctionnel d’états électroniques a configuré.

| Rôle (nom AOA)                     | Nom de rôle                                  | Droit de douane (nom AOA)                     | Nom de droits de douane                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Développeur d’états électroniques             | ERFormatDestinationConfigure        | Configurer la destination du format des états électroniques                |
| ERFunctionalConsultant              | Consultant fonctionnel des états électroniques | ERFormatDestinationConfigure        | Configurer la destination du format des états électroniques                |
| PaymAccountsPayablePaymentsClerk    | Commis au paiement de la comptabilité fournisseur            | ERFormatDestinationRuntimeConfigure | Configurer la destination du format des états électroniques durant l’exécution |
| PaymAccountsReceivablePaymentsClerk | Commis au paiement de la comptabilité client         | ERFormatDestinationRuntimeConfigure | Configurer la destination du format de gestion des états électroniques durant l’exécution |

> [!NOTE]
> Deux privilèges sont utilisés dans les droits précédents. Ces privilèges ont les mêmes noms que les droits correspondants : **ERFormatDestinationConfigure** et **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>J’ai importé des configurations électroniques et je les vois sur la page Configurations des états électroniques. Mais pourquoi je ne les vois pas dans la page Destinations des états électroniques ?

Vérifiez que vous sélectionnez **Nouveau**, puis sélectionnez une configuration dans le champ **Référence**. La page **Destinations des états électroniques** affiche uniquement les configurations pour lesquelles les destinations ont été configurées.

### <a name="is-there-any-way-to-define-which-microsoft-azure-storage-account-and-azure-blob-storage-are-used"></a>Est-il possible de définir quel compte de stockage Microsoft Azure et quel stockage Blob Azure sont utilisés ?

Non Le stockage Blob Microsoft Azure par défaut défini et utilisé pour le système de gestion des documents est utilisé.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Quel est l’objectif de la destination de fichier dans les paramètres de destination ? Que fait ce paramètre ?

La destination **Fichier** est utilisée pour contrôler une boîte de dialogue de votre navigateur Web lorsque vous exécutez un format de gestion des états électroniques en mode interactif. Si vous activez cette destination, ou si aucune destination n’est définie pour une configuration, une boîte de dialogue Ouvrir ou Enregistrer s’affiche dans votre navigateur Web après la création d’un fichier de sortie.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Pouvez-vous donner un exemple de la formule qui fait référence à un compte fournisseur à laquelle je peux envoyer des courriers électroniques ?

La formule est spécifique à la configuration de l’état électronique. Par exemple, si vous utilisez la configuration du virement ISO 20022, vous pouvez utiliser **’$PaymentsForCoveringLetter’.Creditor.Identification.SourceID** ou **model. Payments.Creditor.Identification.SourceID** pour obtenir un compte fournisseur associé.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-grouped-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>L’une des configurations de mon format contient plusieurs fichiers qui sont regroupés dans un dossier (par exemple, Folder1 contient fichier1, fichier2 et fichier3). Comment définir des destinations afin que Folder1.zip ne soit pas créé du tout, que fichier1 soit envoyé par courrier électronique, que fichier2 soit envoyé à SharePoint, et que je puisse ouvrir fichier3 immédiatement après l’exécution de la configuration ?

Votre format doit tout d’abord être disponible dans les configurations d’états électroniques. Si cette condition préalable est remplie, ouvrez la page **Destination des états électroniques** et créez une nouvelle référence pour la configuration. Vous devez ensuite disposer de quatre destinations de fichiers, une pour chaque composant de sortie. Créez la première destination du fichier, donnez-lui un nom tel que **Dossier**, puis sélectionnez un nom de fichier qui représente un dossier dans votre configuration. Puis sélectionnez **Paramètres** et assurez-vous que toutes les destinations sont désactivées. Pour cette destination de fichier, le dossier ne sera pas créé. Par défaut, en raison des relations hiérarchiques entre les fichiers et les dossiers parents, les fichiers se comportent de la même manière. En d’autres termes, ils ne seront envoyés nulle part. Pour remplacer ce comportement par défaut, vous devez créer trois destinations de fichier supplémentaires, une pour chaque fichier. Dans les paramètres de la destination de chacun, vous devez activer la destination à laquelle le fichier doit être envoyé.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des états électroniques](general-electronic-reporting.md)

[Configurer les destinations pour la gestion des états électroniques dépendant de l’action](er-action-dependent-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
