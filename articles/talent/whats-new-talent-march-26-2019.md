---
title: Nouveautés ou modifications dans Dynamics 365 Talent (26 mars 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-26
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d4b59183116784f44f45fddacdfa4aa954383ecd
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023882"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-26-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (26 mars 2019)

[!include [banner](includes/banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

### <a name="enhancements-to-interview-scheduling"></a>Améliorations de la programmation des entretiens
Les améliorations suivantes sont disponibles dans la programmation des entretiens.

- Les recruteurs ou les responsables du recrutement peuvent désormais déclencher un rappel pour qu'un intervieweur envoie ses commentaires. Le modèle d'e-mail associé au rappel est configurable également.
- Lors du partage du récapitulatif d'entretien avec le candidat, le programmateur de l'entretien peut choisir de masquer les noms des interviewers et aussi de masquer des lignes de la vue de synthèse de l'entretien.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

### <a name="embedded-images-in-activities"></a>Images intégrées dans les activités
Vous pouvez désormais inclure des images directement dans les activités. Outre pouvoir copier et coller des images du Web, vous pouvez charger les images à partir de votre système de fichiers local. La taille de l'image est limitée à 1 Mo. Si l'image est trop grande, redimensionnez-la et tentez de la charger à nouveau.

[![Mise en correspondance](./media/embedimages.png)](./media/embedimages.png)

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR
**Version 8.1.2210**

### <a name="custom-field-support-available-for-select-entities-in-common-data-service"></a>Prise en charge de champs personnalisés pour certaines entités dans Common Data Service 

Les entités Common Data Service suivantes prennent maintenant en charge les champs client créés dans Talent :

- Collaborateur
- Origine ethnique
- Statut de vétéran
- Code langue
- Mission
- Type de poste
- Fonction du poste
- Poste
- Type de poste
 
### <a name="employment-history-not-displayed-chronologically"></a>L'historique d'emploi ne s'affiche pas dans l'ordre chronologique
Avec cette modification, la page Historique d'emploi affiche les enregistrements d'emploi dans l'ordre chronologique, indépendamment de la société. Vous pouvez également utiliser des options de tri pour trier par entreprise.

### <a name="fixed-compensation-plans-dont-appear-when-restricting-user-by-company-in-security"></a>Les régimes de rémunération fixe ne s'affichent pas lorsque l'utilisateur est renseigné par entreprise dans les options de sécurité.
Dans cette version, les régimes de rémunération fixe s'affichent désormais lorsque les utilisateurs sont limités par entreprise. Tous les paramètres de sécurité sont respectés, et les régimes fixes s'affichent pour les sociétés auxquelles l'utilisateur est autorisé à accéder. 

### <a name="cant-delete-job-records-using-open-in-excel-option-in-talent"></a>Impossible de supprimer des offres d'emploi en utilisant l'option Ouvrir dans Excel dans Talent
Avec cette version, vous pouvez désormais supprimer des enregistrements d'emploi à l'aide de l'option **Ouvrir dans Excel** dans Talent.

### <a name="upgrade-to-common-data-service"></a>Effectuez une mise à niveau vers Common Data Service.
Les dates butoirs pour la mise à niveau vers Common Data Service arrivent à grands pas. Connectez-vous au centre d'administration de PowerApps pour définir si votre base de données doit être mise à niveau. Pour en savoir plus sur les dates butoirs et les étapes indispensables pour la mise à niveau, voir [Mise à niveau vers Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="in-preview"></a>En mode aperçu

Pour plus d'informations sur les fonctions d'aperçu, voir [Accéder aux fonctions d'aperçu de Talent](./access-preview-feature.md).

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Autoriser les codes motif à être spécifiés sur les types de départ
Les organisations peuvent avoir besoin d'informations supplémentaire sur les demandes de congé. Pour obtenir cette information, les employés doivent inclure un code motif dans leurs demandes de congé. Avec cette version, vous pouvez désormais spécifier les codes motif associés à un type donné de départ et permettre aux employés de sélectionner un code motif pour leurs demandes de congé.

### <a name="configure-reason-codes-to-be-required-when-submitting-time-off-for-certain-leave-types"></a>Configuration des codes motif à exiger lors de l'envoi de congé pour certains types d'absence
Les organisations peuvent exiger la définition de codes motif pour certains types d'absence lorsque les employés envoient une demande de congé. Cela peut être dû à des exigences réglementaires du pays ou de la région, ou à une stratégie d'entreprise. Cette version offre aux RH la possibilité de choisir les types d'absence qui nécessitent un code motif. Cette option est appliquée lorsque les employés envoient une demande de congé où l'absence nécessite un code motif.

## <a name="coming-soon"></a>Prochainement

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Sécurité avancée de la rémunération (fixe et variable)
Nombreuses sont les organisations où les responsables des avantages et de la rémunération ne peuvent accéder qu'à certains enregistrements de rémunération. Ces enregistrements peuvent concerner des cadres ou des employés régionaux. Cette modification permet aux RH de gérer et de tenir à jour les plans de rémunération pour différents groupes d'employés au sein de l'organisation. Vous pouvez affecter des rôles de sécurité aux plans fixes et variables. Ces rôles déterminent l'accès aux plans et aux données des employés relatives aux plans, comme les enregistrements propres aux salaires ou aux primes. Seuls les rôles disposant de l'accès peuvent traiter la rémunération de ces employés.

###  <a name="email-support-for-alerts"></a>Prise en charge des alertes par e-mail
Dans Platform Update 25 pour Finance and Operations, les utilisateurs peuvent créer des règles d'alerte qui diffusent automatiquement des notifications par e-mail aux contacts lorsque des notifications sont déclenchées par un événement. 

### <a name="duplicate-employee-checks-user-interface-changes"></a>Vérification d'employé en double : modifications de l'interface utilisateur
Avec cette modification, les doublons sont détectés au moment de renseigner les champs de nom. Un champ de statut affiche le nombre de doublons trouvés. Vous pouvez sélectionner le lien fourni pour ouvrir une nouvelle page pour évaluer s'il convient d'utiliser la correspondance détectée. Pour éviter d'interrompre la saisie des données, l'écran des doublons ne s'ouvre pas automatiquement.
