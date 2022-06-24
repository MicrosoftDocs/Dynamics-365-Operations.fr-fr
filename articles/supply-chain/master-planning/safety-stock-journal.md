---
title: Utiliser le journal du stock de sécurité pour mettre à jour la couverture minimale pour les articles
description: Cet article explique comment utiliser le journal du stock de sécurité pour mettre à jour la quantité de stock de sécurité pour les articles en calculant les propositions de couverture minimale en fonction des transactions historiques.
author: t-benebo
ms.date: 10/28/2021
ms.topic: article
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, ReqItemTableSetup, ReqItemTable, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-28
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 385144738b83fcf6873eae5204b4784d6ecd5b80
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851767"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage-for-items"></a>Utiliser le journal du stock de sécurité pour mettre à jour la couverture minimale pour les articles

[!include [banner](../../includes/banner.md)]

Le stock de sécurité est une quantité supplémentaire d’un article détenu en stock pour réduire le risque de rupture de stock de l’article. Le stock de sécurité est utilisé comme tampon dans le cas où des commandes client arrivent mais que le fournisseur ne peut pas respecter la date d’expédition demandée par le client.

Cet article décrit comment utiliser le journal de stock de sécurité pour calculer des propositions de couverture minimale basées sur des transactions historiques et comment mettre à jour la couverture d’article avec ces propositions.

## <a name="overview-of-minimum-coverage-usage"></a>Vue d’ensemble de l’utilisation minimale de la couverture

Un stock de sécurité est configuré sur la page **Articles couverts** pour chaque article. Différents types de réapprovisionnement sont représentés par différents codes de couverture. (Pour plus d’informations, voir [Réapprovisionnement du stock de sécurité pour les articles](safety-stock-replenishment.md).) Cependant, tous les codes de couverture utilisent la valeur définie dans le champ **Minimum** sur la page **Articles couverts** pour chaque article. Il existe deux grandes approches pour utiliser le champ **Minimum** :

- **Quantité minimale à des fins min/max** – Cette approche utilise la quantité minimale avec la logique min/max. Elle s’applique lorsque le champ **Code de couverture** est défini sur *Min/max* pour l’article ou le groupe de couverture concerné. La quantité **Minimum** représente l’utilisation quotidienne moyenne multipliée par le délai de livraison de l’article.
- **Quantité minimale aux fins du plan de stock** – Cette approche utilise la quantité minimale pour représenter un plan de stock en combinaison avec des prévisions de demande. Elle s’applique lorsque le champ **Code de couverture** est défini sur *Période* ou *Besoin* pour l’article ou le groupe de couverture concerné. La quantité **Minimum** représente un plan de stock qui reflète le niveau de service clientèle souhaité pour aider à réduire les ruptures de stock, les expéditions partielles et les délais de livraison. La quantité minimale reflète un pourcentage de précision des prévisions pour un article donné. Elle ne représente pas une position de stock souhaitée.

La valeur **Minimum** peut être définie de trois manières :

- Manuellement, sur la page **Couverture de l’article**
- À l’aide de la structure Gestion des données (entités de données *Couverture d’article*)
- Par le calcul du stock de sécurité effectué par les journaux du stock de sécurité

## <a name="calculate-minimum-coverage-based-on-historical-usage"></a>Calculer la couverture minimale en fonction de l’utilisation historique

Les journaux de stock de sécurité sont utilisés pour calculer une quantité minimale proposée en fonction de l’utilisation historique d’un article, soit à des fins min/max, soit à des fins de plan de stock. L’utilisation historique représente toutes les transactions d’émission au cours d’une période spécifiée. Ces transactions de sortie comprennent les transactions de commande client et les ajustements de stock. Les calculs identifient également l’impact de la quantité minimale proposée sur la valeur des stocks et la variation de la valeur des stocks par rapport aux quantités minimales actuelles.

Chaque ligne du journal du stock de sécurité représente un article et ses dimensions de couverture. Ces lignes de journal sont créées et affichées sur les pages **Lignes journal du stock de sécurité** (**Planification \> Planification \> Exécuter \> Calcul du stock de sécurité**). Le processus de gestion d’utilisation des journaux du stock de sécurité pour calculer les quantités minimales proposées est décrit plus loin dans cet article.

Le planificateur utilise un journal du stock de sécurité pour calculer les quantités minimales proposées pour les articles sélectionnés, en fonction de l’utilisation historique au cours des périodes sélectionnées. Les minima proposés peuvent être remplacés manuellement si nécessaire, et vous pouvez examiner l’impact potentiel des minima proposés sur la valeur du stock. Lors de la validation du journal, les quantités minimales associées dans la couverture article sont automatiquement mises à jour.

### <a name="create-a-new-safety-stock-journal-name"></a>Créer un nouveau nom de journal de stock

Vous devez créer au moins un nom de journal de stock de sécurité avant de pouvoir générer ce type de journal. Vous pouvez généralement utiliser plusieurs noms de journaux pour vous aider à séparer vos calculs de stock de sécurité.

1. Accédez à **Planification \> Configurer \> Noms des journaux de stock de sécurité**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Sur la nouvelle ligne, définissez les champs suivants :

    - **Nom** – Permet d’entrer un nom court pour le journal.
    - **Description** – Permet d’entrer une brève description du journal.
    - **Privé pour le groupe d’utilisateurs** – Pour limiter l’audience du nom de journal actuel, sélectionnez un groupe d’utilisateurs.
    - **Supprimer des lignes après la publication** – Cochez cette case pour nettoyer les lignes de journal par défaut au fur et à mesure que vous les validez. Effacez-le pour conserver toutes les lignes publiées.

    Le champ **Type de journal** est en lecture seule et est prédéfini sur *Stock de Sécurité*.

1. Fermez la page.

### <a name="create-a-safety-stock-journal-and-lines"></a>Créer un journal et des lignes de stock de sécurité

Cette étape crée un journal et y ajoute automatiquement des lignes. Chaque ligne identifie un article, ses dimensions de couverture et plusieurs quantités calculées à partir de l’historique d’utilisation. Les quantités calculées incluent les sorties moyennes par délai d’approvisionnement, les sorties moyennes par mois et l’écart type mensuel.

#### <a name="automatically-generate-journal-lines"></a>Générer automatiquement des lignes de journal

Les lignes de journal peuvent être générées automatiquement uniquement si aucune ligne n’existe pour le journal actuellement affiché.

Suivez ces étapes pour générer automatiquement des lignes de journal.

1. Accédez à **Planification \> Planification \> Exécuter \> Calcul du stock de sécurité**.
1. Dans le volet Actions, sélectionnez **Nouveau**. Un journal de stock de sécurité est créé.
1. Sur le raccourci **Détails de l’en-tête du journal**, définissez les champs suivants :

    - **Nom** – Sélectionnez le nom du journal de stock de sécurité auquel ajouter la ligne.
    - **Description** – La valeur par défaut est la description du nom du journal que vous avez sélectionné. Toutefois, vous pouvez modifier la valeur comme vous le voulez.
    - **Supprimer des lignes après la publication** – Cochez cette case pour nettoyer les lignes de journal au fur et à mesure que vous les validez. Effacez-le pour conserver toutes les lignes publiées. Le paramètre est hérité du nom de journal sélectionné.

    Le champ **Journal** est en lecture seule et affiche le numéro d’ID du journal que vous créez et auquel vous ajoutez des lignes.

1. Sur le raccourci **Lignes du journal**, sélectionnez **Créer des lignes** dans la barre d’outils.
1. Dans la boîte de dialogue **Créer des lignes de journal pour les niveaux de stock minimum proposés**, définissez les champs suivants :

    - **Date de début** – Sélectionnez la date de début de la période pour laquelle les émissions doivent être incluses dans le calcul.
    - **Date de fin** – Sélectionnez la date de fin de la période pour laquelle les émissions doivent être incluses dans ce calcul. Il doit s’écouler au moins deux mois entre les dates de début et de fin.
    - **Calculer l’écart type** – Définissez cette option sur *Oui* pour calculer l’écart type. Vous devez définir cette option sur *Oui* pour utiliser l’option **Utiliser le niveau de service** lorsque vous calculez la proposition (comme décrit plus loin dans cet article).

1. Dans le raccourci **Enregistrements à inclure**, vous pouvez configurer des filtres et des contraintes pour définir les articles inclus. (Par exemple, vous pouvez filtrer selon la valeur du **Groupe de couverture**.) Sélectionnez **Filtrer** pour ouvrir une boîte de dialogue d’éditeur de requête standard, dans laquelle vous pouvez définir des critères de sélection, des critères de tri et des jointures. Les champs fonctionnent comme pour d’autres types de requêtes dans Microsoft Dynamics 365 Supply Chain Management.
1. Dans le raccourci **Exécuter à l’arrière-plan**, sélectionnez la tâche à exécuter en mode de traitement par lots, et/ou configurez un programme récurrent. Les champs fonctionnent comme pour d’autres types de [travaux d’arrière-plan](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management.
1. Cliquez sur **OK**. Les lignes sont créées pour les dimensions qui ont des mouvements de stock.

#### <a name="manually-add-or-remove-journal-lines"></a>Ajouter ou supprimer manuellement des lignes de journal

Vous pouvez ajouter et/ou supprimer manuellement des lignes de journal à tout moment (après ou au lieu de générer automatiquement des lignes). Utilisez les boutons suivants sur la barre d’outils du raccourci **Lignes de journal** :

- **Nouveau** – Ajoutez une nouvelle ligne. Saisissez ensuite une valeur dans chaque colonne pour définir le produit à calculer et appliquer de nouveaux minima. Étant donné que les calculs minimaux proposés ne sont pas disponibles pour les lignes ajoutées manuellement, aucune nouvelle valeur de **Quantité minimale calculée** n’est affichée pour eux. Par conséquent, vous devez saisir manuellement les valeurs de **Nouvelle quantité minimale**. Cependant, vous pouvez toujours voir l’impact potentiel de la valeur **Nouvelle quantité minimale** sur la valeur du stock et la variation potentielle de stock par rapport au minimum actuellement spécifié.
- **Supprimer** – Supprimez la ligne sélectionnée.
- **Supprimer des lignes de journal** – Supprimer toutes les lignes du journal.

### <a name="calculate-a-proposal"></a>Calculer une proposition

Cette étape calcule un minimum proposé pour chaque ligne de journal et l’impact potentiel de la ligne sur la valeur du stock. (Le minimum proposé est indiqué comme la valeur de **Quantité minimale calculée**.) Vous pouvez effectuer le calcul plusieurs fois, selon vos besoins. Le calcul met à jour la valeur de **Quantité minimale calculée** qui est affichée pour toutes les lignes de journal.

Les calculs affichés n’affecteront pas les valeurs de quantité minimale réelle pour chaque produit jusqu’à ce que vous sélectionniez **Valider** dans le volet Actions. À ce moment-là, les valeurs **Nouvelle quantité minimale** seront appliquées à chaque produit.

1. Accédez à **Planification \> Planification \> Exécuter \> Calcul du stock de sécurité**.
1. Ouvrez le journal pour calculer une proposition. Vous pouvez également créer un journal comme décrit précédemment dans cet article.
1. Sur le raccourci **Lignes du journal**, sélectionnez **Calculer la proposition** dans la barre d’outils. (Vous n’avez pas besoin de sélectionner de lignes.)
1. Dans la boîte de dialogue **Calculer la proposition pour le niveau de stock minimum**, définissez les champs suivants :

    - **Utiliser la sortie moyenne pendant le délai de livraison** – Sélectionnez cette option pour générer les valeurs **Quantité minimale calculée** basées sur la sortie moyenne au cours de la période spécifiée. Ensuite, dans le champ **Facteur de multiplication**, entrez une valeur pour ajuster le résultat selon les besoins. Par exemple, entrez *1,0* pour utiliser la moyenne exacte calculée ou *1,1* pour ajouter un tampon supplémentaire de 10 pour cent.
    - **Utiliser le niveau de service** – Sélectionnez cette option pour calculer un minimum proposé en fonction du niveau de service souhaité. Ensuite, dans le champ **Niveau de service**, sélectionnez votre niveau de service préféré.
    - **Marge de délai** – Saisissez une valeur pour prolonger le délai normal (par exemple, pour permettre l’administration).
    - **Utiliser la quantité minimale calculée comme nouvelle quantité minimale** – Définissez cette option sur *Oui* pour copier automatiquement les valeurs de la colonne **Quantité minimale calculée** vers la colonne **Nouvelle quantité minimale** pour toutes les lignes une fois le calcul terminé. Si vous définissez cette option sur *Non*, la valeur **Quantité minimale actuelle** sera copiée dans la colonne **Nouvelle quantité minimale** pour toutes les lignes. Vous devrez alors modifier manuellement les valeurs **Nouvelle quantité minimale** selon les besoins.

1. Dans le raccourci **Exécuter à l’arrière-plan**, sélectionnez la tâche à exécuter en mode de traitement par lots, et/ou configurez un programme récurrent. Les champs fonctionnent comme pour d’autres types de [travaux d’arrière-plan](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management.
1. Cliquez sur **OK**. Les résultats du calcul sont affichés dans la colonne **Quantité minimale calculée** sur le raccourci **Lignes de journal**. Pour l’instant, les valeurs ne sont que des valeurs proposées qui n’ont pas encore été appliquées à vos produits.

### <a name="update-minimum-quantity"></a>Mettre à jour la quantité minimale

Vous pouvez sélectionner n’importe quelle ligne dans un journal du stock de sécurité et remplacer manuellement la valeur de son champ **Nouvelle quantité minimale**.

1. Accédez à **Planification \> Planification \> Exécuter \> Calcul du stock de sécurité**.
1. Ouvrez le journal à modifier. Vous pouvez également créer un journal comme décrit précédemment.
1. Sur le raccourci **Lignes de journal**, recherchez la ligne à ajuster, puis modifiez la valeur dans la colonne **Nouvelle quantité minimale**. Par exemple, vous pouvez définir la valeur **Nouvelle quantité minimale** afin qu’elle corresponde à la valeur **Quantité minimale calculée**. Si la valeur **Quantité minimale calculée** est *0* (zéro), vous pouvez entrer la valeur future désirée.

### <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Valider la nouvelle quantité minimale et contrôler le résultat

Procédez comme suit pour valider la nouvelle quantité minimale et contrôler le résultat.

1. Accédez à **Planification \> Planification \> Exécuter \> Calcul du stock de sécurité**.
1. Ouvrez le journal pour publier de nouvelles quantités minimales. Vous pouvez également créer un journal comme décrit précédemment.
1. Dans le volet Actions, sélectionnez **Valider**.
1. Dans la boîte de dialogue **Valider le journal**, définissez le champ **Transférer toutes les erreurs de comptabilisation dans un nouveau journal** au besoin. Sélectionnez ensuite **OK** pour valider le journal.
1. Si vous avez changé la valeur **Nouvelle quantité minimale** d’une ligne sur le raccourci **Lignes de journal**, vous pouvez confirmer la modification en suivant ces étapes :

    1. Pour la ligne que vous avez modifiée, sélectionnez le lien dans la colonne **Numéro d’article**.
    1. Dans la boîte de dialogue **Informations produit**, sélectionnez le lien dans le champ **Numéro d’article** pour ouvrir l’enregistrement de produit lancé associé.
    1. Dans le volet Actions, sous l’onglet **Planifier**, dans le groupe **Couverture**, sélectionnez **Couverture de l’article**.
    1. Notez que la valeur **Minimum** du site et de l’entrepôt que vous avez ajustée à l’aide du journal du stock de sécurité publié a maintenant été mise à jour pour correspondre à votre modification.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Traitement du stock de sécurité pour les articles](safety-stock-replenishment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
