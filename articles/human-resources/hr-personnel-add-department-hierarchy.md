---
title: Créer des départements et les inclure dans la hiérarchie des départements
description: Un département est une unité opérationnelle qui représente une catégorie ou un domaine fonctionnel d’une organisation. Un département est responsable d’un domaine spécifique de l’organisation, par exemple les ventes, la comptabilité ou les ressources humaines. Les départements vous permettent de générer des états sur les domaines fonctionnels. Les départements peuvent avoir la responsabilité des résultats.
author: andreabichsel
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HierarchyDesigner, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 3c4382336e53bc09c51dd845446af9a20a2ba8af
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794467"
---
# <a name="create-departments-and-include-them-in-the-department-hierarchy"></a>Créer des départements et les inclure dans la hiérarchie des départements

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Un département est une unité opérationnelle qui représente une catégorie ou un domaine fonctionnel d’une organisation. Un département est responsable d’un domaine spécifique de l’organisation, par exemple les ventes, la comptabilité ou les ressources humaines. Les départements vous permettent de générer des états sur les domaines fonctionnels. Les départements peuvent avoir la responsabilité des résultats.

Un département peut inclure un groupe de centres de coût. Des postes peuvent être affectés aux départements. Pour créer un département, cliquez sur **Ressources humaines** &gt; **Départements** &gt; **Département**. Le tableau suivant décrit les champs disponibles.

| Champ               | Description                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nom                | Entrez un nom pour le département.                                                                                                                                                                                  |
| Numéro du département   | Il se peut qu’une valeur par défaut soit générée automatiquement si un code souche de numéros est affecté à la référence **Numéro d’organisation** sur la page **Souches de numéros**.                                                 |
| Nom de recherche         | Entrez un nom ou un acronyme pouvant être utilisé pour rechercher le département.                                                                                                                                            |
| Mémo                | Entrez les éventuelles informations supplémentaires ici.                                                                                                                                                                            |
| Dans la hiérarchie        | Une case cochée indique que le département est inclus dans la hiérarchie des départements. Pour plus d’informations sur l’ajout d’un département à la hiérarchie des départements, voir les informations fournies dans cet article. |
| Numéro DUNS         | DUNS est l’acronyme de Data Universal Number System (Système de codage numérique universel des données). Il s’agit d’un numéro de neuf chiffres émis par Dun & Bradstreet.                                                                                                     |
| Responsable             | Spécifiez le contact qui gère le département.                                                                                                                                                                    |
| Adresses           | Ajoutez les informations d’adresse du département. Par exemple, ajoutez l’adresse postale du bâtiment dans lequel le département est situé.                                                                          |
| Informations de contact | Ajoutez les informations de contact du département. Par exemple, ajoutez le numéro de téléphone de la réception du département.                                                                                           |

Pour ajouter un département à la hiérarchie des départements, procédez comme suit.

1.  Cliquez sur **Ressources humaines** &gt; **Départements** &gt; **Hiérarchie des départements**.
2.  Cliquez sur **Modifier**, puis sélectionnez l’organisation à laquelle le département doit être affilié.
3.  Cliquez sur **Insérer**, puis sélectionnez **Département** dans la liste.
4.  Dans la liste des départements qui s’affiche, sélectionnez le département à ajouter à la hiérarchie.
5.  Enregistrez vos modifications. Vous recevez un message indiquant qu’une version temporaire de la hiérarchie a été créée.
6.  Lorsque vous êtes prêt, cliquez sur **Publier** dans le concepteur de hiérarchie. Vous pouvez entrer une date d’effet qui indique quand la hiérarchie doit être publiée. Par exemple, pour ajouter un nouveau département au début de l’année civile suivante, définissez la date d’effet au 1er janvier de la nouvelle année civile. Les modifications apportées à la hiérarchie entreront en vigueur à cette date.

## <a name="steps-for-creating-a-department"></a>Étapes pour créer un département
Reportez-vous à l’article [Définir les nouveaux départements](../fin-and-ops/hr/tasks/define-new-departments.md) pour connaître la procédure pas à pas pour créer un département. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]