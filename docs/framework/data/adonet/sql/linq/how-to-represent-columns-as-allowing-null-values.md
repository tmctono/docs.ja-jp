---
title: '方法: null 値を許可する列として列を表す'
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: 00a837467010c2d8a9f0ca16d6aba2fc5f4c973f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781812"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="f8b71-102">方法: null 値を許可する列として列を表す</span><span class="sxs-lookup"><span data-stu-id="f8b71-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="f8b71-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 属性のプロパティを使用して、関連付けられているデータベース列がnull値を保持できることを<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>指定します。 <xref:System.Data.Linq.Mapping.ColumnAttribute></span><span class="sxs-lookup"><span data-stu-id="f8b71-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="f8b71-104">コード例については、「<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8b71-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="f8b71-105">null 値を許可する列を指定するには</span><span class="sxs-lookup"><span data-stu-id="f8b71-105">To designate a column as allowing null values</span></span>  
  
1. <span data-ttu-id="f8b71-106"><xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="f8b71-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="f8b71-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> プロパティ値を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f8b71-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8b71-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8b71-108">See also</span></span>

- [<span data-ttu-id="f8b71-109">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="f8b71-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="f8b71-110">方法: コードエディターを使用してエンティティクラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="f8b71-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
