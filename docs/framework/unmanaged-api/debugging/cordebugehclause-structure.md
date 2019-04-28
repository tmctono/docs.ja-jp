---
title: CorDebugEHClause 構造体
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 839e698c8921f916fad174bae4f4cc8bb4d02994
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609075"
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="815ca-102">CorDebugEHClause 構造体</span><span class="sxs-lookup"><span data-stu-id="815ca-102">CorDebugEHClause Structure</span></span>
<span data-ttu-id="815ca-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="815ca-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="815ca-104">中間言語 (IL) コードの特定の部分の例外処理 (EH) 句を表しています。</span><span class="sxs-lookup"><span data-stu-id="815ca-104">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="815ca-105">構文</span><span class="sxs-lookup"><span data-stu-id="815ca-105">Syntax</span></span>  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a><span data-ttu-id="815ca-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="815ca-106">Members</span></span>  
  
|<span data-ttu-id="815ca-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="815ca-107">Member</span></span>|<span data-ttu-id="815ca-108">説明</span><span class="sxs-lookup"><span data-stu-id="815ca-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="815ca-109">EH 句の例外情報について説明しているビット フィールド。</span><span class="sxs-lookup"><span data-stu-id="815ca-109">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="815ca-110">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="815ca-110">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="815ca-111">メソッド本体の先頭からの `try` ブロックのオフセット (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="815ca-111">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="815ca-112">`try` ブロックの長さ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="815ca-112">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="815ca-113">この `try` ブロックのハンドラーの場所。</span><span class="sxs-lookup"><span data-stu-id="815ca-113">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="815ca-114">ハンドラー コードのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="815ca-114">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="815ca-115">型に基づく例外ハンドラーのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="815ca-115">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="815ca-116">フィルターに基づく例外ハンドラーのメソッド本体の先頭からのオフセット (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="815ca-116">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="815ca-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="815ca-117">Remarks</span></span>  
 <span data-ttu-id="815ca-118">配列の`CoreDebugEHClause`によって値が返される、 [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="815ca-118">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="815ca-119">EH 句の情報は CLI 仕様によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="815ca-119">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="815ca-120">詳細については、次を参照してください。[標準 ECMA 355。共通言語基盤 (CLI)、6 th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm)します。</span><span class="sxs-lookup"><span data-stu-id="815ca-120">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="815ca-121">`flags` フィールドには、次のフラグを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="815ca-121">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="815ca-122">これらは、CorDebug.idl または CorDebug.h に定義されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="815ca-122">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="815ca-123">フラグ</span><span class="sxs-lookup"><span data-stu-id="815ca-123">Flag</span></span>|<span data-ttu-id="815ca-124">[値]</span><span class="sxs-lookup"><span data-stu-id="815ca-124">Value</span></span>|<span data-ttu-id="815ca-125">説明</span><span class="sxs-lookup"><span data-stu-id="815ca-125">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="815ca-126">0x00000000</span><span class="sxs-lookup"><span data-stu-id="815ca-126">0x00000000</span></span>|<span data-ttu-id="815ca-127">入力された例外句。</span><span class="sxs-lookup"><span data-stu-id="815ca-127">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="815ca-128">0x00000001</span><span class="sxs-lookup"><span data-stu-id="815ca-128">0x00000001</span></span>|<span data-ttu-id="815ca-129">例外フィルターおよびハンドラー句。</span><span class="sxs-lookup"><span data-stu-id="815ca-129">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="815ca-130">0x00000002</span><span class="sxs-lookup"><span data-stu-id="815ca-130">0x00000002</span></span>|<span data-ttu-id="815ca-131">`finally` 句。</span><span class="sxs-lookup"><span data-stu-id="815ca-131">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="815ca-132">0x00000004</span><span class="sxs-lookup"><span data-stu-id="815ca-132">0x00000004</span></span>|<span data-ttu-id="815ca-133">fault 句 (例外がスローされた場合にのみ `finally` 句が呼び出される)。</span><span class="sxs-lookup"><span data-stu-id="815ca-133">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="815ca-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="815ca-134">Requirements</span></span>  
 <span data-ttu-id="815ca-135">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="815ca-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="815ca-136">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="815ca-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="815ca-137">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="815ca-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="815ca-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="815ca-138">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="815ca-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="815ca-139">See also</span></span>

- [<span data-ttu-id="815ca-140">GetEHClauses メソッド</span><span class="sxs-lookup"><span data-stu-id="815ca-140">GetEHClauses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)
- [<span data-ttu-id="815ca-141">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="815ca-141">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
