---
title: "Espace de travail mobile pour la gestion des dépenses"
description: "Cette rubrique fournit des informations sur l'espace de travail mobile pour la gestion des dépenses. Cet espace de travail permet aux utilisateurs de capturer et charger une réception, afin de pouvoir l'associer à un état de dépenses ultérieurement. Les utilisateurs peuvent également créer rapidement une ligne de dépense à l'aide d'un reçu joint, puis créer et gérer leurs états de dépenses."
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 6f6add07a2426b1846cbeb9dee149a63f66f779e
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="expense-management-mobile-workspace"></a>Espace de travail mobile pour la gestion des dépenses

[!INCLUDE [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur l'espace de travail mobile **pour la gestion des dépenses**. Cet espace de travail permet aux utilisateurs de capturer et charger une réception, afin de pouvoir l'associer à un état de dépenses ultérieurement. Les utilisateurs peuvent également créer rapidement une ligne de dépense à l'aide d'un reçu joint, puis créer et gérer leurs états de dépenses. En outre, les approbateurs peuvent utiliser l'espace de travail mobile de **gestion des dépenses** pour afficher les états de dépenses qui leur sont affectés, et d'approuver ou de rejeter ces états de dépenses.


Cet espace de travail mobile est destiné à être utilisé avec l'application mobile Microsoft Dynamics 365 for Unified Operations


## <a name="overview"></a>Vue d'ensemble

Plusieurs organisations exigent qu'une copie du reçu soit ajoutée à un état de dépenses de voyage ou commerciales afin que l'employé soit remboursé. L'espace de travail mobile **Gestion des dépenses** permet aux utilisateurs de créer rapidement de nouvelles lignes de dépense sur l'appareil mobile de leur choix en joignant la photo du reçu. Alternativement, les utilisateurs peuvent prendre en photo le reçu puis l'associer à un état de dépenses ultérieurement. Les employés peuvent également créer et gérer leurs états de dépenses, puis les soumettre pour approbation et remboursement à l'aide d'un appareil mobile.


Spécifiquement, l'espace de travail mobile **Gestion des dépenses** permet aux utilisateurs d'effectuer les tâches suivantes :

- Prendre une photo d'un reçu, et la télécharger dans Microsoft Dynamics 365 for Finance and Operations. Vous pouvez ensuite joindre cette photo à un état de dépenses ultérieurement.
- Charger un fichier contenant le reçu capturé. Vous pouvez ensuite joindre ce fichier à un état de dépenses ultérieurement.
- Créer une nouvelle ligne de dépense à l'aide d'un reçu joint. Vous pouvez alors ajouter une ligne à un état de dépenses ultérieurement, et l'envoyer pour approbation et remboursement.

Si vous utilisez Microsoft Dynamics 365 for Finance and Operations, vous pouvez également utiliser les fonctionnalités suivantes :

- Créer un nouvel état de dépenses.
- Associer des transactions de carte de crédit et autres dépenses précédemment créées dans un état de dépenses.
- Créer de nouvelles dépenses pour un état de dépense.
- Joindre un reçu à toute dépenses d'un état de dépenses, en prenant une photo du reçu ou en téléchargeant un fichier comme reçu capturé.
- Selon la stratégie des dépenses de la société, ajoutez la liste des invités à une dépense.
- Selon la stratégie des dépenses de la société, détaillez les dépenses.
- Soumettez un état de dépenses pour approbation et remboursement.
- Approuver ou rejeter les états de dépenses dont vous êtes un approbateur.

## <a name="prerequisites"></a>Conditions préalables
Les conditions préalables varient, en fonction de la version de Microsoft Dynamics 365 qui a été déployée pour votre organisation.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a>Conditions préalables si vous utilisez Microsoft Dynamics 365 for Finance and Operations 
Si Microsoft Dynamics 365 for Finance and Operations a été déployé pour votre organisation, l'administrateur système doit publier l'espace de travail mobile **Gestion des dépenses**. Pour obtenir des instructions, voir [Publier un espace de travail mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Conditions préalables si vous utilisez la version 1611 de Microsoft Dynamics 365 for Operations avec la mise à jour de plateforme 3 ou ultérieure
Si la version 1611 de Microsoft Dynamics 365 for Operations avec la mise à jour de plateforme 3 ou ultérieure a été déployée pour votre organisation, l'administrateur système doit effectuer les tâches préalables suivantes. 

<table>
<thead>
<tr class="header">
<th>Logiciel requis</th>
<th>Rôle</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implémenter KB 4019015.</td>
<td>Administrateur système</td>
<td>Le KB 4019015 est une mise à jour X++ ou un correctif de métadonnées qui contient l'espace de travail mobile <strong>Gestion des dépenses</strong>. Pour implémenter le KB 4019015, un administrateur système doit procéder comme suit :
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Télécharger le correctif de métadonnées de Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installez le correctif de métadonnées</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Créez un module déployable</a> contenant les modèles <strong>ApplicationSuite</strong> et <strong>ExpenseMobile</strong>, et téléchargez le module déployable vers LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Appliquer le package déployable</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Publiez l'espace de travail mobile pour la <strong>Gestion des dépenses</strong>.</td>
<td>Administrateur système</td>
<td>Voir <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publier un espace de travail mobile</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Télécharger et installer l'application mobile Dynamics 365 for Operations
Téléchargez et installez l'application mobile Dynamics 365 for Unified Operations :

- [Pour les téléphones Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Pour les iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Connexion à l'application mobile
1. Démarrez l'application sur votre appareil mobile.
2. Entrez votre URL Dynamics 365.
4. Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d'utilisateur et mot de passe. Entrez vos informations d'identification.
5. Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s'affichent. Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.


[![Extraire pour actualiser](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Capturer un reçu à l'aide de l'espace de travail mobile Gestion des dépenses

1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des dépenses**.
2. Sélectionnez **Capturer le reçu**.
3. Sélectionnez **Prendre une photo** ou **Choisir une image**.
4. Utilisez l'une des procédures suivantes :

    - Si vous sélectionnez **Prendre une photo**, procédez comme suit :

        1. L'appareil-photo s'ouvre sur votre appareil mobile, pour vous permettre de prendre une photo du ticket de caisse. Lorsque vous avez terminé de prendre la photo, sélectionnez **OK** pour accepter la photo.
        2. Facultatif : entrez un nom pour la photo, puis entrez des notes.

    - Si vous avez sélectionné **Choisir une image**, procédez comme suit :

        1. Sélectionnez une image dans la liste.
        2. Facultatif : entrez un nom pour l'image, puis entrez des notes.

5. Sélectionnez **Terminé**.

## <a name="quickly-enter-expenses-by-using-the-expense-management-mobile-workspace"></a>Entrer rapidement des dépenses à l'aide de l'espace de travail mobile Gestion des dépenses
1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des dépenses**.
2. Sélectionnez **Entrée rapide de dépense**.
3. Sélectionnez la catégorie de la dépense. Vous verrez la liste des catégories de dépense dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si votre catégorie ne figure pas dans la liste, sélectionnez **Rechercher** pour effectuer une recherche en ligne. Recherchez par catégorie de dépense, ou lancez une recherche par type de dépense.
4. Entrez la date de transaction de la dépense.
5. Facultatif : entrez le marchand pour la dépense.
6. Entrez le montant de la dépense.
7. Ssélectionnez la devise de la dépense. Vous verrez la liste des codes de devise dans votre application pour l'utilisation hors ligne. Par défaut, 400 dévises sont chargées, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si votre devise ne figure pas dans la liste, sélectionnez **Rechercher** pour effectuer une recherche en ligne. Recherchez par devise, ou lancez une rechercher par nom.
8. Sélectionnez **Prendre une photo** ou **Choisir une image**.
9. Utilisez l'une des procédures suivantes :

    - Si vous avez sélectionné **Prendre une photo**, l'appareil-photo s'ouvre sur votre appareil mobile, pour vous permettre de prendre une photo du ticket de caisse. Lorsque vous avez terminé de prendre la photo, sélectionnez **OK** pour accepter la photo.
    - Si vous avez sélectionné **Choisir une image**, sélectionnez une image dans la liste.

10. Sélectionnez **Terminé**.

## <a name="approve-an-expense-report-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Approuver un état de dépenses à l'aide de l'espace de travail mobile Gestion des dépenses (si vous utilisez la mise à jour de juillet 2017)
1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des dépenses**.
2. **Approbations des dépenses** affiche le nombre d'états de dépenses qui vous sont affectés pour approbation. Ce nombre est mis à jour environ toutes les 30 minutes. Sélectionnez **Approbations des dépenses**.

    La liste des états de dépenses qui vous sont affectés pour approbation s'affiche.
    
3. Sélectionnez un état de dépenses pour en afficher les détails.
4. Sélectionnez une dépense pour en afficher les détails. Les informations affichées pour une dépense incluent tous les détails du reçu, de l'invité, et des détails.
5. De retour sur la page **État des dépenses**, sélectionnez pour approuver ou rejeter l'état des dépenses.
6. Entrez des commentaires pour l'action d'approbation.
7. Sélectionnez **Terminé**.

## <a name="create-a-new-expense-report-and-submit-it-for-approval-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Créez un état de dépenses et soumettez-le pour approbation à l'aide de l'espace de travail mobile Gestion des dépenses (si vous utilisez la mise à jour de juillet 2017)
1. Sur votre appareil mobile, ouvrez l'espace de travail **Gestion des dépenses**.
2. Sélectionnez **Entrée de dépense**.
3. Sélectionnez **Nouvel état**, ou sélectionnez un état de dépenses existant dans la liste.
4. Pour les nouveaux états de dépenses, entrez l'objet et toute information supplémentaire disponible. Ces informations varient en fonction de la manière dont la gestion des dépenses est configurée pour votre société.
5. Sélectionnez **Terminé**.
6. Pour ajouter des dépenses existantes, telles que des transactions de carte de crédit, à l'état des dépenses, sélectionnez **Attacher**.
7. Sélectionnez une ou plusieurs dépenses dans la liste.
8. Sélectionnez **Terminé**.
9. Pour ajouter une nouvelle dépense à l'état des dépenses, sélectionnez **Nouvelle dépense**.
10. Sélectionnez la catégorie de la dépense. Vous verrez la liste des catégories de dépense dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si votre catégorie ne figure pas dans la liste, sélectionnez **Rechercher** pour effectuer une recherche en ligne. Recherchez par catégorie de dépense, ou lancez une recherche par type de dépense.
11. Facultatif : entrez le marchand pour la dépense.
12. Entrez la date de transaction de la dépense.
13. Entrez le montant de la dépense.
14. Ssélectionnez la devise de la dépense. Vous verrez la liste des codes de devise dans votre application pour l'utilisation hors ligne. Par défaut, 400 dévises sont chargées, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si votre devise ne figure pas dans la liste, sélectionnez **Rechercher** pour effectuer une recherche en ligne. Recherchez par devise, ou lancez une rechercher par nom.
15. Sélectionnez **Terminé**.
16. Pour ajouter des détails supplémentaires à la dépense, sélectionnez **Ajouter plus de détails**. Les champs disponibles varient en fonction de la configuration de la gestion des dépenses de votre société.
17. Si la stratégie de la société nécessite un reçu pour la dépense, sélectionnez **Reçus**, puis procédez comme suit :

    1. Sélectionnez **Capturer le reçu** ou **Associer un ticket de caisse**.
    2. Utilisez l'une des procédures suivantes :

        - Si vous avez sélectionné **Capturer un reçu**, procédez comme suit :

            1. Sélectionnez **Prendre une photo** ou **Choisir une image**.
            2. Utilisez l'une des procédures suivantes :

                - Si vous sélectionnez **Prendre une photo**, procédez comme suit :

                    1. L'appareil-photo s'ouvre sur votre appareil mobile, pour vous permettre de prendre une photo du ticket de caisse. Lorsque vous avez terminé de prendre la photo, sélectionnez **OK** pour accepter la photo.
                    2. Facultatif : entrez un nom pour la photo, puis entrez des notes.

                - Si vous avez sélectionné **Choisir une image**, procédez comme suit :

                    1. Sélectionnez une image dans la liste.
                    2. Facultatif : entrez un nom pour l'image, puis entrez des notes.

            3.  Sélectionnez **Terminé**.

        - Si vous avez sélectionné **Associer un ticket de caisse**, procédez comme suit :

            1.  Sélectionnez une ou plusieurs images de la liste.
            2.  Sélectionnez **Terminé**.

    3. Pour revenir aux détails des dépenses, cliquez sur le bouton **Précédent**.

18. Si la stratégie de la société nécessite des invités pour la dépense, sélectionnez **Invités**, puis procédez comme suit :

    1. Sélectionnez **Invité**, **Invités précédents** ou **Collègues**.
    2. Utilisez l'une des procédures suivantes :

        - Si vous avez sélectionné **Invité**, procédez comme suit :

            1. Entrer le nom de l'invité.
            2. Facultatif : Entrez l'organisation et/ou le pays de l'invité.
            3. Facultatif : Entrer le titre de l'invité.
            4. Sélectionnez **Terminé**.

        - Si vous avez sélectionné **Invités précédents**, procédez comme suit :

            1. Sélectionnez un ou plusieurs invités précédents de la liste. Vous découvrez une liste d'invités précédents que vous avez ajoutés aux états de dépenses précédents chargés dans votre application pour une utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si votre invité précédent ne figure pas dans la liste, sélectionnez **Rechercher** pour effectuer une recherche en ligne. Recherchez par nom, ou lancez une recherche par organisation, pays ou titre.
            2. Sélectionnez **Terminé**.

        - Si vous avez sélectionné **Collègues**, procédez comme suit :

            1. Sélectionnez un ou plusieurs collègues de la liste. Vous verrez la liste des collègues chargés dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si votre collègue ne figure pas dans la liste, sélectionnez **Rechercher** pour effectuer une recherche en ligne. Recherchez par nom, ou lancez une recherche par société ou titre.
            2. Sélectionnez **Terminé**.

    3. Pour revenir aux détails des dépenses, cliquez sur le bouton **Précédent**.

19. Si la stratégie de la société nécessite que la dépense soit détaillée, sélectionnez **Détailler**, puis procédez comme suit :

    1. Sélectionnez la première date à détailler.
    2. Sélectionnez **Ajouter énumération**.
    3. Sélectionnez la sous-catégorie de détails des dépenses. Vous verrez la liste des sous-catégories de dépense dans votre application pour l'utilisation hors ligne. Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre. Pour plus d'informations, les développeurs doivent consulter [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si votre sous-catégorie ne figure pas dans la liste, sélectionnez **Rechercher** pour effectuer une recherche en ligne. Rechercher par nom de sous-catégorie de dépense.
    4. Entrez le montant de la transaction pour l'énumération.
    5. Modifiez la date de transaction au besoin.
    6. Sélectionnez **Terminé**.
    7. Répétez les étapes précédentes jusqu'à ce que vous ayez ajouté tous les détails de la date sélectionnée.
    8. Pour les jours supplémentaires, vous pouvez sélectionner **Copier vers le jour suivant** pour copier les détails au jour suivant. Sinon, vous pouvez sélectionner la date à détailler et ajouter des détails comme pour la première date.
    9. Après avoir terminé de détailler les dépenses, sélectionnez le bouton **Précédent** pour revenir aux détails de dépenses.

20. Pour revenir à la page **États des dépenses**, cliquez sur le bouton **Précédent**.
21. Répétez les étapes précédentes jusqu'à ce que vous ayez ajouté toutes les dépenses.
22. Sélectionnez **Soumettre**.
23. Entrez des commentaires pour l'approbateur.
24. Sélectionnez **Terminé**.

