---
title: 型 <type> の式はクエリ不可能です
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 78b47601bf0a013d079f638f6dac27511e01aec4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874206"
---
# <a name="expression-of-type-type-is-not-queryable"></a><span data-ttu-id="f5148-102">型 \<type> の式はクエリ不可能です</span><span class="sxs-lookup"><span data-stu-id="f5148-102">Expression of type \<type> is not queryable</span></span>

<span data-ttu-id="f5148-103">型 \<type> の式はクエリ不可能です。</span><span class="sxs-lookup"><span data-stu-id="f5148-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="f5148-104">LINQ プロバイダーに対してアセンブリ参照や名前空間インポートが不足していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f5148-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="f5148-105">クエリ可能型は、<xref:System.Linq>、<xref:System.Data.Linq>、および <xref:System.Xml.Linq> 名前空間で定義します。</span><span class="sxs-lookup"><span data-stu-id="f5148-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="f5148-106">LINQ クエリを実行するには、これらの名前空間の 1 つ以上をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5148-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="f5148-107"><xref:System.Linq> 名前空間により、LINQ を使用してコレクションや配列などのオブジェクトに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f5148-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="f5148-108"><xref:System.Data.Linq> 名前空間により、LINQ を使用して ADO.NET データセットと SQL Server データベースに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f5148-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="f5148-109"><xref:System.Xml.Linq> 名前空間により、LINQ を使用して XML に対してクエリを実行し、Visual Basic の XML 機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5148-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="f5148-110">**エラー ID:** BC36593</span><span class="sxs-lookup"><span data-stu-id="f5148-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f5148-111">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f5148-111">To correct this error</span></span>  
  
1. <span data-ttu-id="f5148-112"><xref:System.Linq>、<xref:System.Data.Linq>、または <xref:System.Xml.Linq> 名前空間の `Import` ステートメントをコード ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="f5148-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="f5148-113">プロジェクト デザイナー (**マイ プロジェクト**) の **[参照]** ページを使用して、プロジェクトの名前空間をインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f5148-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2. <span data-ttu-id="f5148-114">クエリのソースとして指定した型がクエリ可能型であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5148-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="f5148-115">つまり、<xref:System.Collections.Generic.IEnumerable%601> または <xref:System.Linq.IQueryable%601> を実装する型です。</span><span class="sxs-lookup"><span data-stu-id="f5148-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5148-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5148-116">See also</span></span>

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [<span data-ttu-id="f5148-117">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="f5148-117">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f5148-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="f5148-118">LINQ</span></span>](../../programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="f5148-119">XML</span><span class="sxs-lookup"><span data-stu-id="f5148-119">XML</span></span>](../../programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="f5148-120">参照と Imports ステートメント</span><span class="sxs-lookup"><span data-stu-id="f5148-120">References and the Imports Statement</span></span>](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="f5148-121">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="f5148-121">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- <span data-ttu-id="f5148-122">[[参照設定] ページ (プロジェクト デザイナー) (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="f5148-122">[References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span></span>
