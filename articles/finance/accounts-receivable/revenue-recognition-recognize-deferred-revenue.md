---
title: Constater le produit différé
description: Cette rubrique fournit des informations sur la façon de constater le produit à l'aide de la fonctionnalité de constatation du produit.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: ace1d00ec25a57b26b1858369c32d9134a380977
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459011"
---
# <a name="recognize-deferred-revenue"></a>Constater le produit différé

[!include [banner](../includes/banner.md)]

> [!NOTE]
> La fonctionnalité de constatation du produit ne peut pas être activée via la gestion des fonctionnalités. Vous devez pour l'instant utiliser les clés de configuration pour l'activer.

Cette rubrique décrit le processus de constatation du produit dans l'échéancier de constatation du produit. Une fois qu'une facture a été validée pour une commande client, un échéancier de constatation du produit est créé pour chaque ligne de commande client comportant un échéancier de produit. L'échéancier de produit d'une ligne sert à déterminer si le produit de cette ligne doit être différé.

## <a name="view-revenue-recognition-schedule-details"></a>Afficher les détails de l'échéancier de constatation du produit

Il existe deux méthodes pour accéder aux détails de l'échéancier de constatation du produit.

- Vous pouvez ouvrir l'échéancier de constatation du produit directement depuis une commande client facturée. Dans ce cas, les informations de l'échéancier de produit sont filtrées pour afficher exclusivement les détails correspondant à la commande client sélectionnée. Cette approche est utile lorsque vous validez les détails de l'échéancier pour une commande client.
- Vous pouvez ouvrir l'échéancier de constatation du produit à partir de la page **Constatation du produit \> Tâches périodiques**. Cette approche est souvent utilisée lorsque le produit est constaté à la fin d'une période. Lors de la première ouverture de la page, aucune information n'apparaît. Utilisez les filtres présents au-dessus de la grille pour définir des critères d'affichage des détails de l'échéancier. Vous pouvez filtrer les dates de facture en entrant une plage de dates, une commande client, un client, un ID de projet ou un état.

[![Page Echéanciers de produit](./media/revenue-recognition-rev-revenue-schedules.png)](./media/revenue-recognition-rev-revenue-schedules.png)

L'organisateur **Dimension financière** sous la grille affiche les dimensions financières de la ligne de commande client. Ces dimensions ont été prise en compte lors de la validation du produit différé. Elles sont également prises en compte lors de la constatation du produit. Les valeurs de dimension qui sont utilisées dépendent de la structure de compte affectée au produit et aux comptes principaux du produit différé.

## <a name="recognize-revenue"></a>Constatation du produit

Vous pouvez constater le produit en exécutant le processus **Créer un journal** à partir de la page **Constatation du produit**. Vous pouvez ouvrir cette page à partir de la commande client ou des **Tâches périodiques**. Si le processus est exécuté à partir de la commande client, il constate uniquement le produit de la commande client sélectionnée. Généralement, le processus est plutôt exécuté à partir des **Tâches périodiques** ; ainsi, il constate le produit pour toutes les factures de commande client validées.

Pour définir les critères de sélection et de validation du produit, sélectionnez **Créer un journal** pour ouvrir la boîte de dialogue **Créer un journal**.

[![Options des paramètres de Créer un journal](./media/revenue-recognition-create-journal.png)](./media/revenue-recognition-create-journal.png)

Dans la boîte de dialogue, utilisez les options du groupe de champs **Date de traitement** pour définir la date de validation utilisée lors de la constatation du produit. Si vous sélectionnez **Date sélectionnée**, vous pouvez entrer une date de validation dans le champ **Date de transaction**. Si vous sélectionnez **Date d'échéancier de produit**, la date de transaction n'est pas utilisée. Au lieu de cela, la valeur du champ **Date de constatation** sur chaque ligne de l'échéancier est utilisée comme date de validation.

Ensuite, dans le champ **À partir du**, entrez la date « à partir du » pour la constatation du produit. Toutes les lignes de l'échéancier comportant une date de constatation équivalente ou antérieure à la date « à partir du » sont l'objet de la constatation, pour autant qu'elles ne soient pas en attente.

Après avoir terminé de définir les dates, sélectionnez **OK** dans la boîte de dialogue pour créer le journal. Vous recevez un message d'information indiquant le nombre de transactions créées et le journal dans lequel elles ont été créées. Le journal n'est pas validé automatiquement. Par conséquent, le responsable de la constatation du produit a le temps à valider quelles sont les lignes de l'échéancier qui sont constatées.

Une fois le processus exécuté, les lignes de l'échéancier qui ont été transférées au journal sont marquées comme **Traitées**. L'indicateur **Traité** indique que les lignes ont été transférées au journal ; elles peuvent cependant être validées ou invalidées. Une fois le journal de constatation du produit validé, l'indicateur **Traité** demeure. Si le journal de constatation du produit est supprimé, ou si une ligne est supprimée, l'indicateur **Traité** est supprimé. De cette manière, la ligne peut être constatée à nouveau lorsque le processus **Créer un journal** est réexécuté.

[![Page Echéanciers de constatation du produit](./media/revenue-recognition-rev-recog-schedule-02.png)](./media/revenue-recognition-rev-recog-schedule-02.png)

Dans la page **Journal de constatation du produit** (**Constatation du produit \> Entrées de journal \> Journal de constatation du produit**), ouvrez **Lignes** pour afficher les détails de ce qui est constaté. Une transaction distincte est toujours créée pour chaque ligne d'échéancier constatée, même si les lignes sont validées à la même date en utilisant les mêmes comptes généraux.

[![Page N° document de journal](./media/revenue-recognition-journal-voucher.png)](./media/revenue-recognition-journal-voucher.png)

La colonne **Compte** affiche le compte général du produit différé. Ce compte général ne peut pas être modifié. Cette restriction permet de garantir que le compte général de produit différé correct est exonéré. Ce compte général n'est pas vérifié par rapport à la structure de compte, car il peut avoir été modifié depuis la dernière occurrence de validation du compte général de produit différé.

La colonne **Compte de contrepartie** affiche le compte général du produit. Par défaut, le compte général de produit est récupéré à partir des profils de validation des stocks, et les dimensions financières sont extraites de la ligne de commande client. Ce compte général est validé par rapport à la structure de compte actuelle. Il peut toutefois être modifié si la structure de compte a été modifiée et nécessite des dimensions financières supplémentaires.

Le montant par défaut provient de la ligne correspondante de l'échéancier ; il ne peut pas être modifié.

Par défaut, si la commande client est une commande client à plusieurs devises, le taux de change est défini comme le taux de change de la facture. Cela permet de garantir que les montants en devise comptable et en devise de déclaration sont totalement exonérés. En raison de l'arrondi, le taux de change de la dernière ligne de l'échéancier peut différer légèrement du taux présent sur la facture.

Une fois le journal de constatation du produit validé, le N° document est entré dans le programme. S'il existe plusieurs numéros document pour la même ligne de l'échéancier, un astérisque (\*) apparaît sur la ligne. Pour afficher les numéros document qui ont été validés pour cette ligne, sélectionnez **Transactions du N° document**.

## <a name="modify-the-revenue-recognition-schedule-details"></a>Modifier les détails de l'échéancier de constatation du produit

La majeure partie des données des détails de l'échéancier de produit ne peut pas être modifiée. Il est impossible d'ajouter de nouvelles lignes à l'échéancier, comme il est impossible de supprimer des lignes existantes. Les détails de l'échéancier de produit pour chaque ligne de commande client doivent être tenues à jour pour assurer que, au fil du temps, l'entreprise constate le même montant reporté.

### <a name="edit-schedule-lines"></a>Modifier des lignes d'échéancier

Certaines modifications des lignes de l'échéancier sont autorisées. Il est possible de modifier les champs des lignes suivants :

- **En attente** : cet indicateur peut être activé ou désactivé avant que la ligne soit traitée. Pour désactiver l'indicateur, sélectionnez la ligne, puis sélectionnez **Supprimer l'attente**. Le produit ne peut pas être constaté sur les lignes en attente. Les lignes peuvent être automatiquement mises en attente si l'échéancier de produit est paramétré pour la mise en attente automatique.

    [![Échéanciers de produit : modifier des lignes d'échéancier](./media/revenue-recognition-rev-revenue-schedules.png)](./media/revenue-recognition-rev-revenue-schedules.png)

- **Date de constatation** : la date de constatation peut être modifiée avant que la ligne soit traitée. Lors de l'exécution du processus de création du journal de constatation du produit, une date est entrée dans le champ **Constatation du produit à partir du**. Cette date est comparée à la date indiquée dans le champ **Date de constatation** pour déterminer quelles lignes doivent être constatées.
- **Montant à débloquer** : le montant qui sera débloqué peut être modifié avant que la ligne soit traitée. Vous pouvez réduire le montant du produit constaté, mais vous ne pouvez pas l'augmenter. Ce champ permet à l'entreprise de constater une partie du produit à la date de constatation. Si le montant est modifié, le montant dans le champ **Montant restant** affiche la quantité de produit qui doit toujours être constatée.
- **Quantité à débloquer** : si l'échéancier de produit est paramétré pour une occurrence ou pour un mois, le champ **Quantité à débloquer** affiche la quantité de la ligne de commande client. Ce champ peut également être modifié et offre un autre méthode pour constater une partie du produit. Par exemple, si la quantité de la ligne est 5, vous pouvez remplacer cette quantité pour qu'elle soit inférieure à 5. Le montant dans le champ **Montant à débloquer** est mis à jour en proportion.

### <a name="update-contract-terms"></a>Mettre à jour les termes du contrat

Les détails de l'échéancier de produit sont créés en fonction de l'échéancier affecté à la ligne de commande client au moment où la facture est validée. Si l'échéancier de produit de la ligne de commande client n'est pas valide, il ne peut pas être modifié sur la commande client après que la commande client a été facturée. Vous devez alors utiliser le bouton **Mettre à jour les termes du contrat** pour modifier l'échéancier de produit. L'échéancier de produit peut modifié avant ou après que le produit a été constaté.

Pour modifier l'échéancier, sélectionnez une ligne d'échéancier pour l'article que vous modifiez. Dans l'illustration suivante, la ligne pour l'article S0008 qui a été validé selon un échéancier de produit de 12 mois est sélectionnée. Lorsque vous sélectionnez **Mettre à jour les termes du contrat**, une boîte de dialogue afficher les dates de début et de fin de contrat, ainsi que l'échéancier de produit.

[![Dates de début et de fin du contrat](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)

Modifiez les dates de début et de fin de contrat afin qu'elles correspondent à la plage de dates correcte. Lorsque vous modifiez la plage de dates, la valeur dans le champ **Nombre d'occurrences** doit correspondre à un échéancier de produit défini dans le système. Dans cet exemple, comme le contrat a été modifié en contrat de 24 mois, il convient de paramétrer un échéancier de produit de 24 mois. Comme il existe un échéancier de produit de 24 mois, celui-ci est entré par défaut et le contrat peut être modifié. S'il n'existe pas d'échéancier de produit ayant le nombre d'occurrences correspondant, le contrat ne peut pas être modifié. Une fois que vous avez mis à jour les termes du contrat et l'échéancier de produit selon vos besoins, sélectionnez **OK** dans la boîte de dialogue pour enregistrer vos modifications.

[![Plage de dates du contrat mise à jour](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)

Les modifications de contrat ont les effets suivants sur les détails de l'échéancier de produit :

- Si aucun produit n'a été constaté pour le produit, toutes les informations de l'échéancier précédent sont supprimées et remplacées par les détails du nouvel échéancier de produit. Par exemple, l'article S0008 comportait initialement 12 lignes dans les détails de l'échéancier. Ces 12 lignes sont supprimées et remplacées par 24 lignes, conformément au nouvel échéancier de produit.
- Si le produit a été constaté pour le produit, une partie du produit n'a pas été correctement constatée car la constatation portait sur un échéancier de produit erroné. Ces lignes doivent être contrepassées et constatées à nouveau, selon le nouvel échéancier. Dans ce scénario, ide nouvelles lignes d'échéancier sont crées, comportant des montants négatifs à la date de constatation d'origine. De nouvelles lignes sont alors créées pour constater les montants selon le nouvel échéancier de produit. Par exemple, le 8 août 2019, vous avez constaté un produit de 10,53 USD. Le 8 septembre 2019, vous avez identifié un produit de 13,16 USD. Par conséquent, deux lignes sont créées avec ces dates. Une ligne contient 10,53 USD, et l'autre ligne contient 13,16 USD. Vingt-quatre lignes sont alors créées, et le produit différé total de 160,61 USD est réparti entre elles. Vous pouvez valider les lignes de contrepassation en exécutant le processus **Créer un journal**.

[![Echéancier de constatation du produit](./media/revenue-recognition-rev-recog-schedule-03.png)](./media/revenue-recognition-rev-recog-schedule-03.png)
