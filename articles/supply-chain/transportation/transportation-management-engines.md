---
title: Moteurs de gestion de transport
description: Les moteurs de gestion de transport définissent la logique utilisée pour générer et traiter les frais de transport dans Gestion du transport.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSGenericEngine, TMSMileageEngine, TMSRateEngine, TMSTransitTimeEngine, TMSZoneEngine, TMSFreightBillTypeAssignment, TMSZoneMaster, TMSEngineParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf9c256c4b9ade408111a46899ee266b2eb0d651
ms.sourcegitcommit: 890a0b3eb3c1f48d786b0789e5bb8641e0b8455e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920107"
---
# <a name="transportation-management-engines"></a>Moteurs de gestion de transport

[!include [banner](../includes/banner.md)]

Les moteurs de gestion de transport définissent la logique utilisée pour générer et traiter les frais de transport dans Gestion du transport. 

Le moteur de gestion de transport calcule des tâches, comme les frais de transport du transporteur. Il permet de modifier les stratégies de calcul au moment de l’exécution, en fonction des données dans Supply Chain Management. Un moteur de gestion de transport ressemble à un plug-in associé à un contrat de transporteur particulier.

## <a name="what-engines-are-available"></a>Quels sont les moteurs disponibles ?
Le tableau suivant répertorie les moteurs de gestion de transport disponibles.

| Moteur de gestion de transport | Description                                                                                                                                                                                                                                                                                                                 |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Moteur de taux**                  | Calcule les frais.                                                                                                                                                                                                                                                                                                           |
| **Moteur générique**               | Moteurs auxiliaires simples utilisés par d’autres moteurs, qui ne requièrent pas de données de Supply Chain Management, par exemple, un moteur de répartition. Les moteurs de répartition permettent de réduire les coûts finaux du transport pour des commandes et des lignes spécifiques, selon des dimensions telles que le volume et le poids. |
| **Moteur de kilométrage**               | Calcule la distance de transport.                                                                                                                                                                                                                                                                                     |
| **Moteur de temps de transit**          | Calcule le temps nécessaire pour atteindre la destination finale.                                                                                                                                                                                                                                       |
| **Moteur de zone**                  | Calcule la zone en fonction de l’adresse actuelle, ainsi que le nombre de zones qui doivent être traversées pour aller de l’adresse A à l’adresse B.                                                                                                                                                                    |
| **Type de facture des frais de transport**            | Standardise la facture de transport et les lignes de la facture de frais de transport et permet de mettre en correspondance automatiquement la facture de frais de transport.                                                                                                                                                                                                                |


<a name="what-engines-must-be-configured-to-rate-a-shipment"></a>Quels moteurs doit-on configurer pour évaluer une expédition ?
---------------------------------------------------

Pour évaluer une expédition pour un transporteur spécifique, vous devez configurer plusieurs moteurs de gestion de transport. Un **moteur de frais** est nécessaire, mais d’autres moteurs de gestion du transport peuvent être requis pour prendre en charge le **moteur de frais**. Par exemple, le **moteur de frais** peut être utilisé pour extraire les données du **moteur de kilométrage** et calculer les frais en fonction du kilométrage entre la source et la destination.

## <a name="whats-required-to-initialize-a-transportation-management-engine"></a>De quoi a-t-on besoin pour initialiser un moteur de gestion de transport ?
Un moteur de gestion de transport requiert le paramétrage de données d’initialisation afin de fonctionner de façon spécifique. La configuration peut inclure les types de données suivants :
-   Références à d’autres moteurs de gestion de transport. Pour plus d’informations, voir l’exemple de configuration dans cette section.
-   Références aux types .NET utilisés par le moteur de gestion de transport.
-   Données de configuration simples.

Dans la plupart des cas, vous pouvez cliquer sur le bouton **Paramètres** dans les écrans de paramétrage du moteur de gestion du transport pour configurer les données d’initialisation. **Exemple de configuration d’un moteur de frais faisant référence à un moteur de kilométrage** L’exemple suivant présente le paramétrage requis pour un moteur de frais basé sur le type de moteur .NET Microsoft.Dynamics.Ax.Tms.Bll.MileageRateEngine et référence un moteur de kilométrage.

|          Paramètre           |                                                                                  Description                                                                                  |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <em>RateBaseAssigner</em>   | Type .NET qui interprète les données d’affectation de base des frais pour un schéma particulier. La syntaxe de la valeur de paramètre est composée de deux segments délimités par une barre verticale ( |
|  <em>MileageEngineCode</em>  |                       Code de moteur de kilométrage qui identifie l’enregistrement du moteur de kilométrage dans la base de données.                        |
| <em>ApportionmentEngine</em> |                        Code de moteur générique qui identifie le moteur de répartition dans la base de données.                        |

<a name="how-is-metadata-used-in-transportation-management-engines"></a>Comment utilise-t-on les métadonnées dans les moteurs de gestion de transport ?
----------------------------------------------------------

Les moteurs de gestion du transport qui se fondent sur des données définies dans Supply Chain Management peuvent utiliser différents schémas de données. Le système de gestion du transport permet à différents moteurs de gestion de transport d’utiliser les mêmes tables de base de données physique génériques. Pour vous assurer que l’interprétation des données du moteur au moment de l’exécution est correcte, vous pouvez définir des métadonnées pour les tables de la base de données. Cela réduit le coût de génération de nouveaux moteurs de gestion du transport, car il n’est pas nécessaire d’ajouter de tables ni de structures d’écran dans Operations.

## <a name="what-can-be-used-as-search-data-in-rate-calculations"></a>Quelles données de recherche peut-on utiliser pour les calculs de frais ?
Les données utilisées lorsque vous calculez des frais sont contrôlées par la configuration des métadonnées. Par exemple, si vous souhaitez rechercher des frais en fonction de codes postaux, vous devez paramétrer les métadonnées en fonction du type de recherche de code postal.

## <a name="do-all-engine-configurations-require-metadata"></a>Toutes les configurations de moteur requièrent-elles des métadonnées ?
Non, les moteurs de gestion de transport utilisés pour extraire les données requises pour le calcul de frais à partir de systèmes externes n’ont pas besoin de métadonnées. Les données de frais pour ces moteurs peuvent être récupérées à partir des systèmes du transporteur externe, généralement via un service Web. Par exemple, vous pouvez utiliser un moteur de kilométrage qui récupère les données directement de Bing Maps. Vous n’avez donc pas besoin de métadonnées pour ce moteur.

| **Remarque**                                                                                                                                                                                                                                                                                                                                                                     |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Les moteurs de gestion du transport qui sont livrés avec Supply Chain Management se fondent sur des données extraites de l’application. Les moteurs qui se connectent à des systèmes externes ne sont pas inclus dans Operations. Toutefois, le modèle d’extensibilité basé sur le moteur permet de créer des extensions avec les outils Visual Studio. |

## <a name="how-do-i-configure-metadata-for-a-transportation-management-engine"></a>Comment puis-je configurer les métadonnées d’un moteur de gestion de transport ?
Les métadonnées des moteurs de gestion de transport sont configurées différemment selon les différents types de moteurs.

| Moteur de gestion de transport               | Configuration des métadonnées                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Moteur de taux**                                | Requiert un **type de base de taux**. Le type de base pour les frais contient les métadonnées des données de base des frais et les données d’affectation de base des frais. La structure des métadonnées de base des frais est déterminée par le type de moteur de frais. La structure des métadonnées d’affectation de base des frais est déterminée par le type d’assignateur de base des frais associé à ce moteur de frais. Vous paramétrez le type de base de taux d’un moteur de frais dans la page **Moteur de frais** et dans la page **Données principales du taux**. |
| **Moteur de zone**                                | Nécessite la configuration des métadonnées directement dans la table maître des zones.                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Moteur de temps de transit** et **Moteur de kilométrage** | Récupère les métadonnées directement depuis l’écran paramétrage de la configuration du moteur de kilométrage.                                                                                                                                                                                                                                                                                                                                                                                  |

  **Exemple de métadonnées pour un moteur de frais** Le moteur de gestion du transport nécessite l’identification de l’adresse d’origine, l’état et le pays/la région de destination et les points de départ et d’arrivée de l’expédition. Selon ces exigences, les métadonnées ressemblent aux données du tableau suivant. Le tableau répertorie également des informations sur le type de données d’entrée obligatoire.
-   Définissez ces informations dans **Gestion du transport** &gt; **Paramétrage** de la page **Type de base de taux**.

| Ordre | Nom                          | Type de champ | Type de données | Type de recherche    | Obligatoire |
|----------|-------------------------------|------------|-----------|----------------|-----------|
| 1        | Code postal d’origine            | Affectation | Chaîne    | Code postal    | Sélectionné  |
| 2        | État de destination             | Affectation | Chaîne    | Région          |           |
| 3        | Code postal du point de départ | Affectation | Chaîne    | Code postal    | Sélectionné  |
| 4        | Code postal du point d’arrivée   | Affectation | Chaîne    | Code postal    | Sélectionnée  |
| 5        | Pays de destination           | Affectation | Chaîne    | Pays/région |           |

### <a name="whitepaper"></a>Livre blanc

Pour plus d’informations, téléchargez le livre blanc suivant (écrit pour prendre en charge AX2012, mais s’applique toujours à Dynamics 365 Supply Chain Management)

- [Moteurs de gestion du transport](https://download.microsoft.com/download/e/0/9/e0957665-c12f-43c7-94c0-611cc49d7d61/TransportationManagementEnginesInAX.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]