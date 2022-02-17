---
title: Des problèmes de traitement se produisent après l’installation d’une charge de travail d’entrepôt d’unités d’échelle
description: Cette rubrique décrit les problèmes qui peuvent survenir peu de temps après l’installation d’une charge de travail d’entrepôt d’unités d’échelle et donne des conseils pour les résoudre.
author: perlynne
ms.date: 1/13/2022
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningWorkbench, WHSOutboundLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-01-13
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f589ffed61b695f471989ab1dd693f30cd5d5262
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071633"
---
# <a name="processing-issues-occur-after-a-scale-unit-warehouse-workload-is-installed"></a>Des problèmes de traitement se produisent après l’installation d’une charge de travail d’entrepôt d’unités d’échelle

Cette rubrique décrit les problèmes qui peuvent survenir peu de temps après l’installation d’une charge de travail d’entrepôt d’unités d’échelle et donne des conseils pour les résoudre.

## <a name="issue-1-error-after-a-load-is-released-from-a-load-planning-workbench"></a>Problème 1 : erreur après la libération d’un chargement à partir d’un atelier de planification des chargements

### <a name="symptoms-of-issue-1"></a>Symptômes du problème 1

Lorsque vous libérez un chargement depuis la page **Atelier de planification des chargements** ou **Atelier de planification des chargements sortants**, vous recevez un message d’erreur au format suivant :

> Une exception s’est produite lors de la validation du chargement %1 ; le chargement n’a pas pu être libéré.
> 
> MISE À JOUR WHSSHIPMENTTABLE SET…
> 
> Impossible de modifier un enregistrement dans les expéditions (WHSShipmentTable). ID expédition : …

Voici un exemple réel qui inclut des exemples de données :

> Une exception s’est produite lors de la validation du chargement USMF-000033 ; le chargement n’a pas pu être libéré.
Session 5133 (administrateur)
>
> MISE À JOUR WHSSHIPMENTTABLE SET ORDERNUM=?,RECVERSION=?,MODIFIEDDATETIME=?,MODIFIEDBY=? OÙ ((RECID=?) ET (RECVERSION=?))  
> [Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Scale Unit @@ a tenté de mettre à jour les enregistrements appartenant à l’unité d’échelle @A.  
> Objet Serveur Azure :
>
> Impossible de modifier un enregistrement dans les expéditions (WHSShipmentTable). ID expédition : USMF-000031, USMF-000033. La base de données SQL a émis une erreur.

### <a name="cause-of-issue-1"></a>Cause du problème 1

Ce problème peut se produire si la combinaison suivante de conditions existe lorsque vous installez la charge de travail d’entrepôt d’unités d’échelle :

- Le système comprend un chargement non lancé où plusieurs lignes sont associées à différentes commandes, et certaines lignes de chargement ne sont pas associées à une expédition.
- Le système est configuré pour utiliser la consolidation des expéditions.

Dans un déploiement de topologie hybride distribuée, chaque enregistrement de chargement et d’expédition est marqué comme appartenant à une unité d’échelle ou à un hub spécifique. Lorsque vous libérez un chargement de la page **Atelier de planification des chargements**, le système modifie la propriété affectée. Toutefois, en raison des conditions répertoriées précédemment, le système peut ne pas être en mesure de résoudre la propriété des données. Par conséquent, il ne parvient pas à libérer le chargement vers l’entrepôt.

### <a name="resolution-of-issue-1"></a>Résolution du problème 1

Divisez le chargement en deux chargements plus petits avant de le libérer dans l’entrepôt.

## <a name="issue-2-error-while-a-wave-is-processed-on-a-scale-unit"></a>Problème 2 : Erreur lors du traitement d’une vague sur une unité d’échelle

### <a name="symptoms-of-issue-2"></a>Symptômes du problème 2

Lorsque vous traitez une vague sur une unité d’échelle, vous recevez un message d’erreur au format suivant :

> Vous ne pouvez pas modifier la ligne de chargement avec RecId =%1, ID de chargement = %2, car il appartient toujours au hub d’entreprise. Veillez à ce que le chargement sortant correspondant ait été lancé sur une unité d’échelle et que les lignes de commande magasin aient ainsi été créées.

Voici un exemple réel qui inclut des exemples de données :

> Journal d’informations pour la tâche Exécuter la vague USMF-000000012 (9223377668365210)  
> Journal d’informations pour la tâche Exécuter la vague USMF-000000012 (9223377668370462)  
> Vous ne pouvez pas modifier la ligne de chargement avec RecId = 68719478242, ID de chargement = USMF-000034, car il appartient toujours au hub d’entreprise. Veillez à ce que le chargement sortant correspondant ait été lancé sur une unité d’échelle et que les lignes de commande magasin aient ainsi été créées.

### <a name="cause-of-issue-2"></a>Cause du problème 2

Dans un déploiement de topologie hybride distribuée, la propriété des données de chargement et d’expédition est marquée comme appartenant à une unité d’échelle ou à un hub spécifique. Dans le cadre du traitement de vague, la propriété des données devrait être attribuée à une unité d’échelle.

Lorsque vous installez un chargement de travail d’entrepôt d’unités d’échelle, si une expédition ouverte est associée à un chargement et à une vague, le système ne peut pas contrôler la propriété des données. Par conséquent, le traitement de vague échoue sur l’unité d’échelle.

### <a name="resolution-of-issue-2"></a>Résolution du problème 2

Libérez la charge dans l’entrepôt depuis le hub.

## <a name="troubleshoot-issues-by-viewing-a-records-ownership-and-destination"></a>Résoudre les problèmes en affichant la propriété et la destination d’un enregistrement

Dans un déploiement de topologie hybride distribuée, de nombreux types d’enregistrement sont marqués comme appartenant à une unité d’échelle ou à un hub spécifique. Une fois que vous êtes passé à une topologie hybride distribuée et/ou que vous avez configuré une nouvelle charge de travail d’entrepôt d’unités d’échelle, le système attribue la propriété à chaque enregistrement pertinent. Ce processus peut parfois produire des erreurs ou des résultats inattendus. Par conséquent, les informations sur la propriété d’un enregistrement et la destination de transfert peuvent vous aider à résoudre les problèmes qui surviennent après avoir effectué ces types de modifications.

Suivez ces étapes pour afficher la propriété et la destination de transfert d’un enregistrement.

1. Ouvrez l’enregistrement concerné.
1. Dans le volet Actions, sous l’onglet **Options**, dans le groupe **Infos sur l’enregistrement**, sélectionnez **Afficher tous les champs**.
1. La page qui apparaît affiche toutes les valeurs pour tous les champs disponibles pour l’enregistrement sélectionné. Passez en revue les champs suivants :

    - **SYSSCALEUNITID** : ce champ indique le propriétaire actuel de l’enregistrement.
    - **SYSTARGETSCALEUNITID** : ce champ affiche l’ID d’unité d’échelle du hub ou l’unité d’échelle vers laquelle l’enregistrement sera transféré lorsque le propriétaire actuel a fini de l’utiliser. La valeur de ce champ est utilisée par les traitements par lots qui gèrent ce type de processus. Bien que ce champ ne soit pas directement lié à la propriété, la propriété peut changer lorsque l’enregistrement est transféré. Dans certains cas, ce champ reste vide.
