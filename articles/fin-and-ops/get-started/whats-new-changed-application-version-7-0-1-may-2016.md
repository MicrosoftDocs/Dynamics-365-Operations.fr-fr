---
title: "Nouveautés ou modifications apportées à la version 7.0.1 de l’application Dynamics AX (mai 2016)"
description: "Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version 7.0.1 de Microsoft Dynamics AX. Cette version a été publiée en mai 2016 et a pour numéro de version 7.0.1265.23014."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: AX 7.0.0, Operations, UnifiedOperations
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 8b58cb4f9de393b3f381dbe0aa4330d5ebd62795
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017

---

# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a>Nouveautés ou modifications apportées à la version 7.0.1 de l’application Dynamics AX (mai 2016)

[!include[banner](../includes/banner.md)]


Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version 7.0.1 de Microsoft Dynamics AX. Cette version a été publiée en mai 2016 et a pour numéro de version 7.0.1265.23014.

<a name="electronic-reporting-er"></a>Gestion des états électroniques
-------------------------

|                                                                                                                                                                                        |                                                                                                                                                                                                                                                                                                                                                        |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Que pouvez-vous faire ?**                                                                                                                                                                   | **Pourquoi est-ce important ?**                                                                                                                                                                                                                                                                                                                             |
| Configurez une boîte de dialogue d’exécution pour les états électroniques afin que les utilisateurs puissent sélectionner les dimensions financières de leur choix.                                     | Au moment de l’exécution, dans la boîte de dialogue d’exécution d'un état électronique, les utilisateurs peuvent sélectionner plusieurs dimensions financières. Les détails des dimensions financières sélectionnées seront affichées dans le document électronique qui est généré.                                                                                                                              |
| Configurez l’accès à plusieurs dimensions financières lors de la conception d’un état électronique, via un seul mappage à la source de données souhaitée.                                                  | La même configuration d'états électroniques peut servir à générer des documents électroniques qui présentent les données transactionnelles ainsi que des détails des dimensions financières, quel que soit le nombre de dimensions financières qui sont sélectionnées par l’utilisateur ou configurées pour l’entité juridique ou l'instance actuelle.                                             |
| Configurez un état électronique pour entrer des données dans les colonnes générées de manière dynamique d’un document électronique qui est créé au format de feuille de calcul OPENXML.                                           | Un état électronique peut entrer des données dans une feuille de calcul OPENXML qui est générée, par la réplication des colonnes horizontalement. Par conséquent, la même configuration d'états électroniques peut être réutilisée pour générer des documents électroniques ayant un nombre différent de colonnes générées de façon dynamique.                                                                                 |
| Configurez les destinations d'états électroniques afin que le résultat d’un format de sortie soit dirigé vers une destination spécifique : fichier, courrier électronique ou archive (dossier Microsoft SharePoint ou stockage Microsoft Azure). | Auparavant, lorsque vous exécutiez une configuration d'état électronique, une zone de message apparaissait nécessitant une de l'utilisateur pour enregistrer ou ouvrir un fichier. Vous pouvez maintenant configurer une destination pour chaque configuration de format et pour chaque composant de sortie (un dossier ou un fichier) séparément. Les utilisateurs qui disposent des droits d’accès appropriés peuvent également modifier les paramètres de destination au moment de l’exécution. |

## <a name="pos--microsoft-dynamics-ax-retail"></a>POS – Microsoft Dynamics AX Retail
|                                |                                                                                                                                                                                         |
|--------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Que pouvez-vous faire ?**           | **Pourquoi est-ce important ?**                                                                                                                                                              |
| Utilisez le navigateur Google Chrome. | Les détaillants peuvent maintenant démarrer Cloud POS depuis le navigateur Chrome et peuvent bénéficier de toutes les fonctionnalités qui sont disponible dans la version de Cloud POS sur Internet Explorer et Microsoft Edge. |

## <a name="financial-reporting"></a>États financiers
|                                                                     |                                                                                                                                                                                                                                                                                                                    |
|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Que pouvez-vous faire ?**                                                | **Pourquoi est-ce important ?**                                                                                                                                                                                                                                                                                         |
| Recréez le magasin de données d'états financiers.                          | Lorsque vous déplacez des bases de données Dynamics AX entre différents environnements ou que vous apportez d'autres modifications invasives à l’environnement Dynamics AX, la base de données de génération d'états financiers peut devoir être recréée.  Un script Windows PowerShell est désormais fourni pour recréer la base de données pour vous.                                                                |
| Vous ne pouvez plus sélectionner les options du générateur d'états qui ne sont pas valides. | Plusieurs options du générateur d'états qui étaient utilisées dans les versions de mise sur le marché de Management reporter ne s’appliquent pas à cette version de Dynamics AX. Ces options étaient liées à la génération, la sortie et la liaison d'états financiers. Ces options ont été supprimées du générateur d'états financiers pour empêcher les erreurs de l’utilisateur. |

## <a name="financial-management"></a>Gestion financière
|                                                            |                                                                  |
|------------------------------------------------------------|------------------------------------------------------------------|
| **Que pouvez-vous faire ?**                                       | **Pourquoi est-ce important ?**                                       |
| Générez des fichiers de paiement positif pour les paiemets de Comptabilité fournisseur. | Les fichiers de paiement positifs peuvent être générés pour aider les banques à empêcher les fraudes par chèque. |

## <a name="warehouse-and-production"></a>Entrepôt et production
|                                                                                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Que pouvez-vous faire ?**                                                                                                                                                                                                                                                                                                                                                                    | **Pourquoi est-ce important ?**                                                                                                                                                                                                                                                                                                                                                                                                              |
| Définissez une stratégie de travail d’entrepôt qui contrôle la création du travail pour un ensemble de produits à des emplacements spécifiques.                                                                                                                                                                                                                                                                          | Les processus d'entrepôt n'incluent pas systématiquement les tâches. À l'aide de la nouvelle stratégie de travail d'entrepôt, vous pouvez empêcher la création de tâche pour le prélèvement de matières premières et le rangement de produits finis pour un ensemble de produits à des emplacements spécifiques.                                                                                                                                                                                                     |
| Spécifiez que les plaques d’immatriculation d’un emplacement de sortie de production ne font pas l'objet d'un contrôle.                                                                                                                                                                                                                                                                                                               | Vous pouvez maintenant spécifier que les plaques d’immatriculation d’un emplacement de sortie de production ne font pas l'objet d'un contrôle. Par exemple, cette fonctionnalité est utile lorsqu’un ordre de fabrication en amont signale les éléments terminés directement à un emplacement qui sert d’emplacement d’entrée en production pour un ordre de fabrication en aval.                                                                                                                                                     |
| Prenez en charge les nomenclatures qui incluent des articles dotés de dimensions de produit différentes d’un même article.                                                                                                                                                                                                                                                                                                     | Lorsque vous utilisez une ou plusieurs des dimensions de produit dans la production, vous pouvez avoir des situations où vous souhaitez produire un article, basé sur une autre variante du même article. Pour plus d'informations, voir [ce blog](https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/).                                                                  |
| Les ordres de fabrication avec des structures circulaires au premier niveau de leurs nomenclatures sont exclus du calcul de nomenclature pour la planification de la ressource matérielle.                                                                                                                                                                                                                                     | Il n’est pas possible d’affecter des niveaux de nomenclature corrects aux variantes de produit pour les ordres de fabrication entraînant une circularité dans la hiérarchie de nomenclature.                                                                                                                                                                                                                                                                                                  |
| Calculez les différents niveaux de nomenclature pour la planification des ressources matérielles et le calcul de coût : • Pour la planification de ressource matérielle, les niveaux de nomenclature sont calculés dans la nouvelle table **ReqItemLevel**. Les ordres de fabrication terminés sont ignorés dans le calcul. • Pour le calcul des coûts de production, les niveaux de nomenclature sont calculés dans la table **InventTable**. Les ordres de fabrication terminés sont inclus dans le calcul. | • Lors de l’exécution de planification des ressources matérielles, par exemple, la planification planifie le plan et les explosions, seuls les niveaux de nomenclature utilisés pour la planification de ressource matérielle doivent être recalculés. Autrement dit, il n’est pas nécessaire de calculer les niveaux de la nomenclature utilisés pour le calcul de la production. • Lors de l’exécution des opérations d’évaluation des coûts, par exemple, les stocks de clôture, seuls les niveaux de nomenclature utilisés pour le calcul de coût de la production doivent recalculés. |

 

<a name="see-also"></a>Voir également :
--------

[Nouveautés ou changements](whats-new-changed.md)

[Guides de tâches nouveaux ou mis à jour (mai 2016)](new-updated-task-guides-available-may-2016.md)



