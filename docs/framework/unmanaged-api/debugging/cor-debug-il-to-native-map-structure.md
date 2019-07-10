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
ms.openlocfilehash: 238e59978bd084379fe6c0576107d674812bce8d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740786"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="1dfb8-102">COR_DEBUG_IL_TO_NATIVE_MAP 構造体</span><span class="sxs-lookup"><span data-stu-id="1dfb8-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="1dfb8-103">Microsoft intermediate language (MSIL) コードをネイティブ コードにマップするために使用するオフセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1dfb8-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dfb8-104">構文</span><span class="sxs-lookup"><span data-stu-id="1dfb8-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="1dfb8-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="1dfb8-105">Members</span></span>  
  
|<span data-ttu-id="1dfb8-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="1dfb8-106">Member</span></span>|<span data-ttu-id="1dfb8-107">説明</span><span class="sxs-lookup"><span data-stu-id="1dfb8-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="1dfb8-108">MSIL コードのオフセット。</span><span class="sxs-lookup"><span data-stu-id="1dfb8-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="1dfb8-109">ネイティブ コードの開始のオフセット。</span><span class="sxs-lookup"><span data-stu-id="1dfb8-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="1dfb8-110">ネイティブ コードの最後のオフセット。</span><span class="sxs-lookup"><span data-stu-id="1dfb8-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1dfb8-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="1dfb8-111">Requirements</span></span>  
 <span data-ttu-id="1dfb8-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dfb8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dfb8-113">**ヘッダー:** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="1dfb8-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="1dfb8-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1dfb8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1dfb8-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dfb8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dfb8-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dfb8-116">See also</span></span>

- [<span data-ttu-id="1dfb8-117">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="1dfb8-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="1dfb8-118">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="1dfb8-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="1dfb8-119">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="1dfb8-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="1dfb8-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="1dfb8-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
