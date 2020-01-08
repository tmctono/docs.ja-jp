---
title: '方法 : 継承階層を割り当てる'
ms.date: 03/30/2017
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
ms.openlocfilehash: 737cb8743d8fd9c93cd46ebf50fba3fe554a35f2
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634665"
---
# <a name="how-to-map-inheritance-hierarchies"></a><span data-ttu-id="dc9fc-102">方法 : 継承階層を割り当てる</span><span class="sxs-lookup"><span data-stu-id="dc9fc-102">How to: Map Inheritance Hierarchies</span></span>
<span data-ttu-id="dc9fc-103">LINQ で継承マッピングを実装するには、次の手順に従って、継承階層のルートクラスで属性および属性プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-103">To implement inheritance mapping in LINQ, you must specify the attributes and attribute properties on the root class of the inheritance hierarchy as described in the following steps.</span></span> <span data-ttu-id="dc9fc-104">Visual Studio を使用する開発者は、オブジェクトリレーショナルデザイナーを使用して継承階層をマップできます。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-104">Developers using Visual Studio can use the Object Relational Designer to map inheritance hierarchies.</span></span> <span data-ttu-id="dc9fc-105">「[方法: O/R デザイナーを使用して継承を構成する](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-105">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc9fc-106">サブクラスには特別な属性やプロパティは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-106">No special attributes or properties are required on the subclasses.</span></span> <span data-ttu-id="dc9fc-107">特に、サブクラスに <xref:System.Data.Linq.Mapping.TableAttribute> 属性がない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-107">Note especially that subclasses do not have the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span>  
  
### <a name="to-map-an-inheritance-hierarchy"></a><span data-ttu-id="dc9fc-108">継承階層を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="dc9fc-108">To map an inheritance hierarchy</span></span>  
  
1. <span data-ttu-id="dc9fc-109">ルート クラスに <xref:System.Data.Linq.Mapping.TableAttribute> 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-109">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the root class.</span></span>  
  
2. <span data-ttu-id="dc9fc-110">ルート クラスに対し、階層構造の各クラスについて <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-110">Also to the root class, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute for each class in the hierarchy structure.</span></span>  
  
3. <span data-ttu-id="dc9fc-111">各 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 属性に対し、<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-111">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, define a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> property.</span></span>  
  
     <span data-ttu-id="dc9fc-112">このプロパティは、データベース テーブルの <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 列に含まれる値を保持し、このデータ行が属するクラスまたはサブクラスを示します。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-112">This property holds a value that appears in the database table in the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> column to indicate which class or subclass this row of data belongs to.</span></span>  
  
4. <span data-ttu-id="dc9fc-113">各 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 属性に対し、<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> プロパティも追加します。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-113">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, also add a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> property.</span></span>  
  
     <span data-ttu-id="dc9fc-114">このプロパティは、キー値が示すクラスまたはサブクラスを表す値を保持します。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-114">This property holds a value that specifies which class or subclass the key value signifies.</span></span>  
  
5. <span data-ttu-id="dc9fc-115">1 つの <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 属性にのみ、<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-115">On only one of the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attributes, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> property.</span></span>  
  
     <span data-ttu-id="dc9fc-116">このプロパティは、データベーステーブルの識別子の値が継承マッピングのどの <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 値とも一致しない場合に、*フォールバック*マッピングを指定するために機能します。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-116">This property serves to designate a *fallback* mapping when the discriminator value from the database table does not match any <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value in the inheritance mappings.</span></span>  
  
6. <span data-ttu-id="dc9fc-117"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-117">Add an <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> property for a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
     <span data-ttu-id="dc9fc-118">このプロパティは、<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 値を保持する列であることを示します。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-118">This property signifies that this is the column that holds the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc9fc-119">使用例</span><span class="sxs-lookup"><span data-stu-id="dc9fc-119">Example</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc9fc-120">Visual Studio を使用している場合は、オブジェクトリレーショナルデザイナーを使用して継承を構成できます。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-120">If you are using Visual Studio, you can use the Object Relational Designer to configure inheritance.</span></span> <span data-ttu-id="dc9fc-121">「[方法: O/R デザイナーを使用して継承を構成する](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-121">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span></span>  
  
 <span data-ttu-id="dc9fc-122">次のコード例では、`Vehicle` がルートクラスとして定義されており、前述の手順が LINQ の階層を記述するように実装されています。</span><span class="sxs-lookup"><span data-stu-id="dc9fc-122">In the following code example, `Vehicle` is defined as the root class, and the previous steps have been implemented to describe the hierarchy for LINQ.</span></span>  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="dc9fc-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc9fc-123">See also</span></span>

- [<span data-ttu-id="dc9fc-124">継承のサポート</span><span class="sxs-lookup"><span data-stu-id="dc9fc-124">Inheritance Support</span></span>](inheritance-support.md)
- [<span data-ttu-id="dc9fc-125">方法 : コード エディターを使用してエンティティ クラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="dc9fc-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
