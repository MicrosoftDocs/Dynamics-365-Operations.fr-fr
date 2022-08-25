---
title: Type de destination pour l’impression d’états électroniques
description: Cet article explique comment configurer une destination d’imprimante pour chaque composant DOSSIER ou FICHIER d’un format de gestion des états électroniques.
author: kfend
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423
ms.assetid: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: 7e01476b85c6c35d7c36c90db4d64ab2a2930fec
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271732"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Destination d’imprimante

[!include [banner](../includes/banner.md)]

Vous pouvez envoyer un document généré directement à une imprimante réseau pour une impression directe.

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer, vous devez installer et configurer l’agent de routage de documents, puis enregistrer les imprimantes réseau. Pour plus d’informations, voir [Installer l’agent d’acheminement de document pour activer l’impression réseau](./install-document-routing-agent.md).

## <a name="make-the-printer-destination-available"></a>Rendre la destination de l’imprimante disponible

Pour rendre la destination de l’**Imprimante** disponible dans l’instance actuelle de Microsoft Dynamics 365 Finance, accédez à l’espace de travail **Gestion des fonctionnalités** et activez les fonctionnalités suivantes, dans cet ordre :

1. Convertir les documents sortants des rapports électroniques aux formats Microsoft Office vers le format PDF
2. Agent d’acheminement de document en tant que destination des rapports électroniques pour les documents sortants

[![Activation de la fonction de destination de l’imprimante ER dans la gestion des fonctionnalités.](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Conditions d’application

#### <a name="pdf-printing"></a>Impression PDF

Dans les versions de Finance avant la version 10.0.18, la destination de l’**Imprimante** ne peut être configurée que pour les composants de fichier utilisés pour générer une sortie au format PDF imprimable (**fusion PDF** ou éléments de format de **fichier PDF**) ou Microsoft Office Excel et Format Word (**fichier Excel**). Lorsque la sortie est générée au format PDF, elle est envoyée à une imprimante. Lorsque la sortie est générée au format Office à l’aide de l’élément de format **Fichier Excel**, elle est automatiquement convertie au format PDF, puis envoyée à une imprimante.

Cependant, à partir de la version 10.0.18, vous pouvez configurer la destination **Imprimante** pour l’élément de format **Common File**. Cet élément de format est principalement utilisé pour générer une sortie au format TXT ou XML. Vous pouvez configurer un format ER qui contient l’élément de format **Common File** comme élément de format racine et l’élément de format **Contenu binaire** comme le seul élément imbriqué sous celui-ci. Dans ce cas, l’élément de format **Common File** produira une sortie dans le format spécifié par la liaison que vous configurez pour l’élément de format **Contenu binaire**. Par exemple, vous pouvez configurer cette liaison pour [remplir](tasks/er-document-management-files-5.md#modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format) cet élément avec le contenu d’une pièce jointe [Gestion de documents](../../fin-ops/organization-administration/configure-document-management.md) au format PDF ou Office (Excel ou Word). Vous pouvez imprimer la sortie en utilisant la destination **Imprimante** configurée. 

> [!NOTE]
> Lorsque vous sélectionnez l’élément de format **Common\\File** pour configurer la destination **Imprimante**, il n’existe aucun moyen de garantir, au moment de la conception, que l’élément sélectionné produira une sortie au format PDF ou une sortie pouvant être convertie au format PDF. Par conséquent, vous recevez le message d’avertissement suivant : « Veuillez veiller à ce que la sortie qui est générée par le composant de format sélectionné puisse être convertie au format PDF. Sinon, décochez l’option « Convertir en PDF ». Vous devez prendre des mesures pour éviter les problèmes d’exécution lorsqu’une sortie non PDF ou non convertible en PDF est fournie pour l’impression au moment de l’exécution. Si vous prévoyez de recevoir une sortie au format Office (Excel ou Word), l’option **Convertir en PDF** doit être sélectionnée.
>
> Dans la version 10.0.26 et ultérieures, pour utiliser l’option **Convertir en PDF**, vous devez sélectionner **PDF** pour le paramètre **Type d’acheminement de document** de la destination **Imprimante** configurée.

#### <a name="zpl-printing"></a>Impression ZPL

Dans la version 10.0.26 et ultérieures, vous pouvez configurer la destination **Imprimante** pour l’élément de format **Common\\File** sélectionnant **ZPL** pour le paramètre **Type d’acheminement de document**. Dans ce cas, l’option **Convertir en PDF** est ignorée lors de l’exécution et la sortie TXT ou XML est envoyée directement à une imprimante sélectionnée à l’aide du contrat Zebra Programming Language (ZPL) de l’[Agent d’acheminement de document (DRA)](install-document-routing-agent.md). Utilisez cette fonction pour un format ER qui représente une mise en page d’étiquette ZPL II pour imprimer diverses étiquettes.

[![Définition du paramètre Type d’acheminement du document dans la boîte de dialogue Paramètres de destination.](./media/ER_Destinations-SetDocumentRoutingType.png)](./media/ER_Destinations-SetDocumentRoutingType.png)

Pour plus d’informations sur cette fonctionnalité, voir [Concevoir une nouvelle solution ER pour imprimer des étiquettes ZPL](er-design-zpl-labels.md).

### <a name="limitations"></a>Limitations

La destination de l’**Imprimante** est implémentée uniquement pour les déploiements cloud.

### <a name="use-the-printer-destination"></a>Utiliser la destination de l’imprimante

1. Définissez l’option **Activé** sur **Oui** pour envoyer un document généré à une imprimante.
2. Dans le champ **Nom d’imprimante**, sélectionnez l’imprimante réseau requise.
3. Définissez l’option **Enregistrer dans les archives d’impression ?** sur **Oui** pour stocker la sortie générée dans l’archive d’impression, afin qu’elle soit disponible pour une impression ultérieure. Pour accéder ultérieurement à la sortie archivée, accédez à **Administration de l’organisation** \>**Recherches et états** \>**Archive d’état**.

[![Utilisation de la destination de l’imprimante.](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> L’option **Convertir en PDF** ne doit pas être activée lorsque vous configurez la destination de l’**Imprimante**. La conversion PDF à des fins d’impression se produira même si l’option est désactivée.

Pour utiliser une [orientation de la page](electronic-reporting-destinations.md#SelectPdfPageOrientation) spécifique lorsque vous imprimez un document sortant au format Excel, vous devez activer l’option **Convertir en PDF**. Lorsque vous définissez l’option **Convertir en PDF** sur **Oui**, le champ **Orientation de la page** devient disponible. Dans le champ **Orientation de la page**, sélectionnez une orientation de la page.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des états électroniques](general-electronic-reporting.md)
- [Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
