---
title: Tâche de nettoyage des entrées disponibles de la gestion de l’entrepôt
description: Cette rubrique décrit la tâche de nettoyage des entrées disponibles, qui permet d’améliorer les performances du système en identifiant et en supprimant les enregistrements associés mais inutiles.
author: perlynne
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 93c77434a912554dab486b42c0c9fffd68cf9435
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226001"
---
# <a name="warehouse-management-on-hand-entries-cleanup-job"></a>Tâche de nettoyage des entrées disponibles de la gestion de l’entrepôt

Les performances des requêtes utilisées pour calculer l’inventaire disponible sont affectées par le nombre d’enregistrements dans les tables impliquées. Une façon d’améliorer les performances consiste à réduire le nombre d’enregistrements que la base de données doit prendre en compte.

Cette rubrique décrit la tâche de nettoyage des entrées disponibles, qui supprime les enregistrements inutiles dans les tables InventSum et WHSInventReserve. Ces tables stockent les informations de disponibilité pour les articles activés pour le traitement de gestion d’entrepôt. (Ces éléments sont appelés éléments WHS.) La suppression de ces enregistrements peut améliorer considérablement les performances des calculs de disponibilité.

## <a name="what-the-cleanup-job-does"></a>Ce que fait la tâche de nettoyage

La tâche de nettoyage des entrées disponibles supprime tous les enregistrements des tables WHSInventReserve et InventSum dont toutes les valeurs de champ sont *0* (zéro). Ces enregistrements peuvent être supprimés car ils ne contribuent pas aux informations de disponibilité. La tâche supprime uniquement les enregistrements qui se trouvent en-dessous du niveau **Emplacement**.

Si le stock physique négatif est autorisé, la tâche de nettoyage peut ne pas être en mesure de supprimer toutes les entrées pertinentes. La raison de cette limitation est que la tâche doit autoriser un scénario spécial où un contenant contient plusieurs numéros de série et où l’un de ces numéros de série est devenu négatif. Par exemple, le système aura une disponibilité zéro au niveau du contenant lorsqu’un contenant aura +1 pièces du numéro de série 1 et –1 pièces du numéro de série 2. Pour ce scénario spécial, la tâche effectue d’abord une suppression globale, où elle essaie de supprimer en partant des niveaux inférieurs.

## <a name="schedule-and-configure-the-cleanup-job"></a>Programmer et configurer la tâche de nettoyage

La tâche de nettoyage des entrées disponibles est disponible dans **Gestion des stocks \> Tâches périodiques \> Nettoyage \> Nettoyage des entrées disponibles de la gestion de l’entrepôt**. Utilisez les paramètres de tâche standard pour contrôler la portée et le programme d’exécution de la tâche. En outre, les paramètres suivants sont fournis :

- **Supprimer s’il n’y a pas eu de mise à jour depuis plusieurs jours** – Entrez le nombre minimum de jours à attendre avant de supprimer une entrée disponible qui est tombée à zéro. Utilisez ce paramètre pour réduire le risque de supprimer des entrées disponibles qui sont toujours utilisées. Si vous souhaitez que le nettoyage soit effectué dès que possible, entrez *0* (zéro) ou laissez le champ vide.
- **Durée d’exécution maximale (heures)** – Entrez la durée d’exécution maximale de la tâche de nettoyage, en heures. Si la tâche n’est pas terminée avant la fin de ce délai, elle enregistrera le travail effectué jusqu’à présent, puis se fermera. Cette capacité est particulièrement pertinente pour les implémentations où le stock est important. Dans ces cas, vous devez programmer l’exécution de la tâche aux heures où la charge du système est aussi légère que possible. Si vous souhaitez que le traitement par lots continue de s’exécuter jusqu’à sa fin, entrez *0* (zéro) ou laissez le champ vide. Ce paramètre n’est disponible que si la fonctionnalité associée a été [activée dans votre système](#max-execution-time).

Bien que vous puissiez exécuter la tâche pendant les heures ouvrées normales, nous vous recommandons de l’exécuter en dehors des heures de travail. De cette façon, vous évitez les conflits qui peuvent se produire si un utilisateur travaille avec un enregistrement qui est également en cours de nettoyage.

Si la tâche tente de supprimer un enregistrement d’un élément alors que cet enregistrement est utilisé par un autre utilisateur, une erreur de blocage se produit pour la tâche de nettoyage ou pour l’utilisateur.

Lorsque la tâche s’exécute, sa taille de validation est 100. Cela signifie qu’elle essaiera d’opérer la validation toutes les 100 suppressions. Cependant, comme certaines suppressions sont basées sur des ensembles, il peut exister des scénarios dans lesquels plus de 100 enregistrements peuvent être supprimés dans la même transaction. Par conséquent, des remontées de blocage peuvent parfois se produire.

## <a name="possible-user-impact"></a>Impact possible pour l’utilisateur

Les utilisateurs peuvent être affectés si la tâche de nettoyage des entrées disponibles supprime tous les enregistrements d’un niveau donné (tel que le niveau de contenant). Dans ce cas, la fonctionnalité permettant de voir que le stock était auparavant disponible dans un contenant peut ne pas fonctionner comme prévu, car les entrées disponibles pertinentes ne sont plus disponibles. Cela peut être expérimenté, par exemple, dans les situations suivantes :

- Sur la page **Liste disponible**, lorsque l’utilisateur désélectionne la condition **Quantité \<\> 0** ou sélectionne la condition **Transactions clôturées** dans les paramètres **Affichage des dimensions**.
- Dans un état **Stock physique par dimension de stock** pour les périodes passées, lorsque l’utilisateur définit le paramètre **Date de référence**.

Cependant, l’amélioration des performances fournie par la tâche de nettoyage devrait compenser ces petites pertes de fonctionnalité.

## <a name="make-the-maximum-execution-time-setting-available"></a><a name="max-execution-time"></a>Rendre disponible le paramètre Durée maximale d’exécution

Par défaut, le paramètre **Durée maximale d’exécution** n’est pas disponible. Si vous voulez l’utiliser, vous devez utiliser la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer la fonction associée dans votre système. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Durée d’exécution maximale pour la tâche de nettoyage des entrées disponibles de gestion de l’entrepôt*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]