---
title: Recommandations intelligentes
description: Cette rubrique explique comment le Machine Learning peut être utilisé pour fournir des recommandations pour des missions et des candidats à un poste.
author: andreabichsel
manager: AnnBe
ms.date: 03/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: fb31b413cfe3cd168bbb12ce6070325ff5f736da
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517975"
---
# <a name="intelligent-recommendations"></a>Recommandations intelligentes

[!include[banner](../includes/banner.md)]

Le Machine Learning peut aider les recruteurs et les responsables de l'embauche à identifier rapidement les meilleurs candidats à un poste. Il peut également créer des prospects pour trouver le poste le plus adapté à leur profil et à leurs intérêts. À mesure que ces fonctionnalités sont utilisées, et que des commentaires sont fournis, les recommandations s'amélioreront.

> [!NOTE] 
> - Les fonctionnalités de recommandation intelligente sont disponibles uniquement avec le [Module complémentaire Recrutement complet](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - La fonctionnalité décrite dans cette rubrique est accessible dans le cadre d'une version préliminaire. Le contenu et la fonctionnalité peuvent faire l'objet de modifications. Pour utiliser cette fonction, demandez à un administrateur de l'activer à l'aide des **Paramètres d'administrateur** dans Attract. Définissez, **Recommandation de candidat**, **Recommandation de mission**et **Recommandation de prospect** sur **Activé**. Pour plus d'informations, voir [Accéder aux fonctions d'aperçu de Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature). 


## <a name="candidate-recommendations"></a>Recommandations de candidats

Du fait que les annonces d'emploi peuvent attirer de centaines de candidats, il peut être difficile pour les recruteurs et les responsables de l'embauche de trouver les candidats dont les qualifications et la formation correspondent le mieux au poste. En analysant la corrélation entre la description et les besoins de la mission, et les données des CV et les profils des candidats, le Machine Learning peut être utilisé pour produire des recommandations de candidats. Les recommandations de candidats peuvent aider les recruteurs et les responsables de l'embauche à identifier les meilleurs talents et à la passer au stade de l'entretien plus rapidement. Pour toutes les missions, s'il y a plus de dix candidats ou prospects avec des CV ou des profils complets, les candidats ou prospects qui répondent le mieux aux exigences de la mission s'affichent dans la section **Candidats à prendre en compte** de la page **Mission**.

Pour n'importe quel candidat recommandé, vous pouvez sélectionner **Afficher le candidat** sur la fiche candidat pour consulter le profil du candidat et effectuer des opérations sur sa candidature. Vous pouvez utiliser le bouton (**...**) pour ouvrir le profil du candidat sur un nouvel onglet. Vous pouvez également utiliser ce bouton pour fournir une rétroaction sur la recommandation. Ainsi, vous aidez à affiner le moteur de recommandation et à améliorer les futures recommandations. Toutes les recommandations que vous ne souhaitez pas sont supprimées de la section **Candidats à prendre en compte** lorsque vous actualisez la page **Mission**. Vous pouvez utiliser la fiche rétroaction pour indiquer pourquoi vous n'avez pas trouvé la recommandation utile.

## <a name="job-recommendations"></a>Recommandations professionnelles 

Lorsqu'un employé potentiel utilise le site de carrière pour postuler à une mission, Attract recommande d'autres postes vacants au sein de l'organisation. Ces recommandations sont basées sur les candidatures passées et sur le CV ou le profil de candidat du prospect. Par conséquent, les recommandations de missions permettent aux prospects d'identifier rapidement les postes les mieux adaptés pour eux. Les recommandations de poste sont fournies aux prospects si plus de dix missions sont publiées sur le site de carrière. Les prospects peuvent ouvrir les détails d'un annonce d'emploi de la fiche recommandation. Ils peuvent également fournir une rétroaction sur une recommandation afin d'améliorer les futures recommandations.

## <a name="prospect-recommendations"></a>Recommandation de prospect 

Lorsqu'un nouveau poste est vacant, il peut falloir un certain temps pour faire des recherches dans tout votre réseau de talents et parmi tous les candidats antérieurs. Pour qu'Attract vous aide à faire cela, vous pouvez utiliser des algorithmes intelligents d'apprentissage machine. Cela signifie qu'Attract examine tous les candidats et suggère ceux qui sont une bonne correspondance dès que vous créez l'offre d'emploi. Pour afficher ces recommandations, activez le stade **Prospect** pour l'emploi. Il peut prendre jusqu'à une minute à Attract pour examiner toute votre base de données de candidats pour émettre des recommandations.

Les recommandations s'affichent sous forme de fiches dans l'onglet **Prospects** de toute offre d'emploi pour laquelle le stade **Prospect** est activé. Ces fiches répertorient les compétences trouvées dans le profil du prospect, ainsi que les informations sur l'éducation et les qualifications. Si vous remarquez une recommandation que vous aimez, vous pouvez ajouter le candidat comme prospect pour cet emploi.

> [!NOTE]
> Si vous avez récemment commencé à utiliser Attract, vous devez attendre d'avoir au moins 10 candidats avec des profils complets ou des CV avant de pouvoir utiliser cette fonctionnalité.

Pour éviter un éventuel biais dans les recommandations, Attract n'examine les profils des candidats qu'en fonction des compétences, des qualifications et d'autres mots clés qui correspondent à la description de l'emploi. En outre, Attract supprime les informations personnelles identifiables des profils des candidat avant l'évaluation.
