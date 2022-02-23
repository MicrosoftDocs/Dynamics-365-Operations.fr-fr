---
title: Planifier la gestion du pointage dans Retail
description: Cette rubrique décrit les scénarios pris en charge pour la Gestion du pointage de vente au détail dans Dynamics 365 Commerce.
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: cca5e3232450e75f931a621b278c134129fc745c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412386"
---
# <a name="time-and-attendance-management-in-retail"></a>Planifier la gestion du pointage dans Retail

[!include [banner](includes/banner.md)]

Cette rubrique décrit les scénarios pris en charge pour la Gestion du pointage de vente au détail dans Dynamics 365 Commerce.

## <a name="manage-worker-setup-and-scheduling"></a>Gérer la configuration et la planification des collaborateurs

### <a name="initial-configuration"></a>Configuration initiale

- Exécutez l'Assistant Configuration.
- Enregistrez des collaborateurs en tant que collaborateurs qualifiés pour l'enregistrement des heures.

### <a name="plan-worker-schedules"></a>Panifiez des programmes de collaborateur

- Appliquez des profils à l'aide du Planificateur de travail. Pour plus d'informations, voir [Application des profils à l'aide du Planificateur de travail](https://technet.microsoft.com/library/aa551234.aspx).

Pour plus d'informations sur les étapes de configuration, voir [Paramétrage du module Pointage](https://technet.microsoft.com/library/aa496971.aspx).

### <a name="commerce-specific-configuration"></a>Configuration spécifique à Commerce

- Activez un profil de fonctionnalité pour Horloge de pointage, pour les collaborateurs pour lesquels vous souhaitez activer les enregistrements d'heures. Cliquez sur **Profils de fonctionnalité des PDV** &gt; **Fonctions** &gt; **Enregistrement des heures des PDV** &gt; **Activer l'enregistrement des heures**.
- Configurez des groupes d'autorisations de point de vente (PDV) pour activer l'autorisation Afficher les entrées de l'horloge de pointage. Cette autorisation permet à l'utilisateur d'afficher les enregistrements d'horloge de pointage d'autres collaborateurs du magasin (et d'un autre magasin auquel l'utilisateur est associé, via le carnet d'adresses). Vous souhaitez peut-être activer cette autorisation pour un rôle de responsable mais pas pour un rôle de caissier. Cliquez sur **Groupes d'autorisations des PDV** &gt; **Afficher les entrées de l'horloge**.

## <a name="register-time"></a>Heure d'enregistrement

### <a name="cashier-and-non-cashier-time-registrations"></a>Enregistrements d'heures du caissier et de collaborateur autre que caissier

- Sur le PDV :

    - Opérations de pointage à l'arrivée :

        - Connectez-vous à une opération sans lien avec le tiroir-caisse ou à une nouvelle équipe de travail.
        - Sélectionnez une opération d'horloge de pointage.
        - Sélectionnez l'opération souhaitée :

            - Pointage à l'arrivée
            - En pause
            - Pause-déjeuner
            - Pointage à la sortie

        <table>
        <thead>
        <tr>
        <th>Statut actuel</th>
        <th>Opérations disponibles</th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td>Pointage à l'arrivée</td>
        <td>
        <ul>
        <li>En pause</li>
        <li>Pause-déjeuner</li>
        <li>Pointage à la sortie</li>
        </ul>
        </td>
        </tr>
        <tr>
        <td>En pause</td>
        <td>Pointage à l'arrivée</td>
        </tr>
        <tr>
        <td>Pause-déjeuner</td>
        <td>Pointage à l'arrivée</td>
        </tr>
        <tr>
        <td>Pointage à la sortie</td>
        <td>Pointage à l'arrivée</td>
        </tr>
        </tbody>
        </table>

        [![États de l'horloge de pointage](./media/timeclockstates.png)](./media/timeclockstates.png)

- Affichez le message de confirmation et validez que la durée d'activité actuelle est correcte.
- Journal :

    - Cliquez sur **Journal** pour afficher l'activité d'horloge de pointage.
    - Utilisez des filtres de durée pour sélectionner des périodes différentes.
    - Si vous travaillez dans plusieurs emplacements de magasin, vous voyez s'afficher vos enregistrements d'heures de tous les magasins dans lesquels vous avez enregistré des heures. Vous pouvez utiliser le filtre de magasin pour afficher les enregistrements d'heures d'un magasin sélectionné.

- Fuseaux horaires différents :

    - Si vous affichez l'heure à partir d'un autre emplacement (pour le journal du caissier, ou en utilisant **Afficher les entrées de l'horloge de pointage** pour un scénario de responsable), et que cet emplacement est dans un fuseau horaire différent, les enregistrements des heures proposés sont convertis dans votre fuseau horaire local. Par exemple, vous êtes responsable de deux magasins, l'un en Arizona et l'autre dans le Nevada. Un caissier enregistre un pointage à l'arrivée à 9h00 du matin en Arizona. À ce moment, l'heure au Nevada est 8h00 du matin Par conséquent, si vous êtes dans le magasin du Nevada et que vous consultez les enregistrements des heures, l'enregistrement des heures est marqué comme 8h du matin.

## <a name="view-worker-time-registrations"></a>Afficher les enregistrements des heures des collaborateurs

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a>Affichez les enregistrements des heures du collaborateur, et filtrez par magasin ou par type d'activité

Sur le PDV :

- Sélectionnez **Afficher les entrées de l'horloge de pointage**.
- Vous découvrez les activités d'enregistrement de l'horloge de pointage de tous les collaborateurs affectés aux magasins auxquels vous êtes également affecté.
- Vous pouvez utiliser des filtres par type d'activité et magasin pour filtrer les enregistrements des heures.

## <a name="process-and-manage-time-registrations"></a>Traitement et gestion des enregistrements des heures

Un utilisateur de Commerce suit le flux de travail pour calculer, approuver et transférer les enregistrements des heures vers le salaire.

### <a name="primary-operations"></a>Opérations principales

- Calculer
- Approuver
- Soumettre à la paie

### <a name="other-common-operations"></a>Autres opérations courantes

- Pointage à la sortie en masse
- Enregistrer des absences

Pour plus d'informations sur le traitement des enregistrements des heures et des présences, voir [Traitement des enregistrements de pointage](https://technet.microsoft.com/library/aa573180.aspx).
