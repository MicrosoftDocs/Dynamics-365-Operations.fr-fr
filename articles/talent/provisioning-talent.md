---
title: Mettre en service Microsoft Dynamics 365 for Talent
description: "Cette rubrique décrit le processus de mise en service d'un nouvel environnement pour Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ba1a3a78d59f3aec91473ba9bb20bda4804ec92e
ms.openlocfilehash: 0a43f5ff0987ede9f0cb80e5b4854f78e19e329b
ms.contentlocale: fr-fr
ms.lasthandoff: 03/23/2018

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Mettre en service Microsoft Dynamics 365 for Talent

[!include[banner](includes/banner.md)]

Cette rubrique décrit le processus de mise en service d'un nouvel environnement de production pour Microsoft Dynamics 365 for Talent. Cette rubrique suppose que vous avez acheté Talent par l'intermédiaire d'un fournisseur de solutions Cloud (CSP) ou dans le cadre d'un contrat d'architecture d'entreprise (EA). Si vous disposez d'une licence Microsoft Dynamics 365 existante qui inclut déjà le plan de service Talent et que vous ne pouvez pas effectuer les étapes décrites dans cette rubrique, contactez le support technique.

Pour commencer, l'administrateur global doit se connecter à [Microsoft Dynamics Lifecycle Services](http://lcs.dynamics.com) (LCS) et créer un projet Talent. Il n'est pas nécessaire de contacter le support technique ou les représentants de Dynamics Service Engineering (DSE) sauf si un problème de licence vous empêche de mettre en service Talent.

## <a name="create-an-lcs-project"></a>Créer un projet LCS
Pour utiliser LCS pour gérer vos environnements Talent, vous devez d'abord créer un projet LCS.

1. Connectez-vous à [LCS](https://lcs.dynamics.com/Logon/Index) à l'aide du compte utilisé pour vous abonner à Talent.
2. Sélectionnez le signe plus (**+**) pour créer un projet.
3. Sélectionnez **Microsoft Dynamics 365 for Talent** comme nom et version du produit.
4. Sélectionnez la méthodologie **Dynamics 365 for Talent**.
5. Sélectionnez **Créer**.

Pour plus d'informations sur la mise en route de Talent, consultez la méthodologie **Talent** que vous avez créée dans votre nouveau projet. Une fois que vous avez terminé de créer le projet, exécutez la procédure suivante pour mettre en service votre environnement Talent.

## <a name="provision-a-talent-project"></a>Mettre en service un projet Talent
Une fois que vous avez créé un projet LCS, vous pouvez mettre en service Talent dans un environnement.

1. Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Talent**.
2. Talent est toujours mis en service dans un environnement Microsoft PowerApps pour permettre l'intégration et l'extensibilité des applications PowerApps. Lisez la section « Sélectionnant d'un environnement PowerApps » de cette rubrique avant de continuer. 
3. Si vous ne disposez pas déjà d'un environnement PowerApps, suivez les étapes décrites dans la section « Créer un environnement PowerApps (si nécessaire) » de cette rubrique avant de continuer.

    > [!NOTE]
    > Pour afficher les environnements existants ou en créer de nouveaux, la licence P2 PowerApps doit être affectée à l'administrateur qui met en service Talent. Si votre organisation ne dispose pas d'une licence P2 PowerApps, vous pouvez en obtenir une auprès de votre fournisseur CSP ou à partir de la [Page de tarification PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

4. Sélectionnez **Ajouter**, puis sélectionnez l'environnement dans lequel mettre en service Talent.
5. Sélectionnez **Oui** pour accepter les termes et commencer le déploiement.

    Votre nouvel environnement apparaît dans la liste des environnements dans le volet de navigation à gauche. Toutefois, vous ne pouvez pas commencer à utiliser l'environnement jusqu'à ce que le statut de déploiement soit mis jour sur **Déployé**. Ce processus ne prend généralement que quelques minutes. Si le processus d'approvisionnement est infructueux, vous devez contacter le support technique.

6. Sélectionnez **Se connecter à Talent** pour utiliser votre nouvel environnement.

> [!NOTE]
> Si vous ne vous êtes pas encore déconnecté, vous pouvez déployer une instance de test de Talent dans le projet. Vous pouvez ensuite utiliser cette instance pour tester votre solution jusqu'à ce que vous vous déconnectiez. Si vous utilisez votre nouvel environnement pour les tests, vous devez répéter cette procédure pour créer un environnement de production.

> [!NOTE]
> Les environnements Talent qui sont mis en service via LCS ne contiennent pas de données de démonstration configurées pour les tâches liées aux Ressources humaines (RH) ou spécifiques à Talent. Si vous exigez un environnement qui contient les données de démonstration, nous vous recommandons de vous inscrire gratuitement pour une période de 60 jours [Environnement d'évaluation Talent](https://dynamics.microsoft.com/en-us/talent/overview/). Bien qu'un environnement d'évaluation soit la propriété de l'utilisateur qui l'a demandé, d'autres utilisateurs peuvent être invités via l'expérience d'administration système pour Core RH. Les environnements d'évaluation contiennent des données fictives qui peuvent être utilisées pour explorer le programme de manière sûre. Ils ne sont pas destinés à être utilisés comme environnements de production. Notez que lorsque l'environnement d'évaluation expire après 60 jours, toutes les données qu'il contient sont supprimées et ne peuvent pas être récupérées. Vous pouvez vous inscrire à un nouvel environnement d'évaluation après expiration de l'environnement existant.

## <a name="select-a-powerapps-environment"></a>Sélectionner un environnement PowerApps

L'intégration entre les environnements Talent et PowerApps permet d'intégrer et d'étendre l'utilisation des données Talent à l'aide des outils PowerApps. La compréhension de l'objectif des environnements PowerApps vous aidera non seulement à créer des applications pour étendre Talent, mais aussi à sélectionner l'environnement approprié lorsque du provisionnement de Talent. Pour plus d'informations sur les environnements PowerApps, notamment la portée de l'environnement, l'accès à l'environnement ainsi que la création et le choix d'un environnement, voir [Annonce des environnements PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). 

Utilisez les consignes suivantes pour déterminer dans quel environnement PowerApps déployer Talent : 
1. Dans LCS, sélectionnez Gérer les environnements, ou accédez directement au Centre d'administration de PowerApps, dans lequel vous pouvez afficher les environnements existants et créer des environnements.
2. Un seul environnement Talent est mappé à un seul environnement PowerApps.
3. Un environnement PowerApps « contient » l'application Talent, ainsi que les applications PowerApps, Flow et CDS correspondantes. Si l'environnement PowerApps est supprimé, les applications qu'il contient le sont aussi.
4. Des stratégies d'intégration de données et de test doivent être envisagées, par exemple : Bac à sable (Sandbox), UAT, Production. Par conséquent, nous vous recommandons de définir les différentes implications pour le déploiement, car il sera difficile de modifier l'environnement Talent mappé à un environnement PowerApps par la suite.
5. Les environnements PowerApps suivants ne peuvent pas être utilisés pour Talent et seront filtrés de la liste de sélection dans LCS :
 
    **Environnements CDS 2.0** CDS 2.0 sera rendu disponible au public le 21 mars 2018 ; toutefois, Talent ne prend pas encore en charge CDS 2.0. Même si vous pouvez afficher et créer des bases de données CDS 2.0 dans le Centre d'administration PowerApps, elles ne sont pas utilisables dans Talent. L'option pour utiliser les environnements CDS 2.0 dans les déploiements de Talent sera disponible à une date ultérieure.
   
 > [!Note]
 > Pour distinguer les environnements CDS 1.0 et 2.0 dans le portail d'administration, sélectionnez un environnement et consultez **Détails**. Les environnements CDS 2.0 font tous référence au fait que « Vous pouvez gérer ces paramètres dans le Centre d'administration de Dynamics 365 », pointent vers une version d'instance, et n'ont aucun onglet Base de données. 
 
   **Environnements PowerApps par défaut** Bien que chaque locataire soit automatiquement provisionné avec un environnement PowerApps par défaut, nous ne vous recommandons pas de l'utiliser avec Talent, car tous les utilisateurs d'un locataire ont accès à l'environnement PowerApps et peuvent involontairement endommager des données de production lors de tests et en explorant avec les intégrations PowerApps ou Flow.
   
   **Environnements de test** Les environnements avec un nom comme « TestDrive – alias@domain » sont créés avec une période d'expiration de 60 jours et expirent après ce délai, entraînant la suppression automatique de votre environnement.
   
   **Zones non prises en charge** Actuellement, Talent n'est pris en charge que dans les zones suivantes : États-Unis, Europe ou Australie.
  
6. Il n'existe aucune action spécifique à effectuer une fois que vous avez déterminé l'environnement correct à utiliser. Poursuivez le processus de provisionnement. 
 
## <a name="create-a-new-powerapps-environment-if-required"></a>Créer un environnement PowerApps (si nécessaire)

Exécutez un script PowerShell pour créer un environnement PowerApps pour Talent dans le contexte de l'administrateur de locataire disposant de la licence PowerApps Plan 2. Le script automatise les étapes suivantes :


 + Création d'un environnement PowerApps
 + Création d'une base de données CDS 1.0
 + Effacer tous les exemples de données dans la base de données CDS 1.0


Complétez les instructions suivantes pour exécuter le script :

1. Téléchargez le fichier ProvisionCDSEnvironment.zip à l'emplacement suivant : [Scripts ProvisionCDSEnvironment](https://go.microsoft.com/fwlink/?linkid=870436)  

2. Décompressez le contenu complet du fichier ProvisionCDSEnviroinment.zip dans un dossier.

3. Exécutez le programme Windows PowerShell ou Windows PowerShell ISE en tant qu'administrateur.

   Visitez la rubrique [Définir la stratégie d'exécution](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) pour en savoir plus sur la définition de la stratégie d'exécution afin que les scripts puissent être exécutés.
  
4. Dans PowerShell, accédez au dossier où vous avez décompressé le fichier et exécutez la commande suivante, pour remplacer les valeurs comme indiqué ci-dessous :
 
   ```.\ProvisionCDSEnvironment -EnvironmentName MyNewEnvironment -Location YourLocation```

    
   **EnvironmentName** doit être remplacé par votre nom d'environnement. Ce nom s'affichera dans LCS et sera visible lorsque les utilisateurs sélectionnent l'environnement Talent à utiliser. 

   **YourLocation** doit être remplacé par l'une des régions prises en charge par Talent : États-Unis, Europe, Australie. 

   **-Verbose** est facultatif et fournit des informations détaillées à envoyer au support technique si des problèmes sont rencontrés.

5. Poursuivez le processus de provisionnement.
 


## <a name="grant-access-to-the-environment"></a>Autoriser l'accès à l'environnement
Par défaut, l'administrateur global ayant créé l'environnement y a accès. Cependant, les autres utilisateurs d'application doivent avoir un accès explicitement autorisé. Pour accorder l'accès, [ajoutez des utilisateurs](../dev-itpro/sysadmin/tasks/create-new-users.md) et [affectez-leurs les rôles appropriés](../dev-itpro/sysadmin/tasks/assign-users-security-roles.md) dans Core RH. Vous devez également ajouter ces utilisateurs à l'environnement PowerApps, afin qu'ils puissent accéder aux applications Attract et Onboard. La procédure est décrite ici. Si vous avez besoin d'aide pour effectuer les étapes, voir le billet de blog [Présentation du centre d'administration PowerApps](https://powerapps.microsoft.com/en-us/blog/introducing-admin-center-for-powerapps/).

Cette procédure est effectuée par l'administrateur global qui a déployé l'environnement Talent.

1. Ouvrez le [Centre d'administration PowerApps](https://preview.admin.powerapps.com/environments).
2. Sélectionnez les environnements appropriés.
3. Sous l'onglet **Sécurité**, ajoutez les utilisateurs requis au rôle **Créateur d'environnement**.

    Notez que cette dernière étape, dans laquelle vous ajoutez manuellement des utilisateurs à l'environnement PowerApps, est temporaire. Par la suite, elle sera effectuée automatiquement lorsque les utilisateurs sont ajoutés à Core RH.

