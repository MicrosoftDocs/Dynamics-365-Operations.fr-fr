---
title: FAQ sur l'intégration Dynamics 365 for Talent à Dynamics 365 for Finance and Operations
description: Cette rubrique explique quelles données sont synchronisées dans le cadre d'une intégration de Talent et de Finance and Operations.
author: negudava
manager: AnnBe
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2018-12-31
ms.dyn365.ops.version: Talent
ms.openlocfilehash: aea025bc4898d6399e82030cf1f52b21949e014f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304399"
---
# <a name="dynamics-365-for-talent-to-dynamics-365-for-finance-and-operations-integration-faq"></a>FAQ sur l'intégration Dynamics 365 for Talent à Dynamics 365 for Finance and Operations

[!include [banner](includes/banner.md)]

Cette rubrique répond aux questions fréquentes associées aux données synchronisées lorsque Dynamics 365 for Talent est intégré à Dynamics 365 for Finance and Operations.

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a>Toutes les données sont-elles synchronisées ou seulement certaines entités de données ?

Avec Core Human Resources (HR), un sous-ensemble des données est synchronisé. Pour obtenir une liste de toutes les entités, voir [Intégration de Dynamics 365 for Talent à Dynamics 365 for Finance and Operations](talent-financeandoperations-integration.md).

Pour Attract et Onboard, toutes les données sont propres à Common Data Service (CDS) pour les applications.

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a>Puis-je créer une mise en correspondance sans utiliser les modèles ?

Les modèles sont le point de départ. Vous pouvez créer votre propre modèle, mais un modèle est toujours requis lors de la création d'un projet d'intégration. Pour en savoir plus sur l'intégrateur des données, les modèles et les projets, voir [Intégrer les données dans Common Data Service pour les applications](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).

## <a name="can-i-map-financial-dimensions-to-transfer-between-talent-and-finance-and-operations"></a>Puis-je mettre en correspondance les dimensions financières à transférer entre Talent et Finance and Operations ?

Les dimensions financières ne sont actuellement pas dans CDS pour les applications et, par conséquent, ne font pas partie du modèle par défaut. Cette entité est prévue, mais actuellement, aucun calendrier de publication n'est disponible.

Pour les données résidant dans Finance and Operations, mais qui n'existent pas dans Talent, associez les deux systèmes en utilisant **Configurer les liens** dans Talent. Pour en savoir plus sur la manière de configurer les liens entre Talent et Finance and Operations, voir [Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (31 octobre 2018)](whats-new-talent-october-31.md).

![](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-and-operations-why"></a>Parfois, dans le cadre de l'importation d'employés, ces derniers deviennent inactifs dans Finance and Operations. Pourquoi ?

Vous pouvez obtenir cette erreur si les employés ne disposent pas d'un enregistrement des détails d'emploi actif dans Talent. Pour résoudre ce problème, accédez à **Gestion du personnel \> Employés \> Historique des emplois \> Gestionnaire de date**, puis vérifiez qu'il existe bien un enregistrement des détails d'emploi actif.

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a>Si je choisis de ne mettre en correspondance qu'un sous-ensemble de champs, les modifications apportées à des champs non mis en correspondance déclencheront-elles une synchronisation ?

La synchronisation des données respecte le programme d'exécution. L'intégration sélectionne un enregistrement si un des champs de l'enregistrement change, peu importe si le champ fait partie de la mise en correspondance d'intégration.

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a>Comment puis-je envoyer les changements uniquement aux employés actifs et non pas à ceux dont le contrat est terminé ?

En utilisant « Requête avancée », vous pouvez filtrer et reconstituer les données source avant de les transmettre à la cible.

![](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-and-operations-for-a-specific-entity"></a>Puis-je préciser quels champs à envoyer à Finance and Operations pour une entité spécifique ?

Les champs peuvent être ajoutés ou supprimés depuis la tâche d'intégration. Les champs de données qui existent sur l'entité CDS pour les applications (CDS 2.0) ne sont pas tous renseignés depuis Core HR.
Des informations supplémentaires peuvent être renseignées via PowerApps.

![](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-talent-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a>Je paramètre l'intégration en tant que traitement par lots, mais Talent a perdu la connexion au système cible. Comment puis-je envoyer le même jeu de modifications au système cible ?

Aucune configuration spéciale n'est requise pour le traitement des exceptions. L'intégrateur des données détecte automatiquement les erreurs et les signale à la source et à la cible, autorisant de nouvelles tentatives manuelles. Toutefois, il n'autorise pas la correction manuelle des données. Si les mises à jour des données sont nécessaires, elles doivent survenir à la source ou à la cible.

## <a name="can-i-set-up-bi-directional-integration"></a>Puis-je définir une intégration bi-directionnelle ?

Non, l'intégration est actuellement unidirectionnelle (Talent vers Finance and Operations). Un modèle par défaut est disponible pour envoyer les données depuis Talent vers Finance and Operations.

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a>Puis-je autoriser la suppression d'enregistrements dans le cadre de mon intégration ?

Non, l'intégrateur des données ne capture pas les enregistrements supprimés pour le transfert des données. Seules la création des données et les mises à jour (UPSERT) sont actuellement incluses.

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a>Puis-je ré-exécuter l'exécution erronée ? Si oui, cela enverra-t-il un fichier complet ou uniquement les modifications ?

La première exécution de l'intégrateur des données est toujours une exécution complète. Les exécutions suivantes sont basées sur le suivi des modifications. En cas d'erreur d'exécution, les enregistrements dans le cadre de la série sont extraits et les modifications les plus récentes effectuées depuis CDS sont envoyées.

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a>Lorsque j'enregistre le projet, j'obtiens l'erreur suivante : « Le projet rencontre des erreurs de mise en correspondance. » Que puis-je faire ?

Vérifiez la configuration de vos clés d'intégration, apportez toutes les modifications souhaitées à la configuration, puis actualisez les entités dans le projet.

Lorsque le modèle par défaut est utilisé, les clés d'intégration sont automatiquement importées. Ce problème peut survenir lorsque de nouvelles tâches sont ajoutées au modèle existant.

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a>Si je dispose d'un nombre N d'entités juridiques dans lesquelles des employés ont des emplois, dois-je créer une mise en correspondance pour chacune d'entre elles ?

Oui, pour chaque entité juridique dans Finance and Operations, vous aurez besoin d'un projet d'intégration distinct dans l'intégration des données.

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a>Je dois transférer les données qui ne font pas partie du modèle par défaut fourni par Microsoft. Puis-je le faire ?

Oui, des champs peuvent être ajoutés ou supprimés depuis le modèle existant. Le modèle peut être modifié pour inclure des données supplémentaires depuis d'autres entités CDS pour les applications. L'entité doit être dans CDS pour les applications afin d'être incluse dans le modèle. 

## <a name="i-just-created-new-finance-and-operations-and-talent-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a>Je viens de créer de nouveaux environnements Finance and Operations et Talent, et j'obtiens l'erreur « La valeur des données enfreint l'intégrité des contraintes. » Pourquoi ?

Parmi les causes de cette erreur peuvent figurer :

- Le transfert des données a généré une extraction des doublons au niveau des enregistrements à la source (CDS).

- Le transfert des données a des valeurs nulles pour les champs requis dans Finance and Operations. Vérifiez les données qui se trouvent dans CDS et qui répondent aux exigences de Finance and Operations.

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a>S'il existe des erreurs d'exécution et si l'ID d'employé ne s'est pas synchronisé, comment trouver la tâche de l'historique qui affiche l'enregistrement d'employé échoué ?

L'intégrateur des données créera plusieurs projets dans Finance and Operations. La relation entre la tâche de l'intégrateur des données et le projet Finance and Operations est une relation de type une-à-une.

Retracez le temps d'exécution depuis l'historique d'exécution de l'intégrateur des données et recherchez le projet Indice -1 dans Finance and Operations. Si le numéro de tâche est 9 dans l'intégrateur des données, l'indice dans Finance and Operations est 8.

1. Capturez l'indice de tâche depuis l'intégrateur de données (dans cet exemple, il s'agit de « 9 »).

![Capturer l'indice de tâche depuis l'intégrateur de données](media/CaptureTaskIndex.png)

2. Retracez le temps d'exécution du projet.

![Retracer le temps d'exécution du projet](media/CaptureTimeOfExecution.png)

3. Dans Finance and Operations, identifiez Indice -1. Dans cet exemple, le projet avec suffixe « 8 » et le temps d'exécution du projet Indice « 0 » correspond au temps d'exécution à l'étape 2.

![Identifier l'indice](media/IdentifyIndex.png)

## <a name="after-integrating-talent-and-finance-and-operations-i-dont-see-my-talent-data-in-finance-and-operations-what-do-i-do"></a>Après l'intégration de Talent and Finance and Operations, je ne vois pas mes données Talent dans Finance and Operations. Que puis-je faire ?

L'intégration à Finance and Operations est un processus en deux étapes. Tout d'abord, vérifiez que les données Talent sont mises à jour et disponibles dans CDS. Il s'agit d'une synchronisation quasiment en temps réel et cela peut être vérifié dans PowerApps en observant les données dans les entités des données.

![Données dans CDS](media/DataInCDS.png)

Si les données ne s'affichent pas comme prévu dans CDS, vérifiez que l'entité est prise en charge dans l'intégration. Pour inclure des données supplémentaires dans CDS, un modification sera requise du côté de Microsoft.

Si l'entité est prise en charge et si les données sont disponibles dans CDS, vérifiez que la mise en correspondance est correcte dans l'intégrateur des données. Si la mise en correspondance de l'intégrateur semble appropriée, vérifiez que l'exécution des tâches de gestion des données est un succès. Des erreurs peuvent survenir pendant l'exécution des traitements par lots. Pour plus d'informations sur la gestion des données, voir [Gestion des données](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json).

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-and-operations-what-should-i-do"></a>Les adresses pour mes employés sont incorrectes après leur importation dans Finance and Operations. Que dois-je faire ?

La souche de numéros pour **ID emplacement** utilise le même modèle dans Talent et Finance and Operations. La souche de numéros doit être unique des deux côtés afin qu'il n'y ait pas de conflit d'adresses lors de l'intégration des données de CDS vers Finance and Operations.

Pendant la mise en place de Talent, vérifiez que les souches de numéros ne sont pas identiques dans Talent et Finance and Operations. Vérifiez que toutes les souches de numéros ne sont pas identiques lorsque les données doivent être conservées dans les deux systèmes.

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a>Lors de la création de mon ensemble de connexionx, la connexion n'apparaît pas dans la liste déroulante Connexion. Que puis-je faire ?

Veillez, lors de la création de vos connexions, à choisir Dynamics 365 for Finance and Operations (actuellement en aperçu) et Common Data Service.

## <a name="when-syncing-employments-i-get-the-errors-companyinfofk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a>Lors de la synchronisation des emplois, j'obtiens les erreurs « CompanyInfo_FK doesn’t exist » ou « The value '12/31/2154 11:59:59 pm » dans le champ « Date de fin de l'emploi » reste introuvable dans le tableau « Emploi » associé. Que dois-je faire ?

Veillez à bien mettre en correspondance les entités juridiques appropriées. La synchronisation des entités juridiques ne fait pas partie du modèle par défaut. Aussi, il est prévu que chaque entité juridique présente dans Talent et CDS soit également présente dans Finance and Operations.
En outre, veillez à sélectionner les bonnes entités juridiques pour le jeu de connexions associé.

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-and-operations-appears-to-be-empty-what-should-i-do"></a>Après la configuration de mon projet, la mise en correspondance des champs pour Finance and Operations semble vide. Que dois-je faire ?

Actualisez les entités des données dans Finance and Operations en accédant à **Gestion des données \> Paramètres de l'environnement \> Paramètres d'entité \> Actualiser la liste des entités.** Quelques minutes devraient s'avérer nécessaires avant de pouvoir voir ces mises en correspondance. Ce problème survient lorsque des projets sont créés.

![Mise en correspondance de champs manquante](media/MissingFieldMapping.png)

## <a name="additional-resources"></a>Ressources supplémentaires

- Intégrateur des données : 

  - [Intégration des données dans Common Data Service pour les applications](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator)

  - [Gestion et dépannage des erreurs de l'intégrateur des données](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator-error-management)

  - [Répondre aux demandes DSR pour les journaux générés par le système dans PowerApps, Microsoft Flow et Common Data Service pour les applications](https://docs.microsoft.com/en-us/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- Gestion des données :

  - [Gestion des données](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json)