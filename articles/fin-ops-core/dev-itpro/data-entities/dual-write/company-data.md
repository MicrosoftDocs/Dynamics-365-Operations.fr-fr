---
title: Concept de société dans Dataverse
description: Cette rubrique décrit l’intégration des données de société entre Finance and Operations et Dataverse.
author: RamaKrishnamoorthy
ms.date: 08/04/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 24cd936fd330ce2bdfc6aa7cac75ab5bacbbf3d0
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416777"
---
# <a name="company-concept-in-dataverse"></a>Concept de société dans Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


Dans Finance and Operations, le concept d’une *société* est à la fois juridique et commercial. C’est également une limite de sécurité et de visibilité pour les données. Les utilisateurs travaillent toujours dans le contexte d’une seule société, et la plupart des données sont agrégées par bandes par la société.

Dataverse n’a pas de concept équivalent. Le concept le plus proche celui d’*unité commerciale*, qui est principalement une limite de sécurité et de visibilité pour les données utilisateur. Ce concept n’a pas les mêmes implications juridiques ou commerciales que celui de société.

Comme les unités commerciales et la société ne sont pas des concepts équivalents, il est impossible de forcer une mise en correspondance un à un (1:1) entre elles dans le cadre de l’intégration de Dataverse. Toutefois, comme les utilisateurs doivent, par défaut, être autorisés à consulter les mêmes lignes dans l’application et Dataverse, Microsoft a introduit une table dans Dataverse nommée cdm\_Company. Cette table est équivalente à la table Société dans l’application. Pour garantir que la visibilité des lignes est équivalente entre l’application et Dataverse de manière prédéfinie, il est recommandé d’effectuer le paramétrage suivant pour les données dans Dataverse:

+ Pour chaque ligne de société Finance and Operations activé en double écriture, une ligne cdm\_Company associé est créée.
+ Lorsqu’une ligne cdm\_Company est créé et activé pour la double écriture, une unité commerciale par défaut ayant le même nom est créé. Bien qu’une équipe par défaut soit automatiquement créée pour cette unité commerciale, cette dernière n’est pas utilisée.
+ Une équipe avec un propriétaire distincte est créée avec le même nom. Elle est également associée à l’unité commerciale.
+ Par défaut, le propriétaire de toute ligne créée et doublement écrite dans Dataverse est défini sur l’équipe « Propriétaire de DW » liée à l’unité commerciale associée.

L’illustration suivante montre un exemple de ce paramétrage de données dans Dataverse.

![Paramétrage des données dans Dataverse.](media/dual-write-company-1.png)

En raison de cette configuration, toutes les lignes liées à la société USMF sont détenu par une équipe liée à l’unité commerciale USMF dans Dataverse. Par conséquent, tout utilisateur ayant accès à cette unité commerciale via un rôle de sécurité défini sur la visibilité au niveau de l’unité commerciale peut à présent voir ces lignes. L’exemple suivant montre comment les équipes peuvent être utilisées pour fournir un accès correct à ces lignes.

+ Le rôle « Responsable des ventes » est affecté aux membres de l’équipe « Ventes USMF ».
+ Les utilisateurs qui disposent du rôle « Responsable des ventes » peuvent accéder à toutes les lignes de compte membres de la même unité commerciale dont ils sont membres.
+ L’équipe « Ventes USMF » est liée à l’unité commerciale USMF mentionnée précédemment.
+ Par conséquent, les membres de l’équipe « Ventes USMF » peuvent voir les comptes qui appartiennent à l’utilisateur « DW USMF », provenant de la table Société USMF dans Finance and Operations.

![Utilisations possibles des équipes.](media/dual-write-company-2.png)

Comme le montre l’illustration précédente, cette correspondance 1:1 entre l’unité commerciale, la société et l’équipe est uniquement un point de départ. Dans cet exemple, une unité commerciale « Europe » est créée manuellement dans Dataverse comme parent de DEMF et d’ESMF. Cette nouvelle unité commerciale racine est indépendante de la double écriture. Toutefois, elle peut être utilisée pour donner membres de l’équipe « Ventes EUR » l’accès aux données du compte dans DEMF et ESMF en définissant la visibilité des données sur **BU parent/enfant** dans le rôle de sécurité associé.

Une rubrique finale pour expliquer comment la double écriture détermine à quelle l’équipe propriétaire elle doit affecter les lignes. Ce comportement est contrôlé par la colonne **Équipe propriétaire par défaut** dans la ligne cdm\_Company. Lorsqu’une ligne cdm\_Company est activé pour la double écriture, un plug-in crée automatiquement l’unité commerciale et l’équipe propriétaire associées (si elles n’existent pas encore), et définit la colonne **Équipe propriétaire par défaut**. L’administrateur peut modifier cette colonne avec une valeur différente. Toutefois, l’administrateur ne peut pas désactiver la colonne tant que la table est activée pour la double écriture.

> [!div class="mx-imgBorder"]
![Colonne d’équipe propriétaire par défaut.](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Agrégation par bande et amorçage de la société

L’intégration de Dataverse apporte la parité de la société à l’aide d’un identificateur de société pour agréger les données par bande. Comme l’illustration suivante le montre, les tables spécifiques à la société sont développées de sorte qu’elles aient une relation plusieurs à un (N:1) avec la table cdm\_Company.

> [!div class="mx-imgBorder"]
![Relation plusieurs à un (N:1) entre une table spécifique à la société et la table cdm_Company.](media/dual-write-bootstrapping.png)

+ Pour les lignes, une fois une société ajoutée et enregistrée, la valeur passe en lecture seule. Par conséquent, les utilisateurs doivent s’assurer de sélectionner la société adéquate.
+ Seules les lignes ayant des données de la société sont admissibles à la double écriture entre l’application et Dataverse.
+ Pour les données Dataverse existantes, une expérience d’amorçage menée par l’administrateur sera disponible prochainement.


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a>Renseigner automatiquement le nom de l’entreprise dans les applications Customer Engagement

Il existe plusieurs façons de renseigner automatiquement le nom de l’entreprise dans les applications Customer Engagement.

+ Si vous êtes administrateur système, vous pouvez définir l’entreprise par défaut en accédant à **Paramètres avancés > Système > Sécurité > Utilisateurs**. Ouvrez le formulaire **Utilisateur**, et dans la section **Informations sur l’organisation**, définissez la valeur **Société par défaut sur les formulaires**.

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="Définissez la société par défaut dans la section Informations sur l’organisation.":::

+ Si vous disposez d’un accès en **Écriture** à la table **SystemUser** pour le niveau **Unité commerciale**, vous pouvez modifier la société par défaut sur n’importe quel formulaire en sélectionnant une société dans le menu déroulant **Société**.

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="Modifier le nom de l’entreprise sur un nouveau compte.":::

+ Si vous disposez d’un accès en **Écriture** aux données de plusieurs sociétés, vous pouvez alors modifier la société par défaut en choisissant une ligne appartenant à une société différente.

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="Choisir une ligne modifie la société par défaut.":::

+ Si vous êtes configurateur ou administrateur système et que vous souhaitez renseigner automatiquement les données de l’entreprise sur un formulaire personnalisé, vous pouvez utiliser les [événements de formulaire](/powerapps/developer/model-driven-apps/clientapi/events-forms-grids). Ajoutez une référence JavaScript à **msdyn_/DefaultCompany.js** et utilisez les événements suivants. Vous pouvez utiliser n’importe quel formulaire prêt à l’emploi, par exemple, **Compte**.

    + Événement **OnLoad** pour le formulaire : définissez la colonne **defaultCompany**.
    + Événement **OnCharge** pour la colonne **Société** : définissez la colonne **updateDefaultCompany**.

## <a name="apply-filtering-based-on-the-company-context"></a>Appliquer le filtrage en fonction du contexte de l’entreprise

Pour appliquer un filtrage basé sur le contexte de l’entreprise sur vos formulaires personnalisés ou sur des colonnes de recherche personnalisées ajoutées aux formulaires standard, ouvrez le formulaire et utilisez la section **Filtrage des enregistrements associés** pour appliquer le filtre d’entreprise. Vous devez le définir pour chaque colonne de recherche qui nécessite un filtrage basé sur la société sous-jacente sur une ligne donnée. Le paramètre est affiché pour **Compte** dans l’illustration suivante.

:::image type="content" source="media/apply-company-context.png" alt-text="Appliquer le contexte de l’entreprise.":::



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]