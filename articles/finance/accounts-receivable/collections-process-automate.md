---
title: Automatisation du processus de recouvrement
description: Cette rubrique décrit le processus de configuration des stratégies de processus de recouvrement qui identifient automatiquement les factures client qui nécessitent un rappel par e-mail, une activité de recouvrement ou une lettre de recouvrement à envoyer au client.
author: JodiChristiansen
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 59db852024faf457db7ac145b67619b31555aaf2
ms.sourcegitcommit: 3f6cbf4fcbe0458b1515c98a1276b5d875c7eda7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2021
ms.locfileid: "7486867"
---
# <a name="collections-process-automation"></a>Automatisation du processus de recouvrements

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le processus de configuration des stratégies de processus de recouvrement qui identifient automatiquement les factures client qui nécessitent un rappel par e-mail, une activité de recouvrement (comme un appel téléphonique) ou une lettre de recouvrement à envoyer au client. 

Les organisations passent souvent beaucoup de temps à effectuer des recherches dans des états de solde chronologiques, des comptes client et des factures ouvertes pour savoir quels clients doivent être contactés au sujet d’une facture ouverte ou d’un solde de compte. Cette recherche réduit le temps passé par un agent de recouvrement à communiquer avec les clients pour recouvrer les soldes en souffrance ou résoudre les litiges relatifs aux factures. L’automatisation du processus de recouvrement vous permet de définir une approche stratégique de votre processus de recouvrement. Cela vous aide à appliquer les activités de recouvrement de manière cohérente en fournissant des rappels par e-mail personnalisés ou un processus programmé pour l’envoi de lettres de recouvrement. 

## <a name="collections-process-setup"></a>Configuration du processus de recouvrement
Vous pouvez utiliser la page **Configuration du processus de recouvrement** (**Crédits et recouvrements > Configuration > Configuration du processus de recouvrement**) pour créer un processus de recouvrement automatisé qui planifiera des activités, enverra des e-mails et créera et publiera des lettres de recouvrement de clients. Les étapes du processus sont basées sur la facture ouverte principale ou la plus ancienne. Chaque étape utilise cette facture pour déterminer quelle communication ou activité doit avoir lieu avec un client spécifique.  

Les équipes de recouvrement envoient généralement un préavis relatif à chaque facture impayée afin qu’un client soit averti lorsque la facture est sur le point d’être échue. La sélection **Prérelance** peut être définie pour permettre d’appliquer une étape de chaque hiérarchie de processus pour chaque facture lorsque l’échéance des factures atteint cette étape.

### <a name="process-hierarchy"></a>Hiérarchie des processus
Chaque regroupement de clients ne peut être affecté qu’à une seule hiérarchie de processus. Le rang hiérarchique de cette étape identifie le processus qui aura la priorité si un client est inclus dans plus d’un pool auquel une hiérarchie de processus est attribuée. L’ID de pool détermine quels clients seront affectés au processus. Chaque hiérarchie configurée peut être affectée uniquement à une automatisation de processus.

Les jours calmes sont utilisés pour s’assurer qu’un client n’est pas contacté trop fréquemment par le processus automatisé. Par exemple, si les jours calmes sont définis sur deux, un client ne sera pas contacté par le processus automatisé pendant au moins deux jours, même si la facture principale d’origine a été réglée en totalité. 

Pour exclure les clients de l’automatisation du processus si le solde chronologique client ou le montant de la facture est inférieur à une valeur définie, sélectionnez **Solde chronologique client inférieur à** ou **Montant de la facture inférieur à** dans le champ **Exclure du processus** et entrez la valeur du montant.

Cochez l’option **Utiliser la prédiction** pour créer des activités de recouvrement à l’aide des prévisions de paiement du client. Les activités créées utiliseront le modèle d’activité de **Prédictions de paiement** sur la page **Paramètres de la comptabilité client**, onglet **Automatisation du processus de recouvrement**. 

### <a name="process-details"></a>Détails du processus
Cliquez sur **Nouveau** pour ajouter un nouveau détail de processus à la hiérarchie. Le champ **Description** est utilisé pour identifier le but ou le nom de l’étape dans la hiérarchie. Sélectionnez le **Type d’action** pour définir l’étape qui va créer une activité, envoyer un e-mail ou créer une lettre de recouvrement. 

- Le **Document commercial** définit le modèle utilisé pour créer le type d’action. Ce document peut être un modèle d’activité, un modèle d’e-mail ou une lettre de recouvrement envoyé(e) à chaque client. L’automatisation du processus de recouvrement crée uniquement des lettres de recouvrement par client, quelle que soit la manière dont les autres paramètres de recouvrement sont définis.
- **Lorsque** définit l’étape de processus qui se produira avant ou après la date d’échéance de la facture principale (la plus ancienne), et est utilisée avec le numéro affiché dans la colonne **Jours par rapport à la date d’échéance de la facture**. 
- Cochez l’option **Pré-relance** pour créer une action pour chaque facture en une seule étape dans une hiérarchie de processus. Les actions de pré-relance sont généralement un préavis relatif aux factures impayées afin qu’un client soit averti lorsqu’une facture est sur le point d’être échue. La pré-relance ne peut être marquée que pour une activité par hiérarchie. Lorsque vous sélectionnez un type d’action par e-mail, le destinataire sera utilisé pour définir si le message électronique est envoyé à un client, groupe de vente ou agent de recouvrement. 
- La valeur dans le champ **Contact à des fins commerciales** détermine alors quel contact du compte de ce client recevra la communication.

### <a name="business-document-details"></a>Détails des documents commerciaux
Les détails du document commercial varient en fonction du type d’action sélectionné dans les détails du processus. Lorsque le type d’action est une activité, les détails du modèle d’activité seront affichés. Ces détails incluent le nom du modèle d’activité, le type d’activité qui sera créé, le but de l’activité, le nombre de jours prévus pour terminer l’activité et les détails de l’activité. Cette activité sera ensuite liée à la facture principale qui informe le destinataire de l’action nécessaire pour terminer l’activité.

Si le type d’action est un e-mail dans les détails du processus, cette section contiendra deux raccourcis. Le premier est utilisé pour définir l’ID du modèle, la description de l’e-mail, la langue par défaut, le nom d’utilisateur qui sera affecté aux e-mails envoyés automatiquement et l’adresse e-mail de l’expéditeur associée. Le second permettra de créer le corps de l’e-mail après les valeurs des champs **Langue** et **Objet** enregistrées en sélectionnant **Modifier**. Cela ouvrira une fenêtre permettant de charger du contenu HTML. 

> [!Note]
> Vous pouvez enregistrer un message électronique Outlook contenant le corps du texte de la communication au format HTML. Vous pouvez ensuite télécharger le contenu du message pour mettre en œuvre le modèle. <br> <br> Si le type d’action de lettre de collecte est sélectionné, il n’y aura pas de section de détail de document commercial sur la page de configuration.

Utilisez le bouton **Historique du processus de recouvrement** pour afficher l’historique récent de la hiérarchie de processus sélectionnée. 

Cliquez sur l’action **Affectation du processus de recouvrement** pour afficher les clients affectés à un processus de recouvrement. Utilisez **Afficher un aperçu de l’affectation de client** pour afficher la hiérarchie à laquelle un client spécifique est affecté. Utilisez **Afficher un aperçu de l’affectation de processus** pour prévisualiser les clients qui seront affectés à une hiérarchie lors de son exécution. Cliquez sur **Affectation manuelle** pour afficher les clients qui ont été affectés manuellement à un processus ou sélectionnez les clients à affecter à un processus.

Cliquez sur l’action **Traiter la simulation** pour afficher les actions qui seront créées si l’automatisation de processus sélectionnée est exécutée à ce moment. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
