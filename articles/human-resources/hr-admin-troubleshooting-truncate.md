---
title: Éviter la troncation de texte de la hiérarchie des postes et exporter dans Visio
description: Cette rubrique explique comment résoudre le problème de noms de personnes et de postes tronqués dans la hiérarchie des postes dans Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8a9a8d22df0416ef417a6216c3131bfb6d40d200
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413533"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a>Éviter la troncation de texte de la hiérarchie des postes et exporter dans Visio

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Problème**

Lorsqu’un client affiche la hiérarchie des postes dans Microsoft Dynamics 365 Human Resources, les noms des personnes et les postes sont tronqués. Par conséquent, il peut être difficile d’effectuer une capture d’écran, ou d’imprimer et de distribuer la hiérarchie.

![Hiérarchie des postes.](media/position-h.png)

**Cause**

Ce comportement est fait exprès.

**Résolution**

Malheureusement, les utilisateurs ne peuvent pas facilement modifier la taille du texte. Toutefois, vous pouvez exporter la hiérarchie des postes de Human Resources puis les importer dans Microsoft Visio. Bien que l’article suivant ait été rédigé pour Microsoft Dynamics AX 2012, le processus s’applique toujours à Human Resources : [Exporter une hiérarchie des postes vers Microsoft Visio](/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).

Procédez comme suit pour exporter dans Visio.

1. Dans Human Resources, ouvrez la page de liste **Postes**.

    Pour inclure des informations supplémentaires dans le diagramme de structure de l’organisation, ajoutez des champs à la liste **Postes**, afin qu’ils soient disponibles lorsque vous utilisez l’**Assistant Diagramme de l’organisation** ultérieurement dans cette procédure.

2. Dans le volet Actions, sélectionnez le bouton **Ouvrir dans Microsoft Office**, puis, sous **Exporter vers Excel**, sélectionnez **Postes**. Sinon, appuyez sur Ctrl+T.

    ![Exporter la page de la liste des postes vers Excel.](media/org-admin.png)

3. Enregistrez le fichier Excel exporté.

    ![Boîte de dialogue Exporter vers Excel.](media/export-excel.png)

4. Dans Visio, sélectionnez **Visio – Créer**, puis sélectionnez la catégorie de modèle **Entreprise**.

    ![Nouveau diagramme.](media/new.png)

5. Sélectionnez **Assistant de graphique d’organisation**, puis sélectionnez **Créer**.

    ![Boîte de dialogue Assistant de graphique d’organisation.](media/orgchart-wizard.png)

6. Sélectionnez **Informations déjà stockées dans un fichier ou une base de données**, puis sélectionnez **Suivant**.

    ![Assistant Diagramme de l’organisation 1.](media/orgchart-wizard7.png)

7. Choisissez **Un texte, Org Plus (\*.txt), ou fichier Excel**, puis sélectionnez **Suivant**.

    ![Assistant Diagramme de l’organisation 2.](media/orgchart-wizard3.png)

8. Naviguez pour sélectionner le fichier Excel exporté contenant la hiérarchie des postes, puis sélectionnez **Suivant**.

    ![Assistant Diagramme de l’organisation 3.](media/orgchart-wizard2.png)

9. Définissez le champ **Nom** sur **Poste**, définissez le champ **Référence** sur **Poste de référence**, puis sélectionnez **Suivant**.

    ![Assistant Diagramme de l’organisation 4.](media/orgchart-wizard1.png)

10. Sélectionnez les champs qui doivent être affichés sur chaque nœud, puis sélectionnez **Suivant**.

    ![Assistant Diagramme de l’organisation 5.](media/orgchart-wizard5.png)

11. Ajoutez la colonne **Poste** à la liste **Champs de données de forme**, puis la sélectionnez **Suivant**.

    ![Assistant Diagramme de l’organisation 6.](media/orgchart-wizard6.png)

12. Les images ne sont pas actuellement disponibles. Par conséquent, sur la page suivante, sélectionnez **Suivant**.
13. Sélectionnez **Je souhaite que l’Assistant répartisse automatiquement mon graphique d’organisation entre les pages**.

    ![Assistant Diagramme de l’organisation 7.](media/orgchart-wizard4.png)

14. Sélectionnez **Terminer**.

    Si des postes ne figurent pas dans la structure, vous êtes invité à les inclure dans le diagramme.

Le diagramme généré dans Visio affiche chaque responsable sur une feuille de calcul distincte.

Selon les champs sélectionnés à inclure dans le diagramme, chaque nœud affiche les informations appropriées lorsque le fichier Visio est généré.

![Diagramme de la hiérarchie.](media/hierarchy.png)

**Option supplémentaire**

Dans Human Resources, vous pouvez également pouvoir utiliser l’espace de travail **Personnes** pour afficher des informations associées à la hiérarchie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
