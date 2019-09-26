---
title: COR_DEBUG_IL_TO_NATIVE_MAP 構造体
ms.date: 03/30/2017
api_name:
- COR_DEBUG_IL_TO_NATIVE_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: babb1ace1385c241b782691f22bfb4fbb689e310
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274072"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="7d66b-102">COR_DEBUG_IL_TO_NATIVE_MAP 構造体</span><span class="sxs-lookup"><span data-stu-id="7d66b-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="7d66b-103">Microsoft intermediate language (MSIL) コードをネイティブ コードにマップするために使用するオフセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d66b-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d66b-104">構文</span><span class="sxs-lookup"><span data-stu-id="7d66b-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="7d66b-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7d66b-105">Members</span></span>  
  
|<span data-ttu-id="7d66b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7d66b-106">Member</span></span>|<span data-ttu-id="7d66b-107">説明</span><span class="sxs-lookup"><span data-stu-id="7d66b-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="7d66b-108">MSIL コードのオフセット。</span><span class="sxs-lookup"><span data-stu-id="7d66b-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="7d66b-109">ネイティブコードの開始位置のオフセット。</span><span class="sxs-lookup"><span data-stu-id="7d66b-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="7d66b-110">ネイティブコードの末尾のオフセット。</span><span class="sxs-lookup"><span data-stu-id="7d66b-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d66b-111">要件</span><span class="sxs-lookup"><span data-stu-id="7d66b-111">Requirements</span></span>  
 <span data-ttu-id="7d66b-112">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d66b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d66b-113">**ヘッダー:** Corprof.idl、CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="7d66b-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="7d66b-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="7d66b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d66b-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d66b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d66b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d66b-116">See also</span></span>

- [<span data-ttu-id="7d66b-117">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="7d66b-117">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="7d66b-118">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="7d66b-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="7d66b-119">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="7d66b-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="7d66b-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="7d66b-120">Debugging</span></span>](index.md)
