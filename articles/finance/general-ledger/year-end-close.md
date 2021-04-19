---
title: Clôture de fin d’exercice
description: Cette rubrique décrit le paramétrage et les étapes nécessaires pour exécuter le processus de clôture de fin d’exercice dans la comptabilité.
author: kweekley
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cdb81df1701851330b0501c03e41eb10e639bc77
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842318"
---
# <a name="year-end-close"></a>Clôture de fin d’exercice

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le paramétrage et les étapes nécessaires pour exécuter le processus de clôture de fin d’exercice dans la comptabilité. 

À la fin d’un exercice, vous devez exécuter le processus de clôture de fin d’exercice pour transférer les soldes d’ouverture vers la nouvelle année. La plupart des organisations exécutent le processus de clôture de fin d’exercice plusieurs fois. La première fois sert à déplacer les soldes vers le nouvel exercice. La clôture de fin d’exercice peut ensuite être exécutée de nouveau, autant de fois que nécessaire, pour déplacer les soldes des entrées d’ajustement vers le nouvel exercice. 

Lors du processus de clôture de fin d’exercice, il existe deux types de transactions possibles. Une transaction d’ouverture est toujours générée et sert à créer les soldes d’ouverture dans le nouvel exercice. La transaction d’ouverture montre les soldes du compte général de bilan dans le nouvel exercice et les soldes des comptes de résultat dans le compte général des bénéfices non répartis dans le nouvel exercice. La transaction de clôture est créée de manière facultative pour réduire à zéro les soldes des comptes de résultat dans l’exercice en cours de clôture.

## <a name="prepare-to-run-the-year-end-close"></a>Préparation de la clôture de fin d’exercice
Avant d’exécuter le processus de clôture de fin d’exercice, validez les paramètres pour les éléments suivants : 

Sur la page **Compte principal** :

-   Vérifiez que le **Type de compte principal** est défini correctement pour chaque compte principal. Le type de compte principal sert à déterminer si le solde du compte principal doit être transféré comme solde d’ouverture ou clôturé dans les bénéfices non répartis dans la transaction d’ouverture.
-   Le champ **Compte d’ouverture** peut servir à transférer le solde du compte principal dans un nouveau compte principal pendant la clôture de fin d’exercice. Le nouveau compte principal est entré dans le champ **Compte d’ouverture**. En général, il sera utilisé pour les comptes principaux de bilan lorsque le compte principal est désactivé et qu’un nouveau compte principal est utilisé pour le nouvel exercice.

Dans la page **Paramètres de comptabilité** sous **Clôture d’exercice**:

-   L’option **Supprimer les transactions de clôture d’exercice** sert à spécifier si la transaction d’ouverture générée par le système d’une clôture de fin d’exercice précédente doit être supprimée lors de la nouvelle exécution de la clôture de fin d’exercice. Si cette option est définie sur **Oui**, la transaction d’ouverture précédente est supprimée et une nouvelle transaction d’ouverture est créée sur la base des soldes actuels. Si cette option est définie sur **Non**, la transaction d’ouverture précédente est conservée et une transaction d’ouverture supplémentaire est créée pour transférer les soldes à partir des transactions d’ajustement validées après la clôture de fin d’exercice précédente.
-   L’option **Créer des transactions de clôture lors du transfert** sert à créer des transactions de clôture dans l’exercice en cours de clôture afin de réduire à zéro les soldes des comptes de résultat. Si cette option est définie sur **Oui**, les transactions de clôture et d’ouverture sont toutes les deux créées. Si cette option est définie sur **Non**, seule la transaction d’ouverture est créée dans l’exercice suivant pour transférer les soldes. Les soldes de compte de résultat restent à la fin de l’exercice.
-   L’option **Définir le statut de l’exercice sur définitivement clôturé** sert à affecter à l’exercice le statut Définitivement clôturé. Utilisez ce paramètre avec précaution, car toutes les périodes ayant le statut définitivement clôturé ne peuvent plus être ouvertes, ce qui empêche de valider les ajustements dans l’exercice. Il est recommandé de définir cette option sur **Non**.
-   L’option **Le N° de justificatif est obligatoire** sert à définir si un N° de justificatif est requis lors de l’exécution du processus de clôture de fin d’exercice. Il est recommandé de demander un N° de justificatif afin d’identifier facilement la transaction d’ouverture.

Dans la page **Calendrier fiscal** :

-   l’exercice suivant doit exister avant d’exécuter la clôture de fin d’exercice. L’exercice suivant est requis pour pouvoir créer les soldes de début de la période d’ouverture.

Sur la page **Calendrier comptable** :

-   facultatif : chaque période fiscale pour l’exercice en cours de clôture peut être définie sur **En attente** pour empêcher de saisir de nouvelles transactions. Lorsque des entrées d’ajustement sont identifiées, les périodes en attente peut être rouvertes pour valider les entrées d’ajustement, même si le processus de clôture de fin d’exercice a déjà été exécuté.

## <a name="define-year-end-close-templates"></a>Définir des modèles de clôture de fin d’exercice
Une fois le système configuré, le processus de clôture de fin d’exercice peut être exécuté. Dans la page **Clôture de fin d’exercice**, il est possible de définir un modèle pour le groupe d’entités juridiques pour lesquelles le processus de clôture de fin d’exercice doit être exécuté. Le modèle sera réutilisé à chaque clôture de fin d’exercice, mais peut être modifié si votre organisation change. 

Tout d’abord, définissez le **Nom du groupe** pour le modèle et sélectionnez le calendrier fiscal. Le nom du groupe doit identifier le groupe d’entités juridiques incluses.  Par exemple, les modèles peuvent être configurés selon des critères géographiques, avec des groupes distincts créés pour les entités juridiques d’Amérique du Nord, de la zone EMEA et de la zone APAC. 

Ensuite, des entités juridiques peuvent être ajoutées au modèle. Des entités juridiques peuvent être ajoutées en sélectionnant une hiérarchie organisationnelle ou en sélectionnant les entités juridiques. Si une hiérarchie organisationnelle est sélectionnée, seules les entités juridiques de la hiérarchie qui utilisent le calendrier fiscal sélectionné sont ajoutées au modèle. Si vous utilisez les entités juridiques pour les ajouter au modèle, seules les entités juridiques ayant le même calendrier fiscal peuvent être ajoutées. Le même calendrier fiscal est nécessaire parce que la clôture de fin d’exercice est exécutée en sélectionnant un exercice, lequel peut varier d’un calendrier à l’autre. 

Une fois les entités juridiques ajoutées, définissez les comptes principaux de bénéfices non répartis pour chaque entité juridique. Le champ **Date de la dernière clôture de fin d’exercice** est mis à jour chaque fois que la clôture de fin d’exercice est exécutée pour l’entité juridique. 

L’onglet **Dimension financière** sert à définir les dimensions financières utilisées dans la transaction d’ouverture. Notez que les paramètres que vous définissez ne sont pertinents que dans l’entité juridique sélectionnée dans la grille **Entités juridiques**. Vous répèterez le paramétrage pour chaque entité juridique de la grille. 

L’option **Transférer les dimensions du bilan** sert à définir si les dimensions financières dans les transactions validées dans les comptes de bilan doivent être conservées dans la transaction d’ouverture. Il est recommandé de définir cette option sur **Oui**. L’option **Transférer les dimensions du résultat** sert à définir quelles dimensions financières des transactions validées dans le compte de résultat seront transférées vers le compte principal de bénéfices non répartis. Tout d’abord, identifiez les dimensions financières concernant l’entité juridique sélectionnée. Cela inclut toutes les dimensions financières validées au cours de l’année, même si la dimension financière ne fait pas partie d’une structure de compte active. Ensuite, définissez chaque dimension comme **Clôturer individuellement** ou **Clôturer tout**.  La valeur par défaut est **Clôturer tout**, qui conserve les valeurs d’origine de dimension financière des transactions validées et les utilise pour créer les soldes d’ouverture pour le compte des bénéfices non répartis. Des soldes de départ distincts des bénéfices non répartis seront créés pour chaque combinaison unique de valeurs de dimension financière. Si **Clôturer individuellement** est sélectionné, toutes les transactions validées avec cette dimension financière sont résumées dans un solde d’ouverture de bénéfices non répartis pour la valeur de dimension entrée dans le champ après **Clôturer individuellement**. Par exemple, supposons que toutes les transactions pour l’exercice ont été validées avec la structure de compte Compte principal – Département. Dans la dimension financière Département dans le modèle, **Clôturer individuellement** est sélectionné, et la valeur 100 est entrée. Si le revenu total de toutes les transactions validées dans les départements 200, 300 et 400 est de 100 000 euros, un solde d’ouverture est créé pour les bénéfices non répartis – 100. Si vous sélectionnez **Clôturer individuellement** et laissez vierge la valeur de dimension financière, toutes les transactions seront validées dans les bénéfices non répartis avec cette valeur de dimension vierge. 

Le processus de clôture de fin d’exercice ne s’applique pas aux structures de compte. Cela est dû au fait que les structures de compte peuvent changer tout au long d’un exercice et qu’il n’est pas toujours possible d’identifier la structure de compte concernée en raison de ces modifications.  Lorsque des transactions d’ouverture sont créées, les soldes seront transférés avec les dimensions financières telles qu’elles ont été définies dans le modèle de clôture de fin d’exercice. Les entrées de soldes d’ouverture ne peuvent plus inclure de dimensions financières dans la structure de compte actuelle et dans les combinaisons de segments qui ne sont plus valides dans la structure de compte actuelle. Si votre organisation souhaite exclure une dimension financière pour le solde d’ouverture du compte de bénéfices non répartis, définissez la dimension financière sur **Clôturer individuellement** et laissez vierge la valeur de la dimension.

## <a name="run-the-year-end-close-process"></a>Exécution de la clôture de fin d’exercice
Une fois les modèles de clôture de fin d’exercice créés, le processus de clôture de fin d’exercice est initialisé en sélectionnant **Exécuter la clôture fiscale** dans le volet Action. Sélectionnez la totalité ou un sous-ensemble d’entités juridiques à partir du modèle pour lequel exécuter la clôture de fin d’exercice. Lors de l’exécution de la clôture de fin d’exercice pour la première fois dans un exercice, vous choisirez vraisemblablement toutes les entités juridiques pour créer des soldes d’ouverture pour chacune. Si vous exécutez à nouveau la clôture de fin d’exercice, vous pouvez choisir d’exécuter le processus uniquement pour les entités juridiques pour lesquelles des entrées d’ajustement ont été validées. 

Sélectionnez l’exercice pour lequel vous souhaitez exécuter le processus de clôture de fin d’exercice. S’il existe plusieurs périodes de clôture pour la dernière période de l’exercice, le champ **Nom de la période** devient disponible et vous pouvez choisir la période de clôture pour valider la transaction de clôture, si le paramétrage est défini de sorte à créer la transaction de clôture. 

Entrez un N° de justificatif, lequel peut être obligatoire ou non, selon le paramétrage défini dans les paramètres de comptabilité. Le même N° de justificatif sera utilisé pour toutes les entités juridiques sélectionnées pour le processus de clôture de fin d’exercice. Le N° de justificatif n’est pas généré à l’aide d’une souche de numéros. Il est recommandé d’entrer un N° de justificatif, même s’il n’est pas obligatoire. L’entrée d’un N° de justificatif facilite la recherche de la transaction d’ouverture dans le nouvel exercice. Si un N° document n’est pas indiqué, le N° de justificatif sera vide pour la transaction d’ouverture. 

Si vous souhaitez annuler une clôture de fin d’exercice précédente pour l’exercice sélectionné, définissez l’option **Annuler la clôture précédente** sur **Oui**. La clôture de fin d’exercice sera annulée, mais le processus pourra être exécuté à nouveau à tout moment. Si vous annulez une clôture de fin d’exercice, la **Date de la dernière clôture de fin d’exercice** sera indisponible. 

Le processus de clôture de fin d’exercice s’exécute par défaut en mode de traitement par lots. Il est recommandé d’exécuter le processus en mode de traitement par lots, pour permettre à l’utilisateur de revenir à d’autres activités. Une fois le processus de clôture de fin d’exercice terminé, la **Date de la dernière clôture de fin d’exercice** est mise à jour à la date de la session.

Pour plus d’informations, voir [Clôture de la comptabilité en fin de période](close-general-ledger-at-period-end.md) et [Clôturer l’exercice](tasks/close-fiscal-year.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]