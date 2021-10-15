---
title: Configuration des coûts automatiques
description: Cette rubrique décrit comment configurer des règles de coût pour différents niveaux de voyage entrant. Sur la base de ces règles, le système calcule les coûts et les ajoute automatiquement. Par conséquent, les utilisateurs n’ont pas à ajouter manuellement les coûts.
author: sherry-zheng
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostAutoSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 0fe795127300ac99c3f5ee65cb1f6e0841ad4d95
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575798"
---
# <a name="auto-costs-setup"></a>Configuration des coûts automatiques

[!include [banner](../../includes/banner.md)]

Vous pouvez utiliser la page **Coûts automatiques** pour configurer des règles de coût pour divers domaines de coûts (tels que les voyages, les conteneurs d’expédition, les folios, les commande fournisseur, les articles ou les lignes d’ordre de transfert). En fonction des règles et des champs que les utilisateurs sélectionnent lorsqu’ils créent des enregistrements pour l’un des domaines de coûts, le système calcule les coûts et les ajoute automatiquement. Par conséquent, les utilisateurs n’ont pas à ajouter manuellement les coûts.

Pour utiliser les coûts automatiques, accédez à **Prix au débarquement \> Configuration des coûts \> Coûts automatiques**. Configurez ensuite vos règles de coût automatique comme décrit dans le reste de cette rubrique.

## <a name="work-with-cost-areas"></a>Travailler avec des zones de coûts

Les coût automatique fonctionnent comme des accords commerciaux ou des frais divers automatique. Chaque enregistrement de coût automatique appartient à un niveau de coût spécifique. Utilisez le champ **Zone de coût** dans le volet de liste de la page **Coûts automatique** pour sélectionner la zone de coût avec laquelle vous souhaitez travailler. Le volet de liste affiche uniquement les coûts automatiques qui appartiennent à la zone de coûts actuellement sélectionnée. Tout coût automatique que vous créez appartiendra au domaine de coûts actuellement sélectionné.

Les domaines de coûts permettent au système de répartir les coûts entre les lignes de commande fournisseur dans un domaine de coûts. Par exemple, un coût pour un conteneur d’expédition répartira la valeur sur tous les produits de ce conteneur d’expédition. S’il y a deux conteneurs d’expédition ou plus, le même type de coût peut être spécifié pour chaque conteneur d’expédition. Par conséquent, le type de conteneur peut être utilisé pour trouver le coût automatique correct.

## <a name="buttons-on-the-action-pane"></a>Boutons sur le volet Action

Le tableau suivant décrit les boutons disponibles directement sur le volet Actions de la page **coût automatique**.

| Bouton | Description |
|---|---|
| Modifier | Modifiez un coût automatique existant. |
| Créer | Créer un coût automatique. |
| Retirer | Supprimer un coût automatique. |
| Copier depuis | Créez un enregistrement de coût automatique qui est basé sur un enregistrement existant. Vous pouvez ensuite modifier librement le nouvel enregistrement. Ce bouton vous aide à créer rapidement des coûts automatiques. |
| Afficher les dimensions | Ouvrez une boîte de dialogue dans laquelle vous pouvez sélectionner les dimensions de stock affichées pour les transactions de coût que vous affichez. Si vous décochez les cases, moins de dimensions d’inventaire seront affichées pour les transactions de coût. Par conséquent, moins de détails seront affichés pour la transaction. Si une dimension de stock est spécifiée pour un coût automatique, le coût automatique ne sera appliqué que lorsque la dimension de stock spécifiée est utilisée pour l’article lors d’un voyage. |

## <a name="settings-on-the-header"></a>Paramètres sur l’en-tête

La combinaison de paramètres dans la section d’en-tête détermine quand et comment un coût automatique spécifique est ajouté à un voyage. Un coût automatique sera appliqué à un voyage, à un conteneur d’expédition ou à un folio uniquement lorsque les détails du coût automatique correspondent aux détails de l’en-tête de cette zone de coût. La somme de tous les coûts automatiques correspondants détermine le coût au débarquement estimé d’un voyage. Ce coût est réparti sur tous les articles du navire ou du voyage.

Le tableau suivant décrit tous les champs pouvant s’afficher dans la section de l’en-tête. Cependant, les champs spécifiques disponibles varient en fonction du domaine de coût et des dimensions d’affichage actuellement sélectionnés.

| Champ | Description |
|---|---|
| **Code de compte** | <p>Vous devez sélectionner l’une des valeurs suivantes :</p><ul><li>**Table** – La règle de coût s’applique uniquement à un fournisseur spécifique.</li><li>**Groupe** – La règle de coût s’applique à un groupe de fournisseurs spécifiques. Le système recherchera le [groupe de types de coût fournisseur](costing-parameters-setup.md) qui est associé à l’enregistrement du fournisseur.</li><li>**Tous** – La règle de coût s’applique à tous les fournisseurs. |
| **Société d’expédition** | Sélectionnez le fournisseur ou le groupe de fournisseurs auxquels s’applique la règle. Ce champ n’est disponible que si vous sélectionnez *Table* ou *Groupe* dans le champ **Code de compte**. |
| **Courtier en douane** | Sélectionnez le fournisseur ou le groupe de fournisseurs auxquels s’applique la règle. Ce champ n’est disponible que si vous sélectionnez *Table* ou *Groupe* dans le champ **Code de compte**. |
| **Article - valide pour** | <p>Vous devez sélectionner l’une des valeurs suivantes :</p><ul><li>**Table** – La règle de coût s’applique uniquement à un article spécifique.</li><li>**Groupe** – La règle de coût s’applique à un groupe d’articles spécifiques. Le système recherchera le [groupe de types de coût article](costing-parameters-setup.md) qui est associé à l’enregistrement de l’article.</li><li>**Tous** – La règle de coût s’applique à tous les articles.|
| **Relation d’article** | Sélectionnez l’article ou le groupe d’articles auxquels s’applique la règle. Ce champ n’est disponible que si vous sélectionnez *Table* ou *Groupe* dans le champ **Code article**. |
| **Mode de livraison** | Sélectionnez le mode de livraison (par exemple par avion ou par mer) auquel s’applique la règle de coût. |
| **Type de conteneur** | Le type de conteneur d’expédition dans lequel les marchandises seront expédiées. Un coût automatique ne peut être appliqué à un voyage que si le type de conteneur défini dans la configuration du coût automatique correspond au type de conteneur du voyage. |
| **Port De** et **Port À** | Le port d’origine ("de") et le port de destination ("à") du voyage. (Certains conteneurs d’expédition peuvent avoir des ports "à" différents, car le voyage peut s’arrêter à plusieurs ports.) Un coût automatique ne peut être appliqué à un voyage que si les ports "de" et "à" dans la configuration du coût automatique correspondent aux ports "de" et "à" du voyage. |
| **Numéro de coût automatique** | Identificateur unique de la règle de coût automatique. La valeur de ce champ est automatiquement générée en fonction de la séquence de numéros définie sur la page **Paramètres de coût au débarquement**. |
| **Dimensions de stock** | Certaines zones de coûts vous permettent d’inclure une ou plusieurs dimensions d’article sur l’en-tête (telles que la taille, la couleur, l’entrepôt et le numéro de lot). Sélectionner **Dimensions d’affichage** dans le volet Actions pour sélectionner les dimensions à inclure. |

## <a name="settings-on-the-lines-fasttab"></a>Paramètres de l’organisateur Lignes

Sur le raccourci **Lignes**, ajoutez une ligne pour chaque devise qui peut être utilisée lorsqu’un coût est appliqué à une ligne de commande fournisseur lors d’un voyage. 

Pour les articles et les commande fournisseur, le système comparera la devise de chaque ligne de commande avec les devises spécifiées sur le raccourci **Lignes**. Il n’appliquera que la valeur de coût définie pour la ligne ou l’article correspondant. Si aucune ligne n’est configurée pour la devise de la ligne ou de l’élément, le coût automatique ne sera pas appliqué à cette ligne ou à cet élément.

Pour les autres types de zones de coûts, toutes les lignes de l’onglet **Lignes** s’appliquera à chaque voyage, conteneur d’expédition, folio ou ligne d’ordre de transfert qui correspond aux valeurs établies sur l’en-tête.

Le tableau suivant décrit tous les champs pouvant s’afficher sur chaque ligne. Cependant, les champs spécifiques disponibles varient en fonction du domaine de coût actuellement sélectionné.

| Champ | Description |
|---|---|
| **Devise** | Sélectionnez la devise à laquelle s’applique la ligne. Cette devise est liée à la commande fournisseur. Lorsque le système essaie de trouver les coût automatique qui doivent être appliqués à un voyage et à ses lignes de voyage, il sélectionne la ligne qui a la même devise que la commande fournisseur. Ce champ n’est disponible que lorsque le champ **Zone de coût** est défini sur *commande fournisseur* ou *Article*. |
| **Code de type de coût** | Type de coût. |
| **Méthode de répartition** | <p>Méthode utilisée pour répartir les coûts sur les lignes. Les options suivantes sont disponibles :</p><ul><li><p>**Pourcent** – La valeur du champ **Valeur de coût** est un pourcentage qui s’applique à la valeur totale des marchandises.</p><p>Par exemple, si le champ **Valeur de coût** est défini sur *dix*, et la valeur totale des marchandises est 800 USD, la valeur de coût est 80 USD (= 800 USD × 10 pour cent).</p></li><li>**Quantité** – Le coût sera réparti en fonction de la quantité de marchandises.</li><li>**Montant** – Le coût sera réparti en fonction de la valeur de marchandises.</li><li>**Volume** – Le coût sera réparti en fonction du volume de marchandises. Le volume est spécifié sur la fiche article.</li><li>**Poids** – Le coût sera réparti en fonction du poids de marchandises. Le poids est spécifié sur la fiche article.</li><li>**Volumétrique** – Le coût sera réparti en fonction de la valeur volumétrique de marchandises.</li><li><p>**Mesure** – Cette option permet de spécifier une mesure dans le module **Prix au débarquement**. Les mesures sont souvent utilisées par des organisations qui ne connaissent pas le volume ou le poids individuel des marchandises, mais qui nécessitent une répartition plus précise que celle fournie par les options **Montant** ou **Quantité**. Le transitaire ou l’agent fournira à l’organisation le poids ou la mesure cubique, au niveau d’un article ou de la commande fournisseur.</p><p>Par exemple, le fret maritime est égal à 900 USD. L’article A a un poids de 800 kilogrammes (kg) et un volume de 2 mètres cubes (m³). L’article B a un poids de 100 kg et un volume de 1 m³. Voici les résultats lorsque les coûts sont répartis au poids :</p><ul><li>Article A = 800 USD</li><li>Article B = 100 USD</li></ul><p>Voici les résultats lorsque les coûts sont répartis par volume :</p><ul><li>Article A = 600 USD</li><li>Article B = 300 USD</li></ul><p>**Remarque :** Quand le champ **Méthode de répartition** est défini sur *Mesure*, le système utilise les mesures saisies à la fois pour le domaine de coûts (le conteneur d’expédition) et les lignes. Ces mesures ne doivent pas nécessairement correspondre au total attendu. Cependant, si vous avez besoin qu’ils totalisent le total attendu, vous pouvez effectuer une vérification en utilisant les statistiques pour examiner la mesure totale. Le paramètre de l’invite de mesure et la mise à jour automatique de la mesure au niveau de l’expédition ou du conteneur sont définis sur l’en-tête du voyage.</p></li></ul> |
| **Date de début** | Spécifiez le début de la plage de dates pour le calcul des coûts, s’il existe une plage de dates. Cette date est la première date à laquelle le coût automatique s’appliquera. |
| **Au** | Spécifiez la fin de la plage de dates pour le calcul des coûts, s’il existe une plage de dates. Cette date est la dernière date à laquelle le coût automatique s’appliquera. |
| **Catégorie** | <p>Permet de sélectionner la méthode à utiliser pour calculer le coût. Les options suivantes sont disponibles :</p><ul><li>**Fixe** – Le coût sera réparti en fonction de la méthode de répartition.</li><li>**Unité** – Le coût sera attribué par unité. Par conséquent, la méthode de répartition ne sera pas utilisée.</li><li>**Pourcent** – Un pourcentage de la valeur des marchandises sera ajouté. Par conséquent, la méthode de répartition ne sera pas utilisée.</li><li>**Taux** – Sélectionnez cette option s’il y a des ventilations de quantité. Le champ **Méthode de répartition** de la ligne doit être défini sur *Mesure*.</li><ul> |
| **Répartition par quantité** | <p>Cochez cette case pour que le bouton **Ventilation de quantité** soit disponible sur le raccourci **Lignes**. Les répartitions de quantité permettent de décomposer le coût et de varier les différents coûts en fonction de la quantité inscrite sur la ligne de commande du voyage. Cette fonctionnalité est souvent utilisée lorsque le mode de livraison est l’air. Le champ **Catégorie** de la ligne doit être défini sur *Taux*.</p><p>La quantité est basée sur l’option sélectionnée dans le champ **Méthode de répartition**. La valeur de coût sera jusqu’à la quantité qui est entrée dans le champ **Valeur de coût**.<p>Par exemple, des quantités de 45 à 100 kg produisent une charge de 6,00 USD par mesure (par exemple, kg/m³). Les quantités qui dépassent 100 kg produisent une charge de 5,50 USD par mesure (par exemple, kg/m³).</p> |
| **Coût** | Permet d’entrer la valeur du coût. |
| **Code devise de coût** | Sélectionnez la devise du coût. |
| **Groupe de taxe d’article** | Permet de sélectionner le coût. |
| **Coût minimal** | <p>Ce champ s’applique uniquement si la case **Réparti par quantité** est cochée. Si la mesure n’atteint pas cette valeur, la valeur minimale est sélectionnée, quels que soient les coûts spécifiés sur la page **Répartition de quantité**.<p>Par exemple, des quantités de 0 à 45 kg produisent une charge de 6 USD par mesure (kg/m³). Des quantités de 46 à 100 kg produisent une charge de 5,50 USD par mesure (kg/m³). Si 2 kg sont expédiés, la répartition de quantité créera une valeur de coût de 12 USD. Cependant, si le champ **Coût minimum** est défini sur *100 USD*, le coût final sera de 100 USD.</p> |
| **Regroupement** | Cochez cette case pour permettre aux utilisateurs de déplacer ce coût du niveau du conteneur d’expédition au niveau du voyage. Dans ce cas, les coûts peuvent être automatiquement calculés au niveau du conteneur d’expédition. Cependant, ils peuvent également être combinés et répartis entre tous les articles dans tous les conteneurs d’un voyage, au lieu de tous les articles dans les conteneurs d’expédition individuels. |
| **Type de coût lié** | <p>Liez la ligne actuelle à une autre ligne du même enregistrement de coût automatique en spécifiant la valeur **Code de type de coût** de la ligne à laquelle vous souhaitez établir un lien. Cette fonctionnalité n’est disponible que lorsque le champ **Catégorie** de la ligne actuelle est défini sur *Pour cent*. Lorsque la ligne courante est liée à une autre ligne, le coût de la ligne courante sera basé sur le coût de l’autre ligne.</p><p>Par exemple, le fret est 1 000 USD et vous voulez que le supplément carburant soit de 10 % du coût du fret. Dans ce cas, la ligne doit avoir une valeur de **Catégorie** de *Pourcent*, une valeur de **Valeur de coût** de *10 %*, et une valeur de **Type de coût lié** de *Cargaison*.</p> |
| **Ajustement de la valeur** et **Montant de l’ajustement** | <p>Utilisez ces champs pour ajuster la valeur et le montant de différentes valeurs de pourcentage. Ils ne sont disponibles que lorsque le champ **Zone de coût** est défini sur *Article*.</p><p>Différents coûts peuvent être configurés pour différents composants d’un article. Un composant d’un article peut avoir un pourcentage de coût différent de celui des autres composants de cet article. Cette approche est parfois nécessaire pour évaluer une partie spécifique des marchandises à des taux différents.</p><p>Par exemple, le droit pour une montre est calculé selon deux taux : un composant de la montre a un taux de droit de 10 pour cent et un second composant un taux de droit de 2 pour cent. Dans ce cas, les coûts seront répartis entre les deux composants.</p><p>Le coût est calculé pour l’article, mais la valeur de coût est ajustée par la valeur des composants qui ont la catégorie de coût différente. Le coût des composants restants peut ensuite être calculé en utilisant le montant par lequel le calcul précédent a été ajusté.</p><p>Par exemple, le composant A de la montre a un coût de 9,50 USD et un droit de 10 pourcent, et le composant B a un coût de 0,50 USD et un droit de 2 pourcent. Par conséquent, le coût total est 10,00 USD. La première entrée concerne la ligne de 10 %. Il utilise les valeurs suivantes :</p><ul><li>**Catégorie :** *Pourcent*</li><li>**Valeur du coût :** *10*</li><li>**Valeur ajustée :** *Ajuster par*</li><li>**Valeur ajustée :** *-0,50*</li></ul><p>Cette configuration spécifie que le coût de l’article (10 USD) doit être réduit de 0,50 USD (le prix du composant B) avant qu’un droit de douane de 10 % ne soit calculé. Par conséquent, 10 % seront appliqués à 9,50 USD.</p><p>La deuxième entrée est pour la ligne 2 pour cent (le 0,50 USD par lequel l’entrée précédente a été ajustée). Il utilise les valeurs suivantes :</p><ul><li>**Catégorie :** *Pourcent*</li><li>**Valeur du coût :** *2*</li><li>**Valeur ajustée :** *Utilise*</li><li>**Ajustement :** *0,50*</li></ul><p>Cette configuration calcule le droit restant à payer sur le composant B.</p> |
