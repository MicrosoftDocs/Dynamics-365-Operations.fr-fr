---
title: Configuration des paramètres des ressources humaines (RH) dans les entités juridiques
description: Vous devez définir des paramètres partagés pour les enregistrements communs à des sociétés, tels que les Enregistrements de poste. Cet article explique comment définir des paramètres de Ressources humaines communs à des entités juridiques.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmSharedParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: ef269740123e17c204dd6ce244b75615229cbd49
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010635"
---
# <a name="set-up-human-resources-hr-parameters-across-legal-entities"></a>Configuration des paramètres des ressources humaines (RH) dans les entités juridiques

[!include [banner](includes/banner.md)]

Vous devez définir des paramètres partagés pour les enregistrements communs à des sociétés, tels que les Enregistrements de poste. Cet article explique comment définir des paramètres de Ressources humaines communs à des entités juridiques.

Certains types d'enregistrements, tels que les enregistrements de poste, sont partagés entre des sociétés. Pour ces enregistrements, vous devez définir des paramètres partagés. Par exemple, vous utilisez la page **Paramètres partagés de ressources humaines** pour définir les paramètres de ressources humaines dans les entités juridiques. 

Sur la page **Paramètres partagés de ressources humaines**, les paramètres sont regroupés en zones, selon leur fonctionnalité. 

### <a name="previously-released-functionality"></a>Fonctionnalité précédemment lancée
Sous l'onglet **Identification**, vous devez sélectionner les types d'identifications qui représentent les numéros d'identification répertoriés sur la page. Vous devez paramétrer des types d'identification pour pouvoir entrer des informations d'identification pour les travailleurs. Les informations sur le numéro de sécurité sociale, le numéro d'identité national, l'ID étranger, et le code ID personnel sont tenues à jour sur la page **Type d'identification**. Pour définir un nouveau type d'identification ou consulter la liste des types existants, cliquez sur **Gestion du personnel** &gt; **Onglet Liens** &gt; **Paramétrage** &gt; **Types d'identification**. Vous pouvez entrer un code et une description simples. 

### <a name="if-youre-using-dynamics-365-talent"></a>Si vous utilisez Dynamics 365 Talent
Sous l'onglet **Identification**, vous devez sélectionner les types d'identifications qui représentent les numéros d'identification répertoriés sur la page. Vous devez paramétrer des types d'identification pour pouvoir entrer des informations d'identification pour les travailleurs. Les informations sur le numéro de sécurité sociale, le numéro d'identité national, l'ID étranger, et le code ID personnel sont tenues à jour sur la page **Type d'identification**. Pour définir un nouveau type d'identification ou consulter la liste des types existants, cliquez sur **Ressources humaines** &gt; **Paramétrage** &gt; **Types d'identification**. Vous pouvez entrer un code et une description simples. 

Sous l'onglet **Souches de numéros**, vous pouvez sélectionner les souches de numéros utilisées pour les enregistrements suivants : Numéro personnel, Poste, ID demande de l'utilisateur, Document I-9, Candidat, Discussion, ID avantage et Action d'un membre du personnel (si ce type d'enregistrement est activé). Pour tenir à jour les références et codes des souches de numéros, utilisez la page de liste **Souches de numéros**. Pour rechercher cette page, utilisez la fonctionnalité de recherche de page. 

Sous l'onglet **Postes**, indiquez si de nouveaux postes sont disponibles pour l'affectation par défaut :

-   **Toujours** – Vous ne pouvez pas affecter de collaborateurs à de nouveaux postes lorsque des postes sont créés. Lorsque des postes sont créés, la date et l'heure **Disponible pour affectation** de l'onglet **Général** de la page **Poste** sont automatiquement définis à la date et à l'heure de création.
-   **Jamais** – Vous ne pouvez pas affecter de collaborateurs à de nouveaux postes lorsque des postes sont créés. Si vous sélectionnez cette option, vous devez ouvrir la page **Poste** pour chaque nouveau poste lorsqu'il devient disponible, puis sous l'onglet **Général**, entrez la date **Disponible pour affectation** afin d'activer l'affectation du collaborateur.


<a name="additional-resources"></a>Ressources supplémentaires
--------

[Définition des paramètres de RH spécifiques à la société](set-up-company-specific-hr-parameters.md)



