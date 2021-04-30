---
title: Optimiser les requêtes de table virtuelle de Dataverse
description: Optimiser et résoudre les problèmes de performances des requêtes de table virtuelle Dataverse
author: andreabichsel
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8026abd5c3e0f9b78e8c016731fd7785490bc945
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891100"
---
# <a name="optimize-dataverse-virtual-table-queries"></a>Optimiser les requêtes de table virtuelle de Dataverse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a>Sortie

### <a name="overview"></a>Vue d’ensemble

Lors de l'utilisation de tables virtuelles Dataverse pour développer des intégrations et d'autres connexions de données avec Dynamics 365 Human Resources, vous pouvez rencontrer des problèmes de performances avec les requêtes sur les tables virtuelles. La lenteur d'exécution des requêtes peut apparaître sur divers clients ou interfaces. Par exemple, vous pouvez rencontrer le problème dans les circonstances suivantes :

- Lors de l'interrogation d'une table virtuelle via l'APi web Dataverse
- Lors de la création d'une Power App sur une table virtuelle
- Lors de la création d'un rapport Power BI sur une table virtuelle

Toutes ces interfaces ont le potentiel de faire apparaître le problème de performances.

Une des causes de la lenteur des performances avec les tables virtuelles Dataverse tables virtuelles pour Human Resources réside dans les colonnes de clé étrangère de la table virtuelle liées aux [propriétés de navigation](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties) de la table. Lorsque les propriétés de navigation sont créées pour une table virtuelle, une colonne de clé étrangère est automatiquement ajoutée à la table pour représenter la valeur de la clé pour la colonne de clé de la table virtuelle associée. Par exemple, la colonne **_mshr_fk_person_id_value** est ajoutée à l'entité **mshr_hcmworkerbaseentity** avec la propriété de clé étrangère de l'entité **mshr_dirpersonentity**. En raison de la manière dont les valeurs de ces colonnes de clé étrangère sont conservées dans une table, l'extraction des valeurs peut avoir un impact négatif sur les performances d'une requête sur la table virtuelle.

### <a name="potential-symptoms"></a>Symptômes potentiels

Vous pouvez constater cet impact, par exemple, dans les requêtes sur l'entité Worker (Collaborateur) (**mshr_hcmworkerentity**) ou Base worker (Collaborateur de base) (**mshr_hcmworkerbaseentity**). Vous pouvez voir le problème de performances se manifester de différentes manières :

- **Exécution lente des requêtes** : la requête sur la table virtuelle peut renvoyer les résultats attendus, mais prendre plus de temps que prévu pour être menée à bien.
- **Délai d'expiration de la requête** : la requête peut parvenir à expiration et renvoyer l'erreur suivante : « Un jeton a été obtenu pour appeler Finance and Operations, mais Finance and Operations a renvoyé une erreur de type InternalServerError. »
- **Erreur inattendue** : la requête peut renvoyer une erreur de type 400 avec le message suivant : « Une erreur inattendue s'est produite ».

  ![Type d'erreur 400 sur HcmWorkerBaseEntity](./media/HcmWorkerBaseEntityErrorType400.png)

- **Limitation de requêtes** : la requête peut surutiliser les ressources du serveur et devenir sujette à une limitation. Dans ce cas, la requête renvoie l'erreur suivante : « Un jeton a été obtenu pour appeler Finance and Operations, maisFinance and Operations a renvoyé une erreur de type 429. » Pour plus d'informations sur la limitation des requêtes dans Human Resources, voir la [FAQ sur la limitation des requêtes](./hr-admin-integration-throttling-faq.md).

  ![Type d'erreur 429 sur HcmWorkerBaseEntity](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a>Résolution

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a>Limiter le nombre de colonnes incluses dans votre requête de données

Avec les tables virtuelles, l'une des méthodes les plus susceptibles d'améliorer les performances des requêtes consiste à limiter le nombre de colonnes sélectionnées dans la requête. Le conseil général pour optimiser les performances des requêtes consiste à limiter les colonnes renvoyées dans votre requête aux seules propriétés dont vous avez besoin. Cela est particulièrement vrai avec les colonnes de clé étrangère sur les tables virtuelles. Si vous n'avez pas besoin des valeurs des colonnes de clé étrangère pour votre intégration ou votre rapport, structurez la requête de manière à ne sélectionner que les colonnes dont vous avez besoin, à l'exclusion des colonnes de clé étrangère.

#### <a name="selecting-columns-in-an-odata-query"></a>Sélection de colonnes dans une requête OData

Lors de l'interrogation d'une table virtuelle via l'API web Dataverse, vous pouvez limiter le nombre de colonnes incluses dans la requête en utilisant l'option de requête système **$select** et définir les colonnes pour lesquelles vous souhaitez renvoyer des résultats. Pour optimiser les performances, excluez les colonnes de clé étrangère (celles avec le préfixe **_mshr_FK_**) de la requête.

Par exemple, la requête suivante sur l'entité **mshr_hcmworkerbaseentity** n'inclura que les colonnes incluses dans la clause d'option de requête **$select**, à l'exclusion des valeurs de clé étrangère. Cela offre des améliorations significatives des performances sur une requête qui inclut toutes les colonnes de la table.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

La recommandation de limiter le nombre de colonnes sélectionnées s'applique également lors de l'utilisation de l'option de requête **$expand** pour étendre la requête aux tables virtuelles associées via les propriétés de navigation. Par exemple, la requête suivante inclut des colonnes de l'entité **mshr_hcmworkerbaseentity** avec des colonnes développées de l'entité **mshr_dirpersonentity**. Notez que l'option de requête **$select** est également incluse dans la clause d'option de requête **$expand**.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

Lorsque vous utilisez cette méthode de récupération de données avec l'option de requête **$select** dans la clause d'option de requête **$expand**, vous constatez généralement des améliorations de performances plus importantes lorsque la propriété de navigation entre les entités est une relation plusieurs-à-un. Vous ne constaterez peut-être pas la même diminution du temps d'exécution des requêtes lors du développement d'une relation un-à-plusieurs. Pour plus d'informations sur la définition des relations pour les tables virtuelles Dataverse, voir [Relations de table](/powerapps/maker/data-platform/create-edit-entity-relationships).

Pour plus d'informations sur l'utilisation des options de requête système **$select** et **$expand** dans l'API web Dataverse, voir [Récupérer les enregistrements d'entités associés avec une requête](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).

#### <a name="selecting-columns-in-power-bi"></a>Sélection de colonnes dans Power BI

Si vous rencontrez l'une des indications ci-dessus de lenteur lors de l'élaboration d'un rapport Power BI par rapport à une table virtuelle Dataverse, vous pouvez améliorer les performances en excluant les colonnes de clé étrangère des colonnes sélectionnées dans la table du rapport. Par exemple, si vous utilisez Power BI Desktop pour créer un rapport par rapport à l'entité **mshr_hcmworkerbaseentity**, vous pouvez utiliser les étapes suivantes pour sélectionner les colonnes que vous souhaitez inclure dans la requête de rapport.

1. Dans Power BI Desktop, sélectionnez **Plus...** dans la liste déroulante **Obtenir des données**, dans le ruban d'actions.
2. Dans la fenêtre **Obtenir des données**, entrez **Common Data Service** dans la zone de recherche, sélectionnez le connecteur **Common Data Service** et sélectionnez **Connecter**.
3. Dans le champ **URL du serveur** de la fenêtre Common Data Service, entrez l'URI de l'organisation pour votre environnement Dataverse et sélectionnez **OK**.
  
   ![Entrer l'URI de votre environnement Dataverse](./media/PowerBIDataverseURLSetup.png)
  
4. Dans la fenêtre du navigateur, développez le nœud **Entités**.
5. Dans la zone de recherche, saisissez **mshr_hcmworkerbaseentity** et sélectionnez l'entité.
6. Sélectionnez **Transformer les données**.
7. Dans la fenêtre de l'Éditeur Power Query, sélectionnez **Éditeur avancé**.
8. Dans la fenêtre **Éditeur avancé**, mettez à jour la requête pour qu'elle ressemble à celle ci-dessous, en ajoutant ou en supprimant des colonnes au tableau si nécessaire.

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![Mettre à jour la requête dans l'Éditeur avancé pour l'Éditeur Power Query](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. Sélectionnez **Terminé**.

   > [!NOTE]
   > Si vous avez précédemment reçu une erreur de type 429 de la requête avant la mise à jour, vous devrez peut-être attendre la période de nouvelle tentative avant d'actualiser la requête pour qu'elle aboutisse.

10. Cliquez sur **Fermer et appliquer** dans le ruban d'actions de l'Éditeur Power Query.

Vous êtes alors en mesure de commencer à élaborer votre rapport Power BI par rapport aux colonnes sélectionnées dans la table virtuelle.

#### <a name="selecting-columns-in-power-apps"></a>Sélection de colonnes dans Power Apps

De la même manière que pour les requêtes d'API web Dataverse et Power BI, vous pouvez améliorer les performances des requêtes pour Power Apps basé sur les tables virtuelles Dataverse en excluant les colonnes des tables associées de votre application. Si des colonnes d'une table associée ont été incluses dans une page, l'URL de requête construite pour récupérer les données inclura les propriétés de clé étrangère de la table associée. Ceci, comme dans les exemples de [Sélection de colonnes dans une requête OData](#selecting-columns-in-power-apps) ci-dessus, réduit les performances en provoquant des recherches de données supplémentaires.

Pour contourner ce problème, vous pouvez valider qu'aucun champ de données des tables associées n'a été inclus dans un formulaire de données de votre Power App.

1. Dans le volet d'affichage de l'arborescence, sélectionnez le formulaire de données de l'écran.
2. Dans le volet **Propriétés**, sélectionnez **Modifier** sur la propriété **Champs**.
3. Dans le volet **Données**, vérifiez qu'aucun des champs sélectionnés n'est un champ de la table virtuelle de la source de données.

Par exemple, si l'un des champs de données inclus sur une page de l'application fait référence à une autre table, telle que **ThisItem.Worker.Name**, où **Worker** est la table associée, il existe un risque de réduction des performances lors de la récupération des données.

Vous pouvez utiliser [Power Apps Monitor](/powerapps/maker/monitor-overview) pour vous assurer que seules les colonnes dont vous avez besoin sont incluses dans la requête pour obtenir les données de la Power App. Vous pouvez afficher l'URL construite pour l'opération getRows pour vous assurer que les colonnes que vous avez sélectionnées pour votre application seront optimales pour récupérer les données.

![Utiliser Power Apps Monitor pour analyser l'opération getData](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a>Filtrer la requête de données

Une autre méthode pour améliorer les performances d'exécution des requêtes consiste à limiter le nombre d'enregistrements renvoyés dans les résultats de la requête. Vous pouvez le faire en filtrant les résultats pour vous assurer que vous ne recevez que les enregistrements dont vous avez besoin.

Voir [Filtrer les résultats](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) pour plus d'informations sur le filtrage des données de requête.

### <a name="limiting-the-page-size-of-the-query"></a>Limiter la taille de page de la requête

Si vous travaillez avec de grands jeux de données, vous pouvez diviser les résultats de la requête en plusieurs pages en ajoutant l'en-tête de préférence `odata.maxpagesize` aux requêtes de données.

Pour plus d'informations sur la pagination, consultez [Spécifier le nombre d'entités à renvoyer dans une page](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).

## <a name="see-also"></a>Voir également :

- [Configurer des tables virtuelles Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)
- [FAQ sur les tables virtuelles de Human Resources](hr-admin-virtual-entity-faq.md)
- [FAQ sur la limitation de requêtes](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]