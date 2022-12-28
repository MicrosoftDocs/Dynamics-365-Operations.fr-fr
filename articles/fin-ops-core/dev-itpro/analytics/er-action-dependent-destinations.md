---
title: Configurer les destinations pour la gestion des états électroniques dépendant de l’action
description: Cet article explique comment configurer des destinations dépendant d’une action pour un format de gestion des états électroniques configuré pour générer des documents sortants.
author: kfend
ms.date: 12/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.form: ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: 80a432a431891c02e4bf5c71cfe2bd9642c41c75
ms.sourcegitcommit: e9000d0716f7fa45175b03477c533a9df2bfe96d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2022
ms.locfileid: "9843795"
---
# <a name="configure-action-dependent-er-destinations"></a>Configurer les destinations pour la gestion des états électroniques dépendant de l’action

[!include [banner](../includes/banner.md)]

Vous pouvez configurer les [destinations](electronic-reporting-destinations.md) pour chaque composant (dossier ou fichier) au format de [gestion des états électroniques](general-electronic-reporting.md) [configuré](general-electronic-reporting.md#Configuration) pour générer un document sortant. Les utilisateurs qui exécutent un format pour la gestion des états électroniques de ce type, et qui ont les droits d’accès appropriés, peuvent également changer les paramètres de destination configurés au moment de l’exécution.

Dans Microsoft Dynamics 365 Finance **version 10.0.17 et ultérieure**, un format de gestion des états électroniques peut être exécuté en [approvisionnant](er-apis-app10-0-17.md) un code d’action que l’utilisateur exécute en exécutant ce format de gestion des états électroniques. Par exemple, dans le module **Comptabilité client**, dans les paramètres de gestion de l’impression, vous pouvez sélectionner un format de gestion des états électroniques qui génère un document commercial spécifique, comme une facture financière. Vous pouvez ensuite sélectionner **Afficher** pour prévisualiser la facture ou **Imprimer** pour l’envoyer à une imprimante. Si une action utilisateur est transmise pour le format de gestion des états électroniques en cours d’exécution au moment de l’exécution, vous pouvez configurer différentes destinations de gestion des états électroniques pour différentes actions utilisateur. Cet article explique comment configurer les destinations de gestion des états électroniques pour ce type de format de gestion des états électroniques.

## <a name="make-action-dependent-er-destinations-available"></a>Rendre les destinations pour la gestion des états électroniques dépendant de l’action disponibles

Pour configurer les destinations de gestion des états électroniques dépendant d’une action dans l’instance Finance actuelle et activer la [nouvelle](er-apis-app10-0-17.md) API de gestion des états électroniques, ouvrez l’espace de travail [Gestion des fonctionnalités](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace) et activez la fonctionnalité **Configurer les destinations de gestion des états électroniques spécifiques à utiliser pour différentes actions PM**. Pour utiliser les destinations de gestion des états électroniques configurées pour les états spécifiques à l’exécution, activez la fonctionnalité, **Acheminer la sortie des états PM selon les destinations de gestion des états électroniques spécifiques à une action d’utilisateur (vague 1)**.

## <a name="configure-action-dependent-er-destinations"></a>Configurer les destinations pour la gestion des états électroniques dépendant de l’action

Lorsque vous activez la fonctionnalité **Configurer les destinations de gestion des états électroniques spécifiques à utiliser pour différentes actions PM**, vous pouvez configurer les destinations de gestion des états électroniques dépendant d’une action sur l’organisateur **Destination de fichier** de la page **Destination de la gestion des états électroniques**. Pour chaque composant, vous pouvez ajouter un enregistrement et activer des destinations de gestion des états électroniques spécifiques. Pour chaque enregistrement, vous devez spécifier le type de document pour lequel les destinations de gestion des états électroniques configurées doivent être demandées. Dans le champ **Type de document**, sélectionnez l’une des valeurs suivantes :

- Sélectionnez **Électronique** pour appliquer les destinations configurées si aucun code d’action utilisateur n’est fourni lors de l’exécution.
- Sélectionnez **Gestion de l’impression** pour appliquer les destinations configurées si aucun code d’action utilisateur n’est fourni lors de l’exécution.
- Sélectionnez **N’importe laquelle** pour toujours appliquer les destinations configurées, peu importe si une action utilisateur est fournie lors de l’exécution.

Si vous sélectionnez le type de document **Gestion de l’impression**, vous devez spécifier les actions utilisateur auxquelles les destinations de gestion des états électroniques configurées doivent être appliquées. Dans le champ **Action de gestion de l’impression**, sélectionnez l’une des valeurs suivantes :

- Sélectionnez **Afficher** pour appliquer les destinations configurées si l’action utilisateur **Afficher** est fournie lors de l’exécution.
- Sélectionnez **Imprimer** pour appliquer les destinations configurées si l’action utilisateur **Imprimer** est fournie lors de l’exécution.
- Sélectionnez **Envoyer** pour appliquer les destinations configurées si l’action utilisateur **Envoyer** est fournie lors de l’exécution.

> [!NOTE]
> Plusieurs actions peuvent être sélectionnées pour un seul enregistrement de destination.

Si vous sélectionnez le type de document **N’importe lequel**, **Détection automatique** est automatiquement sélectionnée dans le champ **Action de gestion de l’impression** en tant qu’action de l’utilisateur et le comportement suivant se produit :

- Si aucun code d’action utilisateur n’est fourni lors de l’exécution, toutes les destinations de gestion des états électroniques configurées sont appliquées.
- Si un code d’action utilisateur est fourni au moment de l’exécution, une destination de gestion des états électroniques prédéfinie pour une action spécifique est appliquée, **indépendamment du fait qu’elle ait été activée ou non** :

    - Quand l’action **Afficher** est fournie au moment de l’exécution, la destination de gestion des états électroniques **Écran** est appliquée.
    - Quand l’action **Envoyer** est fournie au moment de l’exécution, la destination de gestion des états électroniques **E-mail** est appliquée.
    - Quand l’action **Imprimer** est fournie au moment de l’exécution, la destination de gestion des états électroniques **Imprimante** est appliquée.

Par exemple, vous pouvez utiliser le format de gestion des états électroniques **Facture financière (Excel)** pour imprimer une [facture financière](../../../finance/accounts-receivable/create-free-text-invoice-new.md) lorsque vous la publiez. Pour acheminer un document généré, vous devez configurer des destinations de gestion des états électroniques pour ce format de gestion des états électroniques. Par exemple, vous devrez peut-être configurer ces destinations de gestion des états électroniques pour effectuer les opérations suivantes sur un document généré :

- Archivez le document si le format de gestion des états électroniques est exécuté, mais qu’aucun code d’action n’est fourni (par exemple, lorsque le document est envoyé par voie électronique).
- Prévisualisez le document dans un navigateur Web lorsqu’un utilisateur effectue l’action **Afficher**.
- Archivez et imprimez le document lorsqu’un utilisateur effectue l’action **Imprimer**.
- Archivez le document et envoyez-le par e-mail en tant que pièce jointe d’un e-mail sortant lorsqu’un utilisateur effectue l’action **Envoyer**.

L’illustration suivante montre comment vous pouvez réaliser cette configuration des destinations de gestion des états électroniques en tant qu’ensemble d’enregistrements de destination individuels lorsque chaque enregistrement est configuré pour une action utilisateur individuelle :

![Page de destination de rapport électronique qui a des paramètres de destination dépendants de l’action pour un format de gestion des états électroniques lorsque chaque enregistrement de destination est configuré pour une seule action utilisateur.](./media/er-destination-action-dependent-01.png)

L’illustration suivante montre comment vous pouvez réaliser cette configuration des destinations de gestion des états électroniques en tant qu’ensemble d’enregistrements de destination individuels lorsque chaque enregistrement est configuré pour une destination individuelle :

![Page de destination de rapport électronique qui a des paramètres de destination dépendants de l’action pour un format de gestion des états électroniques lorsque chaque enregistrement de destination est configuré pour une seule destination.](./media/er-destination-action-dependent-01a.png)

> [!NOTE]
> Si un code d’action est fourni pour le format de gestion des états électroniques en cours d’exécution, mais qu’aucune destination n’a été configurée pour ce code d’action, le[ défaut](electronic-reporting-destinations.md#default-behavior) le comportement de destination est appliqué.

## <a name="change-action-dependent-er-destinations-at-runtime"></a>Modifier les destinations pour la gestion des états électroniques dépendant de l’action au moment de l’exécution

Lorsqu’un format de gestion des états électroniques est exécuté, si les actions utilisateur ont été configurées par des utilisateurs disposant des [autorisations](electronic-reporting-destinations.md#security-considerations) pour modifier les paramètres de destination configurés au moment de l’exécution, une boîte de dialogue apparaît, offrant la possibilité de modifier les paramètres de destination configurés. Cette boîte de dialogue est facultative et son apparence dépend de la manière dont l’appel lancé par l’infrastructure de gestion des états électroniques pour exécuter un format de gestion des états électroniques a été implémenté. Si cette boîte de dialogue apparaît, les destinations de gestion des états électroniques qu’elle contient seront activées en fonction de l’action utilisateur fournie.

L’illustration suivante montre un exemple de **Destinations au format de gestion des états électroniques** qui apparaît lorsqu’une facture financière est [ publiée](../../../finance/accounts-receivable/create-free-text-invoice-new.md) et le format de gestion des états électroniques **Facture financière (Excel)** est exécuté pour générer ce document, si l’action **Imprimante** a été provisionnée et les destinations de gestion des états électroniques ont été configurées pour ce format, comme indiqué plus haut dans cet article.

![Boîte de dialogue qui donne la possibilité de modifier les destinations de gestion des états électroniques initialement configurées pour le format de gestion des états électroniques en cours d’exécution.](./media/er-destination-action-dependent-02.gif)

> [!NOTE]
> Si vous avez configuré des destinations de gestion des états électroniques pour plusieurs composants du format de gestion des états électroniques en cours d’exécution, une option sera proposée séparément pour chaque composant configuré du format de gestion des états électroniques.

Si plusieurs formats ER sont applicables en tant que modèles de rapport pour le document sélectionné, toutes les destinations ER pour tous les modèles de rapport ER applicables sont affichées dans la boîte de dialogue et disponibles pour un ajustement manuel au moment de l’exécution.

Si aucun modèle de rapport [SQL Server Reporting Services (SSRS)](SSRS-report.md) n’est applicable au document sélectionné, la sélection standard des destinations de gestion de l’impression est masquée dynamiquement.

À partir de la version Finance **10.0.31**, vous pouvez modifier manuellement les destinations ER affectées au moment de l’exécution pour les documents commerciaux suivants :

- Relevé de compte client
- Note d’intérêt
- Note de lettre de relance
- Conseil de paiement client
- Conseil de paiement fournisseur

Pour activer la capacité de changer les destinations ER au runtime, activez la fonctionnalité **Autoriser l’ajustement des destinations ER au runtime** dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace).

> [!IMPORTANT]
> Pour les rapports **Conseil de paiement client** et **Conseil de paiement fournisseur**, la possibilité de modifier manuellement les destinations ER n’est disponible que si le déploiement en mode Flighting **ForcePrintJobSettings** est activé.

[![Réglage des destinations ER au runtime.](./media/ERdestinaiotnChangeUI.jpg)](./media/ERdestinaiotnChangeUI.jpg)

> [!NOTE]
> Quand l’option **Utiliser la destination de gestion d’impression** est définie sur **Oui**, le système utilise les destinations ER par défaut qui sont configurées pour des rapports d’urgence spécifiques. Toutes les modifications manuelles apportées dans la boîte de dialogue sont ignorées. Définissez l’option **Utiliser la destination de gestion d’impression** sur **Non** pour traiter les documents vers les destinations ER définies dans la boîte de dialogue immédiatement avant d’exécuter les rapports.

Les documents commerciaux suivants ne supposent pas la sélection explicite d’une action par l’utilisateur quand ils sont exécutés :

- Relevé de compte client
- Note d’intérêt
- Note de lettre de relance
- Conseil de paiement client
- Conseil de paiement fournisseur

La logique suivante est utilisée pour déterminer quelle action est utilisée pendant le traitement des rapports précédents :

- Si le déploiement en mode Flighting **ForcePrintJobSettings** est activé :

    - Si l’option **Utiliser la destination de gestion d’impression** est définie sur **Oui**, l’action **Imprimer** est utilisée.
    - Si l’option **Utiliser la destination de gestion d’impression** est définie sur **Non**, l’action **Afficher** est utilisée.

- Si le déploiement en mode Flighting **ForcePrintJobSettings** n’est pas activé :

    - Si l’option **Utiliser la destination de gestion d’impression** est définie sur **Oui**, l’action **Imprimer** est utilisée pour les rapports **Conseil de paiement client** et **Conseil de paiement fournisseur**.
    - Si l’option **Utiliser la destination de gestion d’impression** est définie sur **Non**, le modèle de rapport SSRS par défaut est toujours utilisé pour le Rapports **Conseil de paiement client** et **Conseil de paiement fournisseur**, quels que soient les paramètres ER configurés.
    - L’action **Imprimer** est toujours utilisée pour les rapports **Relevé de compte client**, **Note d’intérêt** et **Note de lettre de relance**.

Pour la logique précédente, les actions **Imprimer** ou **Afficher** peuvent être utilisées pour configurer des destinations de rapport ER dépendantes de l’action. Au moment de l’exécution, seules les destinations ER configurées pour une action spécifique sont filtrées dans la boîte de dialogue.

## <a name="verify-the-provided-user-action"></a>Vérifier l’action utilisateur fournie

Vous pouvez vérifier quelle action utilisateur, le cas échéant, est fournie pour le format de gestion des états électroniques en cours d’exécution lorsque vous effectuez une action utilisateur spécifique. Cette vérification est importante lorsque vous devez configurer des destinations de gestion des états électroniques dépendant de l’action, mais que vous ne savez pas quel code d’action utilisateur, le cas échéant, est fourni. Par exemple, lorsque vous commencez à publier une facture financière et que vous définissez l’option **Facture financière** sur **Oui** dans la boîte de dialogue **Publier une facture financière**, vous pouvez définir l’option **Utiliser la destination de gestion de l’impression** sur **Oui** ou **Non**.

Suivez ces étapes pour vérifier le code d’action utilisateur fourni.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Dans la boîte de dialogue **Paramètres utilisateur**, [définissez](er-trace-reports-compare-baseline.md#configure-er-parameters-to-use-the-baseline-feature) l’option **Exécuter en mode débogage** sur **Oui**.
4. Exécutez une action utilisateur en exécutant un format de gestion des états électroniques. N’oubliez pas que les paramètres d’utilisateur de gestion des états électroniques sont spécifiques à l’utilisateur et à l’entreprise.
5. Accédez à **Administration d’organisation** \> **États électroniques** \> **Journaux de débogage des configurations**.
6. Sur la page **Journaux de débogage de configuration**, filtrez les journaux d’exécution de gestion des états électroniques pour trouver le journal de votre exécution au format de gestion des états électroniques.
7. Examinez les entrées de journal qui doivent contenir l’enregistrement qui présente le code d’action utilisateur fourni, si une action a été fournie pour l’exécution au format de gestion des états électroniques.

    ![Page des journaux d’exécution de rapports électroniques qui contient des informations sur le code d’action de l’utilisateur qui a été fourni pour l’exécution filtrée d’un format de gestion des états électroniques.](./media/er-destination-action-dependent-03.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des états électroniques (ER)](general-electronic-reporting.md)

[Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md)

[Modifications de l’API de la structure de gestion des états électroniques pour Application update 10.0.17](er-apis-app10-0-17.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
