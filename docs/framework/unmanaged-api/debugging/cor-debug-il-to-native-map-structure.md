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
ms.openlocfilehash: 03ce77dd7407db8289abfefba13d71a9af053e10
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142052"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="d1730-102">COR_DEBUG_IL_TO_NATIVE_MAP 構造体</span><span class="sxs-lookup"><span data-stu-id="d1730-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="d1730-103">Microsoft intermediate language (MSIL) コードをネイティブ コードにマップするために使用するオフセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1730-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1730-104">構文</span><span class="sxs-lookup"><span data-stu-id="d1730-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="d1730-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d1730-105">Members</span></span>  
  
|<span data-ttu-id="d1730-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d1730-106">Member</span></span>|<span data-ttu-id="d1730-107">説明</span><span class="sxs-lookup"><span data-stu-id="d1730-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="d1730-108">MSIL コードのオフセット。</span><span class="sxs-lookup"><span data-stu-id="d1730-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="d1730-109">ネイティブ コードの開始のオフセット。</span><span class="sxs-lookup"><span data-stu-id="d1730-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="d1730-110">ネイティブ コードの最後のオフセット。</span><span class="sxs-lookup"><span data-stu-id="d1730-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d1730-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d1730-111">Requirements</span></span>  
 <span data-ttu-id="d1730-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1730-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1730-113">**ヘッダー:** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="d1730-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="d1730-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1730-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d1730-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d1730-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d1730-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1730-116">See also</span></span>

- [<span data-ttu-id="d1730-117">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="d1730-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="d1730-118">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="d1730-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="d1730-119">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="d1730-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="d1730-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="d1730-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
