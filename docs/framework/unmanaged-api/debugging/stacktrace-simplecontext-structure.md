---
title: StackTrace_SimpleContext 構造体
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0625dc72d44485dbb69b42cba5387085d1862bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986532"
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="88893-102">StackTrace_SimpleContext 構造体</span><span class="sxs-lookup"><span data-stu-id="88893-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="88893-103">完全な `CONTEXT` 構造の代わりに使用できる単純なコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="88893-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88893-104">構文</span><span class="sxs-lookup"><span data-stu-id="88893-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="88893-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="88893-105">Members</span></span>  
  
|<span data-ttu-id="88893-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="88893-106">Member</span></span>|<span data-ttu-id="88893-107">説明</span><span class="sxs-lookup"><span data-stu-id="88893-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="88893-108">スタック ポインター、または x86 enter スタック ポインター (ESP) プラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="88893-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="88893-109">フレームのオフセット、または x86 EBP レジスタのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="88893-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="88893-110">命令ポインター、または x86 enter 命令ポインター (EIP) プラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="88893-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88893-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="88893-111">Remarks</span></span>  
 <span data-ttu-id="88893-112">使用できます必要に応じてスタック トレース関数は、通常、アドレス、フレームのオフセット、およびスタック アドレスのみを返す必要があります、ため、`SimpleContext`構造ではなく、大規模な`CONTEXT`構造体。</span><span class="sxs-lookup"><span data-stu-id="88893-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88893-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="88893-113">Requirements</span></span>  
 <span data-ttu-id="88893-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="88893-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88893-115">**ヘッダー:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="88893-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="88893-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88893-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88893-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="88893-117">See also</span></span>

- [<span data-ttu-id="88893-118">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="88893-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="88893-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="88893-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
