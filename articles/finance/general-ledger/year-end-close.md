---
title: Clôture de fin d’exercice
description: Cet article décrit le paramétrage et les étapes nécessaires pour exécuter le processus de clôture de fin d’exercice dans la comptabilité.
author: kweekley
ms.date: 11/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e1c7722b560246fb597f0b7f91a70afecf69e22
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779741"
---
# <a name="year-end-close"></a>Clôture de fin d’exercice

[!include [banner](../includes/banner.md)]

Cet article décrit le paramétrage et les étapes nécessaires pour exécuter le processus de clôture de fin d’exercice dans la comptabilité.

À la fin d’un exercice, vous devez exécuter le processus de clôture de fin d’exercice pour transférer les soldes d’ouverture vers la nouvelle année. La plupart des organisations exécutent le processus de clôture de fin d’exercice plusieurs fois. La première exécution déplace les soldes dans le nouvel exercice comptable. Le processus peut être réexécuté autant que nécessaire pour déplacer les soldes des entrées d’ajustement vers le nouvel exercice.

Lors du processus de clôture de fin d’exercice, il existe deux types de transactions possibles. Une transaction d’ouverture est toujours générée et sert à créer les soldes d’ouverture dans le nouvel exercice. La transaction d’ouverture montre les soldes du compte général de bilan dans le nouvel exercice et les soldes des comptes de résultat dans le compte général des bénéfices non répartis dans le nouvel exercice. La transaction de clôture est créée de manière facultative pour réduire à zéro les soldes des comptes de résultat dans l’exercice en cours de clôture.

## <a name="prepare-to-run-the-year-end-close"></a>Préparation de la clôture de fin d’exercice

Avant d’exécuter le processus de clôture de fin d’exercice, validez les paramètres pour les éléments suivants :

Sur la page **Compte principal** :

- Vérifiez que le champ **Type de compte principal** est correctement défini pour chaque compte principal. Le type de compte principal détermine si le solde du compte principal doit être transféré comme solde d’ouverture ou clôturé dans les bénéfices non répartis dans la transaction d’ouverture.
- Le solde du compte principal peut être transféré dans un nouveau compte principal pendant la clôture de fin d’exercice. Entrez le nouveau compte principal dans le champ **Compte d’ouverture**. En général, ce champ est utilisé pour les comptes principaux de bilan lorsque le compte principal est désactivé et qu’un nouveau compte principal est utilisé pour le nouvel exercice.

Dans la page **Paramètres de comptabilité** sous **Clôture d’exercice**:

- L’option **Supprimer les entrées de fin d’exercice existantes à la re-clôture d’exercice** sert à spécifier si la transaction d’ouverture générée par le système d’une clôture de fin d’exercice précédente doit être supprimée lors de la nouvelle exécution de la clôture de fin d’exercice. Si cette option est définie sur **Oui**, les transactions d’ouverture et de clôture facultatives précédentes sont supprimées et une nouvelle transaction d’ouverture ou de clôture est créée sur la base des soldes actuels. Si cette option est définie sur **Non**, les transactions d’ouverture et de clôture facultatives précédentes sont conservées et une transaction d’ouverture ou de clôture supplémentaire est créée pour transférer les soldes à partir des transactions d’ajustement qui ont été validées après la clôture de fin d’exercice précédente.
- L’option **Créer des transactions de clôture lors du transfert** sert à créer des transactions de clôture dans l’exercice en cours de clôture afin de réduire à 0 (zéro) les soldes de tous les comptes principaux. Si cette option est définie sur **Oui**, les transactions de clôture et d’ouverture sont toutes les deux créées. Si cette option est définie sur **Non**, seule la transaction d’ouverture est créée dans l’exercice suivant pour transférer les soldes. Les soldes de tous les comptes principaux restent à la fin de l’exercice.
- L’option **Définir le statut de l’exercice sur définitivement clôturé** sert à affecter à l’exercice le statut Définitivement clôturé. Utilisez cette option avec précaution, car les périodes dont le statut est Définitivement fermé ne peuvent pas être rouvertes. Par conséquent, les ajustements ne peuvent pas être imputés à l’exercice. Il est recommandé de définir cette option sur **Non**.
- L’option **Le N° document est obligatoire** a été supprimée. Un N° document est désormais requis lors de l’exécution du processus de clôture de fin d’exercice. Le N° document est saisi manuellement à ce moment-là.

Dans la page **Calendrier fiscal** :

- l’exercice suivant doit exister avant d’exécuter la clôture de fin d’exercice. Sinon, les soldes d’ouverture ne peuvent pas être créés dans la période d’ouverture.

Sur la page **Calendrier comptable** :

- facultatif : chaque période fiscale pour l’exercice en cours de clôture peut être définie sur **En attente** pour empêcher de entrer de nouvelles transactions. Lorsque des entrées d’ajustement sont identifiées, les périodes en attente peut être rouvertes afin de valider les entrées d’ajustement, même si le processus de clôture de fin d’exercice a déjà été exécuté.

Sur la page **Configuration du modèle de clôture de fin d’exercice** :

- Quand la fonctionnalité **Améliorations de la fin d’exercice comptable** est activée, le processus de configuration du modèle de clôture de fin d’exercice est séparé du processus d’exécution de la clôture de fin d’exercice. Le modèle peut être défini sur la page **Configuration du modèle de clôture de fin d’exercice** (**Comptabilité \> Configuration de la comptabilité \> Configuration du modèle de clôture de fin d’exercice**), ou il est accessible depuis le processus de clôture de fin d’exercice.

## <a name="define-year-end-close-templates"></a>Définir des modèles de clôture de fin d’exercice

Une fois la configuration configurée, le processus de clôture de fin d’exercice peut être exécuté. Dans la page **Configuration du modèle de clôture de fin d’exercice**, il est possible de définir un modèle pour le groupe d’entités juridiques pour lesquelles le processus de clôture de fin d’exercice doit être exécuté. Le modèle sera réutilisé à chaque clôture de fin d’exercice, mais il peut être modifié si votre organisation change.

Tout d’abord, définissez le champ **Nom du groupe** pour le modèle et sélectionnez le calendrier fiscal. Le nom du groupe doit identifier le groupe des entités juridiques incluses. Lorsque vous déterminez les groupes d’entités juridiques, n’oubliez pas que les entités juridiques peuvent être incluses dans le même groupe uniquement si le même calendrier fiscal est sélectionné pour elles. Par exemple, les modèles peuvent être configurés selon des critères géographiques, et des groupes distincts peuvent être créés pour les entités juridiques d’Amérique du Nord, de la zone EMEA (Europe-Moyen-Orient-Afrique) et de la zone APAC (Asie-Pacifique).

Ensuite, des entités juridiques peuvent être ajoutées au modèle. Des entités juridiques peuvent être ajoutées en sélectionnant une hiérarchie organisationnelle ou en sélectionnant les entités juridiques. Si une hiérarchie organisationnelle est sélectionnée, seules les entités juridiques de la hiérarchie qui utilisent le calendrier fiscal sélectionné sont ajoutées au modèle. Si vous utilisez les entités juridiques pour les ajouter au modèle, seules les entités juridiques ayant le même calendrier fiscal peuvent être ajoutées. Le même calendrier fiscal est nécessaire parce que la clôture de fin d’exercice est exécutée en sélectionnant un exercice, lequel peut varier d’un calendrier à l’autre.

Une fois les entités juridiques ajoutées, définissez les comptes principaux de bénéfices non répartis pour chaque entité juridique.

L’onglet **Dimension financière** sert à définir les dimensions financières utilisées dans la transaction d’ouverture. Notez que le paramétrage de cet onglet ne s’applique qu’à l’entité juridique sélectionnée dans la grille **Entités juridiques**. Vous devez répéter le paramétrage pour chaque entité juridique de la grille.

L’option **Transférer les dimensions du bilan** sert à spécifier si les dimensions financières dans les transactions validées dans les comptes de bilan doivent être conservées dans la transaction d’ouverture. Il est recommandé de définir cette option sur **Oui**. Le paramétrage des dimensions du bilan n’affecte pas les soldes existants dans les comptes généraux des bénéfices non répartis. Ces soldes sont déterminés par les dimensions de profits et pertes définies dans la section suivante. Par exemple, l’exercice 2019 était la première année qui a été clôturée, et l’option **Clôturer tout** a été utilisée pour sélectionner les dimensions **Département** et **Centre de coûts** pour la clôture. Dans ce cas, un compte de bénéfices non répartis distinct a été créé pour chaque combinaison d’un département et d’un centre de coûts. Lors de la clôture de l’exercice 2020, les bénéfices non répartis de l’exercice précédent demeurent tels qu’ils ont été validés, même si l’option **Transférer les dimensions du bilan** est définie sur **Non**. Les soldes validés dans les bénéfices non répartis des clôtures d’exercices précédents ne sont jamais modifiés.

La section **Transférer les dimensions du résultat** sert à spécifier quelles dimensions financières des transactions validées dans les comptes de résultat seront transférées vers le compte principal de bénéfices non répartis. Tout d’abord, identifiez les dimensions financières pertinentes pour l’entité juridique sélectionnée. Ces dimensions financières comprennent toutes les dimensions financières validées au cours de l’année, même si la dimension financière ne fait pas partie d’une structure de compte active. Ensuite, définissez chaque dimension comme **Clôturer individuellement** ou **Clôturer tout**. L’option par défaut est **Clôturer tout**. Cette option conserve les valeurs d’origine de dimension financière des transactions validées et les utilise pour créer les soldes d’ouverture pour le compte des bénéfices non répartis. Des soldes de départ distincts des bénéfices non répartis seront créés pour chaque combinaison unique de valeurs de dimension financière. Si **Clôturer individuellement** est sélectionné, toutes les transactions validées avec cette dimension financière sont résumées dans un solde d’ouverture de bénéfices non répartis pour la valeur de dimension entrée dans le champ qui s’affiche après **Clôturer individuellement**. Par exemple, toutes les transactions pour l’exercice ont été validées avec la structure de compte **Compte principal – Département**. Pour la dimension financière **Département** du modèle, **Clôturer individuellement** est sélectionné, et la valeur **100** est saisie comme valeur de dimension. Si le revenu total de toutes les transactions validées dans les départements 200, 300 et 400 est de 100 000 euros, un solde d’ouverture est créé pour les **Bénéfices non répartis – 100**. Si vous sélectionnez **Clôturer individuellement**, mais laissez vierge la valeur de dimension financière, toutes les transactions seront validées dans les bénéfices non répartis, et la valeur de dimension demeurera vierge.

## <a name="run-the-year-end-close-process"></a>Exécution de la clôture de fin d’exercice

Une fois les modèles de clôture de fin d’exercice créés, vous pouvez lancer le processus de clôture de fin d’exercice sur la page **Clôture de fin d’exercice** (**Comptabilité \> Clôture de période \> Clôture de fin d’exercice**). Avant d’exécuter la clôture de fin d’exercice, vous pouvez ajouter de nouveaux modèles de clôture de fin d’exercice ou modifier les modèles existants en sélectionnant **Configuration du modèle de clôture de fin d’exercice** pour ouvrir la page de configuration des modèles.

Sélectionnez le modèle de clôture de fin d’exercice, puis, dans le volet Actions, sélectionnez **Exécuter la clôture de fin d’exercice**. Sélectionnez la totalité ou un sous-ensemble d’entités juridiques à partir du modèle pour lequel vous exécutez la clôture de fin d’exercice. Si vous exécutez la clôture de fin d’exercice pour la première fois dans un exercice, vous sélectionnerez vraisemblablement toutes les entités juridiques afin de créer des soldes d’ouverture pour chacune. Si vous avez précédemment exécuté la clôture de fin d’exercice, vous pouvez souhaiter la réexécuter uniquement pour les entités juridiques pour lesquelles des entrées d’ajustement ont été validées.

Ensuite, sélectionnez l’exercice pour lequel exécuter le processus de clôture de fin d’exercice. S’il existe plusieurs périodes de clôture pour la dernière période de l’exercice, le champ **Nom de la période** devient disponible. Vous pouvez ensuite sélectionner la période de clôture à utiliser pour valider la transaction de clôture, si le paramétrage est défini de manière à créer la transaction de clôture.

Ensuite, entrez un N° document. Le même N° document sera utilisé pour toutes les entités juridiques que vous avez sélectionnées pour le processus de clôture de fin d’exercice. Le N° document n’est pas généré à l’aide d’une souche de numéros.

Par défaut, le processus de clôture de fin d’exercice s’exécute en mode de traitement par lots. Par conséquent, après l’avoir lancé, vous pouvez retourner à d’autres activités.

Étant donné que les structures de compte peuvent changer au cours d’un exercice, la structure de compte pertinente ne peut pas toujours être identifiée. Par conséquent, le processus de clôture de fin d’exercice ne respecte pas les structures de compte. Lorsque des transactions d’ouverture sont créées, les soldes sont transférés avec les dimensions financières telles qu’elles ont été définies dans le modèle de clôture de fin d’exercice. Les entrées de soldes d’ouverture peuvent inclure des dimensions financières qui n’existent plus dans la structure de compte actuelle et des combinaisons de segments qui ne sont plus valides dans la structure de compte actuelle. Si votre organisation souhaite exclure une dimension financière pour le solde d’ouverture du compte de bénéfices non répartis, définissez la dimension financière sur **Clôturer individuellement** et laissez vierge la valeur de la dimension.

Une fois le processus terminé, un enregistrement est créé pour chaque combinaison d’une entité juridique et d’un exercice. Vous ne verrez que les enregistrements des entités juridiques auxquelles vous avez accès. Chaque enregistrement comprend la date et l’heure système auxquelles le processus a été exécuté, ainsi qu’un lien direct vers les pièces justificatives créées pour la clôture de l’exercice.

[![Enregistrements créés dans le raccourci Historique de clôture de fin d’exercice de la page Clôture de fin d’exercice](./media/run-yr-end-close.png)](./media/run-yr-end-close.png)

Si vous relancez la clôture de fin d’exercice, vous verrez un ou plusieurs enregistrements pour chaque combinaison d’une entité juridique et d’un exercice, en fonction du paramétrage de l’option **Supprimer les entrées de fin d’exercice existantes à la re-clôture d’exercice** sur la page **Paramètres de comptabilité** :

- Si l’option est définie sur **Oui**, le N° document de la clôture d’exercice précédente est supprimé. L’enregistrement est marqué comme **Annulé**, et est estampillé de la date et de l’heure à laquelle l’annulation a été effectuée. De plus, le lien vers le N° document est supprimé. Lorsque la clôture de fin d’exercice est terminée, un nouvel enregistrement est créé pour le nouveau N° document qui est créé.
- Si l’option est définie sur **Non**, l’enregistrement de la clôture d’exercice précédente est conservé, ainsi que le lien vers le N° document. Chaque fois que la clôture de fin d’exercice est réexécutée, un nouvel enregistrement est créé, accompagné d’un lien vers les nouveaux N° documents.

## <a name="reverse-the-year-end-close-process"></a>Annuler le processus de clôture de fin d’exercice

Sur la page **Clôture de fin d’exercice**, vous pouvez annuler une clôture de fin d’exercice. Sélectionnez l’enregistrement concernant la combinaison d’une entité juridique et d’un exercice qui doit être annulé, puis sélectionnez **Annuler la clôture de fin d’exercice**. Le processus d’annulation supprime toutes les pièces justificatives d’ouverture et de clôture qui ont été créées pour l’exercice. L’enregistrement est marqué comme **Annulé**, et est estampillé de la date et de l’heure à laquelle l’annulation a été effectuée. De plus, le lien vers le N° document est supprimé. À l’instar du processus de clôture de fin d’exercice, l’annulation s’exécute en mode de traitement par lots.

Une case à cocher **Afficher annulés**, disponible au-dessus de la grille, vous permet de masquer ou d’afficher les enregistrements des processus de clôture de fin d’exercice inversés. Après avoir exécuté le processus **Annuler la clôture de fin d’exercice**, vous devrez peut-être sélectionner la case à cocher **Afficher annulés** pour voir l’enregistrement. Vous pouvez définir des filtres supplémentaires pour afficher d’autres informations.

[![Utilisation de la case à cocher Afficher annulés pour afficher les enregistrements des processus de clôture de fin d’exercice annulés sur la page Clôture de fin d’exercice](./media/rvrs-yr-end-close.png)](./media/rvrs-yr-end-close.png)

Pour plus d’informations, voir [Clôture de la comptabilité en fin de période](close-general-ledger-at-period-end.md) et [Clôturer l’exercice](tasks/close-fiscal-year.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
