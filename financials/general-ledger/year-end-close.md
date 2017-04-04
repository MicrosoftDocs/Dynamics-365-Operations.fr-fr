---
title: "Clôture de fin d&quot;exercice"
description: "Cette rubrique décrit le paramétrage et les étapes nécessaires pour exécuter le processus de clôture de fin d&quot;exercice de comptabilité dans."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerClosingSheet
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 926ee087a0e0c4743f29315b1d82c7d37e95be28
ms.openlocfilehash: 22233cfa1df79076c8ea42f75ea309bac990d574
ms.lasthandoff: 03/31/2017


---

# <a name="year-end-close"></a>Clôture de fin d'exercice

Cette rubrique décrit le paramétrage et les étapes nécessaires pour exécuter le processus de clôture de fin d'exercice de comptabilité dans. 

À la fin d'un exercice, vous devez exécuter le processus de clôture de fin d'exercice pour transférer les soldes d'ouverture vers le nouvel exercice. La plupart des organisations exécutera la plusieurs fois dans processus de clôture de fin d'exercice. La première fois assurez d'obtenir les soldes entrés dans le nouvel exercice. La clôture de fin d'exercice peut ensuite être exécutée de nouveau, autant de fois sont requises, permet d'entrer les soldes d'ajuster les entrées dans le nouvel exercice. 

Lors de la fin d'exercice clôturez le processus, figurent deux types de transactions possibles créées. Une transaction d'ouverture est toujours générée et est utilisée pour créer les soldes d'ouverture pour le nouvel exercice. Le schéma de transaction d'ouverture que le compte général de bilan soldes dans le nouvel exercice et soldes des soldes de résultat de compte général dans le compte général Bénéfices non répartis dans le nouvel exercice. La transaction de clôture est également créée pour réduire les soldes des comptes de résultat pour mettre dans l'exercice à zéro est clôturé.

## <a name="prepare-to-run-the-year-end-close"></a>Préparation pour exécuter la clôture de fin d'exercice
Avant d'exécuter le processus de clôture de fin d'exercice, contrôlez les paramètres pour les éléments suivants : 

Sur la page **Compte principal** :

-   Validez ** type de compte principal ** est défini correctement pour chaque compte principal. Le type de compte principal utilisé pour déterminer si le solde du compte principal est apporté en avant comme le solde d'ouverture ou de clôture dans les bénéfices non répartis dans la transaction d'ouverture.
-   ** Compte d'ouverture ** le champ peut être utilisé pour transférer le solde du compte principal dans un nouveau compte principal à la clôture de fin d'exercice. Le compte principal est entré dans ** compte d'ouverture ** le champ. En général qui sera utilisé pour les comptes principaux de bilan lorsque le compte principal est désactivé et un compte principal est utilisé pour le nouvel exercice.

Sous ** paramètres de comptabilité ** la page sous ** clôture d'exercice ** :

-   ** Clôture de suppression des transactions d'année ** l'option permet de spécifier si la transaction d'ouverture générée par le système d'une clôture précédente de fin d'exercice doit être supprimée lors de la clôture de fin d'exercice est exécutée de nouveau. Si cette option est définie ** Oui **, la transaction d'ouverture précédente est supprimée et une nouvelle transaction d'ouverture est créée sur la base de les soldes actuels. Si cette option est définie ** aucun **, la transaction d'ouverture précédente est conservée et une transaction d'ouverture supplémentaire est créée pour déplacer les soldes en avant d'ajuster les transactions validées après la clôture précédente de fin d'exercice.
-   ** Créer des transactions de clôture lors de le transfert ** l'option est utilisée pour créer des transactions de clôture dans l'exercice en cours de clôture afin d'effectuer les soldes des comptes de résultat à zéro. Si cette option est définie ** Oui **, la transaction d'ouverture et la transaction de clôture est créée. Si cette option est définie ** aucun **, seule la transaction d'ouverture est créée dans l'exercice suivant pour transférer les soldes. Les soldes de compte de résultat restent à la fin de l'exercice.
-   ** Définir le statut de l'exercice définitivement sur Clôturé ** l'option est utile de définir l'exercice à un statut définitivement clôturé. Utilisez ce paramètre avec précaution, car toutes les périodes avec le statut définitivement clôturé ne peuvent pas être rouvertes, en empêchant les ajustements à valider sur l'exercice. Il est une pratique de définir ce ** aucun **.
-   ** N° document doit être renseigné ** l'option est utile de définir si un N° document est obligatoire lors de l'exécution du processus de clôture de fin d'exercice. Il est une pratique d'exiger d'un numéro de document afin d'identifier facilement la transaction d'ouverture.

Sous ** calendrier fiscal ** la page :

-   L'exercice suivant doit exister avant d'exécuter la clôture de fin d'exercice. L'exercice suivant est requis pour pouvoir créer des soldes d'ouverture de la période d'ouverture.

Sous ** calendrier comptable ** la page :

-   Facultatif : Chaque période fiscale pour l'exercice en cours de clôture peut être définie ** en attente ** pour empêcher les nouvelles transactions d'être entré. En ajustant des entrées sont identifiés, les périodes en attente peut être rouvert pour valider l'ajustement des entrées, même si le processus de clôture de fin d'exercice a déjà été exécutée.

## <a name="define-year-end-close-templates"></a>Définissez les modèles de clôture de fin d'exercice
Une fois que le système soit configuré, le processus de clôture de fin d'exercice ne peut être exécuté. Sous ** clôture de fin d'exercice ** la page, un modèle peut être défini pour le groupe d'entités juridiques pour lesquelles le processus de clôture de fin d'exercice est exécuté. Le modèle sera réutilisé à chaque clôture de fin d'exercice, mais peut être modifié si votre organisation change. 

Premièrement, définissez ** nom du groupe ** pour le modèle, puis sélectionnez le calendrier fiscal. Le nom du groupe doit identifier le groupe d'entités juridiques incluses.  Par exemple, des modèles peuvent être paramétrée selon géographie, aux groupes distincts créés pour les entités juridiques nord-américaines, les entités juridiques d'AEEM, et les entités juridiques d'APAC. 

Ensuite, les entités juridiques peuvent être ajoutées au modèle. Les entités juridiques peuvent être ajoutées en sélectionnant une hiérarchie organisationnelle ou en sélectionnant les entités juridiques. Si une hiérarchie organisationnelle est activée, seules les entités juridiques dans la hiérarchie qui utilisent le calendrier fiscal sélectionné sont ajoutées au modèle. Si vous utilisez des entités juridiques pour ajouter au modèle, seules les entités juridiques avec le même calendrier fiscal peuvent être ajoutées. Le même calendrier fiscal est nécessaire car la clôture de fin d'exercice est exécutée en sélectionnant un exercice, qui peut varier du calendrier au calendrier. 

Une fois les entités juridiques soient ajoutées, définissez les bénéfices non répartis que les comptes principaux pour chaque entité juridique. ** Date de clôture de fin de l'année dernière ** le champ est mis à jour chaque fois que la clôture de fin d'exercice est exécutée pour l'entité juridique. 

** Dimension financière ** l'onglet permet de définir les dimensions financières sont utilisées dans la transaction d'ouverture. Notez que les paramètres que vous définissez sont pertinents que dans l'entité juridique sélectionnée dans ** des entités juridiques ** la grille. Vous répèterez le paramétrage pour chaque entité juridique dans la grille. 

** Dimensions de bilan de transfert ** permet de définir si les dimensions financières dans les transactions validées dans les comptes de bilan doivent être conservées sur la transaction d'ouverture. Il est une pratique de définir cette option ** Oui **. ** Dimensions de résultat de transfert ** permet de définir les dimensions financières dans les transactions validées sur le compte de résultat sera transféré vers le compte principal Bénéfices non répartis. Premièrement, identifiez les dimensions financières concernant l'entité juridique sélectionnée. Cela inclut toutes les dimensions financières validées avec au cours de l'année, même si la dimension financière n'est pas partie d'une structure de compte active. Ensuite, définissez chaque dimension comme ou ** clôture seul ** ou ** clôturer tous **.  La valeur par défaut est ** clôturer tous **, contenant les valeurs de dimension financière d'origine des transactions validées et les utilise pour créer des soldes d'ouverture pour le compte Bénéfices non répartis. Separate bénéfices non répartis que des soldes d'ouverture sont créées pour chaque seule combinaison des valeurs de dimension financière. Si ** clôture seul ** est sélectionné, toutes les transactions validées avec cette dimension financière sont résumées dans un solde d'ouverture Bénéfices non répartis pour la valeur de dimension entrée dans le champ après ** clôture seul **. Par exemple, supposons que toutes les transactions pour l'exercice ont été validées avec structure de compte principal - Département. Dans la dimension financière Département dans le modèle, ** clôture seul ** est sélectionné et 100 est la valeur entrée. Si le revenu de toutes les transactions validait aux départements 200, 300, et 400 est euros, le solde d'ouverture sont créés pour les bénéfices Retained - 100. Si vous sélectionnez ** clôture seul ** et désactivez la de valeurs de dimensions financières, toutes les transactions valider aux bénéfices non répartis avec cette valeur de dimension est vide. 

Le processus de clôture de fin d'exercice ne s'applique pas aux structures de compte. Cela est dû au fait que les structures de compte peuvent changer au cours à un d'exercice et il n'est pas toujours possible d'identifier la structure de compte approprié en raison de ces modifications.  Lorsque des transactions d'ouverture sont créées, les soldes seront apportés en avant à partir de les dimensions financières selon les définis dans le modèle de clôture de fin d'exercice. Les entrées de soldes d'ouverture ne peuvent inclure des dimensions financières plus dans les combinaisons actuelles de structure de compte et de segment qui ne sont plus valides dans la structure de compte actuelle. Si votre organisation souhaite exclure une dimension financière pour le solde d'ouverture retenu de rémunération, définissez la dimension financière soient ** clôture seul ** et pour permettre la valeur de dimension vide.

## <a name="run-the-year-end-close-process"></a>Permet d'exécuter le processus de clôture de fin d'exercice
Une fois les modèles de clôture de fin d'exercice soient créés, le processus de clôture de fin d'exercice est initialisé en choisissant ** exercice d'exécution ** du volet Actions. Permet de sélectionner toutes les règles ou un sous-ensemble entités juridiques du modèle pour lequel exécute la fin d'exercice clôturer. Lors de l'exécution de la clôture de fin d'exercice pour la première fois dans un exercice, vous choisirez vraisemblablement toutes les entités juridiques pour créer des soldes d'ouverture pour toutes les entités juridiques. Si vous exécutez une clôture de fin d'exercice de nouveau, vous pouvez choisir d'exécuter le processus que pour les entités juridiques pour lesquelles ajustant des entrées ont été validés. 

Permet de sélectionner l'exercice pour lequel vous souhaitez exécuter le processus de clôture de fin d'exercice. Si plusieurs périodes de clôture existe pour la dernière période de l'exercice, ** nom de la période ** le champ devient disponible et vous pouvez choisir la période de clôture pour valider la transaction de clôture, si le paramétrage est défini pour créer la transaction de clôture. 

Entrez un N° document, qu'ou ne peut pas être requis, selon le paramétrage défini dans les paramètres de la comptabilité. Le même numéro de document sera utilisé pour toutes les entités juridiques sélectionnées pour le processus de clôture de fin d'exercice. Le n° document n'est pas généré à partir d'une souche de numéros. Il est une pratique d'entrer un N° document, même si elle n'est pas nécessaire. Un numéro de document facilite rechercher la transaction d'ouverture dans le nouvel exercice. Si un N° document n'est pas complété, le document est vide pour la transaction d'ouverture. 

Si vous souhaitez contrepasser une clôture précédente de fin d'exercice pour l'exercice sélectionné, définissez ** d'annuler la clôture précédente ** ** Oui **. La clôture de fin d'exercice est contrepassée, mais il peut être repassé à tout moment. Si vous contrepassez une clôture de fin d'exercice, ** date de clôture de fin de l'année dernière ** sont pas disponible. 

Le processus de clôture de fin d'exercice qui est à exécuter par lots. Il est une pratique d'exécuter le traitement par lots, pour autoriser l'utilisateur au retour à d'autres activités. Une fois le processus de clôture de fin d'exercice terminé, ** date de clôture de fin de l'année dernière ** est mis à jour avec la date de la session.

Pour plus d'informations, voir [fermez la comptabilité à la fin de période] (close-general-ledger-at-period-end.md).


