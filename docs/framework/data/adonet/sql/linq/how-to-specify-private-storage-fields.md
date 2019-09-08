---
title: '方法: プライベート ストレージ フィールドを指定する'
ms.date: 03/30/2017
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
ms.openlocfilehash: e6e6a4e28fbfb327f25874844f28bcbafa6d2805
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793209"
---
# <a name="how-to-specify-private-storage-fields"></a><span data-ttu-id="9d21c-102">方法: プライベート ストレージ フィールドを指定する</span><span class="sxs-lookup"><span data-stu-id="9d21c-102">How to: Specify Private Storage Fields</span></span>
<span data-ttu-id="9d21c-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 属性のプロパティを使用して、基になるストレージフィールドの名前<xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>を指定します<xref:System.Data.Linq.Mapping.DataAttribute> 。</span><span class="sxs-lookup"><span data-stu-id="9d21c-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property on the <xref:System.Data.Linq.Mapping.DataAttribute> attribute to designate the name of an underlying storage field.</span></span>  
  
 <span data-ttu-id="9d21c-104">コード例については、「<xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d21c-104">For code examples, see <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a><span data-ttu-id="9d21c-105">基になるストレージ フィールドの名前を指定するには</span><span class="sxs-lookup"><span data-stu-id="9d21c-105">To specify the name of an underlying storage field</span></span>  
  
1. <span data-ttu-id="9d21c-106"><xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="9d21c-106">Add the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="9d21c-107">フィールドの名前を <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> プロパティの値として代入します。</span><span class="sxs-lookup"><span data-stu-id="9d21c-107">Assign the name of the field as the value of the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d21c-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d21c-108">See also</span></span>

- [<span data-ttu-id="9d21c-109">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="9d21c-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="9d21c-110">方法: コードエディターを使用してエンティティクラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="9d21c-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
