---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 9ff207ea4f2b89ea30eb8f46a3e640ccf3789974
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867012"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="f98dd-102">GetType 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f98dd-102">GetType Operator (Visual Basic)</span></span>

<span data-ttu-id="f98dd-103">指定した型の <xref:System.Type> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f98dd-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="f98dd-104"><xref:System.Type> オブジェクトは、そのプロパティ、メソッド、イベントなど、型に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f98dd-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f98dd-105">構文</span><span class="sxs-lookup"><span data-stu-id="f98dd-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="f98dd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f98dd-106">Parameters</span></span>  
  
|<span data-ttu-id="f98dd-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f98dd-107">Parameter</span></span>|<span data-ttu-id="f98dd-108">説明</span><span class="sxs-lookup"><span data-stu-id="f98dd-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="f98dd-109">情報を必要とする型の名前。</span><span class="sxs-lookup"><span data-stu-id="f98dd-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f98dd-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f98dd-110">Remarks</span></span>  

 <span data-ttu-id="f98dd-111">`GetType` 演算子は、指定された `typename` の <xref:System.Type> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f98dd-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="f98dd-112">定義された型の名前を `typename` で渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f98dd-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="f98dd-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f98dd-113">This includes the following:</span></span>  
  
- <span data-ttu-id="f98dd-114">Visual Basic の任意のデータ型 (`Boolean` や `Date` など)。</span><span class="sxs-lookup"><span data-stu-id="f98dd-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="f98dd-115">.NET Framework の任意のクラス、構造体、モジュール、インターフェイス (<xref:System.ArgumentException?displayProperty=nameWithType> や <xref:System.Double?displayProperty=nameWithType> など)。</span><span class="sxs-lookup"><span data-stu-id="f98dd-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="f98dd-116">アプリケーションで定義されている任意のクラス、構造体、モジュール、インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="f98dd-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="f98dd-117">アプリケーションで定義されている任意の配列。</span><span class="sxs-lookup"><span data-stu-id="f98dd-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="f98dd-118">アプリケーションで定義されている任意のデリゲート。</span><span class="sxs-lookup"><span data-stu-id="f98dd-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="f98dd-119">Visual Basic、.NET Framework、お使いのアプリケーションによって定義された任意の列挙型。</span><span class="sxs-lookup"><span data-stu-id="f98dd-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="f98dd-120">オブジェクト変数の型オブジェクトを取得する場合は、<xref:System.Type.GetType%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f98dd-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="f98dd-121">`GetType` 演算子は、次のような場合に役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="f98dd-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="f98dd-122">実行時に型のメタデータにアクセスする必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="f98dd-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="f98dd-123"><xref:System.Type> オブジェクトは、型のメンバーやデプロイ情報などのメタデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="f98dd-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="f98dd-124">これは、たとえば、アセンブリについて検討するときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="f98dd-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="f98dd-125">詳細については、「<xref:System.Reflection?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f98dd-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="f98dd-126">2 つのオブジェクト参照を比較して、それらが同じ型のインスタンスを参照しているかどうかを確認する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="f98dd-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="f98dd-127">そうである場合、`GetType` は同じ <xref:System.Type> オブジェクトへの参照を返します。</span><span class="sxs-lookup"><span data-stu-id="f98dd-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f98dd-128">例</span><span class="sxs-lookup"><span data-stu-id="f98dd-128">Example</span></span>  

 <span data-ttu-id="f98dd-129">`GetType` 演算子の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f98dd-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="f98dd-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="f98dd-130">See also</span></span>

- [<span data-ttu-id="f98dd-131">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="f98dd-131">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="f98dd-132">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="f98dd-132">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="f98dd-133">演算子および式</span><span class="sxs-lookup"><span data-stu-id="f98dd-133">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
