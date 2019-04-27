---
title: データ コントラクトの等価性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], equivalence
ms.assetid: f06f3c7e-c235-4ec1-b200-68142edf1ed1
ms.openlocfilehash: a526a58ef801e91775756e6a84a94a066d32d284
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857234"
---
# <a name="data-contract-equivalence"></a><span data-ttu-id="0096e-102">データ コントラクトの等価性</span><span class="sxs-lookup"><span data-stu-id="0096e-102">Data Contract Equivalence</span></span>
<span data-ttu-id="0096e-103">クライアントがサービスに特定の型のデータを正常に送信するために、またはサービスがクライアントにデータを正常に送信するために、送信する型が受信側に存在する必要があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="0096e-103">For a client to successfully send data of a certain type to a service, or a service to successfully send data to a client, the sent type does not necessarily have to exist on the receiving end.</span></span> <span data-ttu-id="0096e-104">両方の型のデータ コントラクトが同等であるということが唯一の要件です</span><span class="sxs-lookup"><span data-stu-id="0096e-104">The only requirement is that the data contracts of both types be equivalent.</span></span> <span data-ttu-id="0096e-105">(場合によっては、厳密な等価性は必要ありませんで説明したよう[データ コントラクトのバージョン管理](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md))。</span><span class="sxs-lookup"><span data-stu-id="0096e-105">(Sometimes, strict equivalence is not required, as discussed in [Data Contract Versioning](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md).)</span></span>  
  
 <span data-ttu-id="0096e-106">データ コントラクトを同等にするには、そのデータ コントラクトに同じ名前空間と名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0096e-106">For data contracts to be equivalent, they must have the same namespace and name.</span></span> <span data-ttu-id="0096e-107">また、一方のデータ コントラクトの各データ メンバーには、他方のデータ コントラクトに同等のデータ メンバーがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="0096e-107">Additionally, each data member on one side must have an equivalent data member on the other side.</span></span>  
  
 <span data-ttu-id="0096e-108">データ メンバーを同等にするには、そのデータ メンバーに同じ名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0096e-108">For data members to be equivalent, they must have the same name.</span></span> <span data-ttu-id="0096e-109">さらに、データ メンバーは同じ型のデータを表す必要があります。つまり、データ コントラクトが同等である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0096e-109">Additionally, they must represent the same type of data; that is, their data contracts must be equivalent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0096e-110">データ コントラクト名と名前空間、およびデータ メンバー名は、大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="0096e-110">Note that data contract names and namespaces, as well as data member names, are case-sensitive.</span></span>  
  
 <span data-ttu-id="0096e-111">データ コントラクト名と名前空間、さらにデータ メンバー名の詳細については、次を参照してください。 [Data Contract Names](../../../../docs/framework/wcf/feature-details/data-contract-names.md)します。</span><span class="sxs-lookup"><span data-stu-id="0096e-111">For more information about data contract names and namespaces, as well as data member names, see [Data Contract Names](../../../../docs/framework/wcf/feature-details/data-contract-names.md).</span></span>  
  
 <span data-ttu-id="0096e-112">2 つの型が両側 (送信者と受信者) に存在し、そのデータ コントラクトが同等でない場合 (たとえば、異なるデータ メンバーを含んでいる場合)、そのデータ コントラクトに同じ名前と名前空間を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="0096e-112">If two types exist on the same side (sender or receiver) and their data contracts are not equivalent (for example, they have different data members), you should not give them the same name and namespace.</span></span> <span data-ttu-id="0096e-113">同じ名前と名前空間を使用すると、例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0096e-113">Doing so may cause exceptions to be thrown.</span></span>  
  
 <span data-ttu-id="0096e-114">次の型のデータ コントラクトは同等です。</span><span class="sxs-lookup"><span data-stu-id="0096e-114">The data contracts for the following types are equivalent:</span></span>  
  
 [!code-csharp[C_DataContractNames#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#5)]
 [!code-vb[C_DataContractNames#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#5)]  
  
## <a name="data-member-order-and-data-contract-equivalence"></a><span data-ttu-id="0096e-115">データ メンバーの順序とデータ コントラクトの等価性</span><span class="sxs-lookup"><span data-stu-id="0096e-115">Data Member Order and Data Contract equivalence</span></span>  
 <span data-ttu-id="0096e-116"><xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> クラスの <xref:System.Runtime.Serialization.DataMemberAttribute> プロパティの使用は、データ コントラクトの等価性に影響を与えることがあります。</span><span class="sxs-lookup"><span data-stu-id="0096e-116">Using the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> class may affect data contract equivalence.</span></span> <span data-ttu-id="0096e-117">データ コントラクトを同等にするには、データ メンバーが同じ順序で現れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0096e-117">The data contracts must have members that appear in the same order to be equivalent.</span></span> <span data-ttu-id="0096e-118">既定の順序はアルファベット順です。</span><span class="sxs-lookup"><span data-stu-id="0096e-118">The default order is alphabetical.</span></span> <span data-ttu-id="0096e-119">詳細については、次を参照してください。[データ メンバーの順序](../../../../docs/framework/wcf/feature-details/data-member-order.md)します。</span><span class="sxs-lookup"><span data-stu-id="0096e-119">For more information, see [Data Member Order](../../../../docs/framework/wcf/feature-details/data-member-order.md).</span></span>  
  
 <span data-ttu-id="0096e-120">たとえば、次のコードでは、同等なデータ コントラクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0096e-120">For example, the following code results in equivalent data contracts.</span></span>  
  
 [!code-csharp[C_DataContractNames#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#6)]
 [!code-vb[C_DataContractNames#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#6)]  
  
 <span data-ttu-id="0096e-121">次のコードでは、同等なデータ コントラクトは生成されません。</span><span class="sxs-lookup"><span data-stu-id="0096e-121">However, the following does not result in an equivalent data contract.</span></span>  
  
 [!code-csharp[C_DataContractNames#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#7)]
 [!code-vb[C_DataContractNames#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#7)]  
  
## <a name="inheritance-interfaces-and-data-contract-equivalence"></a><span data-ttu-id="0096e-122">継承、インターフェイス、およびデータ コントラクトの等価性</span><span class="sxs-lookup"><span data-stu-id="0096e-122">Inheritance, Interfaces, and Data Contract Equivalence</span></span>  
 <span data-ttu-id="0096e-123">等価性を判断するとき、別のデータ コントラクトから継承したデータ コントラクトは、基本型のすべてのデータ メンバーを含んでいる 1 つのデータ コントラクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="0096e-123">When determining equivalence, a data contract that inherits from another data contract is treated as if it is just one data contract that includes all of the data members from the base type.</span></span> <span data-ttu-id="0096e-124">データ メンバーの順序が一致する必要があり、基本型のメンバーは派生型のメンバーより前に現れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0096e-124">Keep in mind that the order of the data members must match and that base type members precede derived type members in the order.</span></span> <span data-ttu-id="0096e-125">さらに、次のコード例のように、2 つのデータ メンバーの順序の値が同じ場合、そのデータ メンバーの順序はアルファベット順になります。</span><span class="sxs-lookup"><span data-stu-id="0096e-125">Furthermore, if, as in the following code example, two data members have the same order value, the ordering for those data members is alphabetical.</span></span> <span data-ttu-id="0096e-126">詳細については、次を参照してください。[データ メンバーの順序](../../../../docs/framework/wcf/feature-details/data-member-order.md)します。</span><span class="sxs-lookup"><span data-stu-id="0096e-126">For more information, see [Data Member Order](../../../../docs/framework/wcf/feature-details/data-member-order.md).</span></span>  
  
 <span data-ttu-id="0096e-127">次の例では、型 `Employee` のデータ コントラクトは型 `Worker` のデータ コントラクトと同等です。</span><span class="sxs-lookup"><span data-stu-id="0096e-127">In the following example, the data contract for type `Employee` is equivalent to the data contract for the type `Worker`.</span></span>  
  
 [!code-csharp[C_DataContractNames#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#8)]
 [!code-vb[C_DataContractNames#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#8)]  
  
 <span data-ttu-id="0096e-128">クライアントとサービスの間でパラメーターを渡し、値を返すとき、受信エンドポイントが派生クラスからのデータ コントラクトを予期している場合、基本クラスからのデータ コントラクトを送信できません。</span><span class="sxs-lookup"><span data-stu-id="0096e-128">When passing parameters and return values between a client and a service, a data contract from a base class cannot be sent when the receiving endpoint expects a data contract from a derived class.</span></span> <span data-ttu-id="0096e-129">これは、オブジェクト指向プログラミングの原則に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0096e-129">This is in accordance with object-oriented programming tenets.</span></span> <span data-ttu-id="0096e-130">前の例では、型のオブジェクトで`Person`を送信できない場合に、`Employee`が必要です。</span><span class="sxs-lookup"><span data-stu-id="0096e-130">In the previous example, an object of type `Person` cannot be sent when an `Employee` is expected.</span></span>  
  
 <span data-ttu-id="0096e-131">基本クラスからのデータ コントラクトが予期されるときに派生クラスからのデータ コントラクトを送信することは可能ですが、受信エンドポイントが <xref:System.Runtime.Serialization.KnownTypeAttribute> を使用して派生型を認識している場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="0096e-131">A data contract from a derived class can be sent when a data contract from a base class is expected, but only if the receiving endpoint "knows" of the derived type using the <xref:System.Runtime.Serialization.KnownTypeAttribute>.</span></span> <span data-ttu-id="0096e-132">詳細については、次を参照してください。 [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="0096e-132">For more information, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span> <span data-ttu-id="0096e-133">上記の例では、`Employee` が予期されるときに、受信者のコードが既知の型のリストに `Person` を追加するために <xref:System.Runtime.Serialization.KnownTypeAttribute> を使用している場合のみ、型 Employee のオブジェクトを送信できます。</span><span class="sxs-lookup"><span data-stu-id="0096e-133">In the previous example, an object of type `Employee` can be sent when a `Person` is expected, but only if the receiver code employs the <xref:System.Runtime.Serialization.KnownTypeAttribute> to include it in the list of known types.</span></span>  
  
 <span data-ttu-id="0096e-134">アプリケーション間でパラメーターを渡し、値を返すとき、予期される型がインターフェイスの場合、その型は、型が <xref:System.Object> の予期される型と同等です。</span><span class="sxs-lookup"><span data-stu-id="0096e-134">When passing parameters and return values between applications, if the expected type is an interface, it is equivalent to the expected type being of type <xref:System.Object>.</span></span> <span data-ttu-id="0096e-135">すべての型は最終的に <xref:System.Object> から派生するので、すべてのデータ コントラクトは最終的に、<xref:System.Object> のデータ コントラクトから派生します。</span><span class="sxs-lookup"><span data-stu-id="0096e-135">Because every type ultimately derives from <xref:System.Object>, every data contract ultimately derives from the data contract for <xref:System.Object>.</span></span> <span data-ttu-id="0096e-136">したがって、インターフェイスが予期されるとき、すべてのデータ コントラクト型を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="0096e-136">Thus, any data contract type can be passed when an interface is expected.</span></span> <span data-ttu-id="0096e-137">正常にインターフェイスを使用する追加の手順が必要です。詳細については、次を参照してください。 [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="0096e-137">Additional steps are required to successfully work with interfaces; for more information, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0096e-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="0096e-138">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="0096e-139">データ メンバーの順序</span><span class="sxs-lookup"><span data-stu-id="0096e-139">Data Member Order</span></span>](../../../../docs/framework/wcf/feature-details/data-member-order.md)
- [<span data-ttu-id="0096e-140">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="0096e-140">Data Contract Known Types</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="0096e-141">データ コントラクト名</span><span class="sxs-lookup"><span data-stu-id="0096e-141">Data Contract Names</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-names.md)
