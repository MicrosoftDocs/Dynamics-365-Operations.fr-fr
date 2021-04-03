---
title: Paramétrage des informations de livraison
description: Cette rubrique décrit comment configurer les informations de livraison pour le module de coût au débarquement.
author: sherry-zheng
manager: tfehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMPortTable, ITMLeadTimeTable, ITMLegTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 7b65e1c6bb1b6bf345fdde0f4de7015190052efa
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500524"
---
# <a name="delivery-information-setup"></a>Paramétrage des informations de livraison

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique décrit comment configurer les informations de livraison pour le module de **coût au débarquement**.

## <a name="shipping-ports"></a>Ports d’expédition

Les ports d’expédition identifient la provenance et la destination des marchandises. Pour chaque voyage, un port "à" et un port "de" sont définis, en fonction du voyage sélectionné pour le navire de voyage. Les ports d’expédition sont utilisés pour construire les étapes d’un voyage et aussi les activités de voyage. Ils sont généralement définis à l’aide du nom de la ville et du pays ou de la région où se trouve le port d’expédition physique.

Pour travailler avec les ports d’expédition, accédez à **Coût au débarquement \> Configuration des informations de livraison \> Ports d’expédition**. Là, vous pouvez afficher, ajouter et supprimer des enregistrements pour vos ports d’expédition. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Port d’expédition | Entrez un nom/numéro d’identification unique pour le port d’expédition. |
| Description | Entrez une description du port d’expédition. |

## <a name="tracking-control-center"></a><a name="tracking-control-center"></a>Centre de contrôle de suivi

Vous utilisez le centre de contrôle Suivi pour configurer les délais, les mises à jour de statut et le flux d’informations associés à un voyage lorsque les conteneurs d’expédition se déplacent d’une étape à l’autre. Lorsque vous créez un enregistrement de contrôle de suivi, il est associé à une étape spécifique d’un voyage pour un voyage. Lorsqu’un voyage met à jour une étape, l’enregistrement associé est mis à jour et rempli comme défini. Vous pouvez mettre à jour les informations de suivi pour les voyages individuels à partir de la page **Tous les voyages**.

Pour ouvrir le centre de contrôle de suivi, accédez à **Coût au débarquement \> Configuration des informations de livraison \> Centre de contrôle de suivi**.

Le centre de contrôle de suivi affiche l’une des trois vues de page, en fonction de la valeur sélectionnée dans le champ **Créer un type** dans le volet de liste : *Vierge*, *Délai de mise en œuvre* ou *Mise à jour du statut*. Chaque type de création met à jour un ensemble différent d’informations associées à la progression d’un voyage du point d’origine à la destination finale.

### <a name="common-rule-settings"></a>Paramètres de règle communes

Le tableau suivant présente les champs disponibles pour les trois types de création dans le centre de contrôle Suivi.

| Champ | Description |
|---|---|
| Table source, champ Source | Ces champs identifient une table source et un champ dans la base de données. La règle chargera la valeur dans le champ, puis l’utilisera de la manière définie par d’autres paramètres de la règle. |
| Table cible, champ cible | Ces champs identifient une table de destination et un champ dans la base de données. La règle chargera la valeur dans le champ, puis l’utilisera (ou la remplacera) de la manière définie par d’autres paramètres de la règle. |
| Activité | Ce champ identifie le type d’activité à appliquer à un conteneur d’expédition correspondant à une règle. |
| Critères de correspondance | Ce champ détermine comment le système identifie une correspondance pour une règle. Dans chaque cas, le système examine les données des tables source et de destination pour déterminer si et quand un champ doit être mis à jour dans la table cible.<p>Par exemple, la table source est *Voyages*, et la table cible est *En-tête d’achat* ou *Lignes d’achat*. La table *Voyages* a une valeur **Port De** de *Hong Kong*, et la table *En-tête d’achat* a une valeur **Port De** de *Shanghai*. Une règle est alors créée qui a *Hong Kong* comme port "De". Dans ce cas, les valeurs du champ **Critères de correspondance** fonctionnera de la manière suivante :</p><ul><li>**Tous les deux** – Le champ cible ne sera pas mis à jour, car l’un des deux ports ne correspond pas.</li><li>**Source** – Le champ cible sera mis à jour, car le port "De" de la table source est *Hong Kong*.</li><li>**Cible** – Le champ cible ne sera pas mis à jour, car le port "De" de la table de destination est *Shanghai* (pas *Hong Kong*).</li></ul> |
| Action Copier | Les valeurs disponibles sont *Copier* et *Valeur par défaut*. Sélectionnez *Copier* pour copier la valeur du champ source dans le champ de destination. Sélectionnez *Valeur par défaut* pour définir une valeur statique pour le champ de destination. |
| Par défaut | Quand le champ **Action Copier** est défini sur *Valeur par défaut*, le champ **Valeur par défaut** définit la valeur par défaut du champ de destination. Par exemple, si l’action est liée à une mise à jour de port, et que le champ **Action Copier** le champ est défini sur *Valeur par défaut*, le champ **Valeur par défaut** identifie un port. |
| Étape | Ce champ identifie l’étape du voyage pour laquelle l’action spécifiée se produit, comme le chargement ou les douanes. |
| Fournisseur de service | Si un fournisseur de services spécifique est utilisé pour la mise à jour du statut actuel/l’étape du voyage, ce champ identifie le fournisseur de services. Les fournisseurs de services sont définis dans le compte fournisseur. |

### <a name="lead-time-rules"></a>Règles de délai

Le délai d’exécution est le temps estimé nécessaire à un voyage pour effectuer une étape définie d’un voyage pour un voyage. Le délai de chaque étape d’un voyage est utilisé pour calculer la date de livraison estimée du voyage. Cette date est ensuite saisie dans le champ **Date de livraison confirmée** sur chaque ligne d’achat du voyage.

Vous utilisez des règles de délai pour gérer les mises à jour des dates. Les activités sont automatiquement générées lorsqu’un modèle de voyage est utilisé pour un voyage.

Pour ajouter une règle de délai au centre de contrôle de suivi, procédez comme suit.

1. Utilisez l’une des procédures suivantes :

    - Accédez à **Coût au débarquement \> Configuration de voyage à plusieurs étapes \> Étapes**. Sélectionnez l’étape pour laquelle vous souhaitez configurer les délais, puis, dans le volet Actions, sélectionnez **Centre de contrôle de suivi**. Le centre de contrôle de suivi est préchargé avec des informations sur l’étape sélectionnée.
    - Allez à **Coût au débarquement \> Configuration des informations de livraison \> Centre de contrôle de suivi**. Vous devez ensuite sélectionner manuellement une étape de voyage à l’étape 4 de cette procédure.

1. Dans le volet de liste, définissez le champ **Créer un type** sur *Délai*.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Si vous avez démarré à partir du centre de contrôle de suivi à l’étape 1, définissez le champ **Étape** sur l’étape pour laquelle vous souhaitez créer une règle de délai. Si vous avez démarré à la page **Étapes**, le champ **Étape** est prédéfini sur l’étape que vous avez sélectionnée avant d’ouvrir le centre de contrôle de suivi.

    Basé sur la valeur du champ **Étape**, plusieurs champs sont automatiquement définis, comme indiqué ici :

    - **Table source :** *Activités conteneurs*
    - **Champ source :** *Date de début*
    - **Table cible :** *Activités conteneurs*
    - **Champ cible :** *Date de fin estimée*

1. Dans le champ **Activité**, sélectionnez l’activité à laquelle la règle actuelle doit s’appliquer.
1. Dans le champ **Délai**, saisissez le délai (en jours) à appliquer lorsque la règle actuelle est déclenchée.

### <a name="status-update-rules"></a>Règles de mise à jour du statut

Enregistre où le champ **Créer un type** est défini sur *Mise à jour du statut* mettra à jour le statut des commandes fournisseur, ou le statut au niveau du voyage, du conteneur d’expédition ou du folio. Les statuts peuvent être définis indépendamment. Utilisez-les pour informer l’utilisateur ou le service de l’étape d’un voyage (comme les documents reçus ou les marchandises en transit).

Quand le champ **Créer un type** est défini sur *Mise à jour du statut*, le centre de contrôle Tracking comprend un raccourci **Lignes** où vous pouvez définir une zone de coût et le statut mis à jour du voyage. Par exemple, vous avez une ligne où le champ **Zone de coût** est défini sur *Conteneur*, et le champ **Statut du voyage** est défini sur *Marchandises en transit*. Dans ce cas, lorsqu’une commande termine l’étape spécifiée, le champ **Statut du voyage** du conteneur d’expédition sera mis à jour sur *Marchandises en transit*.

Les mises à jour de statut fournissent le statut d’un voyage tout au long des lignes de voyage et des lignes de commande fournisseur associées à ce voyage. Au fur et à mesure qu’un voyage passe du port, du trajet et des douanes à l’entrepôt de destination, le champ **Statut du voyage** de l’enregistrement de voyage fournit une vue rapide de l’étape à laquelle les articles se trouvent.

Pour ajouter une règle de mise à jour du statut au centre de contrôle de suivi, procédez comme suit.

1. Utilisez l’une des procédures suivantes :

    - Accédez à **Coût au débarquement \> Configuration de voyage à plusieurs étapes \> Étapes**. Sélectionnez l’étape pour laquelle vous souhaitez configurer une mise à jour de statut, puis, dans le volet Actions, sélectionnez **Centre de contrôle de suivi**. Le centre de contrôle de suivi est préchargé avec des informations sur l’étape sélectionnée.
    - Allez à **Coût au débarquement \> Configuration des informations de livraison \> Centre de contrôle de suivi**. Vous devez ensuite sélectionner manuellement une étape de voyage à l’étape 4 de cette procédure.

1. Dans le volet de liste, définissez le champ **Créer un type** sur *Mise à jour du statut*.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Si vous avez démarré à partir du centre de contrôle de suivi à l’étape 1, définissez le champ **Étape** sur l’étape pour laquelle vous souhaitez créer une règle de mise à jour de statut. Si vous avez démarré à la page **Étapes**, le champ **Étape** est prédéfini sur l’étape que vous avez sélectionnée avant d’ouvrir le centre de contrôle de suivi.

    Basé sur la valeur du champ **Étape**, plusieurs champs sont automatiquement définis, comme indiqué ici :

    - **Table source :** *Activités conteneurs*
    - **Champ source :** *Date de fin réelle*
    - **Table cible :** Ce champ est laissé vide.
    - **Champ cible :** Ce champ est laissé vide.

1. Dans le champ **Activité**, sélectionnez l’activité à laquelle votre règle doit s’appliquer.
1. Sur le raccourci **Lignes**, entrez les mises à jour de statut pour chaque zone de coût.

### <a name="blank-type-rules"></a>Règles de type vide

Vous utilisez des enregistrements qui ont une valeur **Créer un type** de *Vierge* pour remplacer ou entrer une valeur de champ, en fonction des données d’un autre champ. Un champ de Coût au débarquement écrasera les données dans d’autres domaines de Microsoft Dynamics 365 Supply Chain Management, en fonction des règles définies dans le centre de contrôle Suivi.

1. Allez à **Coût au débarquement \> Configuration des informations de livraison \> Centre de contrôle de suivi**.
1. Dans le volet de liste, définissez le champ **Créer un type** sur *Vierge*.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Définissez les valeurs source et de destination, les critères de correspondance, l’action de copie et d’autres paramètres pertinents, selon les besoins de votre règle.

### <a name="required-tracking-control-setup"></a>Configuration de contrôle de suivi requise

Pour chaque modèle de trajet, deux enregistrements doivent être configurés dans le centre de contrôle de suivi. Ces deux enregistrements ont une valeur **Créer un type** de *Vierge* et sont utilisés dans toutes les mises en œuvre de coût au débarquement. Ils aident à garantir que la date d’achat confirmée et les dates prévues des marchandises en transit sont mises à jour pour les voyages et sur les lignes de commande fournisseur associées de la manière prévue.

Le premier enregistrement est requis pour mettre à jour les lignes d’achat. Il doit avoir les paramètres suivants :

- **Table source :** *Activités conteneurs*
- **Champ source :** *Date de fin estimée*
- **Table cible :** *Lignes d’achat*
- **Champ cible :** *Confirmé ou date de livraison*

Le deuxième enregistrement est nécessaire pour mettre à jour les marchandises dans les transactions de transit. Il doit avoir les paramètres suivants :

- **Table source :** *Activités conteneurs*
- **Champ source :** *Date de fin estimée*
- **Table cible :** *Ordre de marchandises en transit*
- **Champ cible :** *Date prévue*
