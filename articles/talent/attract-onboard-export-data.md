---
title: Exporter des données depuis Attract et Onboard
description: Exporter des données depuis Dynamics 365 Talent - Attract et Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
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
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461107"
---
# <a name="export-data-from-attract-and-onboard"></a>Exporter des données depuis Attract et Onboard

[!include [banner](includes/banner.md)]

Comme annoncé dans [Suppression des applications Dynamics 365 Talent: Attract et Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), nous supprimerons Dynamics 365 Talent: Attract et Dynamics 365 Talent: Onboard le 1 février 2022. Pour faciliter votre migration vers un autre produit, les deux applications offrent désormais des capacités d'exportation de données.

## <a name="export-data-from-attract"></a>Exporter des données depuis Attract

Vous pouvez exporter vos données sans restreindre l'accès à votre environnement. Vous pouvez le faire à des fins de test ou pour comprendre notre structure de données. Lorsque vous êtes prêt à migrer, limitez l'accès à votre environnement Attract en suivant les instructions après cette procédure. Assurez-vous d'exporter à nouveau vos données. 

1. Atteindre [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. Sous **Exportation de données**, sélectionnez **Demander une exportation de données**.

   ![[Demander une exportation de données depuis Attract](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. Quand la boîte de message **Votre demande est en cours de traitement** s'affiche, sélectionnez **OK**. L'exportation de données peut prendre jusqu'à 20 minutes, selon la taille de votre exportation.

4. Une fois votre exportation terminée, sélectionnez le bouton **Télécharger** à côté. 

   >[!NOTE]
   >Toutes les exportations de données sont disponibles pendant sept jours, moment auquel le lien **Télécharger** expire.</br>
   
Le téléchargement contient un fichier .zip avec vos données Attract, y compris les dossiers suivants :

| Nom de dossier | Description |
| --- | --- |
| Paramètres d'administration | Configurations du centre d'administration Attract. |
| Candidats | Tous les candidats qui ont été ajoutés à des emplois ou à des viviers de talents. |
| Modèles d'e-mail | Tous les modèles d'e-mail configurés pour l'environnement. |
| Modèles de packages d'offre d'emploi | Tous les modèles de packages d'offres d'emploi créés, ainsi que leurs configurations associées. |
| Ensembles de règles d'offre d'emploi |  Tous les fichiers d'ensemble de règles qui ont été téléchargés pour la gestion des offres. |
| Modèles d'offre d'emploi | Tous les modèles de documents d'offre d'emploi créés pour l'environnement. |
| Offres d'emploi | Tous les emplois créés. Les emplois supprimés ne sont pas exportés. Les sous-dossiers contiennent des candidatures, avec des sous-dossiers pour les pièces jointes des candidatures et les packages d'offres, le cas échéant. |
| Modèles d'offres d'emploi | Les modèles de traitement des emplois configurés dans l'environnement. |
| Viviers de talents | Tous les viviers de talents créés, leurs listes de contributeurs et les listes de candidats pour les viviers de talents. |
| Collaborateurs | Liste de tous les collaborateurs présents dans l'environnement, ainsi que leurs rôles. |
| (dossier racine) | Un fichier de schéma JSON qui décrit les champs de structure de données. |

### <a name="restrict-access-to-attract"></a>Restreindre l'accès à Attract

Lorsque vous êtes prêt à migrer, empêchez les non-administrateurs d'accéder à votre environnement Attract et d'exporter vos données.

>[!IMPORTANT]
>La restriction de l'accès à votre environnement Attract est permanente et ne peut pas être annulée. Si vous souhaitez que les utilisateurs non administrateurs continuent d'accéder à votre environnement, ignorez cette étape.

1. Atteindre [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. Pour empêcher les non-administrateurs d'accéder à votre environnement Attract, sous **Restreindre l'accès à cette application**, sélectionnez **Restreindre l'accès maintenant**. Restreindre l'accès supprime également tous les emplois actifs qui ont été publiés.

   ![[Restreindre l'accès non-administrateur à Attract](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. Lorsque vous voyez l'avertissement **Ceci est un changement permanent**, sélectionnez **Restreindre l’accès** pour interdire définitivement l'accès des utilisateurs non-administrateurs à cet environnement. Si vous n'êtes pas prêt à terminer cette étape, sélectionnez **Annuler**.

   ![[Avertissement que restreindre l'accès est un changement permanent](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   >Les administrateurs peuvent continuer d'accéder aux pages d'exportation de données et d'état sur les personnes après que vous avez restreint l'accès à l'environnement Attract.

## <a name="export-data-from-onboard"></a>Exporter des données depuis Onboard

Lorsque vous êtes prêt, vous pouvez télécharger des modèles, des guides et des données de candidats depuis Onboard.

1. Atteindre [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).

2. Sous **Exportation de données**, sélectionnez **Demander une exportation de données**. 

   ![[Demander une exportation de données depuis Onboard](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. Quand la boîte de message **Votre demande est en cours de traitement** s'affiche, sélectionnez **OK**. L'exportation de données peut prendre jusqu'à 20 minutes, selon la taille de votre exportation.

4. Une fois votre exportation terminée, sélectionnez le bouton **Télécharger** à côté. 

   ![[Télécharger une exportation de données depuis Onboard](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   >L'exportation de vos données est disponible pendant sept jours. Après sept jours, le lien **Télécharger** expire et vous devez demander une nouvelle exportation si vous devez télécharger à nouveau vos données. Lorsque vous démarrez une nouvelle exportation de données, tous les téléchargements existants expirent une fois la nouvelle exportation réussie.

Le téléchargement est un fichier .zip qui contient les éléments suivants :

- Un dossier **Modèles** contenant vos modèles Onboard au format de document Word.

- Un dossier **Guides** contenant vos guides Onboard au format de document Word.

## <a name="see-also"></a>Voir également :

[Suppression des applications Dynamics 365 Talent: Attract et Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)

[!INCLUDE[footer-include](../includes/footer-banner.md)]