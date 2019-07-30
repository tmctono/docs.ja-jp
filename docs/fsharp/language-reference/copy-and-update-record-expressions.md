---
title: レコード式のコピーと更新
description: 既存のレコードまたは匿名レコードをコピーし、指定したフィールドを更新して、更新されたレコードまたは匿名レコードを返す "コピーおよび更新式" を作成する方法について説明します。
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: dfb20a6ff8282ae5988772cc0f0841db23aad942
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630378"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="45a2f-103">レコード式のコピーと更新</span><span class="sxs-lookup"><span data-stu-id="45a2f-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="45a2f-104">*レコード式のコピーと更新*は、既存のレコードをコピーし、指定されたフィールドを更新して、更新されたレコードを返す式です。</span><span class="sxs-lookup"><span data-stu-id="45a2f-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="45a2f-105">構文</span><span class="sxs-lookup"><span data-stu-id="45a2f-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="45a2f-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="45a2f-106">Remarks</span></span>

<span data-ttu-id="45a2f-107">既定では、レコードおよび匿名レコードは不変であり、可能な限り既存のレコードに対する更新は行われません。</span><span class="sxs-lookup"><span data-stu-id="45a2f-107">Records and anonymous records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="45a2f-108">更新されたレコードを作成するには、レコードのすべてのフィールドを再度指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45a2f-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="45a2f-109">このタスクを簡略化するために、*コピーと更新の式*を使用できます。</span><span class="sxs-lookup"><span data-stu-id="45a2f-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="45a2f-110">この式は、既存のレコードを取得し、式から指定されたフィールドと、式で指定されていないフィールドを使用して、同じ型の新しいものを作成します。</span><span class="sxs-lookup"><span data-stu-id="45a2f-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="45a2f-111">これは、既存のレコードをコピーする必要があり、フィールド値の一部を変更する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="45a2f-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="45a2f-112">新しく作成されたレコードのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="45a2f-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="45a2f-113">そのレコードのフィールドのみを更新する場合は、次のような*コピーと更新のレコード式*を使用できます。</span><span class="sxs-lookup"><span data-stu-id="45a2f-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="45a2f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="45a2f-114">See also</span></span>

- [<span data-ttu-id="45a2f-115">レコード</span><span class="sxs-lookup"><span data-stu-id="45a2f-115">Records</span></span>](records.md)
- [<span data-ttu-id="45a2f-116">匿名レコード</span><span class="sxs-lookup"><span data-stu-id="45a2f-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="45a2f-117">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="45a2f-117">F# Language Reference</span></span>](index.md)
