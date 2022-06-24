---
title: Configuration des paramètres partagés
description: Cet article explique comment définir des paramètres de Ressources humaines communs à des entités juridiques.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c0d8dbca302d90cc402feb4715a6fcc2b935d8b1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906180"
---
# <a name="configure-shared-parameters"></a>Configuration des paramètres partagés

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous devez définir des paramètres partagés pour les enregistrements communs à des sociétés, tels que les enregistrements **Poste**. Cet article explique comment définir des paramètres de Ressources humaines communs à des entités juridiques.

Certains types d’enregistrements, tels que les enregistrements **Poste**, sont partagés entre des sociétés. Pour ces enregistrements, vous devez définir des paramètres partagés. Par exemple, la page **Paramètres partagés de ressources humaines** permet de définir les paramètres de ressources humaines dans les entités juridiques. 

Sur la page **Paramètres partagés de ressources humaines**, les paramètres sont regroupés en zones, selon leur fonctionnalité. 

### <a name="settings"></a>Paramètres
Sous l’onglet **Identification**, vous devez sélectionner les types d’identifications qui représentent les numéros d’identification répertoriés sur la page. Vous devez paramétrer des types d’identification pour pouvoir entrer des informations d’identification pour les travailleurs. Les informations sur le numéro de sécurité sociale, le numéro d’identité national, l’ID étranger, et le code ID personnel sont tenues à jour sur la page **Type d’identification**. Pour définir un nouveau type d’identification ou consulter la liste des types existants, accédez à **Gestion du personnel** &gt; **Liens** &gt; **Paramétrage** &gt; **Types d’identification**. Vous pouvez entrer un code et une description simples. 

Sous l’onglet **Souches de numéros**, vous pouvez sélectionner les souches de numéros utilisées pour les enregistrements suivants : **Numéro personnel**, **Poste**, **ID demande de l’utilisateur**, **Document I-9**, **Candidat**, **Discussion**, **ID avantage** et **Action d’un membre du personnel** (si ce type d’enregistrement est activé). Pour tenir à jour les références et codes des souches de numéros, utilisez la page de liste **Souches de numéros**. Pour rechercher cette page, utilisez la fonctionnalité de recherche de page. 

Sous l’onglet **Postes**, indiquez si de nouveaux postes sont disponibles pour l’affectation par défaut :

- **Toujours** – Vous ne pouvez pas affecter de collaborateurs à de nouveaux postes lorsque des postes sont créés. Lorsque des postes sont créés, la date et l’heure **Disponible pour affectation** de l’onglet **Général** de la page **Poste** sont automatiquement définis à la date et à l’heure de création.
- **Jamais** – Vous ne pouvez pas affecter de collaborateurs à de nouveaux postes lorsque des postes sont créés. Si vous sélectionnez cette option, vous devez ouvrir la page **Poste** pour chaque nouveau poste au fur et à mesure qu’il devient disponible. Ensuite, sur l’onglet **Général**, entrez la date **Disponible pour affectation** afin d’activer l’affectation des employés.

Sur l’onglet **Accès avancé**, vous pouvez restreindre l’accès à certaines informations ou certains liens :

- **Restreindre l’accès aux informations sur les collaborateurs** – Sélectionnez cette fonctionnalité si les utilisateurs doivent pouvoir afficher les informations sur les employés uniquement pour les entités juridiques auxquelles ils ont accès et pour les employés qui travaillent dans ces entités juridiques.

    Une fois cette fonctionnalité sélectionnée, procéder comme suit pour définir les autorisations appropriées pour chaque utilisateur dont la vue doit être restreinte :

    1. Sur la page **Utilisateurs**, sélectionnez un utilisateur.
    1. Sélectionnez un rôle pour l’utilisateur. L’option **Attribuer des organisations** devient disponible.
    1. Sélectionnez **Affecter des organisations**.
    1. Sur la nouvelle page, sélectionnez **Accorder l’accès à des organisations spécifiques individuellement**, puis sélectionnez les organisations auxquelles l’utilisateur doit avoir accès.
    1. Répétez les étapes 2 à 4 pour chaque rôle supplémentaire de l’utilisateur, y compris le rôle d’utilisateur système.

    > [!NOTE]
    > Les sociétés auxquelles un utilisateur a accès doivent correspondre à tous les rôles de l’utilisateur.

- **Activer la vue de la rémunération inter-sociétés** – La rémunération des salariés est attribuée par entité légale d’emploi. Parfois, un collaborateur peut être employé dans plusieurs entités juridiques en même temps. Lorsque cette fonctionnalité est sélectionnée, la rémunération de chaque entité juridique apparaîtra dans le **Libre service employé** et le **Libre service gestionnaire** sans que vous ayez à modifier les entités juridiques. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
