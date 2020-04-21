---
title: レコード式のコピーと更新
description: 既存のレコードまたは匿名レコードをコピーし、指定されたフィールドを更新し、更新されたレコードまたは匿名レコードを返す「コピーおよび更新式」を記述する方法を説明します。
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: bec3e0ac2fb34e358b199c509c4599b55d7bf35e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739285"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="2cf09-103">レコード式のコピーと更新</span><span class="sxs-lookup"><span data-stu-id="2cf09-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="2cf09-104">*コピーおよび更新レコード式*は、既存のレコードをコピーし、指定されたフィールドを更新して、更新されたレコードを返す式です。</span><span class="sxs-lookup"><span data-stu-id="2cf09-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="2cf09-105">構文</span><span class="sxs-lookup"><span data-stu-id="2cf09-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="2cf09-106">解説</span><span class="sxs-lookup"><span data-stu-id="2cf09-106">Remarks</span></span>

<span data-ttu-id="2cf09-107">レコードと匿名レコードは既定で変更できないので、既存のレコードを更新することはできません。</span><span class="sxs-lookup"><span data-stu-id="2cf09-107">Records and anonymous records are immutable by default, so it is not possible to update an existing record.</span></span> <span data-ttu-id="2cf09-108">更新されたレコードを作成するには、レコードのすべてのフィールドを再指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cf09-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="2cf09-109">このタスクを簡略化するために、*コピー式と更新式*を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2cf09-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="2cf09-110">この式は既存のレコードを受け取り、式の指定されたフィールドと、式で指定された欠落フィールドを使用して、同じタイプの新しいレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="2cf09-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="2cf09-111">これは、既存のレコードをコピーし、フィールド値の一部を変更する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2cf09-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="2cf09-112">たとえば、新しく作成されたレコードを取ります。</span><span class="sxs-lookup"><span data-stu-id="2cf09-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="2cf09-113">そのレコードの 2 つのフィールドだけを更新するには、*コピーおよび更新レコード式*を使用します。</span><span class="sxs-lookup"><span data-stu-id="2cf09-113">To update only two fields in that record you can use the *copy and update record expression*:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="2cf09-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cf09-114">See also</span></span>

- [<span data-ttu-id="2cf09-115">レコード</span><span class="sxs-lookup"><span data-stu-id="2cf09-115">Records</span></span>](records.md)
- [<span data-ttu-id="2cf09-116">匿名のレコード</span><span class="sxs-lookup"><span data-stu-id="2cf09-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="2cf09-117">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="2cf09-117">F# Language Reference</span></span>](index.md)
