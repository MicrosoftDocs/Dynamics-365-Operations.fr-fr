---
title: Configuration de la fonctionnalité de prise en compte de revenu
description: Cette rubrique décrit les options de paramétrage pour la prise en compte de revenu, ainsi que leurs implications.
author: kweekley
ms.date: 04/28/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 5f72ebd743763db7c68340a833c2501d47d27081
ms.sourcegitcommit: 0abc777986112ea2332f5bf0e815b303b952356c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2022
ms.locfileid: "8656719"
---
# <a name="revenue-recognition-setup"></a>Configuration de la fonctionnalité de prise en compte de revenu
[!include [banner](../includes/banner.md)]

Un nouveau module **prise en compte de revenu** qui inclut des options de menu pour tous les paramètres de configuration requis a été ajouté. Cette rubrique décrit les options de paramétrage, ainsi que leurs implications.

> [!NOTE]
> La fonctionnalité de prise en compte de revenu est désormais activée par défaut via Gestion des fonctionnalités. Si votre organisation n’utilise pas cette fonctionnalité, vous pouvez la désactiver dans l’espace de travail **Gestion des fonctionnalités**.
>
> La fonctionnalité de prise en compte de revenu (y compris la fonctionnalité groupée), n’est pas prise en charge pour une utilisation dans les canaux commerciaux (commerce électronique, PDV et centre d’appels). Les articles configurés pour la prise en compte de revenu ne doivent pas être ajoutés aux commandes ou aux transactions créées dans les canaux commerciaux.

Le module **Prise en compte de revenu** comporte les options de paramétrage suivantes :

- Journaux de prise en compte de revenu
- Paramètres pour la prise en compte de revenu
- Échéanciers de produit 
- Configuration des stocks

    - Groupes d’articles et produits lancés
    - Définition de l’échéancier de produit
    - Définition des prix de produit
    - Configuration des stocks

        - Définition de l’échéancier de produit
        - Définition des prix de produit

    - Profils de validation
    - Offres groupées

        - Composants d’offre groupée
        - Article d’offre groupée

- Paramétrage de projet

## <a name="revenue-recognition-journals"></a>Journaux de prise en compte de revenu

Un nouveau type de journal a été introduit pour la prise en compte de revenu. Ce journal est indispensable ; il est utilisé dans deux scénarios.

Le premier scénario a lieu lorsque toutes les obligations contractuelles sont remplies, lorsque le produit différé est constaté lors de la création d’un journal de prise en compte de revenu, lequel est fondé sur l’échéancier de produit. Le journal contient une écriture comptable qui déplace le solde du compte général de produit différé au compte général de produit.

Le deuxième scénario a lieu lorsqu’un journal est créé après une réaffectation. Une réaffectation a lieu lorsqu’une ligne de commande client est ajoutée à une commande client précédemment facturée, ou lorsqu’une nouvelle commande client est créée incluant une ligne qui fait partie du contrat d’origine. Si une facture a été validée avant que la ligne de commande client soit ajoutée, une écriture comptable de correction doit être créée pour la facture client validée.

Le journal est paramétré sur la page **Noms de journal** (**Prise en compte de revenu \> Paramétrage \> Noms de journal**). Le type de journal doit être défini sur **Prise en compte de revenu**. 

## <a name="parameters-for-revenue-recognition"></a>Paramètres pour la prise en compte de revenu

Les paramètres de prise en compte de revenu sont configurés dans l’onglet **Prise en compte de revenu** de la page **Paramètres de comptabilité** (**Prise en compte de revenu \> Paramétrage \> Paramètres de comptabilité**). Les paramètres disponibles sont les suivants :

- **Nom du journal de prise en compte de revenu** : sélectionnez le journal créé pour la prise en compte de revenu. Le journal est requis lorsque le produit est constaté à partir de l’échéancier de produit, ou lorsque vous effectuez la réaffectation d’une commande client déjà facturée.
- **Activer la méthode de répartition de remise** : définissez cette option sur **Oui** pour déterminer le prix du produit via la répartition de la juste valeur qui est définie dans le prix du produit pour chaque produit lancé. Cette répartition inclut la répartition de toutes les éventuelles remises ligne entre les différents articles. Si cette option est définie sur **Non**, le système utilise le prix médian défini dans le prix du produit pour chaque produit lancé. Si cette option est définie sur **Non**, mais qu’aucun prix médian n’est paramétré pour les produits lancés, la répartition du prix de produit n’a pas lieu.
- **Inclure les remises d’en-tête** : définissez cette option sur **Oui** pour déterminer le prix du produit en répartissant les remises d’en-tête sur les produits. Si cette option est définie sur **Non**, la remise d’en-tête n’est pas incluse dans la répartition de prix du produit.
- **Désactiver les termes du contrat** : définissez cette option sur **Activé** si les produits dont le type de produit est **Support post-contrat** peuvent être lancés même si aucune date de début et de fin de contrat n’est définie pour eux. Généralement, les date de début et de fin de contrat sont requises pour les articles du type de produit **Support post-contrat**. Lorsque les dates de début et de fin de contrat ne sont pas définies, les détails de l’échéancier de produit à la validation sont calculés à l’aide du nombre d’occurrences et de la date de facture.
- **Valider les corrections des factures dans la comptabilité client lors de la réaffectation** : lorsque vous refaites la répartition des factures qui ont déjà été validées, l’écriture comptable pour la facture validée doit être corrigée. Cette option permet de spécifier comment cette correction est effectuée.

    - Définissez cette option sur **Non** pour limiter la validation de la transaction de correction dans la comptabilité. Lorsque cette option est définie sur **Non**, aucun document supplémentaire n’est créé dans la comptabilité client pour la correction interne de la comptabilité. Lorsque la facture est payée, le processus de règlement utilise l’ancienne écriture comptable pour valider les éventuels escomptes de règlement, ou les profits ou pertes réalisés.
    - Définissez cette option sur **Oui** pour créer automatiquement un document de contrepassation et une nouvelle facture pour la transaction de correction dans la comptabilité client. Comme cette correction est une correction comptable interne, les nouveaux documents ne sont pas expédiés ni communiqués au client. Le document de contrepassation est réglé par rapport à la facture d’origine, et la nouvelle facture corrigée est payée par le client. Notez que les trois documents sont affichés dans les états, comme le relevé client.

[![Informations de paramétrage.](./media/revenue-recognition-setup-info.png)](./media/revenue-recognition-setup-info.png)

## <a name="revenue-schedules"></a>Échéanciers de produit

Un échéancier de produit doit être créé pour chaque occurrence possible de report du produit. Par exemple, si votre entreprise offre un support sur des périodes de six mois, 12 mois, 18 mois et 24 mois, vous devez créer un échéancier de produit pour chaque période. Le paramétrage de l’échéancier de produit détermine la manière dont le prix du produit est réparti entre le nombre de périodes que vous sélectionnez. Il détermine également les dates par défaut entrées pour l’échéancier de produit créé lorsque la facture est validée.

Si vous constaté le produit par jalons, nous vous recommandons de créer un échéancier de prise en compte de revenu pour le nombre de jalons prévus, indépendamment des dates de constatation. Une fois les échéanciers créés, vous pouvez les modifier pour qu’ils reflètent les dates de jalon prévues. Ces enregistrements peuvent être mis en attente jusqu’à ce que vous soyez averti que le jalon a été atteint et que le produit peut être constaté.

Les échéanciers de produit sont créés sur la page **Échéanciers de produit** (**prise en compte de revenu \> Paramétrage \> Échéanciers de produit**).

[![Echéanciers de produit.](./media/revenue-recognition-revenue-schedules.png)](./media/revenue-recognition-revenue-schedules.png)

Entrez des valeurs descriptives dans les champs **Échéanciers de produit** et **Description**. Les paramètres supplémentaires suivants permettent de créer l’échéancier de produit lors de la validation de la facture.

- **Occurrences** : entrez le nombre de mois ou d’occurrences du report du produit.
- **Attente automatique** : activez cette case à cocher si toutes les lignes de l’échéancier de produit doivent être automatiquement mises en attente lors de la validation de la facture. La mise en attente doit être levée manuellement pour chaque ligne de l’échéancier avant que le produit différé de la ligne puisse être constaté.
- **Termes du contrat automatiques** : activez cette case à cocher si les dates de début et de fin du contrat doivent être définies automatiquement. Ces dates ne sont définies automatiquement que pour des produits lancés du type de produit **Support post-contrat**. La date de début du contrat est automatiquement définie sur la date d’expédition demandée de la ligne de la commande client, et la date de fin de contrat est automatiquement définie comme la date de début plus le nombre de mois ou d’occurrences défini dans le paramétrage de l’échéancier de produit. Par exemple, le produit sur la ligne de commande client concerne une garantie d’un an. L’échéancier de produit par défaut est **12M** (12 mois), et la case à cocher **Termes du contrat automatiques** est activée pour cet échéancier de produit. Si la ligne de commande client contient la date d’expédition demandée 16 décembre 2019, la date de début par défaut du contrat est le 16 décembre 2019, et la date de fin par défaut du contrat est le 15 décembre 2020.
- **Base de constatation** : la base de constatation détermine la manière dont le prix du produit est réparti entre les occurrences.

    - **Mensuellement en jours** : le montant est réparti selon les jours réels dans chaque mois du calendrier.
    - **Mensuellement** : le montant est réparti également sur le nombre de mois défini dans les occurrences.
    - **Occurrences** : le montant est réparti également entre les occurrences, mais il peut inclure une période supplémentaire si vous sélectionnez **Date de début réelle** comme convention de constatation.
    - **Période fiscale en jours** : le montant est réparti selon les jours réels de chaque période fiscale. 

         - Les résultats des champs **Mensuellement en jours** et de **Période fiscale en jours** seront les mêmes lorsque les exercices fiscaux suivront des mois civils. La seule exception est lorsque la convention de constatation est définie sur **Fin de mois/période**, et que les champs **Date de début du contrat** et **Date de fin** sont laissés vides sur une ligne de commande client.

- **Convention de constatation** : la convention de constatation détermine les dates définies dans l’échéancier de produit pour la facture.

    - **Date de début réelle** : l’échéancier est créé en utilisant la date de début du contrat (pour les articles assortis de support post-contrat \[PCS\]), ou la date de facture (pour les articles essentiels et non essentiels).
    - **1er jour du mois/période** : la date sur la première ligne de l’échéancier est la date de début du contrat (ou la date de facture). Toutefois, toutes les lignes de l’échéancier suivantes sont créées pour le premier jour du mois ou de la période fiscale.
    - **Fractionnement au quinze du mois** : la date sur la première ligne de l’échéancier dépend de la date de la facture. Si la facture est validée entre le premier et le quinze du mois, l’échéancier de produit est créé en utilisant le premier jour du mois. Si la facture est validée entre le seize et le dernier jour du mois, l’échéancier de produit est créé en utilisant le premier jour du mois suivant.

        - **Fractionnement au quinze du moi** ne peut pas être sélectionné si la base de reconnaissance est définie sur **Période fiscale en jours**.

    - **1er jour du mois suivant/de la période suivante** : la date sur l’échéancier est le premier jour du mois suivant ou de la période fiscale suivante.
    - **Fin de mois/période** : la date sur la première ligne de l’échéancier est la date de début du contrat (ou la date de facture). Toutefois, toutes les lignes de l’échéancier suivantes sont créées pour le dernier jour du mois ou de la période fiscale. 

Sélectionnez le bouton **Détails de l’échéancier de produit** pour afficher les périodes générales et les pourcentages constatés dans chaque période. Par défaut, la valeur **Constater le pourcentage** est divisée également par le nombre de périodes. Si la base de la constatation est définie sur **Mensuellement**, le pourcentage de constatation peut être modifié. Lorsque vous modifiez le pourcentage de constatation, un message d’avertissement vous informe que le total n’est pas égal à 100 %. SI vous recevez ce message, vous pouvez continuer à modifier les lignes. Toutefois, le pourcentage total doit être égal à 100 avant de fermer la page.

[![Détails de l’échéancier de produit.](./media/revenue-schedule-details-2nd-scrn.png)](./media/revenue-schedule-details-2nd-scrn.png)

## <a name="inventory-setup"></a>Configuration des stocks

Vous pouvez constater le produit pour les produits lancés dans les commandes client, mais pour les catégories de vente sur les commandes client ou les factures financières, si aucun article n’est inclus dans le document. Les sélections effectuées lors du paramétrage des produits lancés déterminent la manière dont le produit de l’article est constaté. Par exemple, les sélections déterminent si le prix du produit est alloué, et si le produit est différé selon un échéancier de produit.

La configuration commence sous le raccourci **prise en compte de revenu** de la page **Groupe d’articles** (**prise en compte de revenu \> Paramétrage \> Paramétrage des stocks et du produit \> Groupe d’articles**). Cette page inclut plusieurs champs de configuration. Ces champs permettent de définir des valeurs par pour uniquement les nouveaux produits lancés créés dans le système. À mesure que les nouveaux produits sont créés, les valeurs que vous définissez ici sont entrées par défaut pour le groupe d’articles. Vous pouvez écraser les valeurs par défaut des produits lancés dans la page **Produits lancés** (**prise en compte de revenu \> Paramétrage \> Paramétrage des stocks et du produit \> Produits lancés**). Les valeurs par défaut définies pour les produits lancés sont alors reportées sur la commande client.

## <a name="item-groups-and-released-products"></a>Groupes d’articles et produits lancés

### <a name="define-the-revenue-schedule"></a>Définir l’échéancier de produit

Le produit dans la ligne de commande client est différé si un échéancier de produit est défini pour le produit lancé et utilisé par défaut sur la ligne de commande client. Si le paramètre est utilisé par défaut pour le produit, vous pouvez définir l’échéancier de produit sur le raccourci **prise en compte de revenu** de la page **Groupe d’articles** (**prise en compte de revenu \> Paramétrage \> Paramétrage des stocks et du produit \> Groupe d’articles**). Vous pouvez également définir le paramètre pour le produit lancé sous le raccourci **prise en compte de revenu** de la page **Produits lancés** (**prise en compte de revenu \> Paramétrage \> Paramétrage des stocks \> Produits lancés**).

Dans le champ **Échéancier de produit**, sélectionnez l’échéancier de produit qui représente la période sur laquelle le produit doit être différé. L’échéancier de produit est automatiquement entré sur la ligne de commande client, et les détails de l’échéancier sont créés lorsque la facture de la commande client est validée.

### <a name="define-the-revenue-price"></a>Définir le prix du produit

Les groupes d’articles et les produits lancés peuvent être paramétrés à l’aide de la méthode du prix médian ou de la méthode de répartition des remises. Les deux méthodes font appel à divers paramètres de la page **Produits lancés** :

- **La répartition du produit est-elle active** – Définissez cette option sur **Oui** pour inclure le produit lancé dans le calcul de la répartition du produit. Si cette option est définie sur **Non**, le produit lancé utilise la méthode du prix médian, si celui-ci est défini. Si le prix médian n’est pas défini, le prix unitaire sur la ligne de commande client est utilisé pour opérer la validation dans le produit ou dans le produit différé.
- **Type de produit** – Sélectionnez le type de produit qui définit le produit lancé :

    - **Essentiel** – L’article est une des principales sources de produits de l’entreprise. Cette valeur est le paramétrage par défaut.
    - **Non essentiel** – L’article n’est pas une des principales sources de produits de l’entreprise. Lorsque les paramètres du prix médian sont utilisés, le prix est « construit » à partir du prix médian, puis réparti. Par exemple, un article essentiel a un prix fixe qui doit être constaté dans le produit. S’il existe une remise, la remise peut être construite à partir du produit de l’article essentiel, mais **seulement** à hauteur du montant du prix fixe. Le reste de la remise est extrait du produit pour les articles non essentiels. Sinon, la remise ne peut pas être construite à partir du produit de l’article essentiel.
    - **Support post-contrat** – L’article prend en charge d’autres éléments qui sont inclus dans la vente au client. Le prix de produit est réparti entre les produits essentiels et non essentiels qui sont inclus dans la vente. Selon le paramétrage, les articles PCS peuvent ne pas exiger que les dates de début et de fin du contrat soient définies dans la ligne de commande client.

- **Exclure de la construction** – Définissez cette option sur **Oui** pour indiquer que le prix médian de l’article ne peut pas être ajusté en dessous du pourcentage minimum défini, ni au-dessus du pourcentage maximal. Tout prix de produit sera dérivé du prix de produit d’un autre produit lancé inclus dans la commande client. Si cette option est définie sur **Non**, le prix médian de l’article peut être ajusté ou construit. Notez que si vous vendez plusieurs articles paramétrés avec le prix médian, au moins un produit lancé doit être paramétré avec l’option **Exclure de la construction** définie sur **Non**. Ainsi, il existe au moins un article vers lequel peuvent être réparties les éventuelles différences de prix de produit.
- **Prix médian** – Définissez cette option sur **Oui** pour indiquer que le prix de produit de l’article doit être ajusté de sorte qu’il soit égal au prix médian s’il est inférieur à la tolérance minimale que vous avez spécifiée ou au-dessus de la tolérance maximale, et que le montant construit soit réparti sur les lignes comportant un produit où l’option **Exclure de la construction** est définie sur **Non**.

    - **Tolérance maximale** – Entrez le pourcentage autorisé au-dessus le prix médian.
    - **Tolérance minimale** – Entrez le pourcentage autorisé au-dessous du prix médian.

Une fois la configuration des paramètres terminée pour le produit lancé, vous devez définir manuellement le prix du produit en entrant le prix de juste valeur ou le prix médian (si vous utilisez la méthode du prix médian) sur la page **Prix de produit** (accédez à **prise en compte de revenu \> Paramétrage \> Paramétrage des stocks \> Produits lancés**, puis, dans le volet Actions, sous l’onglet **Vendre**, dans le groupe **prise en compte de revenu**, sélectionnez **Prix de produit**).

[![Prix de produit.](./media/revenue-recognition-revenue-prices.png)](./media/revenue-recognition-revenue-prices.png)

Le prix de produit qui est défini manuellement dans cette page permet de déterminer la répartition de prix du produit sur chaque commande client, selon les critères définis. Chaque critère est mis en correspondance avec la ligne de commande client pour déterminer le prix de produit à utiliser dans le processus de répartition.

- **Code article** et **Relation d’article** – Un prix de produit peut être défini pour un produit distinct ou un groupe de produits. Si vous sélectionnez **Table** dans le champ **Code article**, sélectionnez le produit lancé dans le champ **Relation d’article**. Si vous sélectionnez **Groupe** dans le champ **Code article**, sélectionnez le groupe d’articles dans le champ **Relation d’article**.
- **Code de compte** et **Numéro de compte/groupe** – Un prix de produit peut être défini pour tous les clients, un client individuel ou un groupe de clients. Si vous sélectionnez **Tous** dans le champ **Code de compte**, le prix est utilisé pour tous les clients. Si vous sélectionnez **Table** dans le champ **Code de compte**, sélectionnez le client dans le champ **Numéro de compte/groupe**. Si vous sélectionnez **Groupe** dans le champ **Code de compte**, sélectionnez le groupe de clients dans le champ **Numéro de compte/groupe**.
- **Devise** – Vous devez entrer un prix de produit distinct pour chaque devise dans laquelle vous saisissez une commande client. Par exemple, si vous faites actuellement des ventes en dollar américain, en dollar canadien et en euro, vous devez définir un prix du produit dans ces trois devises. Le prix de produit n’est pas converti entre une devise (telle que la devise comptable) et un autre devise de transaction utilisée.
- **Montant ou pourcentage de liste** – Spécifiez si le prix de produit est paramétré comme un montant ou comme un pourcentage du prix de liste. Si vous sélectionnez **Pourcentage de liste**, les utilisateurs peuvent entrer le prix médian sous forme de pourcentage du prix de liste au lieu d’un montant. La valeur **Pourcentage de liste** n’est utilisée que pour les produits lancés qui sont paramétrés comme articles PCS.
- **Prix de répartition de produit** – Selon la valeur que vous avez sélectionnée dans le champ **Montant ou pourcentage de liste**, entrez un montant ou un pourcentage pour représenter le prix de produit utilisé pour répartir le produit entre les éléments de la commande client.
- **Date de début** et **Date de fin** – Entrez la plage de dates pendant laquelle le prix de produit est actif. Ces champs sont facultatifs.

Si l’option **Activer la méthode de répartition de remise** sur la page **Paramètres de comptabilité** est définie sur **Oui**, et si le champ **Type de produit** de votre produit lancé est défini sur **Support post-contrat**, vous devez également spécifier les articles qui sont pris en charge par le produit lancé. Ce paramétrage est effectué sur la page **Base de paramétrage** (accédez à **prise en compte de revenu \> Paramétrage \> Paramétrage des stocks \> Produits lancés**, puis, dans le volet Actions, sous l’onglet **Vendre**, dans le groupe **prise en compte de revenu**, sélectionnez **Base de paramétrage**).

Dans la page **Base de paramétrage**, ajoutez un enregistrement pour chaque groupe d’articles que l’article prend en charge. Lorsque la répartition de produit a lieu, le prix de produit sera réparti entre les éléments essentiels et non essentiels de l’article PCS.

### <a name="posting-profiles"></a>Profils de validation

Trois types de validations supplémentaires prennent en charge la possibilité de différer le produit. Ces types de validation sont définis sous l’onglet **Commande client** de la page **Validation** (**prise en compte de revenu \> Paramétrage \> Paramétrage de stock et de produit \> Validation**).

- **Produit différé** – Entrez le compte principal pour le prix de produit qui est validé dans le produit différé (plutôt que dans le produit). Le prix de produit est différé si la ligne de commande client comporte un échéancier de produit.
- **Coût des marchandises vendues différé** – Entrez le compte principal pour le montant du coût des marchandises vendues qui est validé dans le coût des marchandises vendues différé si le produit est également différé.
- **Compensation de produit de facture partielle** – Entrez le compte principal pour le compte de compensation utilisé lorsque la commande client est facturée partiellement ou lorsqu’une redistribution a lieu. Le solde de ce compte revient à 0 (zéro) lorsque les commandes client sont facturées entièrement.

### <a name="bundles"></a>Offres groupées

Les articles en offre groupée sont les seuls produits lancés qui sont paramétrés de manière à inclure des composants. Ce paramétrage est effectué à l’aide de la fonctionnalité de nomenclature. Lorsqu’un article d’offre groupée est entré dans une commande client, les composants individuels servent à déterminer les prix de produit et les échéanciers de produit. Toutefois, les documents imprimés pour le client, tels que la commande client et la facture, contiennent l’article d’offre groupée.

#### <a name="bundle-components"></a>Composants d’offre groupée

Les composants inclus dans une offre groupée doivent être paramétrés sur la page **Produits lancés** (**prise en compte de revenu \> Paramétrage \> Paramétrage de stock et de produit \> Produits lancés**). Ces composants sont des produits lancés ; ils doivent être paramétrés la même manière que les produits inclus dans une nomenclature. Par exemple, un produit lancé peut être un article du type **Article** ou du type **Service**, mais il doit être affecté à un groupe de modèles d’article où l’option **Produit stocké** est définie sur **Oui**. Pour plus d’informations, voir la documentation sur le paramétrage des articles de nomenclature.

Les composants doivent également être paramétrés pour la prise en compte de revenu, exactement comme s’il s’agissait de produits pouvant être vendus individuellement sur une commande client. Par exemple, assurez-vous que le prix de produit correct est défini pour chaque composant, et que la base de prix est paramétrée pour les articles PCS.

#### <a name="bundle-items"></a>Articles d’offre groupée

Lorsque vous configurez un article d’offre groupée vous devez paramétrer deux champs sur la page **Produits lancés** (**prise en compte de revenu \> Paramétrage \> Paramétrage de stock et de produit \> Produits lancés**) :

- Dans le raccourci **Ingénieur**, dans le champ **Type de production**, l’article doit être défini comme article de nomenclature.
- Dans le raccourci **Général**, dans le champ **Offre groupée**, l’article doit être marquée comme article d’offre groupée.

Les composants doivent être ensuite être affectés à l’article parent de l’offre groupée ou de la nomenclature dans la page **Versions de nomenclature** (accédez à **prise en compte de revenu \> Paramétrage \> Paramétrage de stock et de produit \> Produits lancés**, puis, dans le volet Actions, sous l’onglet **Ingénieur**, dans le groupe **Nomenclature**, sélectionnez **Versions de nomenclature**). Pour plus d’informations, voir la documentation sur le paramétrage des nomenclatures.

[![Produits lancés, échéanciers de nomenclature.](./media/revenue-recognition-bom-scheduleds.jpg)](./media/revenue-recognition-bom-scheduleds.jpg)

Si l’article parent de l’offre groupée et les composants d’offre groupée sont paramétrés pour la répartition, le prix du produit de l’offre groupée sera réparti sur les composants en fonction de leur pourcentage de contribution au produit.

## <a name="project-setup"></a>Paramétrage de Projet

La prise en compte de revenu peut également être utilisée pour les commandes client créées via un projet en régie. Pour les commandes client provenant de projets, il vous suffit de définir les comptes principaux dans les profils de validation du projet utilisés pour valider des factures de projet. Les comptes principaux sont définis dans la page **Paramétrage de la validation dans la comptabilité** (**prise en compte de revenu \> Paramétrage \> Paramétrage de Projet \> Paramétrage de la validation dans la comptabilité**).

- **Produit différé de la facture** (sous **Comptes de produit**) – Entrez le compte principal pour le prix de produit qui est validé dans le produit différé (plutôt que dans le produit). Le prix de produit est différé si la ligne de commande client comporte un échéancier de produit.
- **Coût différé** (sous **Comptes de coûts**) – Entrez le compte principal pour le montant du coût des marchandises vendues qui est validé dans le coût des marchandises vendues différé si le produit est également différé.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
