---
title: 入力文字セット (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
ms.openlocfilehash: 3795660cf6086aa67596f31e49c4d950aa653d86
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780420"
---
# <a name="input-character-set-entity-sql"></a><span data-ttu-id="5db72-102">入力文字セット (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5db72-102">Input Character Set (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5db72-103">は、UTF-16 でエンコードされた UNICODE 文字を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5db72-103">accepts UNICODE characters encoded in UTF-16.</span></span>  
  
 <span data-ttu-id="5db72-104">文字列リテラルには、単一引用符で囲んだ任意の UTF-16 文字を含めることができます </span><span class="sxs-lookup"><span data-stu-id="5db72-104">String literals can contain any UTF-16 character enclosed in single quotes.</span></span> <span data-ttu-id="5db72-105">たとえば、N'リテラル文字列' のように記述します。</span><span class="sxs-lookup"><span data-stu-id="5db72-105">For example, N'文字列リテラル'.</span></span> <span data-ttu-id="5db72-106">文字列リテラルが比較される際は、元の UTF-16 の値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5db72-106">When string literals are compared, the original UTF-16 values are used.</span></span> <span data-ttu-id="5db72-107">たとえば、N'ABC' は、日本語とラテンのコードページでは異なります。</span><span class="sxs-lookup"><span data-stu-id="5db72-107">For example, N'ABC' is different in Japanese and Latin codepages.</span></span>  
  
 <span data-ttu-id="5db72-108">コメントには、任意の UTF-16 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5db72-108">Comments can contain any UTF-16 character.</span></span>  
  
 <span data-ttu-id="5db72-109">エスケープされた識別子には、角かっこで囲んだ任意の UTF-16 文字を含めることができます </span><span class="sxs-lookup"><span data-stu-id="5db72-109">Escaped identifiers can contain any UTF-16 character enclosed in square brackets.</span></span> <span data-ttu-id="5db72-110">たとえば、[エスケープされた識別子] のように記述します。</span><span class="sxs-lookup"><span data-stu-id="5db72-110">For example, [エスケープされた識別子].</span></span> <span data-ttu-id="5db72-111">UTF-16 エスケープされた識別子の比較では、大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="5db72-111">The comparison of UTF-16 escaped identifiers is case insensitive.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5db72-112">は、同じように表示されても別のコード ページに由来する文字の複数のバージョンを別々の文字として扱います。</span><span class="sxs-lookup"><span data-stu-id="5db72-112">treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="5db72-113">たとえば、対応する文字が同じコード ページである場合、[ABC] は [abc] と同じものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="5db72-113">For example, [ABC] is equivalent to [abc] if the corresponding characters are from the same code page.</span></span> <span data-ttu-id="5db72-114">ただし、同じ 2 つの識別子のコード ページが異なる場合は、同じものと見なされません。</span><span class="sxs-lookup"><span data-stu-id="5db72-114">However, if the same two identifiers are from different code pages, they are not equivalent.</span></span>  
  
 <span data-ttu-id="5db72-115">空白は、任意の UTF-16 空白文字です。</span><span class="sxs-lookup"><span data-stu-id="5db72-115">White space is any UTF-16 white space character.</span></span>  
  
 <span data-ttu-id="5db72-116">改行は、任意の正規化 UTF-16 改行文字です。</span><span class="sxs-lookup"><span data-stu-id="5db72-116">A newline is any normalized UTF-16 newline character.</span></span> <span data-ttu-id="5db72-117">たとえば、'\n' および '\r\n' は改行文字と見なされますが、'\r' は改行文字ではありません。</span><span class="sxs-lookup"><span data-stu-id="5db72-117">For example, '\n' and '\r\n' are considered newline characters, but '\r' is not a newline character.</span></span>  
  
 <span data-ttu-id="5db72-118">キーワード、式、および句読点には、ラテン語に正規化された任意の UTF-16 文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5db72-118">Keywords, expressions, and punctuation can be any UTF-16 character that normalizes to Latin.</span></span> <span data-ttu-id="5db72-119">たとえば、日本語のコードページの SELECT は有効なキーワードです。</span><span class="sxs-lookup"><span data-stu-id="5db72-119">For example, SELECT in a Japanese codepage is a valid keyword.</span></span>  
  
 <span data-ttu-id="5db72-120">キーワード、式、および区切り記号に使用できるのは、ラテン文字だけです。</span><span class="sxs-lookup"><span data-stu-id="5db72-120">Keywords, expressions, and punctuation can only be Latin characters.</span></span> <span data-ttu-id="5db72-121">`SELECT` は、日本語のコード ページではキーワードではありません。</span><span class="sxs-lookup"><span data-stu-id="5db72-121">`SELECT` in a Japanese codepage is not a keyword.</span></span> <span data-ttu-id="5db72-122">+、-、 \*、/、=、(、)、'、[、] は、ここに示されていないその他の言語コンストラクトは、ラテン文字を指定できますのみです。</span><span class="sxs-lookup"><span data-stu-id="5db72-122">+, -, \*, /, =, (, ), ‘, [, ] and any other language construct not quoted here can only be Latin characters.</span></span>  
  
 <span data-ttu-id="5db72-123">シンプルな識別子に使用できるのはラテン文字だけです。</span><span class="sxs-lookup"><span data-stu-id="5db72-123">Simple identifiers can only be Latin characters.</span></span> <span data-ttu-id="5db72-124">元の値が比較されるので、比較の際のあいまいさが回避されます。</span><span class="sxs-lookup"><span data-stu-id="5db72-124">This avoids ambiguity during comparison, because original values are compared.</span></span> <span data-ttu-id="5db72-125">たとえば、ABC が日本語とラテンのコードページで異なる場合がします。</span><span class="sxs-lookup"><span data-stu-id="5db72-125">For example, ABC would be different in Japanese and Latin codepages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db72-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="5db72-126">See also</span></span>

- [<span data-ttu-id="5db72-127">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="5db72-127">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
