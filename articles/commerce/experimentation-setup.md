---
title: Configurer une expérience
description: Cet article décrit comment configurer une expérience dans un service tiers.
author: sushma-rao
ms.date: 06/08/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1073cdc509622279ce7388b8b406079a4e6e9e09
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946164"
---
# <a name="set-up-an-experiment"></a>Configurer une expérience

Après avoir [défini une hypothèse et déterminé les métriques de réussite que vous souhaitez utiliser](experimentation-identify.md), vous devrez configurer votre expérience dans le service tiers. Le diagramme suivant montre toutes les étapes impliquées dans la configuration et l’exécution d’une expérience sur un site web d’e-commerce dans Dynamics 365 Commerce. Les étapes supplémentaires sont traitées dans d’autres articles.

[ ![Expérimentation parcours utilisateur - Configurer.](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>Configurer votre expérience dans le service tiers
Vous devriez maintenant avoir choisi votre service tiers chargé d’exécuter et de surveiller votre expérience, et avoir configuré le connecteur d’expérimentation. Ces conditions préalables sont répertoriées dans [Expérimentation dans Dynamics 365 Commerce](experimentation-overview.md).

Suivez les étapes requises pour créer votre expérience dans le service tiers. Si le connecteur est correctement configuré, la liste complète des expériences que vous avez configurées dans le service tiers apparaîtra dans le générateur de site Commerce dans un délai d’environ 5 minutes.

## <a name="set-up-your-success-metrics"></a>Configurer vos métriques de réussite
Chaque expérience a besoin de métriques pour mesurer l’impact des variantes et valider l’hypothèse. Suivez les étapes ci-dessous pour activer le calcul des métriques dans le service tiers à l’aide des événements de télémétrie en ligne de Dynamics 365 Commerce.

Pour configurer vos mesures de réussite pour les modules prêts à l'emploi, procédez comme suit.

1. Dans le générateur de site Commerce, sélectionnez **Pages** dans le volet de navigation de gauche, puis sélectionnez la page pour laquelle vous souhaitez collecter des métriques. 
1. Accédez à la section **ID d’événement à suivre** dans le volet des propriétés situé à droite de la page ou du module dont vous souhaitez effectuer le suivi.
1. Sélectionnez **Afficher**. Une liste de tous les ID d’événement de clic s’affiche. Copiez l’événement dont vous souhaitez effectuer le suivi et collez la clé d’événement à l’emplacement désigné dans le service tiers. Si vous avez besoin de plusieurs événements, copiez les clés une par une. 
1. Pour les pages vues, utilisez la valeur de hachage SHA-256 du nom de la page dans le générateur de site suivi de `.PageView`. Par exemple, l'ID d'événement pour `Homepage.PageView` serait `e217eb66c7808ecc43b0f5c517c6a83b39d72b91412fbd54a485da9d8e186a9`.
1. Prenez toutes les autres mesures requises dans le service tiers pour procéder au suivi des métriques.

Pour les clics de module personnalisés, suivez ces étapes pour instrumenter les événements de clic :

1. Préparez un objet **TelemetryContent** pour le module à l'aide de la fonction ci-dessous. Cette fonction prend le nom de la page, le nom du module et l'objet de télémétrie par défaut fourni par le SDK comme entrées.

    ```TypeScript
    getTelemetryObject(pageName: string, moduleName: string, telemetry: ITelemetry): ITelemetryContent
    ```
    
    Vous trouverez un exemple : 
    
    ```TypeScript
    private readonly telemetryContent: ITelemetryContent = getTelemetryObject(this.props.context.request.telemetryPageName!, this.props.friendlyName, this.props.telemetry);
    ```
    
1. Créez les données utiles qui contiennent des informations sur ce qui doit être capturé. Pour les boutons et autres contrôles statiques, vous pouvez inclure **etext** comme "Acheter maintenant" ou "Rechercher". Et pour les composants avec des clics tels que cliquer sur une fiche produit, vous pouvez envoyer le **recid** qui est l'ID d'enregistrement du produit ou l'ID de produit.

    ```TypeScript
    getPayloadObject(eventType: string, telemetryContent: ITelemetryContent, etext: string, recid?: string): IPayLoad
    ```
    À titre d'exemple pour les contrôles statiques, transmettez la chaîne de texte du bouton comme indiqué ci-dessous :

    ```TypeScript
    const payLoad = getPayloadObject('click', this.props.telemetryContent, 'Shop Now', '');
    ```
    À titre d'exemple pour les clics sur le produit, transmettez le recordID du produit comme indiqué ci-dessous :

    ```TypeScript
    const payLoad = getPayloadObject('click', telemetryContent!, '', product.RecordId.toString());
    ```
    
1. Appelez la fonction **OnClick** pour enregistrer l'événement.

    ```TypeScript
    onTelemetryClick = (telemetryContent: ITelemetryContent, payLoad: IPayLoad, linkText: string) => () =>
    ```

    Vous trouverez un exemple :

    ```TypeScript
    onClick: onTelemetryClick(this.props.telemetryContent, payLoad, linkText)
    ```

## <a name="previous-step"></a>Étape précédente
[Identifier une hypothèse et déterminer les métriques pour une expérience](experimentation-identify.md) 


## <a name="next-step"></a>Étape suivante
[Connecter et modifier une expérience](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
