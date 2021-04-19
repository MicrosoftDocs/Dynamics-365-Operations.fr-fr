---
title: Type de destination pour l’impression d’états électroniques
description: Cette rubrique explique comment configurer une destination d’imprimante pour chaque composant DOSSIER ou FICHIER d’un format de gestion des états électroniques.
author: NickSelin
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 83081f8c17a903cd447a34596df2e61ebda0cafc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753430"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Destination d’imprimante

[!include [banner](../includes/banner.md)]

Vous pouvez envoyer un document généré directement à une imprimante réseau pour une impression directe.

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer, vous devez installer et configurer l’agent de routage de documents, puis enregistrer les imprimantes réseau. Pour plus d’informations, voir [Installer l’agent d’acheminement de document pour activer l’impression réseau](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).

## <a name="make-the-printer-destination-available"></a>Rendre la destination de l’imprimante disponible

Pour rendre la destination de l’**Imprimante** disponible dans l’instance actuelle de Microsoft Dynamics 365 Finance, accédez à l’espace de travail **Gestion des fonctionnalités** et activez les fonctionnalités suivantes, dans cet ordre :

1. Convertir les documents sortants des rapports électroniques aux formats Microsoft Office vers le format PDF
2. Agent d’acheminement de document en tant que destination des rapports électroniques pour les documents sortants

[![Activation de la fonction de destination de l’imprimante ER dans la gestion des fonctionnalités](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Conditions d’application

La destination de l’**Imprimante** ne peut être configurée que pour les composants de fichier utilisés pour générer une sortie au format PDF imprimable (fusion PDF ou éléments de format de fichier PDF) ou Microsoft Office Excel / Format Word (fichier Excel). Lorsque la sortie est générée au format PDF, elle est envoyée à une imprimante. Lorsque la sortie est générée au format Microsoft Office, elle est automatiquement convertie au format PDF, puis envoyée à une imprimante.

### <a name="limitations"></a>Limitations

La destination de l’**Imprimante** est implémentée uniquement pour les déploiements cloud.

### <a name="use-the-printer-destination"></a>Utiliser la destination de l’imprimante

1. Définissez l’option **Activé** sur **Oui** pour envoyer un document généré à une imprimante.
2. Dans le champ **Nom d’imprimante**, sélectionnez l’imprimante réseau requise.
3. Définissez l’option **Enregistrer dans les archives d’impression ?** sur **Oui** pour stocker la sortie générée dans l’archive d’impression, afin qu’elle soit disponible pour une impression ultérieure. Pour accéder ultérieurement à la sortie archivée, accédez à **Administration de l’organisation** \>**Recherches et états** \>**Archive d’état**.

[![Utilisation de la destination de l’imprimante](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> L’option **Convertir en PDF** ne doit pas être activée lorsque vous configurez la destination de l’**Imprimante**. La conversion PDF à des fins d’impression se produira même si l’option est désactivée.

Pour utiliser une [orientation de la page](electronic-reporting-destinations.md#SelectPdfPageOrientation) spécifique lorsque vous imprimez un document sortant au format Excel, vous devez activer l’option **Convertir en PDF**. Lorsque vous définissez l’option **Convertir en PDF** sur **Oui**, le champ **Orientation de la page** devient disponible. Dans le champ **Orientation de la page**, sélectionnez une orientation de la page.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des états électroniques](general-electronic-reporting.md)
- [Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
