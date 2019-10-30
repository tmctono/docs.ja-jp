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
ms.openlocfilehash: 2a36c9808f29c038e3185157078c235959baf13c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132374"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="337e2-102">COR_DEBUG_IL_TO_NATIVE_MAP 構造体</span><span class="sxs-lookup"><span data-stu-id="337e2-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="337e2-103">Microsoft intermediate language (MSIL) コードをネイティブ コードにマップするために使用するオフセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="337e2-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="337e2-104">構文</span><span class="sxs-lookup"><span data-stu-id="337e2-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="337e2-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="337e2-105">Members</span></span>  
  
|<span data-ttu-id="337e2-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="337e2-106">Member</span></span>|<span data-ttu-id="337e2-107">説明</span><span class="sxs-lookup"><span data-stu-id="337e2-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="337e2-108">MSIL コードのオフセット。</span><span class="sxs-lookup"><span data-stu-id="337e2-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="337e2-109">ネイティブコードの開始位置のオフセット。</span><span class="sxs-lookup"><span data-stu-id="337e2-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="337e2-110">ネイティブコードの末尾のオフセット。</span><span class="sxs-lookup"><span data-stu-id="337e2-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="337e2-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="337e2-111">Requirements</span></span>  
 <span data-ttu-id="337e2-112">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="337e2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="337e2-113">**ヘッダー:** Corprof.idl、CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="337e2-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="337e2-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="337e2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="337e2-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="337e2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337e2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="337e2-116">See also</span></span>

- [<span data-ttu-id="337e2-117">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="337e2-117">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="337e2-118">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="337e2-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="337e2-119">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="337e2-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="337e2-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="337e2-120">Debugging</span></span>](index.md)
