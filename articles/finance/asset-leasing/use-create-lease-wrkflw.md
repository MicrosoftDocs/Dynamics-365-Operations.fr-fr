---
title: Utiliser les workflows d’approbation de bail
description: Cette rubrique explique comment utiliser les workflows pour approuver les baux d’actifs et comment suivre l’état et l’historique des workflows.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 33faf7aa6bc9e5df4b8b0f004692b2c1803c6994264c7b9a8e3eb404387f6800
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726084"
---
# <a name="use-lease-approval-workflows"></a>Utiliser les workflows d’approbation de bail

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment utiliser les workflows pour approuver les baux d’actifs et comment suivre l’état et l’historique des workflows. Les workflows contribuent à assurer la cohérence de la gestion des approbations de bail en fournissant un ensemble standard d’étapes d’approbation et en affectant des utilisateurs spécifiques qui approuvent chaque étape du processus. Un approbateur peut approuver un bail, le rejeter, demander une modification ou l’affecter à un autre utilisateur pour approbation. Les workflows peuvent également apporter plus de visibilité sur le processus d’approbation en vous permettant de suivre leur statut et leur historique. En outre, vous pouvez afficher une liste de travail centralisée qui répertorie les tâches et les approbations affectées à des approbateurs spécifiques.

Avant d’utiliser cette procédure, assurez-vous qu’au moins un workflow d’approbation de bail a été créé. Si aucun workflow n’existe, créez-en. Pour plus d’informations sur la configuration d’un workflows, voir [Configurer des workflows d’approbation de bail](set-up-lease-wrkflw.md).

1. Soumettre un bail pour approbation. Sur la page **Détails du livre** pour le bail, sélectionnez **Workflow**, puis sélectionnez **Soumettre**.
2. Dans la boîte de dialogue qui apparaît, vous pouvez ajouter un commentaire. L’approbateur désigné verra ce commentaire avec le bail. Lorsque vous avez terminé de saisir le commentaire, sélectionnez **Soumettre**. Le bail est soumis au système de workflow et l’approbateur le reçoit pour approbation.
3. Pour afficher les baux pour lesquels ils sont désignés pour approbation, accédez à **Modules \> Commun \> Éléments de travail \> Éléments de travail qui m’ont été attribués**.
4. Sur la page **Éléments de travail qui m’ont été attribués**, sélectionnez le lien **Identificateur du bail** pour le bail que vous souhaitez consulter. La page qui s’affiche dépend des registres de location et des détails de location auxquels vous avez accès.
5. Lorsque vous avez terminé de consulter le bail, sélectionnez **Workflows**, et décidez des mesures à prendre. Les options comprennent **Approuver**, **Rejeté**, **Demander un changement**, **Déléguer**, et **Annulé**. Vous pouvez également sélectionner **Voir l’historique** pour afficher l’historique d’approbation du bail sélectionné.
6. Après avoir sélectionné une action, entrez un commentaire pour décrire l’action. Lorsque vous avez terminé de saisir le commentaire, sélectionnez l’action **Approuvé** dans la liste.
7. Pour afficher les actions d’approbation, revenez à la page **Détails du bail** de la page **Résumé du bail**, puis sélectionnez **Workflow \> Voir l’historique**.

    Vous pouvez afficher les activités du workflow sur la page **Historique du workflow**. Cette page affiche les étapes du workflow qui ont été suivies pour le bail spécifique. Vous pouvez également utiliser le champ **Éléments de travail** pour afficher le statut des éléments de travail affectés.

8. Pour arrêter un workflow, sur la page **Historique du workflow**, sélectionnez **Rappeler**. Dans la boîte de dialogue qui s’affiche, entrez un commentaire, puis sélectionnez **OK**.
9. Pour désactiver un workflow ou pour activer un workflow précédemment créé, accédez à **Location d’actifs \> Configurer \> Workflow de location**. Puis, sur la page **Workflow de location**, sélectionnez **Workflow \> Versions**. Pour rendre un workflow en cours inactif, sélectionnez le bail actif dans la boîte de dialogue de la version du bail, puis sélectionnez **Rendre inactif**. Pour rendre un workflow existant actif, sélectionnez le workflow, puis sélectionnez **Rendre actif**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
