---
title: ワークフロー サービス内でのシリアル化の構成
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: f894f2e044e35bb278f975ef2385a6b22a8bea49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185343"
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="fc57c-102">ワークフロー サービス内でのシリアル化の構成</span><span class="sxs-lookup"><span data-stu-id="fc57c-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="fc57c-103">ワークフロー サービスは Windows コミュニケーション ファウンデーション (WCF) サービス<xref:System.Runtime.Serialization.DataContractSerializer>なので、 (既定)<xref:System.Xml.Serialization.XmlSerializer>または .</span><span class="sxs-lookup"><span data-stu-id="fc57c-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="fc57c-104">ワークフロー以外のサービスを記述する場合、使用するシリアライザーの型はサービスまたは操作コントラクトで指定されます。</span><span class="sxs-lookup"><span data-stu-id="fc57c-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="fc57c-105">WCF ワークフロー サービスを作成する場合、これらのコントラクトはコードで指定せず、コントラクトの推論によって実行時に生成されます。</span><span class="sxs-lookup"><span data-stu-id="fc57c-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="fc57c-106">コントラクトの推論の詳細については、「[ワークフローでの契約の使用](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc57c-106">For more information about contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="fc57c-107">シリアライザーは、<xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> プロパティを使用して指定されます。</span><span class="sxs-lookup"><span data-stu-id="fc57c-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="fc57c-108">これは、次の図に示すようにデザイナーで設定できます。</span><span class="sxs-lookup"><span data-stu-id="fc57c-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 ![プロパティ ウィンドウでの SerializerOption プロパティを設定します。](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 <span data-ttu-id="fc57c-110">シリアライザーは、次の例に示すようにコードで設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="fc57c-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
```csharp  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
  <span data-ttu-id="fc57c-111">ワークフロー サービスにも既知の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fc57c-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="fc57c-112">既知の型の詳細については、「[データ コントラクトの既知の型](data-contract-known-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc57c-112">For more information about Known Types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="fc57c-113">既知の型は、デザイナーまたはコードで指定できます。</span><span class="sxs-lookup"><span data-stu-id="fc57c-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="fc57c-114">デザイナーで既知の型を指定するには、次の図に示すように、<xref:System.ServiceModel.Activities.Receive>**アクティビティのプロパティ ウィンドウ**で KnownTypes プロパティの横にある省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc57c-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the **Properties Window** for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>
  
 ![[既知の種類] プロパティ ダイアログ ボックスのスクリーンショット。](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 <span data-ttu-id="fc57c-116">これにより、既知の型を検索および指定できる型コレクション エディタが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc57c-116">This displays the Type Collections Editor that allows you to search for and specify known types.</span></span>  
  
 ![型コレクション エディターのスクリーンショット。](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 <span data-ttu-id="fc57c-118">[**新しい型の追加]** リンクをクリックし、ドロップダウンを使用して、既知の型コレクションに追加する型を選択または検索します。</span><span class="sxs-lookup"><span data-stu-id="fc57c-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="fc57c-119">既知の型をコードで指定するには、次の例に示すように <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc57c-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
```csharp
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
            approveExpense.KnownTypes.Add(typeof(Travel));  
            approveExpense.KnownTypes.Add(typeof(Meal));  
```
