---
title: 型 <type> の式はクエリ不可能です
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 121c0a95a3a6bb695d9c73347c733cba215a0de4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801622"
---
# <a name="expression-of-type-type-is-not-queryable"></a><span data-ttu-id="f0cc0-102">型の式\<型 > はクエリ不可能</span><span class="sxs-lookup"><span data-stu-id="f0cc0-102">Expression of type \<type> is not queryable</span></span>
<span data-ttu-id="f0cc0-103">型の式\<型 > はクエリ不可能です。</span><span class="sxs-lookup"><span data-stu-id="f0cc0-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="f0cc0-104">LINQ プロバイダーに対してアセンブリ参照や名前空間インポートを欠落していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0cc0-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="f0cc0-105">クエリ可能型が定義されている、 <xref:System.Linq>、 <xref:System.Data.Linq>、および<xref:System.Xml.Linq>名前空間。</span><span class="sxs-lookup"><span data-stu-id="f0cc0-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="f0cc0-106">1 つ以上の LINQ クエリを実行するこれらの名前空間をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0cc0-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="f0cc0-107"><xref:System.Linq>名前空間によりコレクションや配列などのクエリ オブジェクトを LINQ を使用しています。</span><span class="sxs-lookup"><span data-stu-id="f0cc0-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="f0cc0-108"><xref:System.Data.Linq>名前空間では、LINQ を使用して、ADO.NET データセット、および SQL Server データベースを照会することができます。</span><span class="sxs-lookup"><span data-stu-id="f0cc0-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="f0cc0-109"><xref:System.Xml.Linq>名前空間では、XML のクエリに LINQ を使用して、Visual Basic で XML 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0cc0-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="f0cc0-110">**エラー ID:** BC36593</span><span class="sxs-lookup"><span data-stu-id="f0cc0-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f0cc0-111">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f0cc0-111">To correct this error</span></span>  
  
1. <span data-ttu-id="f0cc0-112">追加、`Import`のステートメント、 <xref:System.Linq>、 <xref:System.Data.Linq>、または<xref:System.Xml.Linq>をコード ファイルの名前空間。</span><span class="sxs-lookup"><span data-stu-id="f0cc0-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="f0cc0-113">使用して、プロジェクトの名前空間をインポートすることも、**参照**プロジェクト デザイナーのページ (**My Project**)。</span><span class="sxs-lookup"><span data-stu-id="f0cc0-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2. <span data-ttu-id="f0cc0-114">クエリのソースはクエリ可能型を指定した型を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0cc0-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="f0cc0-115">実装する型は、<xref:System.Collections.Generic.IEnumerable%601>または<xref:System.Linq.IQueryable%601>します。</span><span class="sxs-lookup"><span data-stu-id="f0cc0-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0cc0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0cc0-116">See also</span></span>

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [<span data-ttu-id="f0cc0-117">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="f0cc0-117">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f0cc0-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="f0cc0-118">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="f0cc0-119">XML</span><span class="sxs-lookup"><span data-stu-id="f0cc0-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="f0cc0-120">参照と Imports ステートメント</span><span class="sxs-lookup"><span data-stu-id="f0cc0-120">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="f0cc0-121">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="f0cc0-121">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- <span data-ttu-id="f0cc0-122">[[参照設定] ページ (プロジェクト デザイナー) (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="f0cc0-122">[References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span></span>
