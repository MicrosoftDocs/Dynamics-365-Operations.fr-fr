---
title: Générer des états sur la Loi sur les soins abordables (ACA)
description: La fonctionnalité est disponible pour aider les employeurs qui ont besoin de suivre les informations déclarées dans les formulaires 1095-B et 1095-C à l'appui de la partie Mandat de l'employeur de la Loi sur les soins abordables. Notez que cette fonctionnalité est uniquement activée pour les entités juridiques aux États-Unis.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 3555be3067db459625df9f9b0ac6b78fc2715289
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430899"
---
# <a name="generate-affordable-care-act-aca-reports"></a>Générer des états sur la Loi sur les soins abordables (ACA)

La fonctionnalité est disponible pour aider les employeurs qui ont besoin de suivre les informations déclarées dans les formulaires 1095-B et 1095-C à l'appui de la partie **Mandat de l'employeur** de la Loi sur les soins abordables. Notez que cette fonctionnalité est uniquement activée pour les entités juridiques aux États-Unis.

## <a name="getting-started"></a>Mise en route
Pour commencer à suivre les informations à reporter dans les formulaires 1095-B et 1095-C, vous devez d'abord créer un ou plusieurs groupes de couverture liés aux soins abordables. Ces groupes de couverture liés aux soins abordables seront utilisés pour indiquer l'offre de couverture fournie à un employé, la part de l'employé sur la prime mensuelle la moins coûteuse (si le coût est supérieur au seuil de pauvreté fédéral), ainsi que la mesure « Safe Harbor » utilisée par l'employeur, le cas échéant. L'utilisation des groupes de couverture liés aux soins abordables permet de gérer les informations de ces champs sans devoir toucher à chaque enregistrement d'employé lorsque les conditions sont identiques. En outre, les groupes de couverture liés aux soins abordables peuvent facilement être affectés à un ou plusieurs employés avec la fonctionnalité d'affectation en masse de la page.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Gestion de plusieurs versions d'un groupe de couverture
Vous pouvez gérer plusieurs versions d'un groupe de couverture, ce qui vous permet de modifier les informations du groupe sans avoir à créer un nouveau groupe et à réaffecter des salariés lorsque quelque chose change dans votre organisation ou dans les avantages offerts. 

Après avoir créé les groupes de couverture liés aux soins abordables (ACA) nécessaires, vous pouvez choisir d'affecter en masse les groupes aux employés avec la fonctionnalité **Affectation collective** dans la page, ou vous pouvez accéder à chaque employé et indiquer si les informations sur la loi sur les soins abordables doivent être suivies et signalées pour cet employé. Vous pouvez également affecter l'employé à un groupe de couverture associé aux soins abordables.

Si les informations sur la couverture liée aux soins abordables n'a pas besoin d'être suivie ni déclarée pour un employé, par exemple en cas de travail à temps partiel, le champ **Couverture d'état** peut être définie sur non. Bien que chaque employé pour lequel les informations ACA doivent être suivies doit être affecté à un groupe de couverture de soins abordables, vous pouvez toujours modifier les options **Offre de couverture**, **Part de coût de l'employé** et **Safe Harbor** sur un ou des mois, qui peuvent nécessiter des valeurs différentes de celles saisies dans le groupe de couverture des soins abordables.

Pour saisir des exceptions à l'une des valeurs du groupe de couverture lié aux soins abordables, cliquez sur le lien Couverture liée aux soins abordables, disponible sur la page Détails du collaborateur, figurant dans la section Informations supplémentaires sous l'onglet Emploi.

## <a name="reporting-health-care-coverage"></a>Génération d'états sur la couverture des soins de santé
En plus de suivre si une couverture d'assurance maladie était offerte à un employé à temps plein, si l'employeur offre une couverture de santé personnelle prise en charge par l'employeur pour laquelle l'employé est inscrit (peu importe si son statut d'emploi est à temps plein ou temps partiel), des informations supplémentaires doivent être signalées dans le formulaire 1095-C. Chaque employé (y compris les personnes à charge) couvert par les régimes d'avantages sociaux pris en charge par l'employeur doit être inclus dans l'état relatif aux mois couverts. 

Vous pouvez indiquer si chaque régime d'avantages sociaux doit être consigné en activant la case à cocher **Déclarer dans le cadre de la loi sur les soins abordables**.

En outre, si les employés ont choisi d'avoir l'une de leurs personnes à charge couvertes par un avantage, vous pouvez indiquer les dates auxquelles la personne à charge a été couverte pour chaque employé dans la page Tenir les avantages à jour. Pour indiquer que la personne à charge est couverte par l'avantage, choisissez le bouton Modifier dans le volet Actions de l'organisateur Personnes à charge.

Dans la page **Gestionnaire des dates de la couverture des personnes à charge**, vous pouvez indiquer les dates auxquelles la personne à charge a été couverte par l'avantage. Entrer les dates dans cette page permet d'activer automatiquement la case à cocher **Couvert** sur la page **Tenir les avantages à jour**.

## <a name="generate-1095b-and-1095c-forms"></a>Générer les formulaires 1095B and 1095C
Vous pouvez également générer les formulaires 109-B and 1095-C à partir du produit, et les distribuer à chacun de vos employés. La génération électronique du formulaire 1095-C et des fichiers de transmission 1094-C correspondants, qui peuvent être utilisés pour un envoi à l'administration fiscale, peuvent également être générés à partir du système.  

Lorsque vous générez le formulaire 1095-C, entrez l'exercice fiscal approprié et indiquez si les numéros de sécurité sociale doivent être masqués. Si vous imprimez des formulaires 1095-C pour plus de 500 employés, vous recevrez plusieurs fichiers PDF. Nous vous recommandons d'augmenter la **Taille maximale de fichier** dans la fenêtre **Paramètres de gestion des documents** à 150 Mo.

## <a name="viewing-information"></a>Affichage des informations
Vous pouvez utiliser la page **Couverture du collaborateur en matière de soins abordables** pour voir quels employés ont été affectés à chaque groupe de couverture, quels employés ne doivent pas être inclus dans un état et quels employés ne sont pas affectés.

Si l'une des valeurs par défaut du groupe de couverture lié aux soins abordables est remplacée, un astérisque s'affiche en regard de la valeur modifiée. Si les valeurs des 12 mois sont identiques et ne sont pas remplacées, la valeur est imprimée dans la colonne **Tous les 12 mois**.

Vous pouvez également utiliser la fenêtre d'interrogation pour déterminer quels employés ont été signalés comme ne bénéficiant pas de la loi ACA, ce qui signifie que vous n'avez pas besoin de suivre si la couverture leur a été offerte et vous n'avez pas besoin de délivrer un formulaire 1095-C en fin d'année. En sélectionnant **À ne pas déclarer dans le cadre de la loi sur les soins abordables** dans le champ **Filtrer par**, vous pouvez générer la liste de tous les employés ayant été marqués pour ne pas recevoir un formulaire 1095-C.

Outre d'afficher la liste des employés qui ne sont pas déclarés dans le cadre de la loi sur les soins abordables, vous pouvez également afficher tous les employés qui ne sont pas affectés (le champ **Couverture d'état ACA** est vide) ou qui ont été affectés au groupe de couverture lié aux soins abordables qui est arrivée à expiration pour l'année sélectionnée dans le champ **Année**.

Vous pouvez exporter les listes des employés générées à l'aide des options de filtrage à partir d'Excel.

Si vous devez déclarer des personnes prises en charge par une couverte personnelle employeur, vous pouvez également consulter les personnes à charge couvertes par les régimes d'avantages sociaux avec la mention **Déclarer dans le cadre de la loi sur les soins abordables** en sélectionnant l'action Afficher la couverture des personnes à charge dans la bande du volet Actions.

**Remarque :** seuls les avantages dont le régime dispose de la mention **Déclarer dans le cadre de la loi sur les soins abordables** s'affichent dans la fenêtre de recherche.
