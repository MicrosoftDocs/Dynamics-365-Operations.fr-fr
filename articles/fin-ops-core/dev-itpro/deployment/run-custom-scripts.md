---
title: Exécuter des scripts X++ personnalisés sans aucun temps d’arrêt
description: Cet article décrit comment télécharger et exécuter des packages déployables contenant des scripts X++ personnalisés sans avoir à interrompre votre système.
author: AndersGirke
ms.date: 12/16/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-12-16
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: ff01e2ff8ec105603bb91e0b555301f36e8985b4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867327"
---
# <a name="run-custom-x-scripts-with-zero-downtime"></a>Exécuter des scripts X++ personnalisés sans aucun temps d’arrêt

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Cette fonctionnalité vous permet de télécharger et d’exécuter des packages déployables contenant des scripts X++ personnalisés sans avoir à passer par Microsoft Dynamics Lifecycle Services (LCS) ou à suspendre votre système. Par conséquent, vous pouvez corriger les incohérences mineures des données sans provoquer de temps d’arrêt gênant.

L’avantage d’utiliser un script X++ pour corriger les incohérences de données mineures est que le système ajustera automatiquement toutes les tables associées selon les besoins lorsqu’il exécutera le script. Cette approche permet d’assurer l’intégrité de la correction et de minimiser le risque d’introduire de nouvelles incohérences.

> [!IMPORTANT]
> Cette fonctionnalité est destinée à la correction des incohérences de données mineures uniquement. Elle ne doit pas être utilisée aux fins suivantes ou à toute autre fin :
>
> - Collecte de données
> - Modifications de schéma
> - Migration de données ou autres processus de longue durée
> - Correction de données qui peuvent être corrigées par d’autres moyens, tels que des processus commerciaux réguliers, des outils de cohérence des données ou d’autres outils en libre-service
>
> La fonctionnalité permet aux utilisateurs autorisés de modifier directement les entités et leurs enregistrements, sans avoir à exécuter la logique métier associée à ces entités. Ces modifications peuvent entraîner des problèmes d’intégrité des données. Par conséquent, votre organisation peut exiger que vous obteniez la validation et l’approbation des auditeurs internes et externes (ou d’autres parties prenantes équivalentes) avant et/ou après l’exécution d’un script. Pour des raisons de conformité, les changements affectant certaines caractéristiques peuvent également devoir être divulgués dans des rapports externes (tels que les états financiers) ou signalés aux autorités gouvernementales. Votre organisation est seule responsable de toute modification apportée à ses données via cette fonctionnalité, de toute validation et approbation ou divulgation de ces modifications, et du respect des lois applicables. Vous assumez tous les risques liés à l’utilisation de cette fonctionnalité.

Tous les packages déployables qui sont téléchargés dans le système passent par un workflow obligatoire. Par mesure de sécurité et pour garantir la séparation des tâches, l’utilisateur qui télécharge un package déployable n’est pas autorisé à l’approuver pour les étapes suivantes du flux de travail. Un autre utilisateur doit l’approuver. Cependant, une fois le package approuvé, l’utilisateur qui l’a téléchargé sera autorisé à effectuer les étapes restantes.

Le système exige que tous les packages déployables passent par un test. Avant que le script ne soit autorisé à s’exécuter sur les données de production, un utilisateur doit valider que la sortie est correcte en sélectionnant **Accepter le journal de tests**. Si la sortie n’est pas correcte, l’utilisateur doit marquer le package comme ayant échoué en sélectionnant **Abandonner**. Dans ce cas, le script ne sera pas autorisé à s’exécuter sur les données de production.

Chaque package téléchargé est enregistré dans le système et passe par un flux de travail défini d’événements. Pour chaque événement, le système conserve un journal qui inclut un horodatage et l’identité de la personne qui a effectué l’événement. De cette façon, le système garantit qu’il existe une piste d’audit.

Comme le montre l’illustration suivante, le système fournit des détails sur la façon dont chaque package déployable a été exécuté dans X++ et quelles entités ont été touchées.

![Page des détails du script.](media/script-details.png "Page des détails du script")

## <a name="assign-duties-to-users-to-control-access"></a>Attribuez des tâches aux utilisateurs pour contrôler l’accès

Cette fonctionnalité offre les responsabilités suivantes. Les administrateurs peuvent utiliser ces responsabilités pour aider à contrôler l’accès à la fonctionnalité.

- **Maintenir des scripts personnalisés** : cette obligation donne la possibilité de télécharger, tester, vérifier et exécuter des scripts X++ personnalisés dans des environnements (tests d’acceptation des utilisateurs \[UAT\] et production).
- **Approuver les scripts personnalisés** : cette obligation donne la possibilité d’approuver un script X++ personnalisé téléchargé. L’approbation est une étape obligatoire avant qu’un script puisse être testé, vérifié et exécuté.

Pour aider à minimiser le risque d’action malveillante, chaque script doit être explicitement approuvé par un utilisateur autre que celui qui l’a téléchargé. Avant de pouvoir utiliser cette fonctionnalité dans votre organisation, un administrateur doit attribuer les tâches précédentes à au moins deux utilisateurs pertinents et hautement fiables. Bien qu’un seul utilisateur puisse avoir les deux fonctions, cet utilisateur ne pourra toujours pas approuver ses propres scripts.

## <a name="create-a-deployable-package"></a>Créer un package déployable

La fonctionnalité nécessite un package déployable standard qui peut être créé dans Visual Studio. Pour des instructions, voir [Créer des packages déployables de modèles](../deployment/create-apply-deployable-package.md).

Votre package déployable doit contenir exactement une classe X++ exécutable. En d’autres termes, il doit avoir une classe qui inclut une méthode qui a la signature suivante.

```xpp
public static void main(Args _args)
```

> [!NOTE]
> Le nom de la méthode principale doit être en minuscules.

## <a name="code-example"></a>Exemple de code

L’exemple de code suivant montre comment un package déployable peut être structuré.

```xpp
class MyScriptClassForIssueXYZ
{
    public static void main(Args _args)
    {
        if (curExt() != 'DAT')
        {
            throw error("This script must run in the DAT company!");
        }

        ttsbegin;

        MyTable myTable;

        update_recordset myTable
            setting myField = 17
            where myTable.myReference == 'xyz';

        if (myTable.RowCount() != 1)
        {
            throw error("Not updating the expected row!");
        }

        info("Success");
  
        ttscommit;
    }

}
```

## <a name="best-practices"></a>Bonnes pratiques

La liste suivante décrit certaines des bonnes pratiques pour réussir l’écriture, l’implémentation et l’exécution d’un script. La liste n’est pas exhaustive et ne doit être considérée qu’à titre indicatif.

- **Écrivez** un message de réussite à la fin du script. De cette façon, vous pourrez voir que le script s’est exécuté sans exception.
- **Ajoutez** un traitement explicite de la portée de la transaction.
- **Utilisez** la logique métier existante, telle que les méthodes `update()`, mais ne contournez **pas** la logique métier en utilisant les méthodes `doUpdate()`, `doInsert()` et `doDelete()`. Cette approche permet de s’assurer que les données dépendantes sont traitées correctement. Cela réduira également considérablement le risque d’autres incohérences de données.
- **Affirmez** le contexte de l’entreprise. Cette approche exposera les erreurs courantes lors de l’exécution d’un script. Par exemple, il révélera si le script est exécuté dans la mauvaise entreprise.
- **Affirmez** que le nombre d’enregistrements concernés correspond à vos attentes. Cette approche révélera si des données ont été déplacées de manière inattendue dans le système pendant la préparation du script.
- **Utilisez** des noms de classe uniques pour chaque script (par exemple, en incluant une référence à un élément de travail dans le nom). Cette approche évitera les problèmes de conflit de noms lorsque vous téléchargez le script. Si une nouvelle itération d’un script est requise, assurez-vous de lui donner un nouveau nom.
- **Testez** chaque script dans un environnement de non-production. Testez l’impact prévu et les effets secondaires non intentionnels sur les données associées. Assurez-vous que tous les processus métier susceptibles d’être affectés peuvent être terminés avec succès et entièrement par la suite.

## <a name="upload-and-run-a-deployable-package"></a>Télécharger et exécuter un package déployable

Utilisez la procédure suivante pour importer et exécuter un script.

1. Dans votre application Finances et Opérations, accédez à **Administration du système \> Tâches périodiques \> Base de données \> Scripts personnalisés**.
1. Sélectionnez **Charger**.
1. Sélectionnez le package déployable que vous avez créé comme décrit précédemment dans cet article. Vous serez invité à spécifier l’objectif du script.
1. Le script doit maintenant être approuvé par un utilisateur autre que celui qui l’a importé. L’approbateur doit suivre la procédure ci-après :

    1. Accédez à **Administration du système \> Périodique \> Base de données \> Scripts personnalisés**.
    1. Sélectionnez le script à approuver, puis sélectionnez **Détails**.
    1. Dans le volet Actions, sous l’onglet **Worflow du processus**, dans le groupe **Démarrer**, sélectionnez **Approuver** ou **Rejeter**. Si vous sélectionnez **Approuver**, le script est marqué comme approuvé et est déverrouillé pour les tests. Si vous sélectionnez **Rejeter**, le script est verrouillé. Dans les deux cas, l’événement est consigné et une copie du script est conservée dans le système.

1. Le script doit être testé pour s’assurer qu’il fait ce qu’il est censé faire. Le testeur peut être le même que le chargeur ou l’approbateur, ou il peut s’agir d’un troisième utilisateur disposant des autorisations requises. Le testeur doit suivre la procédure ci-après :

    1. Accédez à **Administration du système \> Périodique \> Base de données \> Scripts personnalisés**.
    1. Sélectionnez le script à tester, puis sélectionnez **Détails**.
    1. Dans le volet Actions, sous l’onglet **Traiter le flux de travail**, dans le groupe **Tester**, sélectionnez **Exécuter le test**. Le script est exécuté dans une transaction temporaire que le système abandonnera automatiquement pendant qu’il collecte divers journaux et instructions SQL.
    1. Une fois l’exécution du script terminée, consultez les journaux et vérifiez que les résultats répondent à vos attentes. Utilisez l’une des procédures suivantes :

        - Si vous êtes satisfait du résultat du test, sélectionnez **Accepter le journal de test** dans le groupe **Test** sur l’onglet **Traiter le flux de travail** du volet Actions pour permettre l’exécution du script. Le journal des événements reflétera le fait que le script a été testé et indiquera qui l’a testé et quand.
        - Si vous êtes satisfait du résultat du test, sélectionnez **Abandonner** dans le groupe **Fin** sur l’onglet **Traiter le flux de travail** du volet Actions pour éviter l’exécution du script. Le système conservera une copie du script avec un journal de son historique.

1. Lorsque vous êtes sûr que le script répond à vos attentes, sélectionnez **Exécuter** dans le groupe **Exécuter** sur l’onglet **Traiter le flux de travail** du volet Actions. Cette commande fait la même chose que le test précédent, mais la transaction sera validée à la fin.
1. Une fois l’exécution du script terminée, vérifiez le résultat et confirmez que le script a fonctionné comme prévu. Utilisez l’une des procédures suivantes :

    - Si vous êtes satisfait du résultat, sélectionnez **Objectif résolu** dans le groupe **Fin** sur l’onglet **Traiter le flux de travail** du volet Actions. Le journal des événements reflétera le fait que le script a été exécuté avec succès et indiquera qui l’a vérifié et quand. Le script est enregistré, mais il est maintenant verrouillé et ne peut plus être exécuté.
    - Si vous n’êtes pas satisfait du résultat, sélectionnez **Objectif non résolu** dans le groupe **Fin** sur l’onglet **Traiter le flux de travail** du volet Actions. Le journal des événements reflétera le fait que le script a échoué à satisfaire son objectif prévu et indiquera qui l’a exécuté et quand. Le script est enregistré, mais il est maintenant verrouillé et ne peut plus être exécuté. Cependant, le système n’annule pas automatiquement l’action du script. Vous devrez peut-être écrire, importer et exécuter un nouveau script pour annuler l’effet que le script ayant échoué a eu sur votre système.

Votre sélection à la dernière étape définit l’état final du script. Vous pouvez répéter le processus selon vos besoins.

## <a name="upload-and-run-a-deployable-package-through-lcs"></a>Télécharger et exécuter un package déployable via LCS

Au lieu de déployer votre package déployable via l’interface utilisateur de votre application Finances et Opérations, comme décrit dans la section précédente, vous pouvez le télécharger sur LCS et utiliser la procédure habituelle pour le déployer. Pour en savoir plus, voir [Installer des modules déployables à partir de la ligne de commande](../deployment/install-deployable-package.md).

Bien que cette approche comporte moins de restrictions, elle offre moins de protection contre les erreurs. De plus, comme cela nécessite un redémarrage de tous les serveurs, cela entraînera des temps d’arrêt.
