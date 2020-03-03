---
title: Concept de société dans Common Data Service
description: Cette rubrique décrit l'intégration des données de société entre Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 20a3f89821af56cb4c3969c89301d4a8a32ab848
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019785"
---
# <a name="company-concept-in-common-data-service"></a>Concept de société dans Common Data Service

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Dans Finance and Operations, le concept d'une *société* est à la fois juridique et commercial. C'est également une limite de sécurité et de visibilité pour les données. Les utilisateurs travaillent toujours dans le contexte d'une seule société, et la plupart des données sont agrégées par bandes par la société.

Common Data Service n'a pas de concept équivalent. Le concept le plus proche celui d'*unité commerciale*, qui est principalement une limite de sécurité et de visibilité pour les données utilisateur. Ce concept n'a pas les mêmes implications juridiques ou commerciales que celui de société.

Comme les unités commerciales et la société ne sont pas des concepts équivalents, il est impossible de forcer une mise en correspondance un à un (1:1) entre elles dans le cadre de l'intégration de Common Data Service. Toutefois, comme les utilisateurs doivent, par défaut, être autorisés à consulter les mêmes enregistrements dans l'application et Common Data Service, Microsoft a introduit une entité dans Common Data Service nommée cdm\_Company. Cette entité est équivalente à l'entité Société dans l'application. Pour garantir que la visibilité des enregistrements est équivalente entre l'application et Common Data Service de manière prédéfinie, il est recommandé d'effectuer le paramétrage suivant pour les données dans Common Data Service:

+ Pour chaque enregistrement de société Finance and Operations activé en double écriture, un enregistrement cdm\_Company associé est créé.
+ Lorsqu'un enregistrement cdm\_Company est créé et activé pour la double écriture, une unité commerciale par défaut ayant le même nom est créé. Bien qu'une équipe par défaut soit automatiquement créée pour cette unité commerciale, cette dernière n'est pas utilisée.
+ Une équipe avec un propriétaire distincte est créée avec le même nom. Elle est également associée à l'unité commerciale.
+ Par défaut, le propriétaire de tout enregistrement créé et doublement écrit dans Common Data Service est défini sur l'équipe « Propriétaire de DW » liée à l'unité commerciale associée.

L'illustration suivante montre un exemple de ce paramétrage de données dans Common Data Service.

![Paramétrage des données dans Common Data Service](media/dual-write-company-1.png)

En raison de cette configuration, tous les enregistrements liés à la société USMF sont détenu par une équipe liée à l'unité commerciale USMF dans Common Data Service. Par conséquent, tout utilisateur ayant accès à cette unité commerciale via un rôle de sécurité défini sur la visibilité au niveau de l'unité commerciale peut à présent voir ces enregistrements. L'exemple suivant montre comment les équipes peuvent être utilisées pour fournir un accès correct à ces enregistrements.

+ Le rôle « Responsable des ventes » est affecté aux membres de l'équipe « Ventes USMF ».
+ Les utilisateurs qui disposent du rôle « Responsable des ventes » peuvent accéder à tous les enregistrements de compte membres de la même unité commerciale dont ils sont membres.
+ L'équipe « Ventes USMF » est liée à l'unité commerciale USMF mentionnée précédemment.
+ Par conséquent, les membres de l'équipe « Ventes USMF » peuvent voir les comptes qui appartiennent à l'utilisateur « DW USMF », provenant de l'entité Société USMF dans Finance and Operations.

![Utilisations possibles des équipes](media/dual-write-company-2.png)

Comme le montre l'illustration précédente, cette correspondance 1:1 entre l'unité commerciale, la société et l'équipe est uniquement un point de départ. Dans cet exemple, une unité commerciale « Europe » est créée manuellement dans Common Data Service comme parent de DEMF et d'ESMF. Cette nouvelle unité commerciale racine est indépendante de la double écriture. Toutefois, elle peut être utilisée pour donner membres de l'équipe « Ventes EUR » l'accès aux données du compte dans DEMF et ESMF en définissant la visibilité des données sur **BU parent/enfant** dans le rôle de sécurité associé.

Une rubrique finale pour expliquer comment la double écriture détermine à quelle l'équipe propriétaire elle doit affecter les enregistrements. Ce comportement est contrôlé par le champ **Équipe propriétaire par défaut** dans l'enregistrement cdm\_Company. Lorsqu'un enregistrement cdm\_Company est activé pour la double écriture, un plug-in crée automatiquement l'unité commerciale et l'équipe propriétaire associées (si elles n'existent pas encore), et définit le champ **Équipe propriétaire par défaut**. L'administrateur peut modifier ce champ avec une valeur différente. Toutefois, l'administrateur ne peut pas désactiver le champ tant que l'entité est activée pour la double écriture.

> [!div class="mx-imgBorder"]
![Champ d'équipe propriétaire par défaut](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Agrégation par bande et amorçage de la société

L'intégration de Common Data Service apporte la parité de la société à l'aide d'un identificateur de société pour agréger les données par bande. Comme l'illustration suivante le montre, les entités spécifiques à la société sont développées de sorte qu'elles aient une relation plusieurs à un (N:1) avec l'entité cdm\_Company.

> [!div class="mx-imgBorder"]
![Relation plusieurs à un (N:1) entre une entité spécifique à la société et l'entité cdm_Company](media/dual-write-bootstrapping.png)

+ Pour les enregistrements, une fois une société ajoutée et enregistrée, la valeur passe en lecture seule. Par conséquent, les utilisateurs doivent s'assurer de sélectionner la société adéquate.
+ Seuls les enregistrements ayant des données de la société sont admissibles à la double écriture entre l'application et Common Data Service.
+ Pour les données Common Data Service existantes, une expérience d'amorçage menée par l'administrateur sera disponible prochainement.