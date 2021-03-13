---
title: Ajuster les baux
description: La rubrique explique comment ajuster un bail. Un ajustement peut être nécessaire si les conditions du bail sont modifiées, si le bail est prolongé ou si d’autres circonstances changent.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 32d99d9e90b65f7cac74176d21fa4b053ae8f62c
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130753"
---
# <a name="adjust-leases"></a>Ajuster les baux

[!include [banner](../includes/banner.md)]

La rubrique explique comment ajuster un bail. Un ajustement peut être nécessaire si les conditions du bail sont modifiées, si le bail est prolongé ou si d’autres circonstances changent. La location d’actifs est conforme aux directives fournies par l’article 842 sur la codification des normes comptables (ASC 842) et la norme internationale en matière de génération des états financiers 16 (IFRS 16) concernant les modifications des baux. ASC 842-20-15-1 définit une modification de bail comme toute modification des termes et conditions d’un contrat qui entraîne une modification de la portée ou de la prise en compte d’un bail. Le paragraphe 39 d’IFRS 16 indique qu’un locataire doit réévaluer le passif locatif afin qu’il reflète les modifications des paiements de location.

Pour les organisations qui respectent l’ASC 842 ou l’IFRS 16, un bail est réévalué pour refléter une modification de la valeur actuelle des paiements minimaux de location minimums à venir (PVFMLP). Si la PVFMLP augmente, l’écriture de journal créée est un débit au compte de droit d’utilisation de l’actif et un crédit au compte de passif locatif pour la différence entre la nouvelle PVFMLP et la précédente PVFMLP. Si la PVFMLP diminue, l’écriture de journal est un débit au compte de passif locatif et un crédit au compte de droit d’utilisation de l’actif pour la différence.

Si l’ajustement diminue le droit d’utilisation de l’actif au-delà de 0 (zéro), le reste est crédité au gain sur le compte de validation des modifications du bail spécifié sur la page **Comptes de validation de bail**. Le système comptabilise ces transactions et d’autres écritures d’ajustement, telles que les changements de classification, les coûts directs initiaux, les incitations à la location, les acomptes et les coûts de démantèlement qui résultent des modifications de location.

Pour obtenir des indications spécifiques sur les transactions d’ajustement de bail, nous vous recommandons de consulter IFRS 16 et ASC 842.

## <a name="lease-adjustment-wizard"></a>Assistant d’ajustement de bail

Procédez comme suit pour modifier un bail. Les données modifiées mettront à jour les échéanciers de bail après la validation depuis l'assistant **Ajustement de bail**. Vous pouvez enregistrer votre travail et fermer l'assistant à tout moment, puis revenir plus tard pour reprendre votre travail.

Procédez comme suit pour ouvrir l'assistant **Ajustement de bail** à partir du résumé du bail.

1. Accédez à **Location d’actifs \> Baux \> Récapitulatif du bail**. 
2. Sélectionnez le bail à modifier, puis sélectionnez **Assistant d’ajustement**.
3. Suivez les invites de l'assistant pour saisir les modifications requises.

Procédez comme suit pour ouvrir l'assistant **Ajustement de bail** dans la page **Ajustements de bail**, pour un ajustement qui est déjà en cours.

1.  Accédez à **Bail \> Baux \> Ajustements de bail**.
2.  Sélectionnez un bail dont le statut d'ajustement est **En cours**, puis sélectionnez **Assistant d’ajustement**.
3.  Entrez les dates appropriées dans les champs **Date de début de la modification** et **Date de validation**.
4.  Sélectionnez **Suivant**.

    Le bail est maintenant ajouté à la page **Ajustements de bail** et vous pouvez saisir les nouvelles informations.

    Une fois le bail modifié, les champs relatifs aux droits d'utilisation s'appliquent. Si aucun coût direct initial, aucune incitation à la location, aucun paiement anticipé ou aucun coût de démantèlement n’est associé au bail modifié, vous devez laisser les champs correspondants vides. Les montants d’origine ne s’appliqueront pas au bail mis à jour. 

    Par exemple, un bailleur offre une incitation de 1 000 $ pour accepter une prolongation du bail. Dans ce cas, lorsque vous modifiez le bail pour tenir compte de l’extension, vous devez entrer **1 000** dans le champ **Incitations à la location résultant de la modification**.

    Les lignes d'échéancier de paiement affichent désormais tous les paiements du mois et des mois suivants dans le champ **Date de début de la modification**. Les modifications étant prévisionnelles, les échéanciers de paiement ne peuvent pas commencer avant le début de la modification. Pour afficher les échéances de paiement antérieures à la date de début de la modification, accédez à la page **Historique de version des baux**.

8.  Sélectionnez **Suivant**.

    La page suivante présente des détails clés sur l'ajustement prévu du contrat de location, comme la valeur comptable du passif locatif avant la modification et le nouveau passif locatif prévu après la modification. La page affiche également un aperçu de l'entrée de journal pour l'ajustement de bail prévu.

9.  Sélectionnez **Soumettre au workflow** pour soumettre l'ajustement du bail au système de workflow si le workflow d'ajustement de bail est actif et que l'ajustement n'a pas encore été approuvé. Pour plus d’informations sur l’utilisation d’un workflow d'ajustement de bail, voir [Utiliser des workflows d'ajustement de bail](use-create-lease-wrkflw.md).

    > [!NOTE]
    > À ce stade, le système recalcule les variables d'ajustement pour vérifier qu'aucune transaction n'a été imputée au contrat de location depuis le calcul initial de la synthèse d'ajustement et de l'écriture dans le journal d'ajustement. Si des valeurs changent, la grille de synthèse des ajustements est mise à jour et vous pouvez consulter les informations avant de soumettre à nouveau les ajustements de bail au système de workflow.

10. Si un workflow n'est pas actif ou si l'ajustement du bail a été approuvé, sélectionnez **Terminer** pour traiter les modifications et enregistrer l'écriture dans le journal d'ajustement.

    > [!NOTE] 
    > À ce stade, le système recalcule les variables d'ajustement pour vérifier qu'aucune transaction n'a été imputée au contrat de location depuis le calcul initial de la synthèse d'ajustement et de l'écriture dans le journal d'ajustement. Si des valeurs changent, la grille de synthèse des ajustements est mise à jour et vous pouvez consulter les modifications avant de sélectionner **Terminer**. Si le workflow est actif et que l'ajustement du bail a été approuvé, toute modification apportée à la synthèse des ajustements entraînera le rétablissement du statut d'approbation sur **Non soumis**. Dans ce cas, vous devez soumettre à nouveau l'ajustement de bail au système de workflow.

    Sur la page **Ajustements de bail**, le statut de l'ajustement est maintenant défini sur **Terminé**.

    Sur la page **Ajustements de bail**, vous pouvez toujours afficher les raccourcis **Vue d'ensemble de l'ajustement** et **Aperçu de l'entrée d'ajustement**. Les détails du bail et les informations de date sont affichés dans l'historique des versions de ce bail.

    Une nouvelle version du bail et un nouvel ensemble d'échéanciers sont désormais créés à l'aide des informations modifiées. 

13. Pour afficher les nouveaux échéanciers, accédez au bail, puis sélectionnez **Registres**.
14. Pour afficher l'échéancier de paiement nouvellement généré, sélectionnez **Échéancier de paiement**.
15. Pour afficher le nouvel échéancier d’amortissement du passif locatif généré à partir des nouvelles informations, fermez la page **Échéancier de paiement** et ouvrez la page **Programme d’amortissement du passif**.
16. Pour afficher le nouvel échéancier d’amortissement des actifs, ouvrez la page **Programmes d’amortissement des actifs** de la page **Détails des registres**.
17. Pour afficher l’entrée de journal d’ajustement, sélectionnez **Journaux \> Journal de location d’actifs**.

## <a name="cancel-a-lease-adjustment"></a>Annuler un ajustement de bail

Procédez comme suit pour supprimer un ajustement de bail en cours.

1.  Accédez à **Bail \> Baux \> Ajustements de bail**.
2.  Sélectionnez l'ajustement de bail en cours pour l'annuler.
3.  Sélectionnez **Annuler l'ajustement**. 
4.  Cliquez sur **OK**.

    > [!NOTE] 
    > Si vous sélectionnez **Annuler** dans l'assistant **Ajustement de bail**, vous annulez la modification la plus récente effectuée dans l'assistant, mais vous ne supprimez pas l'ajustement en cours.

## <a name="use-the-lease-adjustment-workflow"></a>Utiliser le workflow d'ajustement de bail

Cette section explique comment utiliser le workflow d'ajustement de bail. Le workflow d'ajustement de bail vous aide à gérer les ajustements de bail de manière cohérente en fournissant un ensemble d'étapes d'approbation et en les affectant à des utilisateurs spécifiques chargés d'approuver un ajustement de bail avant qu'il ne devienne définitif. Une fois l'ajustement du bail approuvé dans le workflow, vous pouvez utiliser l'assistant **Ajustement de bail** pour terminer l'ajustement du bail.

1.  Pour soumettre un ajustement de bail pour approbation, accédez à **Bail \> Baux \> Ajustements de bail**.
2.  Sélectionnez l'ID de bail de l'ajustement de bail, puis sélectionnez **Assistant d’ajustement**.
3.  Sur la dernière page de l'assistant, sélectionnez **Soumettre pour approbation**.
4.  Entrez un commentaire sur l'ajustement, puis sélectionnez **OK**.

    Le statut du workflow est remplacé par **Approbation en attente** et tous les champs de l'assistant sont verrouillés pour modification.

5.  Pour approuver un ajustement de bail, accédez à **Bail \> Baux \> Ajustements de bail**.
6.  Sélectionnez l'ID de bail de l'ajustement de bail, puis examinez les raccourcis **Vue d'ensemble de l'ajustement** et **Aperçu de l'entrée d'ajustement**.
7.  Sélectionnez **Flux de travail \> Approuvé**.

    Sur la page **Ajustements de bail**, le statut du flux de travail est maintenant défini sur **Approuvé**. À ce stade, l'ajustement de bail est prêt à être imputé via l'écriture dans le journal d'ajustement.

8.  Pour continuer à traiter l'ajustement de bail et enregistrer l'écriture d'ajustement, accédez à **Bail \> Baux \> Ajustements de bail**.
9.  Sélectionnez l'ID de bail de l'ajustement de bail, puis sélectionnez **Assistant d’ajustement**.
10. Sélectionnez **Suivant** jusqu'à ce qu'atteindre la dernière page de l'assistant, puis sélectionnez **Terminer**.

Le système recalcule les valeurs comptables du contrat de location pour s'assurer que les variables d'ajustement qui ont été approuvées sont à jour. S'il y a des changements, le statut d'approbation est redéfini sur **Brouillon**, et vous devez soumettre à nouveau l'ajustement de bail au système de flux de travail.

## <a name="view-lease-versions"></a>Voir les versions de bail

Si un bail a été modifié, vous pouvez en afficher les différentes versions. Vous pouvez également voir les échéanciers historiques et les détails des baux passés.

1. Sur la page **Récapitulatif du bail**, sélectionnez le bail à copier, puis, dans le volet Actions, sélectionnez **Historique de version des baux**.

    Si le bail sélectionné a été modifié, la page **Historique de version des baux** en montre les différentes versions. Le bail d’origine est étiqueté **1** et les versions ultérieures ont un ordre numérique croissant.

    Pour une version de location sélectionnée, vous pouvez afficher les dimensions financières, les détails du contrat, l’emplacement et les échéances de paiement.

2. Pour afficher les horaires historiques, ouvrez le bail modifié à partir de la page **Récapitulatif du bail**, sélectionnez le livre souhaité, puis, dans le volet Actions, sélectionnez **Historique de version des baux**.
3. Sur la page **Version des registres**, sélectionnez une version et l’échéancier à afficher.
