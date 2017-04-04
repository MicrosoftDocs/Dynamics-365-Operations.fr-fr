---
title: "Configuration des paramètres de RH dans les entités juridiques"
description: "Vous devez définir des paramètres partagés pour les enregistrements communs à des sociétés, tels que les Enregistrements de poste. Cet article explique comment définir des paramètres de Ressources humaines communs à des entités juridiques."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmSharedParameters
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9397e84f03ee5b340fa2aa0a64e582fc0078526e
ms.openlocfilehash: 5df6079605d2d8d320c38d302e8e5e2cba51a3f1
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-hr-parameters-across-legal-entities"></a>Configuration des paramètres de RH dans les entités juridiques

Vous devez définir des paramètres partagés pour les enregistrements communs à des sociétés, tels que les Enregistrements de poste. Cet article explique comment définir des paramètres de Ressources humaines communs à des entités juridiques.

Certains types d'enregistrements, tels que les enregistrements de poste, sont partagés entre des sociétés. Pour ces enregistrements, vous devez définir des paramètres partagés. Par exemple, vous utilisez la page **Paramètres partagés de ressources humaines** pour définir les paramètres de ressources humaines dans les entités juridiques. 

Sur la page **Paramètres partagés de ressources humaines**, les paramètres sont regroupés en zones, selon leur fonctionnalité. 

Sous l'onglet **Identification**, vous devez sélectionner les types d'identifications qui représentent les numéros d'identification répertoriés sur la page. Vous devez paramétrer des types d'identification pour pouvoir entrer des informations d'identification pour les travailleurs. Les informations sur le numéro de sécurité sociale, le numéro d'identité national, l'ID étranger, et le code ID personnel sont tenues à jour sur la page **Type d'identification**. Pour définir un type d'identification ou revoir la liste d'exister des types, cliquez sur ** Ressources humaines ** &gt; ** paramétrage ** &gt; ** types d'identifications **. Vous pouvez entrer un code et une description simples. 

Sous l'onglet **Souches de numéros**, vous pouvez sélectionner les souches de numéros utilisées pour les enregistrements suivants : Numéro personnel, Poste, ID demande de l'utilisateur, Document I-9, Candidat, Discussion, ID avantage et Action d'un membre du personnel (si ce type d'enregistrement est activé). Pour tenir à jour les références et codes des souches de numéros, utilisez la page de liste **Souches de numéros**. Pour rechercher cette page, utilisez la fonctionnalité de recherche de page. 

Sous l'onglet **Postes**, indiquez si de nouveaux postes sont disponibles pour l'affectation par défaut :

-   ** Toujours ** – Vous pouvez affecter des travailleurs à de nouveaux postes lorsque les postes sont créés. Lorsque des postes sont créés, ** disponible pour l'affectation ** la date et l'heure sur ** général ** l'onglet ** poste ** de la page sont automatiquement définies sur les date et heure de création.
-   **Jamais** – Vous ne pouvez pas affecter de collaborateurs à de nouveaux postes lorsque des postes sont créés. Si vous sélectionnez cette option, vous devez ouvrir la page **Poste** pour chaque nouveau poste lorsqu'il devient disponible, puis sous l'onglet **Général**, entrez la date **Disponible pour affectation **afin d'activer l'affectation du collaborateur.


<a name="see-also"></a>Voir également :
--------

[Paramètres spécifiques de temps de paramétrage] (setup-company-specific-hr-parameters.md)


