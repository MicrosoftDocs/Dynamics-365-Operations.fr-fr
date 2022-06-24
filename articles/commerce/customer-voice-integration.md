---
title: Intégrer Customer Voice dans les pages du site d’e-commerce
description: Cet article décrit comment intégrer Microsoft Dynamics 365 Customer Voice dans des pages de sites e-commerce Dynamics 365 Commerce.
author: samjarawan
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: c8c67ecf4950c92fc91c8d119e06e5e8afff0ddf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850328"
---
# <a name="integrate-customer-voice-into-e-commerce-site-pages"></a>Intégrer Customer Voice dans les pages du site d’e-commerce

[!include [banner](../includes/banner.md)]

Cet article décrit comment intégrer Microsoft Dynamics 365 Customer Voice dans des pages de sites e-commerce Dynamics 365 Commerce.

Vous pouvez intégrer [Customer Voice](https://dynamics.microsoft.com/customer-voice/overview/) dans votre site e-commerce pour collecter, analyser et suivre les retours clients en temps réel. Pour commencer l’intégration, vous devez créer un compte et sélectionner un modèle de projet Customer Voice pour le type de commentaires que vous souhaitez recueillir.

## <a name="integrate-the-customer-voice-service"></a>Intégrer le service Customer Voice

Pour créer un compte Customer Voice, allez dans [Customer Voice](https://dynamics.microsoft.com/customer-voice/overview/), et suivez les invites.

Après avoir créé un compte Customer Voice et vous y être connecté, l’étape suivante consiste à sélectionner un modèle de projet pour le type de commentaires que vous souhaitez recueillir.

Pour sélectionner un modèle de projet Customer Voice, procédez comme suit :

1. Accédez à la page du [modèle de projet Customer Voice](https://customervoice.microsoft.com/Pages/ProjectPage.aspx).
1. Sélectionnez **Prise en main**.
1. Sélectionnez le modèle de projet correspondant au type de commentaire que vous souhaitez recueillir, puis sélectionnez **Suivant**.
1. Sur l’onglet **Envoyer**, sélectionnez un format incorporé sous **Choisir un format incorporé**. Le champ **Code intégré** indique le code qui doit être intégré dans le générateur de site Commerce.

Les exemples de cet article utilisent le modèle de projet **Enquête périodique auprès des clients** et le format incorporé **Bouton**.

L’exemple d’illustration suivant montre la page du modèle de projet **Enquête périodique auprès des clients**, avec l’option pour le format incorporé **Bouton** sélectionnée et le code incorporé de cette option affiché dans le champ **Code incorporé**. Trois actions distinctes sont nécessaires pour incorporer le code fourni dans les pages de votre site, comme décrit dans les sections suivantes.

![Page d’enquête périodique auprès des clients Customer Voice avec l’option Bouton sélectionnée.](media/customer-voice-integration-1.png)

### <a name="embed-the-external-script-url"></a>Incorporer l’URL du script externe

Sur toutes les pages du site qui doivent comporter une enquête Customer Voice, vous devez incorporer l’URL de script externe fournie par Customer Voice dans le code incorporé. La meilleure façon d’incorporer le script sur plusieurs pages du site est de créer un fragment dans le générateur de site qui contient l’URL du script externe, puis d’ajouter le fragment aux modèles de page appropriés. Après avoir publié un modèle mis à jour, le code de script externe intégré ressemblera à l’exemple suivant sur les pages de site concernées.

```html
<script src=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.js type="text/javascript"></script>
```

Pour plus d’informations sur les fragments, voir [Utiliser des fragments](work-with-fragments.md).

> [!NOTE]
> Vous n’avez qu’à ajouter l’URL au fragment. Le module de script externe ajoutera l’autre code de script.

Pour incorporer l’URL de script externe dans un fragment, procédez comme suit :

1. Dans le générateur de site, créez un fragment basé sur le [Module de script externe](script-module.md).
1. Dans le nouveau fragment, sélectionnez l’emplacement **Script externe par défaut**.
1. Dans le volet des propriétés **Script externe par défaut**, dans le champ **Source du script**, entrez l’URL du script externe, comme illustré dans l’exemple suivant.

    ![URL de script externe dans le champ Source du script pour le nouveau fragment.](media/customer-voice-integration-2.png)

1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Sélectionnez **Publier** pour publier le fragment.

Le nouveau fragment contenant le bloc de script externe intégré est maintenant prêt à être ajouté au modèle de page approprié.

### <a name="embed-the-external-style-sheet-code"></a>Incorporer le code de la feuille de style externe

Ensuite, sur toutes les pages du site qui doivent comporter une enquête Customer Voice, vous devez incorporer le code de feuille de style externe fourni par Customer Voice dans le code incorporé. Comme décrit dans la section précédente, la meilleure façon d’incorporer le code de feuille de style externe sur plusieurs pages du site est de créer un fragment dans le générateur de site qui contient le code de feuille de style externe, puis d’ajouter le fragment aux modèles de page appropriés. Le code de feuille de style externe intégré ressemblera à l’exemple de code suivant.

```typescript
<link rel="stylesheet" type="text/css" href=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.css />
```

Pour incorporer le code de feuille de style externe dans un fragment, procédez comme suit :

1. Dans le générateur de site, créez un fragment basé sur le [Module de métabalises](metatags-module.md).
1. Dans le fragment, sélectionnez l’emplacement **Métabalises par défaut**.
1. Dans le volet des propriétés **Métabalises par défaut**, dans le champ **Balises meta**, entrez le code de feuille de style, comme illustré dans l’exemple suivant.

    ![Code de feuille de style externe dans le champ Balises meta pour le nouveau fragment.](media/customer-voice-integration-3.png)

1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Sélectionnez **Publier** pour publier le fragment.

Le nouveau fragment contenant le code de feuille de style externe intégré est maintenant prêt à être ajouté au modèle de page approprié.

### <a name="embed-the-inline-script-code"></a>Incorporer le code de script en ligne 

Ensuite, sur toutes les pages du site qui doivent comporter une enquête Customer Voice, vous devez incorporer le code de script en ligne fourni par Customer Voice dans le code incorporé. Comme décrit dans les sections précédentes, la meilleure façon d’incorporer le code de script en ligne sur plusieurs pages du site est de créer un fragment dans le générateur de site qui contient le code de script en ligne, puis d’ajouter le fragment aux modèles de page appropriés.

Dans l’exemple suivant de code de script en ligne, **SURVEY\_KEY** est un espace réservé. La valeur pour **SURVEY\_KEY** doit correspondre à la clé d’enquête réelle fournie par Customer Voice dans le code incorporé. La dernière ligne appelle le code pour afficher le bouton d’enquête après une seconde, afin de s’assurer que les scripts ont suffisamment de temps pour être chargés. Selon l’enquête que vous avez sélectionnée, vous devrez peut-être également ajouter ou mettre à jour d’autres métadonnées, telles que le nom de l’entreprise.

```html
function renderSurveyButton() {
    var se = new SurveyEmbed("SURVEY_KEY","https://customervoice.microsoft.com/","https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/","true");

    var context = {
        "First Name":"",
        "Last Name": "",
        "locale": "en-us",
        "companyname": "Adventure Works"
    };
    se.renderButton(context);
}

setTimeout(renderSurveyButton, 4000);
```

Pour incorporer le code de script en ligne dans un fragment, procédez comme suit :

1. Dans le générateur de site, créez un fragment basé sur le [Module de script en ligne](script-module.md).
1. Dans le fragment, sélectionnez l’emplacement **Script en ligne par défaut**.
1. Dans le volet des propriétés **Script en ligne par défaut**, dans le champ **Script en ligne**, entrez le code de script en ligne, comme illustré dans l’exemple suivant.

    ![Code de script en ligne dans le champ Script en ligne pour le nouveau fragment.](media/customer-voice-integration-4.png)

1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Sélectionnez **Publier** pour publier le fragment.

Le nouveau fragment contenant le code de script en ligne incorporé est maintenant prêt à être ajouté au modèle de page approprié.

## <a name="add-fragments-to-a-template"></a>Ajouter des fragments à un modèle

Lorsque vous avez terminé de créer les fragments contenant le code Customer Voice incorporé, vous devez les ajouter aux modèles de page associés aux pages du site où vous souhaitez les utiliser. Dans l’exemple suivant, les trois exemples de fragments ont été ajoutés à un modèle de page de détails de produit (PDP).

![Exemples de fragments ajoutés à un modèle PDP.](media/customer-voice-integration-5.png)

Une fois le modèle mis à jour publié, l’enquête Customer Voice apparaîtra sur toutes les pages contrôlées par le modèle.

Pour plus d’informations sur les modèles, voir [Utiliser des modèles](work-with-templates.md).

## <a name="configure-content-security-policy"></a>Configurer la stratégie de sécurité du contenu

Par défaut, la stratégie de sécurité du contenu (CSP) n’autorise pas les appels vers d’autres services, sauf si une configuration supplémentaire est effectuée. Par conséquent, après la publication des modèles mis à jour, il est probable que l’enquête ne soit pas chargée sur les pages de site concernées. Pour afficher les erreurs liées au CSP, ouvrez les outils de développement de votre navigateur Web (F12), puis accédez à une page contenant l’enquête. Les erreurs liées au CSP apparaîtront dans la sortie de la console.

Pour configurer le CSP dans le générateur de site pour corriger les erreurs, procédez comme suit :

1. Accédez à **Paramètres du site \> Extensions**.
1. Sur l’onglet **Stratégie de sécurité du contenu**, ajoutez `https://customervoice.microsoft.com/` à l’instruction **child-src**.
1. Ajoutez `https://customervoice.microsoft.com/` à l’instruction **frame-src**.
1. Ajoutez `https://mfpembedcdnmsit.azureedge.net` et **.azureedge.net** à l’instruction **img-src**.

Pour plus d’informations, voir [Stratégie de sécurité du contenu](manage-csp.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Module de script externe](script-module.md)

[Module de métabalises](metatags-module.md)

[Module de script en ligne](script-module.md)

[Stratégie de sécurité de contenu](manage-csp.md)

[Utiliser des fragments](work-with-fragments.md)

[Utiliser des modèles](work-with-templates.md)
