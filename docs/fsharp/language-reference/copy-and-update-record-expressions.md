---
title: レコード式のコピーと更新
description: "'コピーと更新式を' 既存のレコードまたは匿名のレコード、更新プログラムをコピーするフィールドを指定して、更新されたレコードまたは匿名のレコードを返します記述する方法について説明します。"
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: d16f5ca337047ab2eecc8828b21d8a423bf39a1f
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041731"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="6c6c4-103">レコード式のコピーと更新</span><span class="sxs-lookup"><span data-stu-id="6c6c4-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="6c6c4-104">A*コピーして更新するレコード式*を既存のレコードをコピーし、指定のフィールドを更新し、更新されたレコードを返す式を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c6c4-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c6c4-105">構文</span><span class="sxs-lookup"><span data-stu-id="6c6c4-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="6c6c4-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="6c6c4-106">Remarks</span></span>

<span data-ttu-id="6c6c4-107">レコードと匿名は可能な更新プログラムを既存のレコードがないように、既定では、変更できません。</span><span class="sxs-lookup"><span data-stu-id="6c6c4-107">Records and anonymous records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="6c6c4-108">更新したレコードを作成するには、レコードのすべてのフィールドには、もう一度指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c6c4-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="6c6c4-109">このタスクを簡略化する、*コピーして、式を更新*ことができます。</span><span class="sxs-lookup"><span data-stu-id="6c6c4-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="6c6c4-110">この式は、既存のレコードには、式から指定したフィールドと、式で指定された存在しないフィールドを使用して、同じ型の新しいデフォルトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c6c4-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="6c6c4-111">これは、フィールドの値の一部を変更する可能性があります、既存のレコードをコピーする必要があるときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6c6c4-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="6c6c4-112">新しく作成されたレコード インスタンスがかかります。</span><span class="sxs-lookup"><span data-stu-id="6c6c4-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="6c6c4-113">使用することがそのレコードのフィールドでのみ更新する場合は、*コピーして更新するレコード式*次のように。</span><span class="sxs-lookup"><span data-stu-id="6c6c4-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="6c6c4-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c6c4-114">See also</span></span>

- [<span data-ttu-id="6c6c4-115">レコード</span><span class="sxs-lookup"><span data-stu-id="6c6c4-115">Records</span></span>](records.md)
- [<span data-ttu-id="6c6c4-116">匿名のレコード</span><span class="sxs-lookup"><span data-stu-id="6c6c4-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="6c6c4-117">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="6c6c4-117">F# Language Reference</span></span>](index.md)
