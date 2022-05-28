---
title: Configurer les workflows d’approbation de bail
description: La rubrique explique comment configurer un workflow d’approbation qui s’exécutera lors de la création d’un bail.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f7781fcb643d678fed528af947efb01911899f54
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724611"
---
# <a name="set-up-lease-approval-workflows"></a>Configurer les workflows d’approbation de bail

[!include [banner](../includes/banner.md)]

La rubrique explique comment configurer un workflow d’approbation qui s’exécutera lors de la création d’un bail. Pour plus d’informations sur l’utilisation d’un workflow, voir [Utiliser des workflows d’approbation de bail](use-create-lease-wrkflw.md). 

1. Accédez à **Location d’actifs \> Configuration \> workflow de bail**.
2. Dans la page **workflow de bail**, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue qui apparaît, sous **Type de workflow**, sélectionnez le lien **Workflow de bail**.

    L’application est ouverte. Après son exécution, connectez-vous à Azure Active Directory (Azure AD) pour être redirigé vers l’application de workflow.

4. Faites glisser l’élément **Approbation du workflow de location** sur le workflow.
5. Connectez un nœud depuis **Début** à **Approbation du workflow de location**. Puis connectez **Approbation du workflow de location** à **Fin**.
6. Double-cliquez sur **Approbation du workflow de location**.
7. Sélectionnez **Propriétés**, puis, sous **Paramètres de base**, entrez un nom pour le workflow.

    Sur cette page, vous pouvez également définir plus de paramètres pour le workflow. Si vous avez activé **Actions automatiques**, le système entreprendra automatiquement une action spécifique. Les notifications peuvent être envoyées si elles sont spécifiées sur l’onglet **Notifications**. Sur l’onglet **Paramètres avancés**, vous pouvez spécifier un approbateur final, définir une limite de temps et désigner des actions spécifiques qui doivent être effectuées.

8. Lorsque vous avez terminé de définir les paramètres du workflow, sélectionnez **Fermer**.
9. Sélectionnez **Étape 1**, puis sélectionnez **Propriétés**.
10. Sous **Paramètres de base**, entrez un nom pour l’étape, créez une ligne d’objet pour l’approbation et spécifiez les instructions pour l’approbation.
11. Sur la page **Affectation**, sélectionnez le type d’affectation.
12. Pour affecter des utilisateurs spécifiques à l’approbation, sélectionnez **Utilisateur**, sélectionnez les utilisateurs qui approuvent les baux, puis sélectionnez **Fermer**.
13. Cliquez sur **Enregistrer et fermer** pour créer le workflow. Ensuite, lorsque vous y êtes invité, sélectionnez **OK**.
14. Sur la page **Créer le workflow**, sélectionnez **Fermer**.
14. Sélectionnez le nouveau workflow, puis sélectionnez **Versions**. Puis sélectionnez **Rendre actif** pour vous assurer que le workflow est actif.
15. Sélectionnez **Fermer**. La nouvelle version active apparaît.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
