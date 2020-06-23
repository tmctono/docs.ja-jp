---
title: '方法: クラスまたは構造体に基本的なデータ コントラクトを作成する'
description: 次の例に従って、DataContractAttribute 属性を使用して、WCF のクラスまたは構造体を使用してデータコントラクトを作成する方法を学習します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
ms.openlocfilehash: a45fde58795947c3e46fa45750ae1a3faddd8849
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247170"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="a5911-103">方法: クラスまたは構造体に基本的なデータ コントラクトを作成する</span><span class="sxs-lookup"><span data-stu-id="a5911-103">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="a5911-104">このトピックでは、クラスまたは構造体を使用してデータ コントラクトを作成する基本的な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="a5911-104">This topic shows the basic steps to create a data contract using a class or structure.</span></span> <span data-ttu-id="a5911-105">データコントラクトとその使用方法の詳細については、「[データコントラクトの使用](using-data-contracts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5911-105">For more information about data contracts and how they are used, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="a5911-106">基本的な Windows Communication Foundation (WCF) サービスとクライアントを作成する手順を説明するチュートリアルについては、[はじめにのチュートリアル](../getting-started-tutorial.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5911-106">For a tutorial that walks through the steps of creating a basic Windows Communication Foundation (WCF) service and client, see the [Getting Started Tutorial](../getting-started-tutorial.md).</span></span> <span data-ttu-id="a5911-107">基本的なサービスとクライアントで構成される実用的なサンプルアプリケーションについては、「[基本的なデータコントラクト](../samples/basic-data-contract.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5911-107">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="a5911-108">クラスまたは構造体に基本的なデータ コントラクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="a5911-108">To create a basic data contract for a class or structure</span></span>  
  
1. <span data-ttu-id="a5911-109">クラスに <xref:System.Runtime.Serialization.DataContractAttribute> 属性を適用することにより、データ コントラクトを持つ型であることを宣言します。</span><span class="sxs-lookup"><span data-stu-id="a5911-109">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="a5911-110">パブリック型は、属性のないものも含めてすべてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="a5911-110">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="a5911-111"><xref:System.Runtime.Serialization.DataContractSerializer> 属性がない場合は、<xref:System.Runtime.Serialization.DataContractAttribute> によってデータ コントラクトが推論されます。</span><span class="sxs-lookup"><span data-stu-id="a5911-111">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> <span data-ttu-id="a5911-112">詳細については、「[シリアル化](serializable-types.md)可能な型」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5911-112">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
2. <span data-ttu-id="a5911-113">シリアル化するメンバー (プロパティ、フィールド、またはイベント) を定義します。これは、該当する各メンバーに <xref:System.Runtime.Serialization.DataMemberAttribute> 属性を適用することで行います。</span><span class="sxs-lookup"><span data-stu-id="a5911-113">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="a5911-114">このようなメンバーのことを、データ メンバーと呼びます。</span><span class="sxs-lookup"><span data-stu-id="a5911-114">These members are called data members.</span></span> <span data-ttu-id="a5911-115">既定では、すべてのパブリック型がシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="a5911-115">By default, all public types are serializable.</span></span> <span data-ttu-id="a5911-116">詳細については、「[シリアル化](serializable-types.md)可能な型」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5911-116">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a5911-117">プライベート フィールドであっても、<xref:System.Runtime.Serialization.DataMemberAttribute> 属性を適用すると、データが外部に公開されることになります。</span><span class="sxs-lookup"><span data-stu-id="a5911-117">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="a5911-118">機密性のあるデータが含まれていないかどうか確認してください。</span><span class="sxs-lookup"><span data-stu-id="a5911-118">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5911-119">例</span><span class="sxs-lookup"><span data-stu-id="a5911-119">Example</span></span>  
 <span data-ttu-id="a5911-120">次の例では、`Person` 属性と <xref:System.Runtime.Serialization.DataContractAttribute> 属性をクラスとそのメンバーに適用して、<xref:System.Runtime.Serialization.DataMemberAttribute> 型のデータ コントラクトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5911-120">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a5911-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5911-121">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="a5911-122">データ コントラクトの使用</span><span class="sxs-lookup"><span data-stu-id="a5911-122">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="a5911-123">はじめにチュートリアル</span><span class="sxs-lookup"><span data-stu-id="a5911-123">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)
- [<span data-ttu-id="a5911-124">はじめに</span><span class="sxs-lookup"><span data-stu-id="a5911-124">Getting Started</span></span>](../samples/getting-started-sample.md)
