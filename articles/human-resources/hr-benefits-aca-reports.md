---
title: Générer des états sur la Loi sur les soins abordables (ACA)
description: Les déclarations de la Loi sur les soins abordables (ACA) génèrent les formulaires 1095-B et 1095-C pour appuyer la partie **Mandat de l’employeur** de la Loi sur les soins abordables.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c8f336e31e77391ef7e2bc2dca901e6a78fbb914
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066999"
---
# <a name="generate-aca-reports"></a>Générer des rapports ACA


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Les déclarations de la Loi sur les soins abordables (ACA) génèrent les formulaires 1095-B et 1095-C pour appuyer la partie **Mandat de l’employeur** de la Loi sur les soins abordables.

> [!NOTE]
> Les déclarations ACA sont uniquement activées pour les entités juridiques aux États-Unis.

## <a name="getting-started"></a>Mise en route

Pour suivre les informations sur les formulaires 1095-B et 1095-C, vous devez d’abord créer un ou plusieurs groupes de couverture liés à la Loi sur les soins abordables. Les groupes de couverture liés à la Loi sur les soins abordables indiquent :

- L’offre de couverture pour un salarié
- La part de l’employé sur la prime mensuelle la moins coûteuse, si le coût est supérieur au seuil de pauvreté fédéral
- La mesure Safe Harbor utilisée par l’employeur, le cas échéant

Les groupes de couverture liés aux soins abordables vous permettent de gérer les informations de ces champs sans avoir à modifier chaque fiche de l’employé lorsque les conditions sont identiques. Vous pouvez facilement attribuer des groupes de couverture liés aux soins abordables à un ou plusieurs employés avec l’option **Affectation en masse** de la page.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Gestion de plusieurs versions d’un groupe de couverture

Vous pouvez tenir à jour plusieurs versions d’un groupe de couverture quelconque. Cette fonctionnalité vous permet d’apporter des modifications sans avoir à créer un nouveau groupe et à y réaffecter des employés. 

Après avoir créé des groupes de couverture ACA, vous pouvez attribuer en masse les groupes aux employés avec l’option **Affectation en masse**. Vous pouvez également indiquer individuellement si vous souhaitez suivre et rapporter les informations ACA, et affecter un employé à un groupe de couverture de soins abordables.

Vous n’avez pas besoin de suivre certaines informations de couverture ACA, comme pour les employés à temps partiel. Dans ce cas, définissez le champ **Couverture d’état** sur **Non**. Bien que chaque employé pour lequel les informations ACA doivent être suivies doit être affecté à un groupe de couverture de soins abordables, vous pouvez toujours modifier les options suivantes pendant des mois avec des valeurs différentes :

- **Offre de couverture**
- **Part de coût de l’employé**
- **Safe Harbor**

Pour saisir des exceptions à l’une des valeurs du groupe de couverture lié aux soins abordables, cliquez sur le lien **Couverture liée aux soins abordables**, disponible sur la page **Détails du collaborateur**, figurant dans la section **Informations supplémentaires** sous l’onglet **Emploi**.

## <a name="reporting-health-care-coverage"></a>Génération d’états sur la couverture des soins de santé

En plus de suivre si une couverture d’assurance maladie était offerte à un employé à temps plein, si l’employeur offre une couverture de santé personnelle prise en charge par l’employeur pour laquelle l’employé est inscrit (peu importe si son statut d’emploi est à temps plein ou temps partiel), des informations supplémentaires doivent être signalées dans le formulaire 1095-C. Chaque employé (y compris les personnes à charge) couvert par les régimes d’avantages sociaux pris en charge par l’employeur doit être inclus dans l’état relatif aux mois couverts. 

Vous pouvez indiquer si chaque régime de prestations sociales doit être consigné en activant la case à cocher **Déclarer dans le cadre de la loi sur les soins abordables**.

En outre, si les employés ont choisi d’avoir l’une de leurs personnes à charge couvertes par un avantage, vous pouvez indiquer les dates auxquelles la personne à charge a été couverte pour chaque employé dans la page **Tenir les avantages à jour**. Pour indiquer que la personne à charge est couverte par l’avantage, choisissez le bouton **Modifier** dans le volet Actions de le raccourci **Personnes à charge**.

Dans la page **Gestionnaire des dates de la couverture des personnes à charge**, vous pouvez indiquer les dates auxquelles la personne à charge a été couverte par l’avantage. Entrer les dates dans cette page permet d’activer automatiquement la case à cocher **Couvert** sur la page **Tenir les avantages à jour**.

## <a name="generate-1095-b-and-1095-c-forms"></a>Générer des formulaires 1095-B et 1095-C

Vous pouvez également générer les formulaires 1095-B and 1095-C à partir du produit, et les distribuer à chacun de vos employés. Le système peut également générer électroniquement les formulaires 1095-C et les fichiers de transmission 1094-C IRS.  

Lorsque vous générez le formulaire 1095-C, entrez l’exercice fiscal approprié et indiquez si les numéros de sécurité sociale doivent être masqués. Si vous imprimez des formulaires 1095-C pour plus de 500 employés, vous recevrez plusieurs fichiers PDF. Nous vous recommandons d’augmenter la **Taille maximale de fichier** dans la fenêtre **Paramètres de gestion des documents** à 150 Mo.

## <a name="viewing-information"></a>Affichage des informations

Vous pouvez utiliser la page **Couverture du collaborateur en matière de soins abordables** pour voir quels employés ont été affectés à chaque groupe de couverture, quels employés ne doivent pas être inclus dans un état et quels employés ne sont pas affectés.

Si l’une des valeurs par défaut du groupe de couverture lié aux soins abordables est remplacée, un astérisque s’affiche en regard de la valeur modifiée. Si les valeurs des 12 mois sont identiques et ne sont pas remplacées, la valeur est imprimée dans la colonne **Tous les 12 mois**.

Vous pouvez également utiliser la fenêtre d’interrogation pour déterminer quels employés ont été signalés comme ne bénéficiant pas de la loi ACA. Vous n’avez pas besoin de suivre si la couverture leur a été offerte et vous n’avez pas besoin de délivrer un formulaire 1095-C en fin d’année. Sélectionnez **À ne pas déclarer dans le cadre de la loi sur les soins abordables** dans le champ **Filtrer par** pour générer la liste de tous les employés qui ne recevront pas de formulaire 1095-C.

Vous pouvez également afficher tous les employés qui ne sont pas affectés (le champ **Couverture d’état ACA** est vide) ou qui ont été affectés au groupe de couverture lié aux soins abordables qui est arrivée à expiration pour l’année sélectionnée dans le champ **Année**.

Vous pouvez exporter les listes des employés générées à l’aide des options de filtrage à partir d’Excel.

Si vous devez déclarer des personnes prises en charge par une couverte personnelle employeur, vous pouvez également consulter les personnes à charge couvertes par les régimes d’avantages sociaux avec la mention **Déclarer dans le cadre de la loi sur les soins abordables**. Sélectionnez **Afficher la couverture des personnes à charge** dans le volet Actions.

> [!NOTE]
> Seuls les avantages dont le régime dispose de la mention **Déclarer dans le cadre de la loi sur les soins abordables** s’affichent dans la fenêtre de recherche.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
